# Introduction To Algebraic Evaluation

Algebraic evaluation is logic of evaluating noisy agents on unlabeled data.
Starting from simple algebraic equations that connect the statistics of correctness of these agents to their actual responses in a given test, a set of algebraic
postulates - universally true for any test results - can be constructed.
This treats the evaluation of human or machine agents as an inverse problem where we must go from statistics of their observed agreements **and** disagreements to infering their statitistic of correctness given those observations.

By constructing, these algebraic postulates do not contain any probability theory. Otherwise, they would not be postulates. Any probability theory would require that we specify hyperparameters for it. The theorems and conclusions using any model of probability one uses to evaluate agents would, by construction, be invalid when the assumption of the theory applying to the domain fails - the OOD problem.

The algebraic postulates, and their associated logic of consistency, we will be discussing here can be encanpsulated by the acronym - **NTQR**.
1. N: the number of classifiers in the group being tested.
2. T: the number of tests those classifiers took.
3. Q: the number of questions each of those tests contained.
4. R: the number of responses that were possible in each of the questions.

The easiest case to consider is the one of evaluating noisy binary classifiers. If we are going to construct postulates for the evaluation of an ensemble of classifiers, we must also confine ourselves to "black-box" methods. Any use of internals related to how the classifiers made their decisions would have the OOD problem of the type of agent involved in the evaluation. For example, methods used to evaluate neural networks could not be used to evaluate a mix of humans and neural networks.

Evaluation is the forgotten twin of learning. AI researchers and their work
currently focuses on just one side of the learning process - training. As such,
they have missed many of the benefits of considering the theory of evaluation.
In particular, the notion that there exists a logic of consistency whenever we are evaluating ensembles of noisy decisions makers on any finite test.

There have been tentative understandings of this logic in the work of some ML researchers. Most notably the agreement equations of Platanios. But the full scope of the mathematics of treating evaluation as a data streaming problem with its own logic is not even understood to exist. This repository means to correct that by providing code and instruction on the mathematics and engineering of using NTQR logic to evaluate noisy human or machine decision makers.

## Why purely algebraic evaluation?

Because it will make us safer. The current theoretical state of AI is one
that views all tasks as solvable only by *training* methods. The 2022 NeurIPS
ML Safety Workshop is an exemplar of this exclusive theoretical focus on just
one side of learning. Evaluation and its simplicity can help make us safer.
Partly because the mathematics of evaluation is simpler than that of training.
But also from that common sense point of view we all have about safety - the
more ways you have of looking at something, the safer you are.

A safety analogy in another technological realm may clarify why this
focus on just one side of the learning problem is needlesly narrow.
Consider the humble role of thermometers in cars. Temperature thermometers
are not that smart. They just measure and output a single number. But they are
useful because they can be hooked to a car's computer and warn us that our
engine is overheating.

Where are the evaluation thermometers that can do the same for measuring the
quality of the decisions made by noisy judges? What is special about
intelligence that would prevent us from doing this? Nothing. The mathematical
theorem that is central to this work shows that there is a way around this
misconception.

## You can grade three error-indepedent binary classifiers exactly using just algebra

The core of the mathematics of these assertions is the simplest algebraic
evaluator possible - that constructed by processing the decisions of judges
that are error independent in the sample. This simple formulation is enough to
confront THE fundamental problem in any monitoring of intelligent agents - if
they are smarter than us, if we are too lazy to do the work ourselves, if we
ourselves do not know the correct answers to the tests we give them, how do
we stay safe?


## The fallacy of *only-intelligent* evaluation

Since this repository will contain code that carries out purely algebraic
evaluation of binary classifiers, it cannot be the case that the only way
we can evaluate intelligent agents is via the use of ever more
intelligent ones.

<p>
<figure>
    <img src="img/OnlyIntelligentEvaluation.png"
         alt="The master/disciple evaluation paradigm."
         height="400">
    <figcaption>
    Figure Caption: <b>The fallacy of "only intelligent evaluation"</b>
    </figcaption>
</figure>
</p>

### The existential AI risk for those that believe in the fallacy

If *only-intelligent* evaluation is required, then we truly face a risky
AI future. We would be condemmed to a technological arms race with ourselves.
Faced with having to monitor AI agents on data that is unlabeled - the hard
task of evaluation upon system deployment - we would have to invent succesively
smarter AI agents to monitor stupider ones.

This is a pervese race of ``turtles all the way up''. We would be forced
to build ever smarter agents that could very well turn malicious or otherwise
threaten us. Algebraic evaluation is the way out of this trap we have made for
ourselves.

<p>
<figure>
    <img src="img/AlgebraicEvaluation.png"
         alt="The self-evaluation paradigm."
         height="400">
    <figcaption>
    Figure Caption: <b>Bypassing the master/slave relationship of evaluation to
    make us safer.</b>
    </figcaption>
</figure>
</p>

## Guide to the repository

- [**AlgebraicEvaluation.py**](./AlgebraicEvaluation.py):
This Python code contains basic utilities showing
how you can turn the counts of voting patterns by binary classifiers into an
algebraic formalism for carrying out perfect evaluation of binary classifiers
**IF** they are error independent in the sample. The code details all the sample
statistics that are sufficient to write down an exact representation of the
algebraic ideal associated with evaluation (the evaluation ideal).

- [**EvaluationIdealAndVarietyErrorIndependentTrio.nb**](./EvaluationIdealAndVarietyErorrIndependentTrio.nb):
The mathematics of algebraic evaluation is algebraic geometry. Since you are
estimating sample statistics, you get to work in a finite dimensional space
where all parameters are known. You can build exact polynomial representations
of any evaluation you care to set-up for noisy judges on unlabeled data. This
notebook shows how to do the simplest algebraic evaluation possible -
the tests where the noisy judges where independent in their errors. The almost
visceral reactions that critics of algebraic evaluation have to this "spherical
cow" in Evaluation Land is telling of the intuition that years of working in
Training Land has built up in them. All of them have most likely uttered the
phrase "consider an iid sample". In Evaluation Land we get to say "consider
noisy judges error independent on the sample". This simplest and purest of
algebraic evaluators - combining the decisions from error independent judges -
can be used to understand what algebraic evaluation can and cannot do. The
mathematics here is that of algebraic geometry. This may seem complex but if you
just read the text and enjoy the jumble of algebra, you can get a taste of what
can be accomplished by doing evaluation in a purely algebraic manner.

- [**TheForgottenRadicalEmpiricismOfRegnault.md**](./TheForgottenRadicalEmpiricismOfRegnault.md):
The 19th century French physicist, Henri Victor Regnault, is a forgotten philosopher of
science. I would contend a radical empiricist that understood that for evaluation of
experts we do not need to be smarter or aware of their mental states. Evaluation is
easy, expertise is hard. This essay talks about how Regnault thought about the precision
of thermometers. My claim is that whether thermometers or brains, we can evaluate both
algebraically. The algebra in this repository details how.

- [**SimplestExampleOfEvaluationWithAlgebraicGeometry.md**](./SimplestExampleOfEvaluationWithAlgebraicGeometry.md):
Becoming familiar with algebraic geometry can be difficult.
This essay goes thru the simplest ensemble possible,
the trivial ensemble of $n=1$. Algebraic geometry may seem like overkill for
such a trivial ensemble but we hope the reader will use it as a bridge from
their familiarity with evaluating binary classifiers to the unfamiliar topic
of the geometry of polynomial ideals.
