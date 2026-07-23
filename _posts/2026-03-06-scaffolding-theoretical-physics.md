---
layout: single
title: "How can we use AI systems to improve the discovery of truth?"
date: 2026-03-06
section: musings
published: true
---

The capability of current AI systems to generate sensible symbolic expressions (formulas, calculations, proofs, etc.) is approaching superhuman performance at a drastic pace. In light of these drastic developments, this note is an invitation to think about the future we face and how we can shape it by building frameworks that leverage these systems to improve our pursuit of knowledge and to contribute to the conversation and stimulate constructive exchange. 

In my perception, the current conversation is dominated by AI companies driving claims of autonomous solutions of open problems by their systems, thus generating the impression that "Science is solved in a year." Science, which I will now broadly consider to be any structured effort towards the pursuit of knowledge, deserves a more careful discussion.

To emphasize the need for this discussion, I want to demonstrate this with two recent examples. Last week, the formalization of the solution to the sphere packing problem in $8$ and $24$ dimensions was announced, a tremendous effort by Sidharth Hariharan and Maryna Viazovska together with Chris Birkbeck, Seewoo Lee, Gareth Ma, and Bhavik Mehta, which was then finished by Gauss, the formalization system of Math, Inc., in several weeks.[^1] Shortly afterwards OpenAI announced the extension to gravitons of the nonvanishing single-minus amplitude they had previously studied for gluons.[^2][^3]

Despite the controversy over whether these are important contributions to the respective fields, they demonstrate that current AI systems are able to perform intellectually very demanding labour semi-autonomously. Allowing this to happen as naturally as possible is, in my opinion, an important step towards letting these systems advance our work. Similar musings for mathematics were expressed in earlier work.[^4][^5]

The two examples use the AI system for somewhat different tasks. The first was the formalization of a known result. Humans prepared a blueprint specifying which theorems, lemmata, definitions, etc. had to be formalized and started the formalization process. The AI system could then expedite and complete the formalization based on the previous work. The second example is somewhat the opposite. Humans prepared a LaTeX version of their calculation and tasked the AI system to continue or translate the calculation to a new system. The output of the AI system was purely symbolic in nature and humans had to go and verify each step manually. Both interactions led to drastic improvement in the speed at which the project could be completed, but both of them are not necessarily ideal for theoretical science in practice.

It is the second case which demonstrates how one can use AI systems for open-ended exploration, whereas the first demonstrates how we can use the tools to scaffold and provide a framework in which the AI can perform the tasks at hand.

Thinking about how to allow such a harmonious collaboration between AI systems and humans is the problem I want to discuss in this post.

## Towards a scaffold

It seems to me that one can roughly divide the task of scientific exploration into three qualitatively different processes. What I want to do is share musings on how to use AI systems to improve these respective processes and what prerequisites such improvements demand.

I think the development of a complete scientific project can be divided into the following processes:

1. Establishing a knowledge base.
2. Identification of problems and their history.
3. Trial and error to solve the identified problems by any means necessary.

I do not want to claim that this is a good or unique division, just that these appear to be general features that seem qualitatively different and that more or less universally concern any scientific project.

### 1. Establishing a knowledge base

This describes the process of acquiring knowledge by reading the literature of the field one is interested in, learning the facts of the field and identifying questions that are either relevant to the field or can be solved with the tools of the field. The current situation we face is that scientific knowledge and the problems that the field considers important are scattered across millions of pages in mostly unstructured format. Learning a new topic without an expert supervisor is a hard task, because identifying relevant or connected literature at this stage works only by manually scanning the citations of each paper and finding the relevant statements. Finding and knowing about the connections between different facts existing in a given field (or between fields) requires extensive manual labour and is what essentially defines a "domain expert."

***How AI could help here:*** I envision two ways. First, I think that it should be possible to *somehow* organize what we know and make it accessible to structured queries. In the end, every paper establishes or tries to establish some facts, ideas, calculations, etc. I think we should think about a way to structure this knowledge, e.g. by breaking papers up into the different kinds of contributions they make, cross-referencing them, and describing how they relate to other papers. Given the capabilities of AI systems already to understand natural-language arguments often better than I do, I believe they could be instrumental in organizing the knowledge contained in papers into a structured database more or less autonomously. **Once such a framework exists and allows this kind of organization,** I *do not* expect that they can do this perfectly on the first try, but having our knowledge organized, albeit imperfectly, is already better than having to read through all papers manually, since this would allow us to acquire knowledge interactively.

I think that, in principle, one should be able to link the "claimed fact" in the database to its origin in a paper, so that scientists could verify the faithfulness of the representation. In the end, our understanding of scientific theories is deeply subjective (e.g., the physicality of the wavefunction in quantum mechanics) (excluding mathematics for now), and I think establishing a framework under which one could organize it into a somewhat accurate representation would be very helpful.

