# Candidate Millennium Problems of Robotics

These are **twenty draft research problems**, organized under the ten [categories](README.md#categories). Each question names a capability, a central obstacle, and an evaluation that could provide evidence of progress. They are proposals for discussion and refinement, rather than claims of consensus or formal prize problems.

All validation ideas below are this repository's proposals. Linked research provides context and starting points; it does not endorse these problem formulations. Use the shared [evaluation protocol](EVALUATION.md) to define task distributions, resource budgets, and acceptance thresholds before an experiment.

## C01 — Locomanipulation and whole-body coordination

### P01: Coordinated contact transitions

**Question.** Can a robot learn a reusable controller that maintains balance and task progress while transitioning among walking, reaching, bracing, carrying, and pushing contacts in unfamiliar environments?

**Why it is hard.** Contact changes couple object motion, base motion, support forces, and visibility. A locally successful manipulation action can make the whole body unstable or leave the next action infeasible.

**Proposed validation.** Hold out combinations of terrain, payload, object geometry, and contact sequence. Test uninterrupted mobile manipulation with disturbances. Report completion, falls, force-limit violations, energy, and human interventions. Compare with separate locomotion and manipulation controllers under the same observation and training budgets.

**Starting points.** [Mobile ALOHA](README.md#locomanipulation-and-whole-body-coordination), HoMeR, HumanoidBench. Physical validation is necessary for balance and contact claims.

### P02: Whole-body transfer across embodiments

**Question.** Can whole-body skills transfer to a previously unseen robot morphology with a bounded amount of calibration, rather than requiring a new task-specific controller for each body?

**Why it is hard.** Reachability, balance, available contacts, actuator limits, and action semantics vary across bodies. Matching end-effector trajectories alone does not ensure feasible behavior.

**Proposed validation.** Hold an entire robot platform out of pretraining and design selection. Declare exactly which kinematic models, calibration data, and adaptation interactions are allowed. Measure adaptation cost, retained capability, and constraint violations across shared tasks; compare against training the target robot from scratch. Separately report transfers between similar and substantially different morphologies.

**Starting points.** [Open X-Embodiment](README.md#evaluation-protocols-that-measure-generalization-and-reliability), HumanoidBench.

## C02 — Dexterous, contact-rich manipulation with hands

### P03: Dexterity on unfamiliar objects

**Question.** Can a multi-fingered hand reorient, regrasp, and use previously unseen objects while inferring their contact-relevant properties online?

**Why it is hard.** Shape, friction, mass distribution, compliance, and grasp stability are partly hidden and change during manipulation. Training on many object meshes can still leave material and contact behavior poorly covered.

**Proposed validation.** Hold out shape families, materials, mass distributions, and required maneuvers. Test combinations of these shifts with visual occlusion and disturbances. Report object drops, damage, precision, completion time, and adaptation interactions. Compare vision-only, touch-only, and fused policies with matched budgets; include tool use beyond object rotation.

**Starting points.** [Learning Dexterous In-Hand Manipulation, DexGraspNet, and AnyRotate](README.md#dexterous-contact-rich-manipulation-with-hands).

### P04: Bimanual manipulation of deformable objects

**Question.** Can two hands learn transferable manipulation strategies for deformable objects whose changing shape, tension, and internal state are only partially observable?

**Why it is hard.** One hand changes the other hand's feasible actions. Cloth, cables, and soft packaging introduce distributed contacts, hysteresis, and task-relevant states that are difficult to represent and simulate.

**Proposed validation.** Specify distinct material families and tasks such as untangling, routing, folding, and opening packaging. Hold out material properties and initial configurations. Report final-state accuracy, excessive tension, damage, unsuccessful retries, and intervention cost. Test whether transfer works across tasks as well as objects. Declare fixtures, pre-positioning, and any privileged state measurements.

**Starting points.** [Mobile ALOHA](README.md#locomanipulation-and-whole-body-coordination), [SERL](README.md#safe-sample-efficient-rl-in-the-real-world). These provide components and related tasks; the full question needs additional hand-based evaluation.

## C03 — Force and tactile sensing for perception, learning, and control

### P05: Transferable touch representations

**Question.** Can a tactile representation transfer across sensor designs, mounting locations, materials, and sensor aging while preserving information needed for closed-loop control?

**Why it is hard.** Appearance-based tactile measurements depend on sensor geometry, illumination, elastomer condition, calibration, and contact history. Good performance on a perception probe does not establish a useful control representation.

**Proposed validation.** Hold out sensor instances and at least one sensor design. Limit calibration labels and interactions. Test force estimation, slip prediction, and physical manipulation before and after wear. Report both estimation errors and downstream task outcomes; ablate adaptation data, latency, and sensor-specific processing.

**Starting points.** [DIGIT, TACTO, and Sparsh/TacBench](README.md#force-and-tactile-sensing-for-perception-learning-and-control).

### P06: Contact inference under occlusion

**Question.** Can a robot infer hidden contact geometry, slip, and interaction forces well enough to control unfamiliar contact-rich tasks when visual feedback is limited?

**Why it is hard.** Different physical states can produce similar local measurements. The robot must sometimes probe actively to disambiguate the state without damaging the object or destabilizing the grasp.

**Proposed validation.** Use insertion, tool engagement, and fragile-object handling with held-out tolerances, friction, and contact surfaces. Vary occlusion and sensing delays. Measure state-estimation calibration, peak forces, damage, task success, and probing cost. Compare passive sensor fusion with active information-seeking strategies using the same sensors and interactions.

**Starting points.** [FARM, Sparsh, and TACTO](README.md#force-and-tactile-sensing-for-perception-learning-and-control), [AnyRotate](README.md#dexterous-contact-rich-manipulation-with-hands).

## C04 — Human–robot interaction and collaboration

### P07: Collaboration under changing human intent

**Question.** Can a robot coordinate a shared physical task with an unfamiliar person whose goals, timing, and preferred division of work change during execution?

**Why it is hard.** Human intent is latent and must be inferred from language, motion, and context. An efficient action may be unwanted, surprising, or incompatible with the person's next move.

**Proposed validation.** Hold out participants and interaction patterns. Introduce goal changes, interruptions, and ambiguous handovers. Measure joint completion, collisions or near misses, coordination delays, clarification requests, and participant-reported control and comfort. Compare autonomy levels and report variability across participants, rather than only an aggregate success rate.

**Starting points.** [Shared Autonomy, HARMONIC, Human-Robot Gym, and HRIBench](README.md#humanrobot-interaction-and-collaboration).

### P08: Learning individual preferences through interaction

**Question.** Can a robot learn a person's task-specific preferences from sparse corrections and transfer them to new situations without overriding explicit instructions?

**Why it is hard.** Corrections can concern goals, style, comfort, accessibility, or a temporary circumstance. Treating each correction as a permanent global rule can cause unwanted behavior later.

**Proposed validation.** Define observable preferences with participants, then evaluate new tasks, contradictory corrections, and preference changes. Track correction burden, preference violations, task utility, and how readily a person can undo an adaptation. Compare persistent personalization, session-only adaptation, and no personalization. Report individual outcomes and accessibility-related differences with an appropriate human-study protocol.

**Starting points.** [HARMONIC and Shared Autonomy](README.md#humanrobot-interaction-and-collaboration), [KnowNo](README.md#failure-detection-recovery-and-knowing-when-to-ask-for-help).

## C05 — Evaluation protocols that measure generalization and reliability

### P09: Measuring generalization without leakage

**Question.** Can an evaluation protocol distinguish transfer to genuinely new tasks, environments, objects, and embodiments from memorization or interpolation within exposed data?

**Why it is hard.** Training datasets overlap, environments share assets, and model pretraining may be only partly documented. A nominally held-out task can still closely resemble training experience.

**Proposed validation.** Publish split construction and a training-exposure ledger. Evaluate independent object, scene, task, and robot shifts, then their combinations. Include prospective tests created after the model is frozen and evaluation at an independent site. Report unknown exposure explicitly. Test whether benchmark rankings remain stable across these splits and under fixed adaptation budgets.

**Starting points.** [DROID, Open X-Embodiment, SIMPLER, RoboCasa, and BEHAVIOR](README.md#evaluation-protocols-that-measure-generalization-and-reliability).

### P10: Predicting deployment reliability

**Question.** Can finite laboratory and simulation evaluations predict intervention rates and serious failures during sustained physical deployment?

**Why it is hard.** Failures are rare, dependent, and sensitive to environmental drift. Short episodes and averages can hide fragile operating conditions and accumulated maintenance costs.

**Proposed validation.** Freeze systems before prospective multi-site deployment. Compare predicted risk with observed failures, interventions, downtime, and maintenance over declared operating hours. Report uncertainty and failures by severity. Measure how prediction changes under distribution shift and extended operation; preserve every attempted episode and its censoring reason.

**Starting points.** [SIMPLER and diverse household benchmarks](README.md#evaluation-protocols-that-measure-generalization-and-reliability). The [evaluation protocol](EVALUATION.md) distinguishes episode success from sustained reliability.

## C06 — Safe, sample-efficient RL in the real world

### P11: Learning within a physical risk budget

**Question.** Can a robot learn a new contact-rich skill with limited real interaction while respecting explicit constraints throughout training, including exploration?

**Why it is hard.** The dynamics and the safe set may be uncertain, particularly during contact. A constraint penalty in the reward need not prevent a damaging exploratory action.

**Proposed validation.** Declare force, speed, workspace, and damage constraints before training, together with the assumptions of any safety mechanism. Compare learning curves at matched robot-time and intervention budgets. Report violations during training and deployment, shielding events, human takeovers, reward-labeling effort, and performance on held-out dynamics. Separate empirical observations from formal guarantees.

**Starting points.** [SERL, HIL-SERL, safe-control-gym, and Safe Learning in Robotics](README.md#safe-sample-efficient-rl-in-the-real-world).

### P12: Learning without engineered resets

**Question.** Can a robot acquire and improve skills in a continuing real-world process without a person restoring a carefully chosen start state after each attempt?

**Why it is hard.** Failures change the environment and can eliminate useful learning opportunities. Resetting an object, cleaning a spill, or restoring a grasp may be harder than the original task.

**Proposed validation.** Define a continuing task distribution and allowed recovery actions. Count all interaction time, autonomous reset attempts, human reset labor, and unrecoverable states. Compare episode-based training and continuing learning at matched total labor and robot-time budgets. Include environment drift and failure states outside successful demonstrations.

**Starting points.** [SERL's reset-free relocation task](https://serl-robot.github.io/), [failure-recovery methods](README.md#failure-detection-recovery-and-knowing-when-to-ask-for-help).

## C07 — Long-horizon planning and memory

### P13: Grounded planning with delayed consequences

**Question.** Can a robot compose unfamiliar skill sequences while reasoning about physical preconditions, resource use, and consequences that become visible much later?

**Why it is hard.** Plausible symbolic plans can contain infeasible actions. Errors in state estimates and skill outcomes accumulate, while choices such as object placement can block later steps.

**Proposed validation.** Hold out task compositions and causal dependencies. Vary sequence length, introduce disturbances, and require replanning after interrupted execution. Measure full-task completion, feasibility errors, dead ends, resource violations, and intervention burden as a function of horizon. Compare open-loop plans, reactive skill chaining, and feedback-grounded planning with the same skill library.

**Starting points.** [SayCan, Inner Monologue, SayPlan, and CALVIN](README.md#long-horizon-planning-and-memory).

### P14: Persistent memory in changing environments

**Question.** Can a robot retain task-relevant memories across days, revise outdated beliefs, and retrieve the right experience without accumulating stale or misleading state?

**Why it is hard.** Objects move, routines change, and observations are incomplete. A memory must distinguish an observation from an assumption and represent when a stored fact is no longer trustworthy.

**Proposed validation.** Repeat visits to changing physical environments with delayed queries and action requests. Limit storage and compute. Measure retrieval accuracy, stale-belief errors, uncertainty calibration, search time, and downstream task completion. Include object relocation, contradictory observations, and removal of remembered information. Compare episodic, semantic, and combined memory with equal budgets.

**Starting points.** [OpenEQA and SayPlan](README.md#long-horizon-planning-and-memory). Question-answering results should be paired with physical action tests.

## C08 — Lifelong learning and adaptation after deployment

### P15: Skill accumulation without catastrophic forgetting

**Question.** Can a deployed robot accumulate useful skills over a nonstationary task stream while retaining earlier skills and improving how quickly it learns new ones?

**Why it is hard.** Updates can improve a recent task while degrading earlier behavior. Replay, model growth, and repeated retraining consume memory, compute, supervision, and downtime.

**Proposed validation.** Use multiple task orders, recurring old tasks, and unannounced domain changes. Fix memory, model capacity, compute, and interaction budgets. Report retention, forward transfer, time to competence, unsafe regressions, and update downtime throughout the stream. Compare sequential fine-tuning, replay, frozen-policy adaptation, and an explicitly budgeted joint-training reference.

**Starting points.** [LIBERO, Continual World, and Octo](README.md#lifelong-learning-and-adaptation-after-deployment), [RoboCasa365](https://robocasa.ai/).

### P16: Adaptation to wear and changing dynamics

**Question.** Can a robot identify and compensate for changes in actuators, sensors, payloads, and contact mechanics while recognizing when compensation is insufficient and maintenance is required?

**Why it is hard.** A performance change may come from the world, the robot, or faulty sensing. Aggressive adaptation can hide degradation until an unsafe failure occurs.

**Proposed validation.** Introduce controlled, gradual and abrupt changes within declared operating limits. Report adaptation delay, task performance, retained safety margins, misdiagnoses, and maintenance decisions. Separate inference-time adaptation from parameter updates and count their costs. Test recovery when conditions return to normal and assess performance on previously learned tasks.

**Starting points.** [RMA](README.md#lifelong-learning-and-adaptation-after-deployment), [tactile representation research](README.md#force-and-tactile-sensing-for-perception-learning-and-control).

## C09 — Failure detection, recovery, and knowing when to ask for help

### P17: Detecting unfamiliar failures in time

**Question.** Can a robot detect and localize previously unseen failures early enough to prevent escalation, using its own observations rather than an external success oracle?

**Why it is hard.** A failed grasp, blocked insertion, wrong object, and sensor fault may look similar. Late detection can turn a recoverable deviation into damage or a dead end.

**Proposed validation.** Hold out failure mechanisms, tasks, and robot setups. Distinguish imminent, ongoing, and completed failures. Measure detection delay, missed hazardous failures, false alarms, explanation correctness, and downstream outcomes after intervention. Include normal but unusual executions, so novelty alone is insufficient to trigger a failure alarm.

**Starting points.** [AHA and REFLECT/RoboFail](README.md#failure-detection-recovery-and-knowing-when-to-ask-for-help).

### P18: Choosing recovery or human assistance

**Question.** Can a robot decide whether to retry, change strategy, restore the environment, stop, or ask a person for targeted help based on the likely outcome and cost of each option?

**Why it is hard.** A confident retry can amplify damage, while excessive help requests defeat autonomy. Recovery requires understanding both the failure and the remaining feasible actions.

**Proposed validation.** Use recoverable, unrecoverable, and ambiguous failures under distribution shift. Evaluate completion against human-assistance time and physical risk. Report repeated failures, unnecessary requests, unsafe persistence, recovery time, and whether a help request conveys enough information to resolve the problem. Compare fixed retry limits and fixed confidence thresholds with adaptive decisions.

**Starting points.** [KnowNo, REFLECT, AHA, and LIBERO-RECOVER](README.md#failure-detection-recovery-and-knowing-when-to-ask-for-help).

## C10 — Co-design of robot hardware and learning algorithms

### P19: Designing bodies for learnable behavior

**Question.** Can a co-design process choose morphology, compliance, and control architecture that produce robust, broadly useful behavior with less learning and calibration effort?

**Why it is hard.** Each design requires evaluating a learning system, and simulations can favor designs that exploit inaccurate contact or actuator models. A design specialized for one task may be poor across a task distribution.

**Proposed validation.** Fix fabrication, compute, energy, and training budgets. Compare co-designed and manually designed systems across held-out tasks and physical conditions. Count design search and failed prototypes. Validate fabricated candidates and report manufacturability, robustness, data requirements, and maintenance alongside task performance.

**Starting points.** [RoboGrammar, DiffHand, and Evolution Gym](README.md#co-design-of-robot-hardware-and-learning-algorithms).

### P20: Choosing sensing and actuation under a budget

**Question.** Which allocation of tactile coverage, force sensing, cameras, actuator capability, and onboard compute yields the best reliable task performance under a fixed system budget?

**Why it is hard.** Sensor value depends on morphology, policy architecture, training data, and latency. More sensing can increase calibration and integration costs or overwhelm the control loop.

**Proposed validation.** Declare cost, power, mass, latency, and training constraints. Compare sensor and actuator configurations using a shared task distribution and accounting for retraining. Report the frontier between reliability and total system cost, including wear and calibration. Test whether conclusions transfer to unseen tasks and operating conditions.

**Starting points.** [DIGIT and Sparsh](README.md#force-and-tactile-sensing-for-perception-learning-and-control), [UMI and contact-aware design](README.md#co-design-of-robot-hardware-and-learning-algorithms).

## Refining the catalog

Every entry starts with status **Draft proposal**. A useful refinement makes the task distribution, assumptions, resource budgets, and success criteria more precise while preserving the significance of the underlying question.

Contributors may propose new problems, split an overly broad problem, or document that a specific formulation has been answered. Keep identifiers stable; preserve historical context when merging or retiring an entry. A benchmark improvement establishes progress within its stated scope. A broader resolution claim should provide independent reproduction and address the declared generalization and reliability requirements.

Use the [problem proposal template](https://github.com/jiafei1224/awesome-robotics-millennium-problems/issues/new?template=propose-problem.md) and include evidence for both what is now possible and what remains unresolved.
