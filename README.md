# Awesome Millennium Problems of Robotics

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0--1.0-blue.svg)](LICENSE)
[![Contributions welcome](https://img.shields.io/badge/Contributions-welcome-brightgreen.svg)](CONTRIBUTING.md)

> A curated map of the open problems that stand between today's robots and dependable, adaptable physical intelligence.

What would it take for a robot to move, manipulate, collaborate, and keep learning in the real world—with the reliability needed for everyday use?

The initial list brings together **ten research categories, twenty candidate problem statements, and a curated reading list**. “Millennium problems” is an organizing idea: the categories and problem statements are community proposals, open to revision as the field advances. They emphasize physical interaction, learning, and deployment.

**Start here:** browse the [categories](#categories), explore the [candidate problems](PROBLEMS.md), or use the [evaluation protocol](EVALUATION.md) to make a proposed challenge measurable. Contributions that sharpen a question or document a limitation are as valuable as new papers.

**Help shape the research agenda:** submit a pull request to **add a new category** or **propose a specific challenge within any category**. New categories should include at least one concrete challenge and relevant sources. Follow the [step-by-step PR instructions](CONTRIBUTING.md#how-to-submit-a-pull-request) and copy the [challenge template](CONTRIBUTING.md#challenge-template). The category list is open to expansion.

## Contents

- [Categories](#categories)
- [Locomanipulation and whole-body coordination](#locomanipulation-and-whole-body-coordination)
- [Dexterous, contact-rich manipulation with hands](#dexterous-contact-rich-manipulation-with-hands)
- [Force and tactile sensing for perception, learning, and control](#force-and-tactile-sensing-for-perception-learning-and-control)
- [Human–robot interaction and collaboration](#humanrobot-interaction-and-collaboration)
- [Evaluation protocols that measure generalization and reliability](#evaluation-protocols-that-measure-generalization-and-reliability)
- [Safe, sample-efficient RL in the real world](#safe-sample-efficient-rl-in-the-real-world)
- [Long-horizon planning and memory](#long-horizon-planning-and-memory)
- [Lifelong learning and adaptation after deployment](#lifelong-learning-and-adaptation-after-deployment)
- [Failure detection, recovery, and knowing when to ask for help](#failure-detection-recovery-and-knowing-when-to-ask-for-help)
- [Co-design of robot hardware and learning algorithms](#co-design-of-robot-hardware-and-learning-algorithms)
- [Background and perspectives](#background-and-perspectives)
- [Contributing](#contributing)

## Categories

Categories organize related work. **Individual problems are specific research questions**, with assumptions and proposed validation protocols in [PROBLEMS.md](PROBLEMS.md). Their identifiers remain stable when wording changes.

| ID | Category | Candidate problems |
| --- | --- | --- |
| C01 | Locomanipulation and whole-body coordination | [P01: Coordinated contact transitions](PROBLEMS.md#p01-coordinated-contact-transitions); [P02: Whole-body transfer across embodiments](PROBLEMS.md#p02-whole-body-transfer-across-embodiments) |
| C02 | Dexterous, contact-rich manipulation with hands | [P03: Dexterity on unfamiliar objects](PROBLEMS.md#p03-dexterity-on-unfamiliar-objects); [P04: Bimanual manipulation of deformable objects](PROBLEMS.md#p04-bimanual-manipulation-of-deformable-objects) |
| C03 | Force and tactile sensing for perception, learning, and control | [P05: Transferable touch representations](PROBLEMS.md#p05-transferable-touch-representations); [P06: Contact inference under occlusion](PROBLEMS.md#p06-contact-inference-under-occlusion) |
| C04 | Human–robot interaction and collaboration | [P07: Collaboration under changing human intent](PROBLEMS.md#p07-collaboration-under-changing-human-intent); [P08: Learning individual preferences through interaction](PROBLEMS.md#p08-learning-individual-preferences-through-interaction) |
| C05 | Evaluation protocols that measure generalization and reliability | [P09: Measuring generalization without leakage](PROBLEMS.md#p09-measuring-generalization-without-leakage); [P10: Predicting deployment reliability](PROBLEMS.md#p10-predicting-deployment-reliability) |
| C06 | Safe, sample-efficient RL in the real world | [P11: Learning within a physical risk budget](PROBLEMS.md#p11-learning-within-a-physical-risk-budget); [P12: Learning without engineered resets](PROBLEMS.md#p12-learning-without-engineered-resets) |
| C07 | Long-horizon planning and memory | [P13: Grounded planning with delayed consequences](PROBLEMS.md#p13-grounded-planning-with-delayed-consequences); [P14: Persistent memory in changing environments](PROBLEMS.md#p14-persistent-memory-in-changing-environments) |
| C08 | Lifelong learning and adaptation after deployment | [P15: Skill accumulation without catastrophic forgetting](PROBLEMS.md#p15-skill-accumulation-without-catastrophic-forgetting); [P16: Adaptation to wear and changing dynamics](PROBLEMS.md#p16-adaptation-to-wear-and-changing-dynamics) |
| C09 | Failure detection, recovery, and knowing when to ask for help | [P17: Detecting unfamiliar failures in time](PROBLEMS.md#p17-detecting-unfamiliar-failures-in-time); [P18: Choosing recovery or human assistance](PROBLEMS.md#p18-choosing-recovery-or-human-assistance) |
| C10 | Co-design of robot hardware and learning algorithms | [P19: Designing bodies for learnable behavior](PROBLEMS.md#p19-designing-bodies-for-learnable-behavior); [P20: Choosing sensing and actuation under a budget](PROBLEMS.md#p20-choosing-sensing-and-actuation-under-a-budget) |

## Reading list

Entries link to original papers or author-maintained project pages. **Method**, **Benchmark**, **Dataset**, **Hardware**, and **Survey** describe the resource's role; a simulation benchmark or perception dataset supplies partial evidence for a broader deployment problem. Inclusion identifies a useful starting point, rather than a claim that a problem is solved. Recent preprints are marked explicitly.

### Locomanipulation and whole-body coordination

Coordinating locomotion, balance, reaching, and contact across the robot's body.

- [Mobile ALOHA](https://mobile-aloha.github.io/) — **Method / Hardware.** Whole-body teleoperation and imitation learning for bimanual mobile manipulation.
- [HoMeR](https://homer-manip.github.io/) — **Method.** Hybrid imitation learning coupled to whole-body control for mobile manipulation in homes.
- [HumanoidBench](https://humanoid-bench.github.io/) — **Benchmark.** Simulated whole-body locomotion and manipulation tasks with high-dimensional humanoid control.

Candidate problems: [P01](PROBLEMS.md#p01-coordinated-contact-transitions), [P02](PROBLEMS.md#p02-whole-body-transfer-across-embodiments).

### Dexterous, contact-rich manipulation with hands

Regrasping, tool use, insertion, and coordinated manipulation with multi-fingered hands.

- [Learning Dexterous In-Hand Manipulation](https://arxiv.org/abs/1808.00177) — **Method.** A foundational demonstration of simulated RL transferring to real-hand object reorientation.
- [DexGraspNet](https://pku-epic.github.io/DexGraspNet/) — **Dataset.** Large-scale simulated dexterous grasps; a reference for grasp synthesis, distinct from dynamic manipulation evaluation.
- [AnyRotate](https://maxyang27896.github.io/anyrotate/) — **Method.** In-hand rotation across gravity directions using dense tactile sensing and sim-to-real transfer.

Candidate problems: [P03](PROBLEMS.md#p03-dexterity-on-unfamiliar-objects), [P04](PROBLEMS.md#p04-bimanual-manipulation-of-deformable-objects).

### Force and tactile sensing for perception, learning, and control

Using touch and force to estimate hidden contact state and regulate interaction.

- [DIGIT](https://arxiv.org/abs/2005.14679) — **Hardware.** Compact, low-cost, high-resolution vision-based tactile sensing for manipulation.
- [TACTO](https://arxiv.org/abs/2012.08456) — **Tool.** Simulation of high-resolution vision-based tactile sensors.
- [Sparsh and TacBench](https://sparsh-ssl.github.io/) — **Method / Benchmark.** Self-supervised tactile representations and evaluation across touch-centric tasks and sensors.
- [FARM: Force-Aware Robotic Manipulation](https://tactile-farm.github.io/) — **Method.** Tactile demonstrations and policies that predict pose, gripper width, and grip force.

Candidate problems: [P05](PROBLEMS.md#p05-transferable-touch-representations), [P06](PROBLEMS.md#p06-contact-inference-under-occlusion).

### Human–robot interaction and collaboration

Coordinating shared goals while preserving human agency, comfort, and the ability to intervene.

- [Shared Autonomy via Deep Reinforcement Learning](https://arxiv.org/abs/1802.01744) — **Method.** Combines user input and learned assistance without direct access to the user's goal.
- [HARMONIC](https://journals.sagepub.com/doi/10.1177/02783649211050677) — **Dataset.** Multimodal assistive human–robot collaboration data for studying shared autonomy.
- [Human-Robot Gym](https://arxiv.org/abs/2310.06208) — **Benchmark.** Simulated collaboration tasks with a safety shield; guarantees depend on the modeled assumptions.
- [HRIBench](https://arxiv.org/abs/2607.13056) — **Benchmark / 2026 preprint.** Interaction-centered evaluation of intent, coordination, responsiveness, and protocol adherence.

Candidate problems: [P07](PROBLEMS.md#p07-collaboration-under-changing-human-intent), [P08](PROBLEMS.md#p08-learning-individual-preferences-through-interaction).

### Evaluation protocols that measure generalization and reliability

Distinguishing transfer to new situations from performance within a familiar evaluation setup.

- [DROID](https://droid-dataset.github.io/) — **Dataset.** Robot demonstrations collected across varied real-world scenes; useful for studying scene diversity and transfer.
- [Open X-Embodiment](https://robotics-transformer-x.github.io/) — **Dataset / Method.** Standardized data and policies across multiple robot embodiments.
- [SIMPLER](https://simpler-env.github.io/) — **Benchmark.** Paired simulation and real-world evaluation for studying how well simulated results reflect physical policies.
- [RoboCasa / RoboCasa365](https://robocasa.ai/) — **Benchmark / Dataset.** Diverse simulated household tasks, including composite tasks and a 2026 expansion supporting systematic generalist-policy evaluation.
- [BEHAVIOR / OmniGibson](https://behavior.stanford.edu/) — **Benchmark / Tool.** Everyday activity evaluation with richer object states and household interactions.

Candidate problems: [P09](PROBLEMS.md#p09-measuring-generalization-without-leakage), [P10](PROBLEMS.md#p10-predicting-deployment-reliability). See [EVALUATION.md](EVALUATION.md) for a reporting protocol.

### Safe, sample-efficient RL in the real world

Learning useful behavior with limited robot time, human supervision, and physical risk.

- [SERL](https://serl-robot.github.io/) — **Method / Tool.** A software suite for sample-efficient real-world robotic RL, including controllers and reward specification.
- [HIL-SERL](https://hil-serl.github.io/) — **Method.** Human interventions and demonstrations support precise manipulation learned with online RL.
- [safe-control-gym](https://arxiv.org/abs/2109.06325) — **Benchmark / Tool.** Compares control, data efficiency, and constraint satisfaction in simulated dynamical systems.
- [Safe Learning in Robotics: From Learning-Based Control to Safe Reinforcement Learning](https://arxiv.org/abs/2108.06266) — **Survey.** Connects learning-based control, safe RL, uncertainty, and policy certification.

Candidate problems: [P11](PROBLEMS.md#p11-learning-within-a-physical-risk-budget), [P12](PROBLEMS.md#p12-learning-without-engineered-resets).

### Long-horizon planning and memory

Linking high-level plans to executable skills while maintaining an accurate account of past actions and changing world state.

- [SayCan](https://arxiv.org/abs/2204.01691) — **Method.** Grounds language-generated plans in the affordances of available robot skills.
- [Inner Monologue](https://arxiv.org/abs/2207.05608) — **Method.** Incorporates environmental feedback into language-based embodied planning.
- [SayPlan](https://arxiv.org/abs/2307.06135) — **Method.** Uses hierarchical 3D scene graphs to ground scalable task planning.
- [CALVIN](https://arxiv.org/abs/2112.03227) — **Benchmark.** Language-conditioned skill sequences and transfer to new simulated environments.
- [OpenEQA](https://open-eqa.github.io/) — **Benchmark.** Episodic memory and active exploration for embodied question answering; a diagnostic for environment understanding, rather than action execution.

Candidate problems: [P13](PROBLEMS.md#p13-grounded-planning-with-delayed-consequences), [P14](PROBLEMS.md#p14-persistent-memory-in-changing-environments).

### Lifelong learning and adaptation after deployment

Acquiring new skills and adapting to changing conditions while retaining useful prior behavior.

- [LIBERO](https://arxiv.org/abs/2306.03310) — **Benchmark.** Lifelong manipulation learning with spatial, object, goal, and long-horizon task suites.
- [Continual World](https://arxiv.org/abs/2105.10919) — **Benchmark.** Continual robotic RL tasks that probe retention and forward transfer.
- [RMA: Rapid Motor Adaptation for Legged Robots](https://arxiv.org/abs/2107.04034) — **Method.** Online adaptation to terrain and dynamics changes; useful for separating state adaptation from accumulating new skills.
- [Octo](https://octo-models.github.io/) — **Method.** An open generalist policy designed for adaptation to new observation and action spaces; a transfer baseline, not evidence of lifelong retention by itself.

Candidate problems: [P15](PROBLEMS.md#p15-skill-accumulation-without-catastrophic-forgetting), [P16](PROBLEMS.md#p16-adaptation-to-wear-and-changing-dynamics).

### Failure detection, recovery, and knowing when to ask for help

Recognizing when execution diverges from intent, diagnosing the cause, and choosing an appropriate next action.

- [KnowNo: Robots That Ask For Help](https://arxiv.org/abs/2307.01928) — **Method.** Calibrates uncertainty in language-based planning to decide when human help is needed, under stated statistical assumptions.
- [REFLECT](https://arxiv.org/abs/2306.15724) — **Method / Dataset.** Summarizes robot experiences for failure explanation and correction; introduces RoboFail.
- [AHA](https://aha-vlm.github.io/) — **Method / Dataset.** A vision-language model for detecting and reasoning about manipulation failures, trained with procedurally generated failure data.
- [LIBERO-RECOVER](https://arxiv.org/abs/2609.05178) — **Benchmark / 2026 preprint.** Proposes recovery evaluation from perturbed and failed manipulation states; consult the paper for release status.

Candidate problems: [P17](PROBLEMS.md#p17-detecting-unfamiliar-failures-in-time), [P18](PROBLEMS.md#p18-choosing-recovery-or-human-assistance).

### Co-design of robot hardware and learning algorithms

Jointly choosing morphology, sensing, actuation, and learning systems for useful physical capability.

- [RoboGrammar](https://people.csail.mit.edu/jiex/papers/robogrammar/index.html) — **Method.** Searches robot structures and corresponding controllers for terrain traversal.
- [An End-to-End Differentiable Framework for Contact-Aware Robot Design](https://diffhand.csail.mit.edu/) — **Method.** Joint optimization of articulated robot geometry and control using differentiable contact simulation.
- [Evolution Gym](https://evolutiongym.github.io/) — **Benchmark.** Simulated soft-robot morphology and control co-optimization.
- [Universal Manipulation Interface](https://umi-gripper.github.io/) — **Hardware / Method.** A portable demonstration interface and policy-learning system; a practical reference for designing hardware and learning pipelines together.

Candidate problems: [P19](PROBLEMS.md#p19-designing-bodies-for-learnable-behavior), [P20](PROBLEMS.md#p20-choosing-sensing-and-actuation-under-a-budget).

## Background and perspectives

- [The grand challenges of Science Robotics](https://is.mpg.de/publications/2018fischer) — A broad perspective on robotics research challenges, including materials, power, autonomy, interaction, and responsible innovation.
- [What Is Robotics? Why Do We Need It and How Can We Get It?](https://doi.org/10.1146/annurev-control-080320-011601) — A perspective on the relationship between bodies, control, tasks, environments, and the discipline's open questions.

## Contributing

**Pull requests are welcome for new categories, new challenges in existing categories, and refinements to existing challenges.** Fork this repository, edit the relevant files, and open a PR targeting `jiafei1224/awesome-robotics-millennium-problems:main`. See [CONTRIBUTING.md](CONTRIBUTING.md) for the workflow, file checklist, and copyable templates.

For each challenge, explain the research question, why it is hard, what convincing progress would look like, and which primary sources support it. For a new category, explain its scope and how it relates to existing categories, and include at least one challenge. You can submit a PR directly; an [issue](https://github.com/jiafei1224/awesome-robotics-millennium-problems/issues/new/choose) is also useful for discussing an early idea.

The initial problem statements are **draft proposals**. The [problem catalog](PROBLEMS.md) explains how to refine, split, or retire them as evidence improves. Evaluation criteria in this repository are proposed protocols, not results reported by the linked authors.

Maintained by [Jiafei1224](https://github.com/jiafei1224) and contributors. Initial curation: **13 October 2026**.

## License

The original curation and problem statements are released under [CC0 1.0 Universal](LICENSE). Linked papers, code, datasets, and media retain their own licenses.
