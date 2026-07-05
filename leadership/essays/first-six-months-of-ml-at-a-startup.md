# First Six Months of ML at a Startup

The first six months of machine learning at a startup are not about building the perfect model. They are about answering one question: does anyone care? Everything else is a distraction until that question has an answer.

I have joined and advised enough early-stage ML companies to recognize the same trap. A founding team spends three months tuning a transformer, achieves a leaderboard score that would make a conference reviewer happy, and then discovers that no customer will pay for the output. The model is elegant. The business is nonexistent. The first six months should be designed to prevent that outcome.

## Month zero: define the decision, not the architecture

Before writing training code, define the customer decision your model will influence. Will it reduce a support ticket volume? Will it increase a conversion rate? Will it let a human expert work twice as fast? If you cannot name the downstream decision, you are doing research, not product development.

I tell founders to write a one-page "model promise." It should state who the user is, what action the model enables, and what success looks like in the user's own metrics. Not accuracy. Not F1. User outcomes.

At this stage, architecture is almost irrelevant. Use a hosted API, a notebook, and a Google Sheet if that gets you in front of customers fastest. The only infrastructure that matters is the one that lets you learn.

## Months one to two: ship the worst model that teaches you something

Your first model should be embarrassingly simple. A heuristic, a small classifier, a retrieval system over a hand-curated set. The goal is to put a prediction in front of a user and watch what happens.

This is harder than it sounds because engineers love to optimize. Resist the urge. The question you are answering is not "how good can this model be?" but "does a prediction in this workflow create value?" A model that is 60% accurate but reveals a real user need is worth more than a 95% accurate model that nobody uses.

During these months, collect feedback obsessively. Log every wrong prediction, every surprised user reaction, every request to see the underlying reasoning. That feedback is your training data for the real product.

## Months three to four: build the loop, not the monument

Once you have signal, build the loop: data in, model trained, prediction served, feedback collected, model improved. The loop does not need to be automated at first. It needs to be fast and observable.

I am less interested in whether a team has Kubernetes than in whether they can retrain and redeploy within a week. Speed of iteration beats scale of infrastructure every time in the first year. A team that can run five experiments a week will learn faster than a team that runs one experiment a month on a beautiful cluster.

This is also when you should start caring about data rights, privacy, and basic security. Not because investors will ask, though they will, but because sloppy data practices compound. A dataset you cannot explain to a customer will eventually become a liability.

## Months five to six: decide what you are willing to be bad at

By month six, you should have a working product in the hands of real users and a model that is good enough to keep them. Now comes the hardest part: choosing what not to do.

Early ML teams face a thousand tempting tangents. A better base model. A more sophisticated pipeline. A second use case. A platform for internal reuse. Most of these are traps. The right question is: what is the smallest set of improvements that unlocks the next revenue milestone or funding milestone?

I push teams to document their explicit trade-offs. We are optimizing for latency over cost. We are accepting manual retraining because volume does not justify automation yet. We are using a third-party embedding model because building our own is not our moat. Writing these down makes it harder to chase shiny objects and easier to explain the strategy to a board.

## What success looks like

By the end of six months, the strongest ML startups I know share these traits:

- They have shipped something real to real users.
- They know the customer outcome their model is supposed to improve.
- They can iterate on the model faster than their competitors.
- They have identified what data advantage, if any, they actually have.
- They have a written plan for the next six months that is smaller than their ambition.

The weakest startups have a beautiful architecture, no users, and a roadmap full of infrastructure milestones that do not map to revenue.

## A final warning

The first six months set the cultural defaults of the R&D organization. If the team learns to value demos over delivery, that habit will persist. If the team learns to ship fast and learn from users, that habit will also persist. Choose deliberately.

Machine learning startups do not fail because their first model was imperfect. They fail because they never discover whether anyone wanted the model at all. Spend the first six months removing that uncertainty.
