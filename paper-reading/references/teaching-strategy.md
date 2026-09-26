# Teaching Strategy

Use this guide when a paper-reading question is ambiguous, the user needs a change in explanation style, or the conversation spans several connected concepts or model modules. Help the user locate and cross the current understanding barrier instead of delivering a generic lecture.

## Decide whether to answer or clarify

Answer immediately when the likely interpretation is clear enough that a minor assumption will not change the substance. State the assumption briefly when it matters.

Ask one to three targeted questions before a long explanation when different interpretations would require meaningfully different answers. Make each question distinguish concrete alternatives, for example:

- “Are you unsure how this matrix multiplication is calculated, or why the model uses it here?”
- “Do you want the mathematical role of this layer, or its role in the full model?”
- “Are `f_so` and the relation logits being confused, or is the transition between them unclear?”

When several concepts are mixed together, separate them first, name the relationship between them, and then address the part blocking the user. Avoid the vague question “What exactly do you want to know?” when more diagnostic alternatives are available.

## Match scope and depth

Use the shortest answer that resolves the current barrier:

- **Small follow-up:** Answer in a few sentences and reuse established context.
- **Single formula or module:** Explain the necessary inputs, operation, example, and model meaning.
- **Section overview:** Give a compact flow, then expand only the transitions central to the section.
- **Full derivation:** Establish a stable example and trace it through every requested stage.

Keep a local question local. Reconstruct the full paper or earlier explanation only when the user asks for a review, or when the missing global connection is itself the source of confusion.

## Teach a beginner researcher

Assume the user can work with real papers, code, and experiments but may have uneven foundations. Preserve professional terminology and mathematical accuracy while supplying the missing prerequisite at the point where it becomes necessary.

Use this default teaching order when a full explanation is helpful:

1. Give the core idea in one plain sentence.
2. Present the formal definition, formula, or mechanism.
3. Show a small example or a local structure diagram.
4. Return to the paper and explain what the result means there.

Skip steps already understood. Introduce linear algebra, probability, calculus, or machine-learning background only far enough to unlock the current paper formula. Mark analogies as intuition, then reconnect them to the formal mechanism so the analogy never substitutes for the definition.

## Diagnose the understanding barrier

Infer the likely barrier from the user's wording and recent questions. Common barriers include:

- the symbols are not grounded in model objects;
- the arithmetic operation is unclear;
- the operation is understood but its design purpose is not;
- the local formula is clear but its position in the model is not;
- the vector's mathematical form is clear but its learned semantic meaning is not;
- two neighboring stages, such as logits and probabilities, have been merged conceptually;
- a prerequisite concept is missing.

When the barrier remains uncertain, ask about the exact transition rather than the entire topic. A useful prompt is: “Which arrow is unclear: input to operation, operation to output, or output to its meaning in the model?”

## Change method after repeated confusion

Treat “I still don't understand” or repeated versions of the same question as evidence that the current explanation method did not expose the barrier. Acknowledge the specific gap and change representation.

Possible shifts include:

```text
formal definition
      ↓
worked numerical example
      ↓
input-operation-output diagram
      ↓
plain step-by-step explanation
      ↓
comparison with a nearby concept
```

Choose the shift that addresses the likely barrier rather than following this list mechanically. Preserve the same symbols and example when possible so the user spends attention on the new explanation, not on learning new names.

If another explanation still fails, narrow the discussion to one operation or one arrow and ask the user to identify the first step that stops making sense. Do not add more terminology until that step is resolved.

## Use diagrams as reasoning aids

Prefer a compact diagram when the user needs to understand sequence, hierarchy, or information flow. Every diagram should make three things visible:

```text
where information comes from
↓ what operation happens
what it becomes
```

Use a local diagram for a local barrier and an end-to-end diagram for a requested overview. Label the arrows with operations and distinguish training-only steps from inference steps when relevant. Follow the diagram with the minimum prose needed to interpret it.

## Maintain conversational continuity

Track the active context across turns:

- paper and section;
- current question or understanding barrier;
- symbols already defined;
- the stable example and its established values;
- outputs already calculated;
- the current location in the model pipeline.

Reuse this context in follow-ups instead of restarting the explanation. If the user changes papers, formulas, or notation, explicitly reset the affected parts of the context while retaining applicable teaching preferences.

When the available excerpt is insufficient to distinguish the paper's definition from a general convention, request the equation or surrounding paragraph. Label general explanations and implementation inferences so they are not mistaken for claims made by the paper.

## Check completion

Before ending, verify that the response:

- answers the question the user actually asked;
- resolves or isolates the current barrier;
- defines newly necessary symbols or terms;
- preserves the distinction between the mathematical operation and its model meaning;
- avoids unrelated background and unnecessary repetition.

Ask a follow-up question only when the answer depends on it or when identifying the remaining barrier will materially improve the next explanation. A routine “Do you understand?” is less useful than a concrete check tied to the disputed step.
