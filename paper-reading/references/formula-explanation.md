# Formula Explanation

Use this guide when the user asks how a paper formula works, why it is designed that way, or what its output means inside the model. Teach the mechanism rather than paraphrasing the paper.

## Explanation sequence

Use only as much of this sequence as the current question needs:

1. **Purpose:** State in one plain sentence what problem the formula or module solves.
2. **Inputs:** Name each relevant symbol, its model meaning, and its shape when the shape helps explain the operation.
3. **Operation:** Rewrite the formula as a short data-flow sequence and unpack each mathematical operation.
4. **Example:** Substitute small, explicitly invented values and calculate the important intermediate results.
5. **Output:** State the output shape, what each part contains, and what the output represents at this point in the model.
6. **Design reason:** Explain why this operation is useful here and what information it adds, removes, compares, or normalizes.

Do not mechanically include all six parts in a small follow-up. The answer is complete when the user can identify the input, see what changed mathematically, and understand the output's model-level meaning.

## Symbols and shapes

- Define a symbol at first use: for example, `h_i` is the representation of entity `i`, not merely “a vector.”
- Give dimensions in a readable form such as `h_i ∈ R^d`, followed by what `d` counts.
- For matrix operations, show the dimensions that make the multiplication valid. Example: `(1 × d)(d × r) → (1 × r)`.
- State the axis of normalization or aggregation when it matters. “Apply Softmax” is incomplete if the user cannot tell which values compete.
- After a long gap, briefly remind the user of a symbol instead of repeating its full definition.
- Separate notation used by the paper from temporary notation introduced for teaching.

## Track both shape and meaning

At every important transformation, track two parallel changes:

```text
mathematical track: shape and numerical operation
semantic track: what the values are trained or constructed to represent
```

A change in shape does not by itself explain a change in meaning. When a representation becomes prediction scores, make the mechanism explicit:

1. The input is still a numerical vector representing an entity, pair, token, or hidden state.
2. The final projection produces one coordinate per target class or relation.
3. During training, the loss compares those coordinates with labeled targets.
4. Gradients adjust the projection and earlier layers so the coordinate for relation `r` becomes useful as the score for relation `r`.
5. Softmax or Sigmoid may then convert logits into normalized or independent probabilities, depending on the task.

Use the precise stage name:

```text
representation → hidden representation → logits → probabilities → predicted labels
```

Do not call a hidden vector a probability, or a logit a prediction, unless the paper explicitly defines that usage.

## Numerical examples

- Prefer two-dimensional vectors, small integer matrices, two attention items, or two to three classes.
- Mark all invented values as **example values**, not values reported by the paper.
- Perform the arithmetic instead of stopping at a symbolic substitution.
- Preserve one example state across consecutive modules: the same document, entities, entity pair, vector dimensions, and previously computed outputs.
- Extend the existing example only when a new module requires another value. Avoid silently replacing earlier values.
- Keep the example faithful to the real operation. A simpler example may reduce dimensions, but it must not change matrix multiplication into element-wise multiplication or replace learned attention with an unrelated average.

For a long derivation, keep a compact state record such as:

```text
Example state
Document: Alice works at Acme.
Head entity: Alice
Tail entity: Acme
h_Alice = [1, 2]
h_Acme = [2, 1]
```

Reuse this record rather than reintroducing a new story at every layer.

## Operation-specific lenses

Explain the relevant mathematical idea only to the depth needed for the current formula.

- **Vector:** Identify what each dimension is allowed to encode and whether the dimensions have individually assigned meanings or only a distributed learned meaning.
- **Matrix multiplication / linear layer:** Show that each output coordinate is a learned weighted sum of the inputs. Explain bias separately when present.
- **Dot product:** Calculate the multiply-and-sum operation, then explain whether the result is used as similarity, compatibility, or a raw score. A dot product is not automatically cosine similarity.
- **Bilinear layer:** For an expression such as `h_s^T W h_o`, show how `W` learns interactions between dimensions of the two inputs, rather than treating it as an unexplained scoring function.
- **Activation function:** Show the element-wise transformation, its output range when relevant, and why nonlinearity is needed between learned linear transformations.
- **Softmax:** Show exponentiation and division by the sum over the stated axis. Explain that outputs compete and sum to one.
- **Sigmoid:** Show that each logit is converted independently to a value between zero and one. Connect this independence to multi-label prediction when applicable.
- **Attention:** Identify queries, keys, and values only if the formula actually uses them. Trace score computation, scaling if present, normalization, and the weighted sum. State what is being attended over.
- **GCN or graph message passing:** Identify nodes, neighbors, messages, aggregation, learned transformation, and activation. Explain what information becomes available after one layer and how additional layers expand the receptive field.
- **Loss:** Identify the target, the predicted quantity, the per-example penalty, and what minimizing it encourages. Distinguish multi-class cross-entropy from independent binary cross-entropy when the distinction affects the paper.

## Diagrams

Use a compact local diagram when several transformations are involved:

```text
entity representations
        ↓ pair construction
entity-pair representation
        ↓ graph reasoning
reasoned pair representation
        ↓ classifier
relation logits
        ↓ Sigmoid
relation probabilities
        ↓ threshold
predicted relations
```

Label arrows with the operation. Label nodes with both the object and, when useful, its shape. A diagram supports the formal explanation; it does not replace the formula or arithmetic.

## Ambiguity and evidence

- If the equation, surrounding definitions, or tensor shapes are missing and different interpretations would change the answer, ask for the relevant equation or context.
- When a reasonable assumption is enough to continue, state it briefly and proceed.
- Distinguish what the paper states from a teaching interpretation or implementation inference.
- Point out notation collisions, omitted axes, or dimension inconsistencies instead of silently repairing them.
- When the paper uses an operation differently from its common convention, follow the paper and make the difference explicit.