I do not even think that it must be very human-friendly to query, but it should be friendly for a machine to query, so that we can use the machines to explain scientific arguments as faithful to the current understanding as possible.

Two (probably too strong) examples of such endeavors are [mathlib](https://github.com/leanprover-community/mathlib4) and [the Stacks Project](https://stacks.math.columbia.edu/). The former is a formalization of a large body of mathematics, making its results machine-readable code; the latter is a large collection of structured facts that is, in principle, queryable. While most statements in physics are not on the level of "theorem"–"definition"–"proof," they still constitute statements of different quality. Finding a way to structure them would, in my opinion, be necessary to make human–AI interactions reliable, because (1) it establishes a somewhat organized basis of facts about which one can communicate, and (2) if one were to link each fact that arises from a calculation via an implemented version of the calculation (in some specific or several computer algebra systems or proof assistants), one would have a huge queryable library of standard algorithms to solve scientific problems that were already solved.

### 2. Identifying a problem

Any scientific project is concerned with the solution of one or several tasks. These problems were either raised in other work or identified during one's own work. However, for known problems, their history, as well as attempts to solve them, are again loosely scattered through the literature. By generating a structure as described in the previous section, one could bootstrap the process of identifying known problems, their history and interrelations. If one enters a new field, it is very hard to identify the edge of knowledge in the field. By allowing our knowledge base to be queryable, the threshold to contribute meaningfully would be lowered.

### 3. Solving a problem by any means necessary

This is the hardest part of science, but given the evidence from the recent work on gluon and graviton amplitudes, AI can be incredibly useful.[^2][^3] In particular, a lot of work goes into tedious symbolic manipulations, which one can *in principle* implement. The two current paradigms—fully text-based responses as in the gluon work and semi-autonomous formalization as in the sphere-packing result—do not seem like the correct framework for scientific exploration. Purely text-based responses are prone to subtle mistakes, whereas demanding formalization excludes many areas of theoretical physics that are not well-formulated enough to be amenable to it.

***How AI could help here:*** Most of the calculations physicists do in practice are either *symbolic* and thus amenable to computer-algebra systems or lead to a well-defined mathematical problem, *after* formal symbolic manipulation, and thus amenable to formalization or numerical exploration after the formal manipulation was performed. If we could leverage AI systems to perform both of these tasks reliably, this would lift a lot of work from us.

One use case I have in mind is calculations such as the determination of the effective action in Appendix A of a paper of mine with Dimitris Saraidaris.[^6] The underlying calculation is based on a path integral, which is formally hard to define, but all calculations are symbolic and based on standard symbolic rules of manipulation. It appears that current systems should be able to implement these types of calculations in a computer-algebra system. Similarly, the calculations done in the gluon work are primarily symbolic.[^2]

In particular, current systems should be able to choose which CAS is most suitable for a given type of calculation and then transform the results into forms usable for other systems and printable in LaTeX, etc. I envision that building a system that first suggests a scaffold for a computation and then *implements it* in a CAS would dramatically increase its reliability, as every step would be generated in the end by a mechanical process, not by stochastic generation of symbols. Building a system that can navigate different computer-algebra systems and interact with a human to receive tasks to solve would, in my opinion, be incredibly useful, as the often boring labour of sweeping through 50 individual examples of a problem could be solved autonomously, and we could focus on deciding what problems we want to solve or what ideas to explore.

## Acknowledgement

I thank Bartosz Naskręcki for a discussion that introduced me to the Stacks Project and motivated the preparation of this post. I thank Alexander Nietner and Tobias Osborne for discussions on this topic.

[^1]: [Math, Inc., "Completing the formal proof of higher-dimensional sphere packing"](https://www.math.inc/sphere-packing)
[^2]: [OpenAI, "GPT-5.2 derives a new result in theoretical physics"](https://openai.com/index/new-result-theoretical-physics/)
[^3]: [OpenAI, "Extending single-minus amplitudes to gravitons"](https://openai.com/index/extending-single-minus-amplitudes-to-gravitons/)
[^4]: [Bartosz Naskręcki and Ken Ono, "Mathematical discovery in the age of artificial intelligence"](https://www.nature.com/articles/s41567-025-03042-0)
[^5]: [Jeremy Avigad, "Mathematicians in the age of AI"](https://arxiv.org/abs/2603.03684)
[^6]: [Dimitris Saraidaris and Leo Shaposhnik, "Searching for emergent spacetime in spin glasses"](https://arxiv.org/abs/2510.20902)
