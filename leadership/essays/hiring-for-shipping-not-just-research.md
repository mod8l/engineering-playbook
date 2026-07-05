# Hiring for Shipping, Not Just Research

The first ML hire at a startup should not be the person with the most publications. It should be the person most likely to get a model into production and keep it there. This sounds obvious, yet I see startups repeatedly hire brilliant researchers and then wonder why nothing ships.

Research ability and shipping ability are not the same skill. They can coexist in one person, but they often do not. A researcher optimizes for insight. A product engineer optimizes for outcome. A startup needs both, but it needs outcome first.

## The research trap

Startups hire researchers for understandable reasons. Investors ask about technical differentiation. Founders worry about being copied. A PhD from a top lab signals credibility. But signaling is not shipping.

The research trap has a predictable shape. A newly hired research lead builds a small team. They explore novel architectures. They run ablation studies. They write internal papers. Meanwhile, the product team waits for a model that never arrives, or receives a model that is brittle, slow, and impossible to maintain.

By the time the founder realizes the problem, the research team has political cover, the burn rate has climbed, and the product roadmap is months behind. The fix is usually painful: restructure, redefine roles, and sometimes part ways with talented people who were simply hired into the wrong context.

## What shipping looks like

Shipping ML means more than writing a training script. It means:

- Understanding the user outcome the model is meant to improve.
- Writing code that other people can read, test, and deploy.
- Designing systems that fail gracefully when the model is uncertain.
- Instrumenting predictions so the team can learn from production data.
- Making trade-offs between accuracy, latency, and cost.
- Talking to product managers, designers, and customers.

The best ML engineers I have hired could explain their model to a sales team and their infrastructure to a backend engineer. They were not the deepest theorists in the room, but they were the ones who turned theory into working systems.

## The hiring profile

When I hire early ML engineers, I look for a specific balance.

**Breadth over depth.** I want someone who can move from data cleaning to model training to serving without needing a handoff at every step. Depth matters later, when the team is large enough to support specialists.

**Production scars.** I ask about incidents, bad deployments, and models that degraded in production. Candidates who have only worked on benchmark datasets have not yet felt the difference between research and product.

**User empathy.** I want engineers who can describe the user their model serves. If they can only describe the model, they will optimize the wrong thing.

**Code quality.** ML code is still code. If a candidate cannot write clean, tested, reviewable software, their models will become unmaintainable.

**Pragmatism about novelty.** The best candidates get excited about solving a problem, not necessarily about using the newest technique. They will use a heuristic if it is good enough.

## Interview signals

I pay attention to small signals in interviews.

A candidate who asks about deployment infrastructure before asking about model architecture is usually a shipper. A candidate who describes a project by starting with the problem and ending with the user impact is usually a shipper. A candidate who treats accuracy as one variable among several, rather than the only variable, is usually a shipper.

Conversely, I worry when a candidate dismisses engineering practices as "not real ML." I worry when they cannot explain why their favorite model was the right choice for the business. I worry when every project they describe ends at the trained model, not at the deployed system.

## Building a balanced team

Research hires are not bad. They are dangerous when they arrive too early or without production partners. As the company grows, there is absolutely a place for researchers who push the boundaries of what is possible. But they need a production team to carry their work across the finish line.

My preferred early team shape is two or three shipping ML engineers for every one researcher. That ratio shifts as the product stabilizes and the company can afford exploratory bets. Until then, the research function should be a role, not a department.

## The founder's responsibility

Founders cause the research trap as often as hiring managers do. If the founder rewards demos and papers more than shipped features, the team will optimize for demos and papers. If the founder asks "when can a user touch this?" every week, the team will hire and reward shippers.

I tell technical founders: **"Your first ML hire sets the culture. Hire the person you want ten future hires to resemble."** That person is usually someone who would rather ship a slightly worse model this week than a perfect model next quarter.

## Conclusion

Great research is a competitive advantage. But only if it reaches the user. In a startup, the scarce resource is not intelligence. It is time and focus. Hire people who treat shipping as the default, and let the research follow the product.
