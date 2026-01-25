# takara-devkit

## Repo Structure

This repo is for the Latch Agent to work specifically with the Takara Seeker platform.

Each Devkit has the following components:
- `main.md`
- `steps/`
- `lib/`
- `wf/`
- `requirements.txt`

## `main.md`

The agent reads from the following fields in `main.md`:

- `<pre_analysis_questions>` any questions to ask *before* analysis if they are not obvious from context
- `<pre_analysis_step>` step to run before starting the plan to set up the environment
- `<plan>` the names of the steps and where to find step docs
- `<data_structure>` the organization of data in the customer's workspace
- `<self_eval_criteria>` specific, often numerical, pass/fail sanity checks after the agent has completed the entire plan


## `steps/`

Each step in the `<plan>` has its own document that is loaded before executing the step.

- `<goal>` describes the scientific goal of the step
- `<method>` contains a description of the procedure to accomplish the goal
- `<workflows>` contains the names of any Latch workflows the agent should invoke
- `<library>` contains the names of any technology-specific library the agent should use
- `<self_eval_criteria>` contains specific, often numerical, sanity checks to run through before determining the step is complete

## `lib/`

Contains Python library code with technology-specific helper functions the agent can import and use.

## `wf/`

Contains documentation for Latch workflows the agent can invoke. Each workflow document includes:

- `<goal>` describes what the workflow accomplishes
- `<parameters>` describes the workflow parameters and their expected values
- `<outputs>` describes what the workflow returns
- `<example>` provides example code for invoking the workflow

## `requirements.txt`

Optional file listing additional pip packages to install at pod startup. New packages can be added, but versions of packages already in the base image cannot be changed due to version constraints.