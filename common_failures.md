# Most common failures in my digitalization projects

If you are familiar with the situation of [Platform Material Digital](https://www.material-digital.de) or [NFDI Matwerk](https://nfdi-matwerk.de), you are certainly aware of the fact that there are a lot more failures than success stories. Here I would like to document  difficulties I encountered.

Before we start, keep in mind: The keys to success are more or less the same as in other projects, these include: clear goals, effective planning, strong communication, and diligent monitoring. So I do not talk about these points in this document.

## Reason I: Too complex or too simple workflow

This is by far the biggest problem, which is shared by most of the software tools. This is caused by the fact that for any workflow, the underlying model is so flexible that you can in principle solve a lot more problems, so that you would think it does not make much sense to reduce it into a well-defined single-task workflow. Some typical underlying models (obviously not exhaustive) are:

- Schrödinger Equation
- Newton's equation of motion
- Poisson/diffusion equation
- Ginzburg-Landau equation

Now the problem is, many projects go into the following two opposite directions

- Towards a workflow that was meant to be an example, and ended up being able to do only one thing
- Towards a workflow that requires too many parameters/components for anyone to understand how to use it

So basically in the one case the workflow is too rigid, and in the other case it's too flexible. Since this is a document to tell failures, I will not talk about the solutions in detail (maybe you can refer to [How to write workflows](how_to_write_workflows.md)), but here's a short summary of what you should do:

- Separate workflows according to scientific goals
  - Create components that can be reused across different workflows
- Make a clear hiearchy for the input and output data
  - All parameters should be available, but the more technical and esoteric a parameter is, the depper in the hierarchy/more hidden it should be

## Reason II: Excessive purism

When Conda came around, their success was often questioned, because the tools would run more efficiently with a machine-specific compilation than with a standard compilation as offered by Conda. Today, I don't think anyone asks the same question. However, a similar thing basically still happens with our field, as very often experts refuse to give default input values or automatic setting of input values. Then you are left with a workflow tool which does nothing, because you cannot run it without an expert. If this happens, you can ask them this question: There are two coffee vending machines in front of you. One gives you coffee only if you set all the parameters (water temperature, grinding speed, granularity, water pressure, amount of coffee grounds, amount of water), and the other one gives you coffee without setting anything, but you can also change parameters if you want. Which one would you choose?

And finally, remember that there is always inherent uncertainty in any workflow. In experimental workflows, it's the input (uncertainty of the sample), and in simulation workflows, it's the output (uncertainty of the model). So while there are myriads of ways to make parameters reliable (cf. [this document](how_to_write_workflows.md)), we will always have to live with some uncertainty. But that did not hinder us from making progress in science, so I guess we are just as fine.

## Reason III: "My case is special"

When you try to explain how other cases were handled, you very often hear this argument: "Yes, in their case it's easy, but our case is complicated, because ...", and what follows is the kind of banal problems that everyone faces. You can try to explain them why they are wrong, but also be ready to give up on this case, because when this argument is used, it's usually a bad signal.

This being said, there are a few cases where the argument is at least partially valid. The most common one is human in the loop, e.g. a graphical interface, required human input (usually because the software is commercial and there's no way to change it), or experimental workflow nodes. The other one, which is extremely uncommon these days, is the run-time compilation, which basically makes it impossible to be interoperable.

## Reason IV: Too many unfulfilled promises

However honest you are, you are still in the workflow community, where people oversell their software solutions. As a consequence, people take promises very cautiously, however real they actually are. I have experienced it multiple times, as I claimed their software tool can be turned into a workflow, and nothing happened, but they came aboard when I show them a real demonstration. So don't think they lack trust; it's just the reality of the community that they cannot take you at your word. In this case, it might be worth making a live demonstration instead of keeping talking.
