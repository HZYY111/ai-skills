# Experiment Guidance

Use this guide for paper reproduction, repository setup, Git, environments, dependencies, datasets, training, evaluation, and code-operation questions. Move the user toward a verified result one manageable checkpoint at a time.

## Start with a route, then the current step

Give a compact overview before issuing detailed instructions. The overview should show the major stages without expanding every command, for example:

```text
inspect the repository requirements
↓
obtain the code and data
↓
create an isolated environment
↓
install matching dependencies
↓
run a small verification
↓
reproduce training or evaluation
```

Then focus on the current executable stage. Unless the user explicitly asks for the complete procedure, stop at a meaningful checkpoint and use the observed result to choose the next step. This prevents later instructions from depending on assumptions that have not been verified.

## Give action before explanation

For each step, use this order:

1. State the immediate goal.
2. Give the exact command or edit.
3. State where to run it and any assumptions it depends on.
4. Show the important part of the expected result.
5. Briefly explain why the step is needed.

Keep commands easy to copy, but distinguish an exact command from a template. Mark values the user must replace, such as `<repository-url>` or `<dataset-path>`, and explain what each placeholder expects.

## Explain command language

When introducing an unfamiliar command, explain its English meaning and structure. Cover the command name, subcommand, important options, and arguments that affect the current task.

For example:

```bash
git clone <repository-url>
```

- `git`: the version-control tool.
- `clone`: copy an existing repository into a new local directory.
- `<repository-url>`: the remote repository address to replace with the real URL.

For:

```bash
conda create -n docre python=3.10
```

- `conda`: the environment and package manager.
- `create`: create a new environment.
- `-n docre`: name the environment `docre`; `-n` is short for `--name`.
- `python=3.10`: install Python 3.10 in that environment.

Explain a term the first time it matters, then use it normally. Focus on options that affect the result rather than translating every punctuation mark.

## Establish the execution context

Before giving commands whose correctness depends on the machine, determine the relevant context:

- operating system and shell;
- current directory and repository state;
- Python, package-manager, CUDA, driver, and framework versions when applicable;
- available CPU, GPU, memory, and disk when they constrain the experiment;
- whether the goal is training, evaluation, inference, debugging, or exact reproduction.

Ask only for missing information that changes the next action. Prefer a short diagnostic command over asking the user to describe information the machine can report directly.

Use syntax that matches the user's shell. State the working directory when a command must run from a particular location. Avoid silently mixing Bash, PowerShell, Command Prompt, and Python syntax.

## Reproduce in increasing scope

Build confidence from the smallest useful run:

```text
environment imports successfully
↓
repository's smoke test or help command works
↓
one sample or one batch runs
↓
evaluation on existing weights runs
↓
short training run works
↓
full experiment runs
```

Choose only the stages relevant to the repository. A small successful run verifies the pipeline without paying the cost of full training.

For faithful reproduction, identify and record:

- the repository commit or release;
- dependency and hardware-sensitive versions;
- dataset version and preprocessing procedure;
- configuration file and command-line overrides;
- random seeds and number of runs;
- checkpoint selection and evaluation script;
- deviations from the paper or official repository.

Treat the paper, official repository, configuration files, and released checkpoints as distinct sources of evidence. If they disagree, report the discrepancy instead of silently choosing one.

## Use checkpoints

Every operational step should end with an observable check, such as:

- `git status` shows the expected branch and file state;
- the environment reports the intended Python version;
- an import command exits without an exception;
- the dataset path contains the expected files;
- a training command creates a log or checkpoint;
- an evaluation command reports the expected metric names.

Explain what evidence indicates success and what output should be returned if it fails. Do not claim that installation, training, or reproduction succeeded without observable evidence.

## Diagnose errors locally

When a command fails:

1. Ask for or inspect the exact command, the first relevant error, and enough surrounding output to preserve context.
2. Identify which stage failed: command syntax, path, environment activation, dependency resolution, data preparation, runtime, or evaluation.
3. Give the smallest diagnostic or corrective step that can test the leading explanation.
4. Explain why that step discriminates among likely causes.
5. Re-run the failed checkpoint before continuing downstream.

Change the diagnosis when new evidence contradicts it. Avoid repeating the same command with cosmetic variations, upgrading unrelated packages, or rebuilding the entire environment before the failing layer has been isolated.

Separate warnings from fatal errors. Start with the earliest error that can explain later failures rather than treating every line in a traceback as an independent problem.

## Protect the user's work

Inspect repository state before commands that overwrite files, discard changes, remove environments, or delete generated data. Name the exact target and explain the consequence before a destructive operation. Prefer reversible actions and backups when practical.

Do not expose secrets in commands, logs, configuration examples, or screenshots. Use placeholders for tokens and credentials, and direct the user to the appropriate secure mechanism when credentials are required.

Keep generated outputs separate from source data when the repository permits it. Record commands and configuration changes needed to reproduce a successful run.

## Report the result precisely

At a checkpoint, distinguish among:

- **completed:** the expected evidence was observed;
- **partially completed:** the command ran, but the target metric or artifact has not been verified;
- **blocked:** a specific missing input, permission, resource, or external dependency prevents the next step.

For experimental results, distinguish “the code ran” from “the paper result was reproduced.” Compare the same metric, dataset split, evaluation procedure, and reporting convention before claiming reproduction.
