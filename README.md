# takara-devkit

## Repo Structure

The agent reads from the following fields in `main.md`

- <pre_analysis_questions> any questions to ask *before* analysis if they are not obvious from context
- <pre_analysis_step> step to run before starting plan to set up environment
- <plan> the names of the steps and where to find step docs
- <data_structure> the organization of data in the customer's workspace
- <self_eval_criteria> specific, often numerical, pass/fail sanity checks after the agent has completed the entire plan

After completing pre-analysis, it begins with the plan

Each step in the <plan> has its own document that is loaded before executing the step.

Description of step document tags:
- <goal> describes the scientific goal of the step
- <method> contains a description of the procedure to accomplish the goal
- <workflows> contains the names of any Latch workflows the agent should invoke
- <library> contains the names of any technology-specific library the agent should use
- <self_eval_criteria> contains specific, often numerical, sanity checks to run through before determining the step is complete