--- START OF FILE research_ultracompact_universal_ai_en.md ---

# Research Journal: Ultra-Compact Universal AI Model

**Status:** Active Theoretical Research  
**Created:** July 15, 2026  
**Continuity Rule:** Following each substantive research phase, this journal is expanded. Early conclusions are never deleted; if they are revised, the update is noted along with the reason.

## 0. Mandate and Boundaries

### Objective

To discover fundamental principles that *could* allow a system with a very small neural core to demonstrate universal intellectual capabilities far exceeding expectations for its weight count.

This is not an attempt to immediately design or claim a ready-to-use architecture. The space of hypotheses, their limitations, falsification conditions, and a program for further testing are being explored.

### Working Definition of "Ultra-Compact"

Compactness cannot be measured by a single parameter count. This journal separately tracks:

1. Persistent parameters stored on the device;
2. Active parameters and operations per single step;
3. Working memory and KV/state on long tasks;
4. External memory, indices, and tools;
5. Training budget and data volume;
6. Latency, energy, and reliability.

An "ultra-compact model" in the strong sense means a small core with limited overall system resources. Offloading an almost limitless knowledge base or frontier teacher to the outside cannot be counted as intelligence compression; it is a permissible component only if its cost and role are explicitly disclosed.

### Working Definition of "Universality"

Universality refers to the transfer of skills across substantially different open classes of tasks: language, abstract reasoning, planning, learning new rules, tool use, and adaptation to novel data. A single high score on a puzzle set, coding, or search is insufficient.

### What Is Not the Objective

- Cosmetically shrinking an existing Transformer;
- Passing off retrieval or an external API as the knowledge of a small core;
- Treating smooth text as evidence of reliable thinking;
- Building theses on unverified marketing claims.

## 1. Research Protocol

### Questions Every Candidate Principle Must Answer

1. **What deficit does it address:** knowledge capacity, working memory, computational depth, compositionality, learning, reliability, or cost?
2. **Where is the information located:** in weights, state, external memory, tool code, environment data, or compute time?
3. **What is the cost:** bytes, FLOPs, latency, routing errors, training, annotation, and vulnerabilities?
4. **What distinguishes true generalization from leakage/retrieval/memorization?**
5. **How to falsify the hypothesis?** Out-of-distribution tests, ablation, and prediction of both successful and unsuccessful cases are required.

### Levels of Evidence

- **A — Theorem or reproducible broad result.**
- **B — Several strong empirical papers, but with limited scope.**
- **C — A single result or preprint; promising, but unconfirmed.**
- **D — Thought experiment/hypothesis.**

No level C/D will be described as an established fact.

### Basic Metrics for Future Testing

- Accuracy and confidence calibration;
- Transfer to new rules, languages, patterns, and sources;
- Length of stable multi-step trajectory;
- Persistent core bytes, peak RAM, and energy;
- Active FLOPs and latency;
- Dependence of results on external memory and tools;
- Resistance to incorrect sources, contradictions, and prompt injection.

## 2. Initial Hypotheses (Pre-Research)

| ID | Hypothesis | Origin | Initial Status |
|---|---|---|---|
| H0 | A small fixed core cannot absorb the entire independent wide competence of a much larger model without significant losses. | Information capacity constraint. | Plausible; requires clarification. |
| H1 | Most of the useful intelligence gap can be bridged by role separation: a small core selects actions, while facts/computations/verification reside outside weights. | Knowledge, computation, and control are distinct deficits. | Promising. |
| H2 | The primary path to ultra-compactness is not improving a single attention layer, but building a multi-level addressable memory with a cheap mechanism for selecting relevant fragments. | Most facts are needed rarely and locally. | Promising, but high routing risk. |
| H3 | Universal reasoning requires iterative state and verifiable external representations, not just next-token prediction. | Long plans collapse under pure autoregression. | Promising. |
| H4 | Ultra-small models will acquire algorithms more effectively through learning in procedural environments and verifiable actions than through imitating text chains of thought. | Verifiable feedback is cheaper than human labeling. | Unclear. |
| H5 | Conditional computation can yield massive active cost savings, but does not cancel the cost of total storage, the router, and hardware support. | Distinction between total and active parameters. | Strong working hypothesis. |
| H6 | Strong universality requires an internal world model, causal invariants, and active experimentation; a single compressed text corpus is insufficient. | Transfer and grounding problem. | Fundamentally important, but poorly operationalized. |

## 3. Preliminary Falsifiers

- If a candidate merely uses a giant unmeasured memory/external model, it does not prove core ultra-compactness.
- If the advantage disappears when data is split by generator, time, and template, it is not proof of universal transfer.
- If a tool solves a task, the quality of tool selection, problem formulation, answer verification, and refusal must be evaluated separately.
- If efficiency is achieved on a single GPU or a single context length only, it cannot be transferred to edge devices or other modes.
- If "thinking" leaves no verifiable causal trace, its plausibility is not considered proven.

## 4. Update Log

### Update 1 — July 15, 2026: Initialization

Protocol established; initial hypotheses H0–H6 and falsification conditions locked. Next step: separate fundamental constraints from limitations of current Transformer/training recipes.

### Update 2 — July 15, 2026: Fundamental Constraints and H0 Clarification

#### 2.1. Four Different Meanings of "Universality"

First important distinction. In literature, the word "universal" often conflates at least four properties:

1. **Approximation universality:** Given sufficient width/depth, a network can approximate any function from a given class.
2. **Computational universality:** Under idealized assumptions, an architecture can express any computable procedure.
3. **Learnable universality:** A practical learning procedure actually finds the desired program from finite data and budget.
4. **Operational universality:** The system reliably transfers skills to novel real-world tasks under finite memory, time, and energy.

(1) or (2) does not imply (3) and certainly not (4). The Turing completeness theorem for Transformers demonstrates expressive capability under special assumptions, but does not derive compactness, training stability, or low computational cost. This eliminates the frequent false argument: *"the architecture is Turing-complete, therefore a small model is potentially as smart as any large one."*

**Status:** Level A for formal distinctions; transfer to trained AI systems is a logical deduction rather than a separate theorem.

#### 2.2. Thought Experiment E1: Arbitrary Dictionary of Facts

Suppose a system must accurately answer $n$ independent key-value pairs after a single presentation, each carrying $b$ unpredictable bits. If all past data is replaced by a state of volume $s < nb$ bits and the external source is unavailable, the Pigeonhole Principle dictates that two different sets of inputs will map to the same state. For some query, the system will inevitably err on at least one.

**Conclusion E1:** A fixed or bounded small state cannot support the exact retrieval of arbitrarily large amounts of independent new information. It compresses data well only when data has structure/redundancy, or when external memory and lossy compression are permitted.

This is not a prohibition on intelligence. An algorithm can be small, but the data it processes and its intermediate state do not have to be small. Consequently, a promising architecture must distinguish between:

- Compact *invariants/algorithms* worth placing in the core;
- Large or fresh *instance data* stored addressably outside it;
- Temporary reasoning state, whose size should grow with true task complexity.

#### 2.3. Thought Experiment E2: Compact Program vs. Compact Encyclopedia

Euclid's algorithm occupies a small code footprint and applies to infinitely many numbers: inputs possess mathematical regularity. Conversely, a table of random independent correspondences lacks such a short program. This yields a working division:

- **Capability** can be compressed radically if it is an algorithm or invariant;
- **Arbitrary information** cannot be compressed without loss;
- A successful ultra-compact model must seek short generative programs rather than attempting to memorize everything.

This frames the real research goal: to learn how to automatically extract transferable programs/invariants while storing data in a separate memory. This cannot be replaced by simple weight compression.

#### 2.4. Implication for Transformers, SSMs, and RNNs

Full attention preserves an address to every element of the context and thus reconstructs rare details well, but cache costs grow with length. Recurrent and SSM approaches hold a fixed state and yield favorable token costs, but E1 shows their inevitable risk: with a large pool of competing, independent associations, some details must be overwritten or lossily compressed.

Mamba attempts to improve this trade-off via input-dependent selection, making writing/forgetting selective; RWKV similarly achieves recurrent inference costs with parallel training. These are important engineering steps, but they do not cancel the entropy limit of a fixed state. Consequently, neither a pure Transformer nor a pure SSM/RNN looks like a sufficient starting point for strong universality: a hybrid multi-level memory is required.

**Status:** E1 constraint is Level A as an elementary information-theoretic argument; the statement on practical architectural necessity is Level B/D and must be tested.

#### 2.5. Clarification of H0

H0 is confirmed in the following more precise form:

> A small fixed core cannot simultaneously contain an arbitrarily large array of facts, an unbounded working trajectory, and a general behavioral program without loss. However, it *can* act as a compact carrier of algorithmic invariants and control a substantially larger addressable memory/compute, provided the cost of the entire system is accounted for separately.

This does not set a lower bound on "number of parameters for AGI": no such bound exists today. But it forbids treating weight size as the sole resource.

#### 2.6. Counter-Hypotheses and Falsification Conditions

| ID | Counter-Hypothesis | What Would Support It | How Not to Be Fooled |
|---|---|---|---|
| C0a | A fixed continuous state stores far more useful information than its bit estimate. | Reproducible exact recall of random associations significantly exceeding physical state bit-width. | Require finite precision, noise, bit measurements, and new random keys. |
| C0b | Neural networks acquire concise general programs for seemingly random tasks. | Transfer to new generators with provably general hidden programs. | Separate generators, not examples; test extreme input sizes. |
| C0c | Only a very small universal interpreter is needed, and all knowledge is fed in context. | The system solves a wide task set with a small core and explicitly bounded external memory. | Account for context size, search, read time, and addressing quality. |

#### 2.7. First Rejected Simplifications

1. **"Let's just find a Turing-complete minimal network."** Rejected as a criterion for intelligence creation: a universal interpreter can be small, but the program, data, and execution time transfer all complexity.
2. **"Replace full attention with SSM, and scaling vanishes."** Rejected: the problem transforms from storage cost into memory loss/collision.
3. **"Quantize a large model extremely."** Rejected as a fundamental path: quantization reduces the representation of an already found function, but adds neither knowledge nor algorithmic transfer.

#### 2.8. New Questions Following This Phase

1. Can memory be addressable, cheap, and learnable simultaneously such that addresses represent causal/algorithmic roles rather than superficial text similarity?
2. What minimal mechanism decides what to store literally, what to generalize into a rule, and what to forget?
3. Can computation be made adaptive to task complexity: simple cases in a single pass, hard ones via repeating internal state and verification?
4. How to force a small core to discover invariants rather than merely routing to pre-existing tools?

