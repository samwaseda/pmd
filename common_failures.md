# Most Common Failures in My Digitalization Projects

If you are familiar with the situation of [Platform Material Digital](https://www.material-digital.de) or [NFDI MatWerk](https://nfdi-matwerk.de), you are certainly aware that there are far more failures than success stories. Here, I would like to document the difficulties I have encountered.

Before we start, keep in mind: the keys to success are more or less the same as in other projects. These include clear goals, effective planning, strong communication, and diligent monitoring. Therefore, I will not discuss these points in this document.

## Reason I: Workflow Too Complex or Too Simple

This is by far the most common problem, shared by many software tools. It stems from the fact that the underlying models of these workflows are often so flexible that they could, in principle, solve many different problems. As a result, it may seem illogical to reduce them to a well-defined, single-task workflow. Some typical underlying models (not an exhaustive list) include:

* Schrödinger equation
* Newton's equations of motion
* Poisson/diffusion equation
* Ginzburg–Landau equation

Now, the problem is that many projects go in one of two opposite directions:

* Towards a workflow that was meant to be a simple example, but ends up being able to do only one thing
* Towards a workflow that requires too many parameters or components for anyone to understand how to use it

So, in one case the workflow is too rigid, and in the other, it is too flexible. Since this is a document about failures, I won’t go into solutions in detail (you can refer to [How to Write Workflows](how_to_write_workflows.md)), but here’s a brief summary of what you should do:

* Separate workflows according to scientific goals
  * Create components that can be reused across different workflows
* Make a clear hierarchy for input and output data
  * All parameters should be available, but the more technical and esoteric a parameter is, the deeper it should be placed in the hierarchy (i.e., more hidden)

## Reason II: Excessive Purism

When Conda was introduced, many questioned its success because tools could run more efficiently when compiled specifically for a machine, rather than with Conda's default compilation. Today, few would still raise that objection. Yet a similar kind of purism persists in our field: experts often refuse to provide default input values or automatic settings. The result is a workflow tool that can’t be used without expert knowledge.

If this happens, ask them this:
There are two coffee vending machines in front of you. One gives you coffee only if you set all the parameters (water temperature, grinding speed, granularity, water pressure, amount of coffee grounds, amount of water). The other gives you coffee immediately, but allows you to change parameters if you wish. Which one would you choose?

Finally, remember that any workflow inherently involves uncertainty. In experimental workflows, it's in the input (e.g., sample variability), while in simulations, it's in the output (model uncertainty). While there are many ways to make parameters more reliable (see [this document](how_to_write_workflows.md)), some uncertainty is unavoidable. But that has never stopped scientific progress — and it won’t now.

## Reason III: “My Case Is Special”

When you explain how other cases were handled, you often hear this: “Yes, in their case it's easy, but our case is complicated because...,” followed by problems that are, in fact, quite common. You can try to explain why they’re mistaken, but be prepared to give up — this argument is usually a red flag.

That said, there are a few situations where the argument is at least partially valid. The most common is **human in the loop** cases, such as graphical interfaces, required human input (often due to commercial software constraints), or experimental workflow nodes. Another — now very rare — is **run-time compilation**, which effectively prevents interoperability.

## Reason IV: Too Many Unfulfilled Promises

No matter how honest you are, you are part of the workflow community, where software tools are often oversold. As a result, people are cautious about promises — even if they are legitimate. I’ve experienced this multiple times: I claimed that someone’s tool could be integrated into a workflow, and no one responded. But when I showed a working demo, they came on board.

So don’t assume they lack trust; it’s simply a consequence of the community's experience. In such cases, a live demonstration might be more effective than further discussion.
