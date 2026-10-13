# Evaluating Progress on Robotics' Millennium Problems

A useful problem statement specifies the task distribution, the robot's information and resources, and the evidence required to assess progress. This is a **proposed reporting protocol** for this repository, not an established standard or a result from the linked papers.

## 1. Define the claim before running the experiment

- Name the problem identifier and the particular capability being evaluated.
- Define tasks, operating conditions, time horizon, prohibited outcomes, and success criteria.
- Specify what is held out: object instances or families, materials, scenes, task compositions, people, dynamics, or entire robot platforms.
- Declare acceptance thresholds and evaluation budgets in advance. Explain their relevance to the intended use.
- State what would falsify the claim and what remains outside its scope.

## 2. Record exposure and resources

Publish a training-exposure ledger: demonstrations, RL interactions, simulation assets, pretrained models, known overlapping datasets, validation tasks, and model-selection runs. Mark unknown pretraining exposure as unknown.

Count all resources that contribute to the result: robot hours, demonstrations, resets, reward labeling, interventions, calibration, compute, memory, model size, hardware cost, and maintenance. Separate zero-shot results from adaptation results, and report the adaptation budget.

## 3. Test several kinds of generalization

| Shift | Example | Essential distinction |
| --- | --- | --- |
| Object | New geometry, material, or mass distribution | New instances versus new families and physical properties |
| Environment | New home, clutter, lighting, or terrain | Appearance shifts versus changed geometry and dynamics |
| Task | New skill composition or causal dependency | New wording versus genuinely new required behavior |
| Embodiment | New hand, base, kinematics, or sensor layout | Target robot seen in training versus a fully held-out platform |
| Human | New participant, goal, timing, or preference | Repeated users versus unseen users and interaction patterns |
| Time | Wear, drift, recurring tasks, or long operation | Independent short episodes versus continuing deployment |

Test shifts individually and in combination. Keep test data separate from tuning and design decisions. Prospective evaluation after model freeze and independent-site evaluation are especially useful when training exposure is uncertain.

## 4. Measure completion and reliability separately

Report attempted episodes, successful completions, partial outcomes, failure mechanisms, and confidence intervals. Preserve exclusions, aborted runs, timeouts, and censoring reasons. When trials share tasks, sites, or participants, account for that dependence instead of treating every trial as an independent sample.

For deployment-oriented claims, also report:

- Human interventions and assistance minutes per operating hour or completed task.
- Failure rate by severity, including damage and constraint violations.
- Time to failure, recovery success, repeated failures, downtime, and maintenance.
- Performance across sites, task families, participants, and environmental conditions.
- Uncertainty calibration, false alarms, and missed failures when the system makes confidence-based decisions.

Report both aggregate and disaggregated results. A high mean success rate can coexist with poor performance on a task family or rare but serious failures. Zero observed failures in a finite test is an observation with uncertainty, not proof of zero risk.

## 5. Compare systems under matched budgets

Use baselines with comparable data, sensors, compute, and human assistance. Include an ablation that tests the proposed mechanism. Record how much tuning each system received.

For safety claims, list the assumptions behind certificates or shields and whether they hold on the tested hardware. For lifelong learning, measure retention and forward transfer throughout the stream. For memory, measure the effect on action outcomes as well as retrieval or question answering. For hardware co-design, include search, fabrication, calibration, and failed-prototype costs.

## 6. Connect simulation to the physical claim

State whether the evidence comes from simulation, recorded data, physical robots, or a mixture. Describe privileged observations and simulator-specific shortcuts.

When claiming physical performance from simulation, use paired real-world checks across representative conditions and report disagreements. Contact, sensor wear, actuator saturation, and deformable materials need particular attention. Label a simulation-only result according to its evaluated scope.

## 7. Make the result reproducible

Release the protocol, splits, evaluation code, task definitions, hardware configuration, seeds, aggregate results, and failure logs when possible. Identify unavailable artifacts explicitly. Include unselected trials or full evaluation recordings where practical.

A proposed resolution should show that the capability survives independent reproduction and the held-out conditions named in the original problem. If the evidence answers a narrower question, record that narrower result as progress and revise the remaining question accordingly.

## Copyable claim record

```text
Problem ID and version:
Capability claimed:
Task distribution and operating conditions:
Information available to the robot:
Held-out dimensions and exposure ledger:
Training, adaptation, compute, and human-labor budgets:
Predeclared success criteria and prohibited outcomes:
Baselines and model-selection procedure:
Number of trials / operating hours / sites / participants:
Completion, reliability, recovery, and uncertainty results:
Simulation-to-real evidence:
Failure cases and limits of the claim:
Released artifacts and independent reproduction:
```