#### 2.9. Phase Sources

- Pérez, Marinković, Barceló, [*On the Turing Completeness of Modern Neural Network Architectures*](https://arxiv.org/abs/1901.03429). Role: formal computational expressivity of Transformers; Level A for stated theorem.
- Hoffmann et al., [*Training Compute-Optimal Large Language Models*](https://arxiv.org/abs/2203.15556). Role: model size and data as a joint resource rather than a single parameter; Level A/B for empirical scaling laws.
- Gu, Dao, [*Mamba*](https://arxiv.org/abs/2312.00752). Role: selective state and linear sequence cost; Level B for practical comparison.
- Peng et al., [*RWKV: Reinventing RNNs for the Transformer Era*](https://arxiv.org/abs/2305.13048). Role: recurrent inference and parallel training; Level B.
- Eldan, Li, [*TinyStories*](https://arxiv.org/abs/2305.07759). Role: small models capable of coherent behavior under drastically simplified distributions; Level B.

### Update 3 — July 15, 2026: Mechanism Space Post-Transformer

#### 3.1. Principle: "Complexity Must Live Somewhere"

Following E1, it is useful to classify solution spaces not by architecture names, but by *where complexity is offloaded*:

| Family | What Becomes Cheaper | Where Cost is Offloaded | Primary Risk |
|---|---|---|---|
| Sparsity / MoE | Active FLOPs | Expert storage, routing, communication | Faulty router, weak hardware benefit |
| Recurrence / SSM | Long context cost | Loss of details in compressed state | Collisions and forgetting |
| External addressable memory | Core size and knowledge freshness | Retrieval, index, latency, security | Incorrect address/read |
| Fast weights / test-time plasticity | Adaptation speed | Mutable state and stability | Contamination/erasure of memory |
| Iterative recursion / adaptive compute | Unique parameter count | Time, sequential dependency | Infinite/incorrect loops |
| Symbolic executor / types | Operation precision | Semantic parsing and interface design | Narrow DSL, brittle text-to-code transition |
| Algorithmic inductive biases | Size/structure transfer | Risk of overly narrow prior | Non-universality outside task family |

New regularity L1: **Ultra-compactness is not achieved by eliminating complexity; it is achieved by placing each form of complexity into its cheapest and most verifiable carrier.**

#### 3.2. Family P1: Small Program + External Addressable Memory

Neural Turing Machines (NTM) formulated the basic idea: a neural controller interacts with external memory via differentiable addressing; on simple tasks, this learned copying, sorting, and associative recall. Formal work even shows a tiny controller with explicit memory can implement a universal Turing machine.

**Arguments For:**
- Matches E1: arbitrary data need not be crammed into state;
- Separates compact control program from scalable working tape;
- Enables verifying read/write and using discrete structures: stack, graph, table, version log;
- Facilitates learning new facts without rewriting the core.

**Arguments Against:**
- A universal machine as a formal object does not automatically discover useful programs;
- Soft attention over growing memory becomes expensive and blurred;
- Gradient-based addressing training is unstable, especially when read errors break distant results;
- External memory makes the system vulnerable to false writes, conflicts, and prompt injection.

**Interim Assessment:** Not a finished architecture, but a mandatory structural motif. The candidate remains viable, but memory must be hierarchical with discretely verifiable operations rather than purely global soft attention.

#### 3.3. Family P2: Multi-Scale Memory and Test-Time Plasticity

Two close but distinct mechanisms exist:
1. **Memory as a separate addressable carrier:** literal episodes, documents, environment states.
2. **Memory as rapidly modifiable parameterization:** fast weights or neural memory generalizing recent experience during operation.

Fast Weight Memory showed on constrained tasks that rapidly changing weights can store compositional associations. Titans proposes combining short-term attention with long-term neural memory updated at test time, reporting strong results on long contexts. This supports hypothesis H2, but does not yet prove broad universality: both directions must be tested on arbitrary rare facts and prolonged non-monotonic work.

**Thought Experiment E3: "Fact or Rule?"**
A system receives a thousand new observations. Some are independent identifiers; some manifest a single law. The optimal strategy must:
- Store identifiers literally;
- Compress the law into an executable hypothesis;
- Preserve uncertainty and evidence;
- Be capable of revoking a rule upon encountering a counterexample.

A standard KV cache stores everything, a small RNN compresses everything, and RAG retrieves everything by similarity. None of the three mechanisms solves the "fact/rule" distinction by itself. This spawns new hypothesis H7: **A future system's key property is not memory volume, but learning the *type of write* and the reversible transition between episode, rule, and hypothesis.**

**Falsifier for H7:** If a simple combination of retrieval + summarization without explicit typing survives counterexamples, long-term recall, and transfer to a novel generative environment just as well, a dedicated memory-type mechanism is unjustified.

#### 3.4. Family P3: Depth via Weight Reuse

Universal Transformers, Adaptive Computation Time (ACT), HRM, and related recurrent/iterative models share one principle: do not store a new function in every layer, but repeatedly apply a compact operator until the state stabilizes or the budget exhausts.

This is fundamentally interesting: the number of **unique** parameters ceases to match the number of computation steps. Simple cases halt early; hard ones require more iterations. ACT demonstrated this computation distribution on synthetic algorithmic tasks, while Universal Transformer tied shared-weight recurrence to superior transfer on certain algorithmic problems.

**Arguments For:**
- Algorithms naturally consist of repeatedly applied rules;
- The same operator works on tasks of varying lengths;
- A path from wide layers to a compact interpreter;
- Adaptive halting avoids wasting time on easy inputs.

**Arguments Against:**
- Sequential iterations increase latency and complicate training;
- Stopping criteria can be falsely confident;
- A single repeated rule can loop or amplify errors;
- Shared depth without proper state representation merely applies the wrong operation repeatedly.

**Important Negative Result on HRM.** The original HRM paper claims strong 27M recurrent model results on ARC, Sudoku, and mazes. However, independent analysis of the ARC Prize replicated the signal but reached a narrower conclusion: the hierarchical part had near-zero effect relative to an equivalent Transformer, while the insufficiently emphasized outer-loop refinement proved decisive; task transfer was limited, and much of the result resembled rote memorization. Therefore, HRM cannot be cited as proof of a miniature general AGI.

**Revision of H4:** Only the weak version is supported—latent iterative refinement is a strong candidate for algorithmic reasoning. The strong version ("a small parameter count inherently yields universal reasoning") is unconfirmed.

#### 3.5. Family P4: Conditional Computation and "Elastic" Capacity

MoE saves active computation by selecting few expert branches; newer work like MoSE attempts to make even the width of the chosen expert adjustable per budget. This is useful for models operating in diverse modes: brief recognition, deep analysis, coding, multimodality.

**Conclusion L2:** Conditional computation should be viewed as a *budget allocation mechanism*, not an emergence mechanism for new knowledge. It is sensible only alongside a verifiable router, excess computation penalties, and routing error analysis.

For an ultra-compact system, MoE has dual status:
- Promising if experts are small, share base representations, and store different algorithmic roles;
- Unpromising if it is merely a massive library of underutilized parameters: in that case, overall compactness is unachieved.

#### 3.6. Family P5: Neuro-Symbolic and Typed Intermediate Languages

Language models perform poorly on exact arithmetic and long discrete invariants, but excel at translating ambiguous text into approximate structures. Executors/verifiers do the reverse. Hence the idea: the model need not be a calculator, but must construct a compact program or provable operation.

Research on Neural Module Networks and BINDER shows the utility of executable intermediate representations alongside their primary limit: diverse natural language resists fitting into a predefined grammar.

**New Hypothesis H8:** What is needed is not a single rigid DSL, but a *self-extending typed action language* where:
- Base primitives are small, safe, and verifiable;
- Novel composite skills compile into macros;
- Each macro has tests, a type/contract, and provenance;
- The neural net learns to select, synthesize, and reject macros when necessary.

This is currently Level D. Danger: self-expansion rapidly generates messy, unverifiable languages and shifts the general semantics problem into the macro library.

#### 3.7. Family P6: Algorithmic Inductive Biases

Neural Algorithmic Reasoning proposes training neural networks to execute algorithm invariants rather than fitting correlations. Graph network and dynamic programming work are especially interesting: task structure can be represented as message-passing between objects rather than a long string of tokens.

**Arguments For:** If the world has compositional, object, and causal structures, the right inductive bias yields far greater transfer across size and combination than memorizing examples.

**Arguments Against:** Algorithmic "alignment" is often acquired on pre-known algorithm families. A model may excel at graphs while failing to discover novel representations.

Implication of H6: "World model" must not mean a single hidden vector. A more realistic goal is a set of explicit, revisable object-relational models operating at different time scales with active testing capabilities.

#### 3.8. Rejected or Downgraded Ideas Post-Review

1. **HRM as ready proof of ultra-compact universal universality.** Downgraded: outer-loop refinement is interesting, but independent analysis points to limited transfer and a weak role for hierarchy.
2. **Pure differentiable memory as the complete answer.** Downgraded: addressing scale and training remain unresolved.
3. **A single pre-designed universal DSL.** Downgraded: good for narrow domains, too rigid for an open world.
4. **MoE as total size compression.** Rejected: it is primarily a computational, not an informational, economy.

#### 3.9. New Questions Post-Phase

1. How to represent memory such that discrete episodes, compressed rules, and hypotheses are compatible without muddying?
2. Can a repeatedly used compact operator learn to *discover* new algorithms rather than repeatedly executing known templates?
3. How to train halting and budget allocation without encouraging premature confidence?
4. How to empower the system to create verifiable macros without letting it covertly expand the trusted computing base?
5. Can we measure "intelligence per total system bit" rather than active FLOP alone?

#### 3.10. Phase Sources

- Graves, Wayne, Danihelka, [*Neural Turing Machines*](https://arxiv.org/abs/1410.5401). Role: neural controller with external memory; Level B, results preliminary.
- Stogin, Mali, Giles, [*A provably stable neural network Turing Machine*](https://arxiv.org/abs/2006.03651). Role: formal feasibility of a compact controller with explicit memory; Level A for construction, not learnable universality.
- Behrouz, Zhong, Mirrokni, [*Titans: Learning to Memorize at Test Time*](https://arxiv.org/abs/2501.00663). Role: neural long-term memory; Level C, preprint.
- Schlag, Munkhdalai, Schmidhuber, [*Learning Associative Inference Using Fast Weight Memory*](https://arxiv.org/abs/2011.07831). Role: fast weights for compositional associations; Level B in constrained environments.
- Graves, [*Adaptive Computation Time for Recurrent Neural Networks*](https://arxiv.org/abs/1603.08983). Role: adaptive depth; Level B.
- Dehghani et al., [*Universal Transformers*](https://arxiv.org/abs/1807.03819). Role: shared-weight recurrence and dynamic halting; Level B.
- Wang et al., [*Hierarchical Reasoning Model*](https://arxiv.org/abs/2506.21734). Role: strong claim of small recurrent reasoning; Level C, preprint.
- ARC Prize, [*The Hidden Drivers of HRM's Performance on ARC-AGI*](https://arcprize.org/blog/hrm-analysis). Role: independent verification/ablations of HRM; Level B for specific benchmark.
- Tastan et al., [*MoSE: Mixture of Slimmable Experts*](https://arxiv.org/abs/2602.06154). Role: smoother compute budget distribution; Level C/B, recent work.
- Cheng et al., [*Binding Language Models in Symbolic Languages*](https://arxiv.org/abs/2210.02875). Role: executable intermediate representations; Level B, constrained domain.
- Veličković, Blundell, [*Neural Algorithmic Reasoning*](https://arxiv.org/abs/2105.02761). Role: algorithmic inductive biases; Level B as a research program.

### Update 4 — July 15, 2026: Thought Experiments on Transfer, Abstraction, and Self-Compression

#### 4.1. Thought Experiment E4: Identical Observations, Different Causal Worlds

Suppose training always observes `umbrella → rain`. In World A, rain causes umbrellas; in World B, umbrellas are artificially handed out before events, and rain is independent. Observational correlations can be identical, but the intervention `hand out umbrella` has different consequences.

A system storing only sequential statistics cannot distinguish A and B without:
- An object/variable "rain" distinct from the observed feature "umbrella";
- Alternative structural hypotheses;
- Experiments, counterfactuals, or intervention data;
- Memory of which hypothesis is supported by what evidence.

**Conclusion E4:** For strong OOD transfer, compactly predicting the next token is insufficient. We need *factorization of objects, relations, and mechanisms*, alongside the ability to hold competing models prior to testing.

Recent work on object-centric representations supports a weaker empirical thesis: under constrained data, diversity, or downstream compute, object-centric representations transfer novel compositions better in controlled visual worlds. But other work on object-centric world models shows a critical boundary: good reconstruction and prediction of objects do not guarantee stable control due to latent state drift during interactions. Hence, "splitting the world into objects" is a useful bias, but not a finished world model.

**New Hypothesis H9 — Factorized Causal State.** The working memory of a universal compact core must represent not a monolithic vector, but a dynamic graph of entities featuring:
- Object identity and lifespan;
- Typed relations;
- Transition mechanisms/hypotheses;
- Confidence source and degree;
- Local update capabilities upon counterexamples.

**Danger of H9:** Discretizing objects can impose false boundaries where the world is continuous; graphs can swell and destroy compactness. Thus, an object is not an ontological given, but an adaptive hypothesis subject to splitting or merging.

#### 4.2. Thought Experiment E5: Skill Library and Minimum Description Length

Consider a stream of tasks generated by an unknown composition of small operations. Solving each task can be stored as a long trajectory. Alternatively, the system extracts repeating fragments, creates a macro with a contract and tests, and subsequently uses it in shorter programs.

This yields a mechanism for real *competence* compression: not deleting matrix numbers, but discovering repeatedly applicable procedures.

However, macro libraries easily bloat into hidden memorization. Hence the thought criterion for `episode → macro` promotion:

$$\Delta L = L(\text{old solutions}) - [L(\text{new macro}) + L(\text{rewritten solutions})] > \tau$$

where $L$ is code length incorporating tests, types, input descriptions, and invocation costs. A macro is accepted only if it reduces description length across a task set and passes counterfactual tests on novel compositions.

**New Hypothesis H10 — Consolidating Procedural Memory.** Compactness grows when a system regularly turns verified episodes into short, typed, executable abstractions via Minimum Description Length (MDL), while preserving original episodes and counterexamples for rollbacks.

This is a principle, not a finished architecture. It combines:
- Neural pattern induction;
- Discrete verification and types;
- Long-term library;
- A criterion against unbounded "expert" accumulation.

**How to falsify H10:** Compare against an equivalent-memory standard RAG, fixed library, and oracle library. Tests must include novel compositions and anti-examples, factoring library size, tests, and execution time into the cost. If H10 fails to improve length/compositional transfer at identical system cost, the added complexity is unjustified.

#### 4.3. Thought Experiment E6: Task Without a Matching Expert

A novel formal world with unfamiliar operators is presented. No relevant document, ready macro, or trained MoE expert exists in memory. Only input-output examples, safe hypothesis testing, and a bounded compute budget are available.

A system claiming universality must execute a cycle:
1. Notice discrepancies with old explanations;
2. Formulate compact hypotheses;
3. Plan a discriminating experiment;
4. Update state based on results;
5. Either create a verified new primitive or honestly retain uncertainty.

This test excludes four false successes: searching for a ready answer, routing correctly to an old legacy expert, template imitation, and ungeneralized brute-force search.

**Implication:** Future evaluations must assess not just "solving the task," but the quality of *active next-observation selection*. Language and passive corpora alone do not supply this signal fully.

#### 4.4. Thought Experiment E7: Depth vs. Width Under Equal Total Budget

Comparing:
- A: A wide feed-forward block with $P$ unique parameters applied once;
- B: A smaller block with $P/k$ parameters applied $k$ times, plus state and adaptive halting.

If a task consists of a repeating local rule (graph relaxation, iterative refinement, loop execution), B can win: it encodes the rule once and spends time applying it. If a task requires many independent transformations or a wide set of unshareable facts, B loses either in time or quality.

**Regularity L3:** Weight reuse promises *algorithmic*, not encyclopedic, ultra-compactness. It should be evaluated separately on:
- Length and step-count extrapolation;
- Novel compositions of known operations;
- Broad knowledge and linguistic variation.

A combined score obscures this trade-off.

#### 4.5. Thought Experiment E8: Verification as a Compression Source

Consider a thousand long task solutions. Without verification signals, retaining many examples and imitating them is safer. With a cheap strict verifier, one can keep a small candidate program, generate multiple variants, and keep only those passing tests. Computation and verification thus replace part of the capacity required to memorize ready answers.

**New Hypothesis H11 — Verifier-Directed Learning.** The most valuable dataset for a compact universal core is not necessarily the largest text corpus; it is diverse environments where correctness can be cheaply distinguished from plausibility. A compact model must learn to choose representations and actions rather than reproducing long solution texts.

**Limit of H11:** Verifiability is not universal. For policy, science, interpersonal tasks, and incomplete data, no full oracle exists. There, the system must retain probabilistic hypotheses, evidence provenance, and the right to refuse rather than imitating a formal proof checker.

#### 4.6. Candidate Principle P*: Two-Speed Knowledge Consolidation

At the intersection of E3, E5, and E8 emerges not an architecture, but a more concrete principle:
1. **Fast episodic memory** stores observations, attempts, errors, and provenance;
2. **Slow procedural memory** stores only confirmed short invariants/macros;
3. **Compact neural core** selects what to read, what to verify, what to execute, and when to propose consolidation;
4. A "description economy" acts between layers: a rule must pay off its cost on new tasks;
5. Evidence and counterexamples ensure rollbacks.

P* resembles the motivation of short/long-term memory separation, but adds a strict growth criterion for the procedural library. Its key research question: can a neural network *independently* discover correct abstraction boundaries rather than archiving frequent phrases?

#### 4.7. Risks and Negative Predictions for P*

- On distributions lacking repeating structure, P* yields no compression and degrades to episodic memory;
- On shifting rules, premature consolidation is harmful; a Bayesian/statistical threshold and macro revocation are needed;
- In natural language, superficial repeatability can forge false abstractions; semantic counterfactuals rather than n-gram frequencies are required for validation;
- The procedural library can become a hidden MoE; metrics must include its total size, not just the neural controller.

If these negative predictions fail to manifest, P*'s formulation is incorrect or the test fails to discriminate mechanisms.

#### 4.8. Updated Prospect Registry

| Direction | Prospect | Why | Prerequisite for Continuation |
|---|---|---|---|
| P1: addressable memory | High | Necessary for E1 | Clear cost and reliable addressing |
| P2: fast/test-time memory | Medium-high | Adaptation and recent-experience compression | Stress tests on interference and recall |
| P3: shared-weight refinement | Medium | Algorithmic depth on a small core | Transfer beyond a single benchmark |
| P4: MoE/elasticity | Auxiliary | Distributes active budget | Account for total storage and router |
| P5: typed neural-symbolic interface | High for reliability | Precise operations and debugging | Moving beyond narrow fixed DSLs |
| P6: object/causal representations | High, but risky | Chance of OOD compositionality | Stable objects, intervention tests |
| P* : two-speed consolidation | Most interesting synthetic line | Unites memory, abstraction, verification | Prove automated discovery of useful primitives |

#### 4.9. Phase Sources

- Kapl et al., [*Are Object-Centric Representations Better At Compositional Generalization?*](https://arxiv.org/abs/2602.16689). Role: recent controlled evaluation of object-centric bias; Level C/B, preprint.
- Ferraro et al., [*When Object-Centric World Models Meet Policy Learning: From Pixels to Policies, and Where It Breaks*](https://arxiv.org/abs/2511.06136). Role: negative result on transition from representation to control; Level C.
- Veličković, Blundell, [*Neural Algorithmic Reasoning*](https://arxiv.org/abs/2105.02761). Role: algorithmic transfer rationale; Level B as program.
- Dehghani et al., [*Universal Transformers*](https://arxiv.org/abs/1807.03819). Role: context for E7; Level B.
- Li et al., [*Grokked Transformers are Implicit Reasoners*](https://arxiv.org/abs/2405.15071). Role: distinguishing ID and OOD composition; Level C/B, constrained synthetic graphs.

### Update 5 — July 15, 2026: From Hypotheses to Research Program

#### 5.1. Connecting H10 to Program Induction

DreamCoder demonstrated a close motif in constrained domains: solve tasks via programs, periodically expand the language with new abstractions, and train a neural network to guide search. It shows that a "library of thought primitives" is not a pure metaphor: it can be made interpretable, compositional, and transferable to new tasks in restricted worlds.

However, DreamCoder does not solve the main open question of this journal. Its success relies on relatively clear task types, programming languages, and search whose cost can scale rapidly. Thus, H10 now holds the status of:
- A **provably substantive idea** in constrained domains;
- An **unconfirmed hypothesis** regarding scaling to language, perception, causal models, and the open world.

New regularity L4: **Compact intelligence likely needs to learn not only parameters, but also how to change its own representation language.** However, this language shift must be taxed with strict costs, types, and tests, otherwise "abstraction growth" morphs into unaccounted model growth.

#### 5.2. Thought Experiment E9: Good Answer From Bad Internal State

Two hidden worlds yield identical correct answers to a current question, but lead to different consequences after an action. For example, a robot might bypass an obstacle now without distinguishing "fragile ice" from "transparent glass"; the distinction becomes critical on the next step.

A standard loss function penalizing current answers alone does not force representations to preserve this distinction. Even next-token prediction may fail to penalize the model until an appropriate intervention occurs in data.

**New Hypothesis H12 — Contractible Representations.** A substantive internal variable does not need a human name, but requires a verifiable contract specifying:
- What observations it explains;
- What future observations/action effects it predicts;
- What environmental shifts must alter its value;
- What input fraction can be reconstructed or explained through it;
- What uncertainty remains.

This is not a requirement to fully decode every latent back to pixels/tokens: such a requirement is wasteful and bars useful abstraction. We need *selective reversibility* regarding task-significant counterfactuals and the ability to verify contracts via actions.

**Arguments For H12:**
- Reduces risk of the model hiding critical errors in uninterpretable vectors;
- Yields localized signals for correcting worlds/rules rather than global retraining;
- Bridges neural flexibility with programmatic invariants and tests.

**Arguments Against H12:**
- Contract verification itself requires observation languages and tools;
- Causal variables are often unidentifiable from passive data;
- Superfluous constraints can halt the emergence of efficient, non-human representations.

#### 5.3. Thought Experiment E10: Memory as a Controlled Communication Channel Over Time

Consider an agent bounded by $B$ bits of writes per step to persistent memory. It sees a rich stream, but retains only a fraction. A naive compressor keeps the most probable features; an intelligent agent must retain what *will alter future decisions*.

This reframes memory: not a past archive, but a limited-bandwidth channel between past and future.

**New Hypothesis H13 — Counterfactually Valuable Memory Distribution.** The importance of a write must depend not on text surprise or local similarity, but on expected changes across future decisions/verifications with and without that write.

Principally, this aligns closer to the value of information than normal summarization. Practically, it is extremely difficult: evaluating future utility without a solved future is hard. Possible approximations include disagreement among brief hypotheses, predictable error drops in verifiers, or expected future program length reductions.

**Falsification Condition for H13:** If simple recency + retrieval score heuristics ensure identical memory transfer and robustness in streaming environments, complex counterfactual evaluation is unnecessary.

#### 5.4. Candidate Principle P*: Two-Speed Knowledge Consolidation

Instead of a single architecture, we define conditions a future candidate must satisfy:
1. **Core stores transferable transformations, not encyclopedias.**
2. **Episodes, rules, and hypotheses have distinct storage regimes, costs, and update procedures.**
3. **Hard tasks receive more *computation time*, not necessarily more unique parameters.**
4. **Precise solution components can be offloaded to verifiable executors.**
5. **Abstractions must earn their right to exist via description length reduction and counterfactual transfer.**
6. **Memory importance is governed by future action/verification value, not statistical frequency.**
7. **New internal variables require verifiable contracts rather than convenient hidden vectors.**

If these properties cannot coexist in a single system, it is no failure: intelligence likely requires multiple interacting representations. But their total cost becomes part of the ultra-compactness metric.

#### 5.5. Research Program R1–R5

The sequence progresses from worlds where error can be proven to open tasks. Starting with a general web benchmark is prohibited: underlying success causes remain obscured there.

| Phase | Question | Minimal World | Key Baseline | Passing Criterion |
|---|---|---|---|---|
| R1: memory | Can the system separate fact from rule? | Random key stream + hidden laws + counterexamples | RNN/SSM, Transformer+KV, RAG | Exact random fact recall and law transfer at equal total memory |
| R2: recursion | Does weight reuse yield algorithmic transfer? | Graphs, programs, mazes with expanding size | Equal-FLOP and equal-parameter Transformers | Length extrapolation without hidden time/error growth |
| R3: abstractions | Can H10 find useful macros without library bloat? | Tasks from an unknown compositional grammar | Fixed DSL, DreamCoder search, episode RAG | MDL reduction and success on novel compositions |
| R4: causality | Do H9/H12 retain differences needed post-intervention? | Paired worlds with identical correlations and differing mechanisms | Dense latent world model, object-centric only | Correct experiment choice and OOD plan post-intervention |
| R5: integration | Are mechanisms compatible without losing economy? | Multimodal interactive environment with language | Strongest individual variants | Pareto improvement: quality/memory/energy/reliability simultaneously |

#### 5.6. Fair Comparison Protocol

Every R-series run must report:
- Total persistent parameters, including router, embedder, verifier, library, and learned index;
- Peak working memory, including KV, states, episodes, cache, and search history;
- Training: data, generated examples, teacher calls, augmentation, trial counts;
- Active FLOPs and wall-clock time per successful solution, including search and verification;
- Individual curves for ID, OOD, long extrapolation, noise, and interventions;
- False confidence probability and refusal quality;
- Full ablations of each memory and refinement layer.

Situations where a single source task spawns hundreds/thousands of augmented trajectories without accounting for them as training are explicitly prohibited from being called "few-shot learning."

#### 5.7. Early Decision Gates

- **Gate A (post-R1):** If simple hybrid retrieval + short attention cannot be beaten at equal total memory, do not invest in complex neural memory.
- **Gate B (post-R2):** If weight tying improves familiar sizes only or requires more total work than a dense model, treat it as a local optimization, not a foundation.
- **Gate C (post-R3):** If discovered macros fail to reduce MDL or pass novel compositions, reject H10.
- **Gate D (post-R4):** If object/causal states fail to boost intervention success, abandon "world model" as an explanation.
- **Gate E (post-R5):** If integration yields no Pareto improvement but shifts costs to external systems, refrain from claiming ultra-compactness.

#### 5.8. Open Problems That Cannot Be Masked by Engineering

1. **Representation discovery:** How to make systems invent proper variables instead of selecting from preset dictionaries?
2. **Credit assignment across long trajectories:** How to identify which write, hypothesis, or iteration caused late success/failure?
3. **Open security of self-expansion:** Who authorizes new macros gaining access to memory/tools?
4. **General learning without catastrophic forgetting:** What knowledge should become slow parameters vs. revisable data?
5. **Universality metric:** No single ARC/coding/QA score measures the capacity to discover novel representations and act under uncertainty.

#### 5.9. Phase Sources

- Ellis et al., [*DreamCoder: Growing generalizable, interpretable knowledge with wake-sleep Bayesian program learning*](https://arxiv.org/abs/2006.08381). Role: precedent of compositional library growth in constrained domains; Level B.
- Hewitt, Le, Tenenbaum, [*Learning to learn generative programs with Memoised Wake-Sleep*](https://arxiv.org/abs/2007.03132). Role: reuse of discovered programs; Level B/C.
- Wu, Goodman, Ermon, [*Improving Compositionality of Neural Networks by Decoding Representations to Inputs*](https://arxiv.org/abs/2106.00769). Role: partial verifiability of hidden representations; Level B, constrained result.
- Kapl et al., [*Are Object-Centric Representations Better At Compositional Generalization?*](https://arxiv.org/abs/2602.16689). Role: basis of E4; Level C/B.

### Update 6 — July 15, 2026: First Cycle Synthesis and Continuation Point

#### 6.1. What This Cycle Established and What It Did Not

**Established with reasonable confidence:**
1. Small weight counts alone are neither a measure of intelligence nor total cost. Information, working memory, and computation do not vanish under quantization/sparsity.
2. A fixed bounded state cannot precisely hold an unbounded set of independent new facts; external memory, data structures, or lossy compression are required.
3. Iterative weight reuse expresses algorithmic depth with few unique parameters, but trades off sequential time and lacks proof of broad encyclopedic competence.
4. Addressable memory, verifiable execution, and compositional programs are real, albeit domain-constrained, pathways to boost intelligence per parameter.
5. Striking results on narrow reasoning benchmarks do not prove universality: HRM exemplifies the need for independent ablation checks, augmentation, outer-loop refinement, and transfer verification.

**Not established:**
1. Lower bound of parameters/bits for general intellectual competence;
2. Learnable mechanisms for discovering correct objects, causes, and abstractions in open worlds;
3. Methods uniting episodes, rules, programs, and probabilistic hypotheses without manual ontology;
4. Proof that P* scales beyond procedural toy environments;
5. A unified metric for "universal intelligence per byte/joule."

#### 6.2. Status of All Hypotheses Post-First Cycle

| ID | Formulation Summary | Status | Reason / Next Action |
|---|---|---|---|
| H0 | Small core cannot hold arbitrary independent competence without external resources. | Supported | E1; do not treat as AGI lower bound. |
| H1 | Role separation boosts small core utility. | Conditionally supported | Account for total memory/tool costs. |
| H2 | Multi-level addressable memory is a key path. | Strong candidate | R1: compare against simple retrieval + short attention. |
| H3 | Iterative state and verifiable external representations are needed. | Strong candidate | R2 and R3. |
| H4 | Procedural/verifiable training beats text imitation for algorithms. | Partially supported | Test transfer outside verifier domains. |
| H5 | Conditional computation cuts active cost, not total cost. | Supported | Use strictly as an auxiliary mechanism. |
| H6 | Strong transfer requires world models of objects/mechanisms and active tests. | Plausible | R4; no general proof. |
| H7 | Memory must distinguish episode, rule, and hypothesis. | Strong candidate | R1 with counterexamples. |
| H8 | Self-extending typed action language is needed. | Speculative | R3; library bloat risk. |
| H9 | Factorized causal state improves intervention transfer. | Speculative, motivated | R4; test against dense latent. |
| H10 | MDL macro consolidation compresses competence. | Most interesting candidate | R3; DreamCoder is a constrained precedent. |
| H11 | Verifier-directed learning replaces memory with computation/verification. | Supported in verifiable domains | Separate from unverifiable tasks. |
| H12 | Internal abstractions need observation/intervention contracts. | New speculative line | Design selective counterfactual tests. |
| H13 | Memory writes should optimize for future value, not frequency. | New speculative line | R1/R4 against simple heuristics. |

#### 6.3. Main Synthetic Conclusion

The most promising fundamental line is not "yet another efficient layer," but **abstraction economics under resource constraints**:
- A cheap core executes repeating operations, selects computational budgets, and forms hypotheses;
- Episodic memory holds ungeneralized evidence and errors;
- Procedural memory accepts only abstractions that reduce total description length and pass novel tests;
- World model stores competing object-relational hypotheses rather than a single confident text story;
- Executable contracts and verifiers provide external anchor points;
- Complexity is measured across the system: core + library + states + search + time.

This is **not an architecture**, nor a claim that such a system is achievable. It is a bundle of necessary, jointly testable principles. Its value lies in yielding predictions, falsification methods, and avoiding hidden transfer costs.

#### 6.4. Prioritized Continuation Queue

The next research cycle must start with R1, not large system implementations.
1. Formally define world generator `episodes + laws + law shifts + counterexamples`.
2. Define full resource metrics: persistent bits, temporary bits, reads/writes, FLOPs, verifier calls.
3. Implement/simulate **at least four** equally budgeted baseline classes: short Transformer, SSM/RWKV state, retrieval+attention, addressable memory with record types.
4. Pre-register held-out generators and intervention tests prior to results.
5. Explore H10 (macro consolidation) only if Gate A clears; otherwise do not bloat memory.
6. Every macro/novel abstraction must carry: type, provenance, test set, storage cost, reuse stats, and revocation mechanism.

#### 6.5. Instructions for Next Session

- This file is the sole canonical journal. It must be **supplemented**, not replaced by summaries.
- Read sections 0–6 before new searches, especially falsifiers and decision gates.
- Log each new research step in a dedicated `Update N` block with date, question, method, pros/cons, hypothesis status shifts, and sources.
- Retain negative results and downgraded ideas: they guard against rediscovering rejected paths.
- Avoid claiming a "new architecture" prior to passing R1–R4 or discovering strong theoretical counterarguments.
- For computational experiments, preserve protocol, seed, code/env, and outputs in journal appendices.

#### 6.6. Save Point

First theoretical cycle complete. Primary next task: translate R1 into a strict experimental protocol and test H2/H7/H13 under fair full-resource accounting. No architecture selected yet.

### Update 7 — July 15, 2026: Adversarial Review, Part I — H0–H6

**Role of this update:** Independent reviewer. No prior hypothesis retains presumption of truth. Pointing out weaknesses below supersedes preserving a neat general scheme.

#### 7.1. Critique of H0: "A Small Core Cannot Contain Wide Independent Competence"

**What is correct:** E1 is a valid pigeonhole argument solely for exact retrieval of arbitrary independent bits from a finite-physical-precision state. No architecture violates this.

**Logical flaws and hidden assumptions in the prior formulation:**
1. "Competence" was implicitly equated with the entropy of a fact base. Algorithmic competence can be described concisely and operate on unlimited inputs.
2. E1 assumes exact recall of every fact. Real utility often permits probabilistic answers, retrieval, clarification requests, re-observation, or law-based computation.
3. "Fact independence" is a strong assumption. In the natural world, observations are compressible by common mechanisms. Worst-case random tables cannot be mapped to human knowledge without measuring algorithmic complexity.
4. Device-fixed memory, inputs, environments, and time are unseparated. A small universal interpreter can process huge programs supplied on input; this does not make the program core content, but refutes "small cores can't do complex things."
5. The prior text morphed a finite-precision engineering fact into an ontological claim about intelligence limits. Physical systems feature noise, energy, and finite resolution, but bit boundaries depend on media and reliability targets.

**Counterexamples:**
- A compact programming language interpreter solves infinite valid programs without storing answers;
- A small model receiving physical law formulas derives new consequences without storing observation tables;
- A low-complexity environment lets small programs look hyper-universal over huge input sets.

**Corrected Formulation H0':**
> Under finite physical precision and zero extra memory channels, no system can guarantee exact recovery of an arbitrary array of independent information whose entropy exceeds its state. This sets no lower bound on general intelligence, excludes no concise algorithms, and says nothing about real-world compressibility.

**Status:** H0 in broad form downgraded/rejected; H0' retained as a narrow physical-information constraint.

#### 7.2. Critique of H1: "Role Separation Sharply Boosts Small Core Utility"

**Hidden Assumptions:** External retrieval, memory, tools, and verifiers are assumed available, correct, cheap, safe, and well-described. These components are often harder than the text generator itself.

**Alternative Explanations:**
- Tasks are factored via human design into APIs and strict formats; manual design yields the gain, not the small core;
- Large external indices or executors house most required competence;
- Benchmarks reward tool invocation over problem formulation, verification, and refusal timing;
- Routing uses hidden distributional heuristics and breaks under novel task types.

**Counterexamples:**
- Domains with costly/dangerous actions: faulty tool calls exceed the cost of internal model miscalculation;
- Latency-constrained interactive environments: multi-module setups lose to single models due to I/O and coordination overhead;
- Tasks requiring weak signals across sources: modular splits induce interface losses.

**Unaccounted System Limits:** Networks, disks, cold starts, memory bandwidth, permissions, data versioning, prompt injection, API nondeterminism, and observability costs.

**Corrected H1':** Role separation is an engineering heuristic improving Pareto frontiers for tasks with clean interfaces and reliable tools. It proves no core intelligence amplification and requires comparison against end-to-end baselines under equal latency/energy/attack-surface profiles.

**Status:** Substantially downgraded: a "conditionally useful engineering strategy," not a fundamental principle.

#### 7.3. Critique of H2: "Multi-Level Addressable Memory is a Key Path"

**Necessity Issue:** E1 dictates external storage for worst-case exact recall of large arrays. It *does not* dictate it as the key to universal reasoning. The real bottleneck may be abstraction learning, not storage; or highly compressed parametric world models may beat literal retrieval for useful tasks.

**Addressing Issue:** Retrieval itself demands query representation. If the controller lacks task understanding, it cannot formulate clean keys. If addressing is approximate, rare/counterintuitive/negative evidence is systematically dropped. If precise, index/metadata/search costs can surpass the memory saved.

**Counterexamples:**
- Logic tasks whose entire structure fits in a short input: archive access distracts and harms;
- Rapidly updating environments: stale memory degrades actions;
- Novel abstraction tasks lacking similar historical episodes: retrieval returns false analogies.

**Ignored Hardware Realities:** DRAM/SSD bandwidth and random accesses burn energy; vector search demands embeddings, ANN indices, updates, and batch-friendly hardware; KV caches beat external round-trips on short tasks. Differentiable memory historically struggles to scale due to unrolled depth and linear access.

**Corrected H2':** Addressable memory is necessary for long-term precise external data access, but its utility is hierarchical and contingent on learnable addressing. Calling it the "key path" lacks grounds.

**Status:** Downgraded from "high" to "equal candidate; high scaling risk."

#### 7.4. Critique of H3: "Universal Reasoning Requires Iterative State and Verifiable External Representations"

**Necessity Error:** Some complex functions execute via parallel circuits; others are internalized into parameters and executed in single passes. "Reasoning" lacks a universally accepted formal definition implying loops or explicit scratchpads.

**Hidden Assumptions:**
- Computational depth must be sequential rather than compilable into width/specialized circuits;
- External representations render processes verifiable rather than forging another channel for plausible errors;
- Step-explanation capability correlates with correctness causes.

**Counterexamples:** Matrix math, specialized solvers, or learned policies solve task classes without interpretable step traces; long CoTs can be non-functional rationalizations.

**Ignored Physics Boundaries:** Iteration saves unique weights while amplifying latency, accumulation errors, and credit assignment difficulty. For tight real-time budgets, it loses to wide single-step schemes despite smaller memory footprints.

**Corrected H3':** Recurrent computation and verifiable states are useful mechanisms for classes featuring sequential invariants and cheap verification. Their necessity for universality remains unproven.

**Status:** Rejected as a strong claim; retained conditionally as an exploratory vector.

#### 7.5. Critique of H4: "Procedural Environments and Verifiers Beat Text Imitation"

**False Dichotomy:** Text corpora embed compressed human algorithms, social models, informal criteria, and data resistant to verifiers. Procedural environments can be narrow, toy-like, and devoid of real distributions.

**Training Issues:** Reward hacking, misspecification, sparse rewards, combinatorial search, test overfitting, and uncounted side effects. Passing tests does not prove correct mechanisms.

**Counterexample:** Programs passing unit tests fail on hidden corner cases; models optimized to pass tests may degrade in robustness outside them compared to models with rich text priors.

**Corrected H4':** Verifiable environments supply high-quality signals for aspects they genuinely cover. They should complement, not replace, rich pretraining and transfer evaluations.

**Status:** Downgraded: valid scope, unproven comparative generality.

#### 7.6. Critique of H5: "Conditional Computation Allocates Budgets, Doesn't Create Knowledge"

Semantically false. Conditional specialization raises representational capacity under fixed active compute: diverse experts store distinct conditional functions, increasing stored competencies. Discarding this merely because parameters physically exist is invalid.

Conversely, MoE gains can be illusory due to uncompared total parameter counts, greater training compute, data mixing advantages, or hardware utilization. At the edge, storage and memory bandwidth consume active FLOP gains.

**Corrected H5':** MoE/conditional computation alters trade-offs across total storage, active FLOPs, training dynamics, and specialization. It is neither free compactness nor a mere router: it requires four-resource accounting.

**Status:** Prior formulation rejected; H5' is a neutral engineering hypothesis.

#### 7.7. Critique of H6: "Strong Universality Requires Causal World Models and Active Experiments"

**Overstated Necessity:** Closed formal worlds, mathematics, language, and engineering tasks allow strong generalization without physical causal world models or physical actions. Invariant, symmetry, Bayesian, or programmatic representations suffice in specific classes.

**Identifiability Problem:** Causal structures are unidentifiable from passive data alone without assumptions, multi-view data, or interventions. Requiring "learned causal models" hides heavy supervision sources.

**Alternatives:** Multiple environments, invariance, controlled augmentation predictions, formal specifications, expert theory, and simulators supply transfer without universal causal discovery.

**Corrected H6':** Object-relational and causal hypotheses aid transfer under interventions in partially observed dynamic environments, but lack proof as general intelligence prerequisites and carry identifiability issues.

**Status:** Sharply downgraded; restricted to contextual use in R4.

#### 7.8. Shifts in Fundamental Constraints

- Prior claim "fixed states cannot hold arbitrary arrays" was improperly elevated to a general intelligence limit. Correction: it is a narrow worst-case information bound.
- Self-attention/KV-cache limits were hastily deemed architectural fundamentals. They are execution-graph trade-offs movable via alternative carriers, memories, and hardware.
- Turing completeness was cited as a design anchor. Post-revision, it is recognized as largely irrelevant to sample efficiency, robustness, latency, and training dynamics.

#### 7.9. Sources for Adversarial Review I

- Weiss, Goldberg, Yahav, [*On the Practical Computational Power of Finite Precision RNNs for Language Recognition*](https://aclanthology.org/P18-2117/). Role: formal limits showing RNN Turing-completeness depends on infinite precision/unbounded time; Level A for stated regime.
- Locatello et al., [*Challenging Common Assumptions in the Unsupervised Learning of Disentangled Representations*](https://jmlr.csail.mit.edu/papers/volume21/19-976/19-976.pdf). Role: unsupervised disentanglement impossibility without inductive biases; Level A under theorem conditions.
- Aleš, [*Neural Turing Machines: Convergence of Copy Tasks*](https://arxiv.org/abs/1612.02336). Role: training/scaling complexity of NTMs; Level C/limited scope.
- Baumgartner et al., [*Disentangling Dynamical Systems: Causal Representation Learning Meets Local Sparse Attention*](https://arxiv.org/abs/2603.14483). Role: modern refinement showing identifiability depends on structural conditions; Level C, preprint.

### Update 8 — July 15, 2026: Adversarial Review, Part II — H7–H13, P*, and R1–R5

#### 8.1. Critique of H7: "Episodes, Rules, and Hypotheses Must Be Separate Memory Types"

**Hidden Ontology:** The distinction between "fact," "rule," and "hypothesis" shifts with language, tasks, and description levels. A log entry `sensor = 20°C at 14:03` is an episode under one view, a model parameter under another, and evidence for a hypothesis under a third. Environments don't hand out correct tags.

**Risk of False Discretization:** Rigid typing harms continuous, probabilistic, and distributed representations. Counterexample: dynamic systems where useful memory is a posterior over parameters, not "fact/rule" cells.

**Alternative Explanation:** Typed memory advantages stem from manual supervision/metadata injection rather than form. Unified probabilistic memory with strong retrieval and uncertainty matches outcomes.

**Corrected H7':** Memory types are a useful *engineering interface* in known domains; their status as fundamental primitives for autonomous general systems is unproven.

**Status:** Downgraded from strong candidate to high engineering utility / low fundamental confidence.

#### 8.2. Critique of H8: "Self-Extending Typed Action Language"

**Three Fundamental Problems:**
1. Program/macro search combinatorial blowup; general language synthesis and non-trivial property verification are undecidable. Bounded DSLs make fragments decidable, but narrow universality.
2. Types guarantee syntax and safety invariants, not semantic utility. Macros can be type-safe and pass local tests while implementing flawed abstractions.
3. Self-expansion introduces attack vectors and unbounded growth: malicious, false, or redundant macros pollute trusted libraries.

**Counterexamples:**
- Two macros match observed examples but diverge on rare inputs; no finite test set yields general proofs in Turing-complete languages;
- Environment rules shift: optimal macros stay type-safe while becoming harmful;
- Analog control tasks suffer from discrete DSL encoding overhead.

**Corrected H8':** Expandable libraries are admissible only as sandboxed, versioned systems within languages featuring resource caps and contracts. They must not be viewed as automatic concept-discovery mechanisms.

**Status:** Prior open version rejected; restricted version remains viable for applied domains.

#### 8.3. Critique of H9: "Factorized Causal State as Entity Graphs"

**Unproven World Assumption:** Worlds resist clean factorization into persistent objects with discrete identities. Fluids, fields, social fabrics, linguistic semantics, distributed computing, and quantum/statistical systems resist simple object ontology.

**Identifiability:** Object-centric representations are provably recoverable only under compositionality, irreducibility, and decoder constraints. Slot decomposition does not guarantee true objects.

**System Cost:** Dynamic graphs demand entity resolution, identity tracking, relations, garbage collection, probabilistic matching, and graph inference. This can exceed dense-state costs on high-frequency sensor tasks.

**Alternatives:** Implicit neural fields, symmetry/geometric representations, factor graphs, programs, and end-to-end latent states fit alternate regimes.

**Corrected H9':** Object and graph representations are useful inductive biases for scenes with stable compositional entities, but should be switchable/adaptive rather than serving as universal internal currency.

**Status:** Sharply downgraded. Prior graph emphasis recognized as unjustified.

#### 8.4. Critique of H10: "MDL Macro Consolidation Compresses Competence"

**Primary Logical Flaw:** Short descriptions do not equal true, causal, or transferable explanations. MDL depends on coding languages and priors. Identical observations shrink or expand based on primitive choices. MDL cannot arbitrate meaning independently.

**Computational Issue:** Searching for minimal programs is uncomputable/undecidable generally; limited search remains combinatorial. DreamCoder demonstrates constrained domain utility, not a general solution.

**Generalization Issues:**
- Speculative short rules overfit finite samples;
- Macros compress known tasks without improving novel ones if repeatability is superficial;
- "Savings" can derive from convenient DSL choices;
- Retaining original episodes, tests, anti-examples, and versions destroys claimed compactness.

**Corrected H10':** MDL is a rational regularization against library bloat and an abstraction-selection criterion; it must pair with hidden intervention/OOD tests and accounting for coding languages. It is not a truth-discovery mechanism.

**Status:** Substantially downgraded. Remains a practical technique for restricted program induction, not a core line.

#### 8.5. Critique of H11: "Verifier-Directed Learning Replaces Memory with Computation"

**Ignored Costs:** Verification is rarely cheaper than discovery. Proof verification is polynomial relative to proof size, but proof searches are exponential; partially observed planning has high computational complexity. Shifting knowledge to computation bloats time and energy.

**Goodhart Effect:** Models optimize verifiable proxies rather than intents. Unit tests, simulators, and rewards harbor gaps. Complete verifiers for arbitrary programs and semantic properties are impossible (Rice's theorem boundaries).

**Counterexamples:** Medical advice, research hypotheses, political policy, and social action lack automated verifiers. Forcing verification either collapses to human priors or false confidence.

**Corrected H11':** Verifier-directed learning shines where specifications cover critical properties and verification beats search. Outside such domains, it is merely one feedback source among many.

**Status:** Narrowly viable; prior sweeping ambitions rejected.

#### 8.6. Critique of H12: "Contractible Internal Representations"

**Identifiability and Specification Regress:** Identical observation contracts admit multiple internal encodings. Verifying latent semantic correctness requires specifying target variables—shifting problems to contracts. Contracts themselves can be incomplete, stale, or contradictory.

**Cost:** Reversible states, tracking provenance, counterfactual testing, and uncertainty metadata demand memory, training, and compute. They compel models to retain useless details, degrading generalization.

**Counterexample:** Successful chess policies retain useful latents uninterpretable as human concepts; forcing board reconstructions per step harms efficiency without boosting play.

**Corrected H12':** Verifiable contracts are useful only at high-risk boundaries: actions, external memory, tools, and critical states. Demanding them for all latents is unjustified.

**Status:** Downgraded to a safety/engineering mechanism, not an representational principle.

#### 8.7. Critique of H13: "Memory Value Governed by Counterfactual Utility"

**Impractical Optimality:** Value of information depends on unknown future distributions, future policies, and hidden states. Exact POMDP evaluation is computationally intractable, making VOI optimization an unfulfilled target.

**Self-Reference Problem:** Write utility depends on future writes and built libraries. Local evaluations miss rare facts acting as future theoretical keys.

**Counterexamples:**
- Seemingly useless observations become vital post-task-shift;
- Adversarial environments manipulate "informativeness" signals to force distractor storage;
- Stationary tasks favor recency/retrieval over expensive valuation.

**Corrected H13':** Future utility estimation is a normative guide, not a working mechanism. Cheap verifiable approximations and regret analyses against simple heuristics are required.

**Status:** Sharply downgraded; a research framing, not a candidate mechanism.

#### 8.8. Critique of P*: "Two-Speed Consolidation + Abstraction Economics"

P* lacks independent novelty. It glues H7, H10, H11, H12, and H13, inheriting all their vulnerabilities: typed ontologies, MDL language dependence, verifier complexity, unidentifiable contracts, and intractable valuations.

**Danger Scenario:** Systems rapidly consolidate early false regularities into procedural libraries. Libraries then guide retrieval, planning, and tests, creating self-confirming loops. Such systems look confident and compact until failing upon environmental shifts.

**Corrected P*':** If pursued, consolidation must be reversible, slow, competitive across representations, and evaluated strictly on unrevealed generators. Absent proof, P* is a research program label, not an architectural principle.

**Status:** Downgraded from top synthetic line to high-risk integration hypothesis.

#### 8.9. Critique of R1–R5 and Decision Gates

1. **Toy Ontology Risk:** R1–R4 world generators preset what facts, rules, objects, and interventions mean. Models merely master hidden grammars; results cannot be termed spontaneous representation discovery.
2. **Resource Accounting Limits:** Parameter bits, library source code, compilers, indices, datasets, hardware kernels, search, and environments resist reduction to single numbers. Accounting remains mandatory, but affects conclusions.
3. **Unequal Baselines:** Single weak SSM/RAG/Transformer setups fail to invalidate classes. Preregistered robust baselines and tuning budgets are required.
4. **Rigid Gates:** Missing component advantages in R1 don't rule out synergy; conversely, invoking "synergy" makes hypotheses unfalsifiable. Fix: set statistical effect floors, budget caps, and stop rules.
5. **Undefined Pareto Improvements:** Maximizing all metrics simultaneously is impossible without profile specifications (edge offline, server batch, realtime agent, scientific solver).

**Status of R1–R5:** Useful methodological drafts requiring preregistration, randomized seeds, independent generators, and external replication prior to guaranteeing falsification.

#### 8.10. Updated Dead-End Risk Registry

| Line | Dead-End Risk | Reason |
|---|---:|---|
| H0' finite-state information bound | Low | Narrow valid statement, low design guidance |
| H1' role separation | Medium | Often useful, easily masks external complexity |
| H2' addressable memory | Medium-high | Addressing and bandwidth scaling bottlenecks |
| H3' recursive/refinement compute | Medium | Useful on algorithms, uncertain elsewhere |
| H4'/H11' verifier learning | Medium-high | Strong only under clean specs |
| H5' conditional compute | Medium | Real engineering value, not a general compactness path |
| H6'/H9' causal/object state | High | Strong assumptions, identifiability, domain limits |
| H7' memory types | Medium-high | Useful UI, unproven fundamentals |
| H8' self-extending DSL | High | Search, safety, semantic undecidability |
| H10' MDL macro library | Medium-high | Useful regularization, compression ≠ truth |
| H12' representation contracts | Medium-high | Useful at boundaries, costly/unidentifiable internally |
| H13' value-of-information memory | High | Right target, presumes intractable POMDP planning |
| P*' integrated consolidation | High | Compounded risks, lacks independent mechanism |

#### 8.11. Sources for Adversarial Review II

- Brady et al., [*Provably Learning Object-Centric Representations*](https://arxiv.org/abs/2305.14229). Role: shows object representation identifiability demands explicit assumptions; Level A under theorem conditions.
- Dittadi et al., [*Generalization and Robustness Implications in Object-Centric Learning*](https://arxiv.org/abs/2107.00637). Role: empirical robustness limits of object-centric models; Level B.
- Ellis et al., [*DreamCoder*](https://arxiv.org/abs/2006.08381). Role: constrained library learning precedent; Level B.
- Madhusudan et al., [*Decidable Synthesis of Programs with Uninterpreted Functions*](https://pmc.ncbi.nlm.nih.gov/articles/PMC7363337/). Role: undecidability of general synthesis and boundary rules; Level A.
- Edinburgh RL course, [*Planning: A Few Classic POMDP Results*](https://opencourse.inf.ed.ac.uk/sites/default/files/https/opencourse.inf.ed.ac.uk/rl/2025/rl13beyondmarkov_1.pdf). Role: computational complexity of finite-horizon POMDP planning; Level A textbook exposition.

### Update 9 — July 15, 2026: Adversarial Review, Part III — Fundamentals vs. Engineering and Fair Bypasses

#### 9.1. Constraints Approaching Fundamentality

| Constraint | Exact Domain of Action | What It Does NOT Mean |
|---|---|---|
| Finite physical state information | Cannot reliably distinguish/recover more independent info than physical states/channels allow. | Sets no parameter count for intelligence; bars no algorithmic compression. |
| Finite bandwidth | Data, memory, sensors, and modules must exchange info; accuracy/speed/energy trade off. | Doesn't dictate specific GPU interconnects or KV cache optimizations. |
| Computability | No general algorithm resolves all non-trivial semantic properties of arbitrary programs; undecidability holds. | Doesn't render practical bounded languages, tests, and proof-checkers useless. |
| Computational complexity | Some search/planning classes require high worst-case resources. | Doesn't bar fast answers on real task distributions or heuristics. |
| Statistical uncertainty / No-Free-Lunch | Zero universally optimal learning algorithms without distribution assumptions. | Doesn't bar strong priors, active learning, or world structures. |
| Information thermodynamics | At finite temps, irreversible erasure has lower entropic bounds; reliable physical states require resources. | Doesn't fix MAC operation energies or ban reversible/analog approaches. |

**Self-Correction:** The journal previously conflated the first three items with neural network properties. Erroneous. Fundamental constraints demand paying *somewhere*, but don't dictate paying via Transformer parameters or vector DBs.

#### 9.2. Constraints Mistaken for Fundamentals

1. **Quadratic self-attention and linear KV caches:** Artifacts of specific attention graphs and autoregressive inference, not intelligence limits. Local/sparse schemes, recurrence, new memory fabrics, hardware co-design, and alternative execution orders alter them.
2. **FP16/BF16 matrices and von Neumann bottlenecks:** Properties of current digital hardware. Compute-in-memory, analog, photonic, 3D memory, and sparse kernels shift energy/latency profiles.
3. **Power-law scaling:** Empirical relations tied to chosen models, data, losses, and training regimes; distribution or objective shifts alter coefficients and regimes. They are not laws stating intelligence must cost $N$ parameters.
4. **End-to-end differentiability/SGD:** Dominant engineering practice, not theorems proving all useful representations must be learned this way. Search, evolution, Bayesian inference, program synthesis, local plasticity, and hybrids remain valid.
5. **Next-token prediction and chains-of-thought:** Useful interfaces/lenses, not definitions of thought. They can be insufficient, redundant, or suboptimal.
6. **Parameters as the sole capacity:** False. Programs, states, data, retrievers, and physical dynamics require accounting. Conversely, ignoring their costs is invalid.

#### 9.3. Fair Bypasses of Engineering Bottlenecks and Their Limits

**A. Analog / Compute-in-Memory / Photonic Hardware:** Lowers energy and accelerates matrix math via physical superposition. Modern analog NN results show promise, but noise, calibration, data conversion, dynamic range, storage, and precision persist. This changes constants and economic limits, bypassing neither information limits nor task complexity.

**B. Reversible Computing:** Logically reversible operations curb irreversible erasure costs. Interactive systems still require memory clearing, I/O, error correction, and finite states. Reversibility promises energy trade-offs, not free thought.

**C. Probabilistic / Thermodynamic Computing:** Physical noise aids sampling and generative/inference tasks. Costs include stochastic errors, distribution management, and digital/symbolic correction where guarantees matter. Expands Pareto frontiers, doesn't yield free solvers.

**D. Quantum Computing:** Quantum algorithms alter complexity for specific tasks. They offer no general exponential speedups, losslessly compress no random facts, and demand error correction. Referencing "quantum" as a universal bypass for H0' is prohibited.

**E. Embodiment and Active Learning:** Choosing observations slashes sample complexity in structured environments and relieves identifiability issues. Actions carry costs, risks, latency, and don't make passive data free.

**F. Algorithm Discovery, Program Synthesis, and Evolution:** Finds short programs unfindable via SGD. Bypasses *optimization* barriers, not worst-case complexity or finite-sample generalization limits.

**G. Multi-Agent / Social Systems:** Leverages parallelism, hypothesis variety, and division of labor. Shared memory, communication, and coordination scale; leads to effective systems, not compact single cores.

#### 9.4. Modern AI Assumptions Subject to Error

Unverified propositions requiring testing rather than blind rejection:

1. **"More pretraining data and parameters drive general intelligence."** Missing algorithmic priors might drastically improve sample efficiency. Counter-risk: such priors equal manual coding and resist transfer.
2. **"One universal dense latent beats explicit structures."** Modularity, programs, geometry, or local plasticity might yield better compositionality. Counter-risk: explicit structures fail to scale to messy worlds.
3. **"Store all skills in slow weights."** Dynamic memory and procedures might prove superior. Counter-risk: memory controllers become bloated models.
4. **"Language is a sufficient reasoning interface."** Environments, actions, sensors, and non-linguistic states may be mandatory. Counter-risk: embodiment adds hardware/data, not compactness.
5. **"External text CoTs are the best test-time compute use."** Latent refinement, search, execution, or parallel hypotheses may outperform them. Counter-risk: hidden reasoning resists control and debugging.
6. **"Hierarchies/objects should be hand-designed."** They might need adaptive emergence. Counter-risk: unguided emergence triggers identifiability failures.
7. **"Training and inference are distinct phases."** Fast weights/continual adaptation blur boundaries. Counter-risk: drift, poisoning, and forgetting.

#### 9.5. Falsifiers of Negative Ultra-Compactness Forecasts

Substantive results that would overturn negative expectations without violating math/physics:
- A discovered learnable prior systematically extracting short mechanisms across hidden generators and transferring them, with fully disclosed priors and data;
- A compact reusable operator robustly extrapolating algorithmic tasks *while* retaining broad linguistic/perceptual competence without hidden external models;
- A memory controller yielding reliable addressing, novel task induction, and rule shifts at lower total cost than hybrid baselines;
- Hardware platforms dropping target compute costs so ultra-compactness hits energy/latency targets despite identical logical ops;
- Active-learning systems documenting sample requirements cuts via discriminating experiments while preserving safety.

Each demands new generators, independent replication, and resource reporting. None implies AGI by default.

#### 9.6. Correction of Research Objectives

"Ultra-compact universal model with extremely high intelligence" merges at least four independent goals: small weights, low energy, low latency, and broad transfer. They conflict. A fairer program seeks **Pareto system sets for specific deployment profiles**, not a magic point.

This is no surrender to scaling, but defense against unfalsifiable promises: outperforming on one metric while offloading costs to data centers, libraries, or time fails the strict definition of ultra-compactness.

#### 9.7. Sources for Adversarial Review III

- Kaplan et al., [*Scaling Laws for Neural Language Models*](https://arxiv.org/abs/2001.08361), and Bahri et al., [*Explaining Neural Scaling Laws*](https://arxiv.org/abs/2102.06701). Role: scaling laws are empirical/model-dependent, not fundamental intelligence lower bounds.
- [*60 years of Landauer’s principle*](https://doi.org/10.1038/s42254-021-00400-8). Role: energy bounds of irreversible erasure; not specific neural net cost evaluations.
- Zhao et al., [*A blueprint for precise and fault-tolerant analog neural networks*](https://www.nature.com/articles/s41467-024-49324-8). Role: engineering-mutable precision/energy trade-offs in analog NN.
- Liu et al., [*Sparsity in Deep Learning*](https://www.jmlr.org/papers/v22/21-0366.html). Role: sparse efficiency depends on training and hardware execution.

### Update 10 — July 15, 2026: Adversarial Review Synthesis, Null Hypothesis, and Corrected Continuation Point

#### 10.1. The Missing Null Hypothesis

**N0 — Null Hypothesis:** Currently, no single architectural mechanism creates an ultra-compact system matching wide universal competence far exceeding strong baselines under equal *total* resources. Observed gains will likely prove:
- Domain-specific;
- Resource trade-offs;
- Dependent on external priors, data, tools, or hardware;
- Fragile under stricter OOD/intervention tests.

N0 bars treating neat compositions of memory, recursion, DSLs, and verifiers as breakthroughs without comparative proof.

#### 10.2. Hypothesis Registry Post-Adversarial Review

| Hypothesis | Final Status | Surviving Elements | Rejected Elements |
|---|---|---|---|
| H0 → H0' | Narrow hard constraint | Finite-state exact recall of independent info | General intelligence lower bound inference |
| H1 → H1' | Conditional heuristic | Useful role splits given clean APIs/tools | Small core intelligence amplification |
| H2 → H2' | Open candidate, high risk | External data storage needs | "Addressable memory is the key path" |
| H3 → H3' | Open candidate, medium risk | Iterative compute for recursive algorithms | Need for loops/traces for all reasoning |
| H4 → H4' | Narrowly viable | Verifier signal in covered domains | Superiority over text/broad learning globally |
| H5 → H5' | Neutrally viable | Conditional compute alters capacity/compute trade | "Creates no competence" / free compactness |
| H6 → H6' | Low general confidence | Causal/object priors for interventions | World models needed for all universality |
| H7' | Engineering, not fundamental | Typed stores in known workflows | Natural universal memory trio |
| H8' | Restricted DSLs only | Sandboxed typed libraries in closed domains | Open self-expansion as discovery solution |
| H9' | Domain-specific prior | Objects for stable compositional scenes | Entity graphs as universal internal currency |
| H10' | Regularization / library technique | MDL against bloat at fixed languages | MDL as truth/causality criterion |
| H11' | Narrowly viable | Search with cheap strict verification | Shifting memory to computation universally |
| H12' | Safety interface | Contracts at external boundaries | Total internal latent contractibility |
| H13' | Normative framework | Value of information as ideal | Computable general memory allocation mechanism |
| P*' | High-risk integration | Reversible consolidation as a test target | Status as leading fundamental line |

**Implication:** Post-criticism, zero hypotheses retain status as probable fundamental solutions. Several restricted mechanisms remain with distinct regimes.

#### 10.3. Research Method Audit

1. **Zero own experiments:** Findings remain preliminary. Thought experiments expose flaws, not measure effects.
2. **Missing systematic literature reviews:** Targeted searches miss negative replications and alternative options.
3. **Preprint reliance:** Results lack stability; even peer-reviewed outcomes remain task- and hardware-bound.
4. **Abstract reliance:** Risks misinterpreting assumptions, metrics, and ablations.
5. **Level mixing:** Early updates conflated theorems, empirical results, and design proposals.
6. **Confirmation bias:** Prior formulations forged illusions of unified architectures.
7. **Undefined goals:** "Universality" and "ultra-compactness" lack operational definitions.

#### 10.4. Corrected Next Phase Program

Instead of R1 (typed memory), initiate **R0 — Exploration on Discriminating Worlds**.

**R0.1 — Preregistered Hypotheses:** Max 3 competing accounts (N0 baseline, M retrieval limits, C structured generator limits).
**R0.2 — Non-Anthropomorphic Generators:** Four families (algorithmic, random, continuous non-object, non-stationary).
**R0.3 — Strict Baselines & Resource Counts:** Fixed implementations, seeds, tuning budgets, persistent storage, peak RAM, latency, energy proxies, interactions, and code budgets.
**R0.4 — Double Transfer Checks:** Hide test instances, augmentation rules, and distribution shifts.
**R0.5 — Explicit Stop Rules:** If mechanisms fail predetermined effects across two families under full accounting, accept N0 provisionally.

#### 10.5. Rational Lines Without Hype

- Applied systems: clean model/memory/tool separation, policy access control, verifiers, hardware-aware compression.
- Architecture science: comparing recursive/shared-weight compute against dense baselines on hidden algorithmic generators.
- Representation learning: conditions under which object/causal structures are identifiable and useful.
- Program induction: bounded libraries with audited priors, languages, and tests.
- Hardware: analog, in-memory, and reversible tech for energy/latency gains, not intelligence-per-bit proofs.

#### 10.6. New Critical Questions

1. How to define testable "universality" cleanly?
2. How to quantify "injected external knowledge" in architectural priors?
3. How to normalize system costs across hardware without FLOP debates?
4. How to test abstraction discovery absent human ontologies?
5. How to build online learning protocols avoiding poisoning loops?

#### 10.7. Self-Critique Save Point

Theoretical cycle concluded sans architectures. Next allowed task: **R0 (falsifying world design and preregistered protocols)**, avoiding premature P* integrations.

## 5. Registry of Open Questions

1. What share of useful universality offloads from weights without external dependency?
2. Does a compact, learnable, hardware-efficient long-term state representation beat KV caches and RAG in transfer?
3. How to distinguish found compact algorithms from data contamination and search?
4. Can architectures learn new rules via short-lived state modifications without destroying old skills?
5. What is the active computation lower bound for reliable compositional reasoning?

## 6. Sources

Populated strictly with utilized sources, notation of evidence levels, and roles.

---

## Blind Spots of the Research

### Update 11 — Auditing Missing Questions, Not Past Errors

**Status:** This section evaluates past assumptions as an external observer. The question is: what classes of explanation and definitions were excluded from view?

### 11.1. Largest Blind Spot: Unit of Analysis

The journal treated systems as **single static neural models**. Five alternatives were overlooked:
1. **Developmental systems:** Small initial specifications yielding mature structures over time via growth, learning, and pruning;
2. **Agent-environment loops:** Competence emerging from active observation, action, and physical artifact manipulation;
3. **Collective systems:** Knowledge distributed across populations, languages, texts, and tools (cumulative culture);
4. **Processes over instances:** Small persistent states backed by heavy search, compilation, or test-time learning;
5. **Embodied physical calculators:** Physics, sensors, and material dynamics sharing compute loads.

### 11.2. Blind Spot Mapping Across Sections

- **§0 (Definitions):** Ignored development, collective culture, and active-loop units.
- **§1–2 (H0/Memory):** Assumed raw storage entropy instead of task-relevant rate-distortion.
- **§3 (Taxonomy):** Presupposed static structural modules instead of dynamic self-organization.
- **§4 (Causality/MDL):** Reduced action to internal graphs rather than active inference loops.
- **§5–6 (R0/R5):** Treated training distributions as external constants rather than co-evolving environments.

### 11.3. Information Theory: Bits vs. Meaning

#### A. Rate-Distortion & Sufficient Statistics
E1 evaluated lossless recall. Agents require task-relevant state representation (Information Bottleneck) preserving action-critical variables.

#### B. Synergy & Communication Complexity
Distributed multi-module systems face bandwidth bottlenecks across perception, memory, and planning.

#### C. Algorithmic Information Theory
Kolmogorov complexity is uncomputable, and time-bounded complexity dictates that short programs can require deep execution times.

### 11.4. Computation & Complexity Limits

Time-space-data trade-offs, average-case complexity, and sample complexity under active interaction were under-analyzed.

### 11.5. Causality, Active Inference, and Predictive Coding

Agents shape their own data streams. Active inference unifies perception, memory, and action into expected free energy minimization loops.

### 11.6. Dynamical Systems & Development

Dynamics, attractors, and phase synchronization can substitute for digital matrix storage.

### 11.7. Cognitive Science & Neuroscience

Complementary Learning Systems (CLS), replay, and schema consolidation provide mechanistic targets beyond simple memory partitions.

### 11.8. Open-Endedness & Collective Intelligence

Populations with cumulative culture break individual scaling limits.

### 11.9. Physics of Computation

Landauer limits, data movement, 3D wiring, and non-volatile substrates govern practical energy envelopes.

### 11.10. Re-evaluating Constraints
- Dense networks, backpropagation, and execution speed profiles are engineering constraints, not laws.

### 11.11. Revised Research Framework

Four parallel units of analysis: mature models, active agents, developmental programs, and cultural systems.

### 11.12. Commitments B0–B8

Establishing dictionary standards, rate-distortion metrics, algorithmic worlds, active loops, developmental checks, continual learning, external scaffolds, and physical accounting.

### 11.13. Anticipated Dead-Ends
Information bottlenecks, AIT search limits, active inference pathologies, and developmental over-parameterization risks.

### 11.14. New Open Questions
Defining distortion metrics, bounding induction, balancing active intervention risks, and measuring cultural error correction.

---

## Counterfactual Audit: "Thirty Years Later, Most of the Journal Was Wrong"

### Update 12 — Dismantling Core Inferences via Competing Theories

#### 12.1. Systemic Alternative Theory: T-ICD (Interactive Computational Distillation)
Competence stems from information sequences, curricula, and counterfactual feedback rather than static parameters.

#### 12.2–12.3. Dismantling H0'–H13'
Critique of all prior hypotheses reveals hidden dependencies on human annotation, proxy benchmarks, and unexamined design priors.

#### 12.4–12.6. Dismantling Integration and Revising Assumptions
Re-evaluating N0, R0, and analytical units.

---

## Update 13 — Universal Transformer Mini-Experiment Probe

### 13.1. What Was Tested
Associative recall across 4 (ID) to 8 (OOD) KV pairs comparing Standard-2, UT-2, UT-8, and Standard-8 models.

### 13.2. Empirical Results
- **Standard-2 (1.6M params):** 0.633 OOD exact match;
- **UT-2 (827k params):** 0.506 OOD exact match;
- **UT-8 (828k params):** 0.882 OOD exact match;
- **Standard-8 (6.3M params):** 0.874 OOD exact match.

UT-8 reaches Standard-8 performance using 13% of the parameter count, but matches its computational cost (6.35M MACs/token vs 1.6M for Standard-2).

### 13.3–13.9. Methodological Caveats and Next Steps
Results validate parameter-storage compression via weight sharing, but show no total computation savings or proof of general algorithmic discovery. Requires scaling sweeps, cross-rule transfer tests, and statistical rigour across more seeds.

---

## Update 14 — Engineering Prototype for 25–100M and Kaggle TPU-8

### 14.1–14.6. Implementation Outline
Packaging shared-weight causal language models (`ut_30m`, `ut_55m`, `ut_90m`) for JAX/Flax execution across Kaggle TPU-8 hardware configurations, paired with streaming dataset pre-packing and training loops.

---

## Update 15 — Autonomous Kaggle Notebook

Consolidated single-file notebook (`kaggle_universal_tpu_all_in_one.ipynb`) encapsulating setup, configs, data pipelines, shared-weight architectures, and training execution blocks.

---

## Update 16 — New JAX Compatibility Fix

Addressed breaking changes in modern JAX (`jax.device_put_replicated` deprecated) by integrating explicit `Mesh`, `NamedSharding`, and `PartitionSpec` logic prior to `pmap` calls across TPU cores.