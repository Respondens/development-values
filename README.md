# Development values

This describes how do we want to work as development team. This is not [coding standards about syntax](https://github.com/Respondens/coding-standards).


## Organization of code

Above all, our code must be readable for humans, our future selves.

This trumps other rules like keeping functions small, or abstractions and patterns.
In the end such rules are measures to improve readability.
We know the context and know if we can make something big and not follow a pattern when that makes it easier to understand.
Only write code once you need it.

Focus on:
- **High cohesion** in code. Organize code in concepts (domains and components).
- Favor **explicit and concrete** code. Tell a story with porcelain methods, move simple tasks to plumbing methods.
- Code doesn’t have to be DRY directly, abstract only after you understand the problem. As a rule of thumb only **abstract after repeating code for the third time**.
- It is not bad for code to have essential complexity (complex domains), spend maintenance to have less accidental complexity (complex code).

Concepts to dive deeper: **Yagni**, optimize for deletability, cohesion vs coupling, dry vs wet.


## Testing wisely

Focus time testing on high-outcome tests.
Avoid making the measurement of testing (e.g. coverage, test ratio, test performance) into a goal on its own.
Don’t overly test since also the test code can contain bugs.

Focus on:
- **End-to-end tests.** This helps cover the actual functionality and is an early signal of bugs. Accept that it might be a bit fragile sometimes.
- **Integration tests of connected components.** This makes sure that separate components actually come together. For example tokenizing documents or restarting book memberships with a repair order.
- **Integration tests with 3rd parties.** Creating separate tests for 3rd party integrations helps removing/mocking those integration points in other tests, which helps in identifying if the bug is on our side or not.
- **Unit tests on specifically complex units.** This helps with refactoring complex functions with lots of input/output variance. For example when using regex matching.
- **Manual testing.** A quick view on the feature as you’re deploying. This is relatively cheap and also helps in verifying that what you thought you developed actually works as intended. This is often more than a test can verify.


## Work in small steps

Getting things done, together, is done by making small steps and deploy often.

For example:
- Start with adding a new method and move calling it to a second PR.
- Build a visual-only interface first and tie things together in a second PR.
- Create the happy path prototype first and work on the edge cases in a second PR.
- Setup an experiment[﹡](https://github.com/github/scientist) to run both old and new code next to each other, cleanup the old code once you’re happy with the results.

This makes it easier for others to review and continue on your work.
And it avoids going into a rabbit hole of edge cases before having something at all.
Shipping is a feature.
This helps us remain flexible and evolve features as we go instead of having to know it all up front.

Concepts to dive deeper: **kaizen**, CI/CD, Agile, getting things done, strangler pattern.


## Knowledge sharing

Focus interactions on knowledge sharing, it is a more important output than the code itself.

For example:
- Code review isn’t about finding bugs (although that is a nice side effect) but about knowing whether we think the same about concepts.
- During incident follow-ups it is less interesting to find the root cause / blame, and more effective to exchange how each person interprets the systems. Then you’ll learn where it might have gone wrong and are in a better shape to come up with solutions, also in the future.
- Have an ubiquitous language for the concepts. Come up with terms, stick to them, re-use them for everything. From css classes to database tables.

Concepts to dive deeper: ubiquitous language.


## Values matter

Stand behind values like web fundamentals, privacy, security, and accessibility.

The organization trusts us to be experts on these and to defend them when needed.
Non developers can’t always weigh the choices with these values in mind.
We can always discuss the amount of effort that goes into improving this, but not discard them.

Focus on:
- Use native components to stay close to what people expect.
- Discuss features before building to practice privacy & security by design.
- Explain the ways data can leak, or how accessibility can help different types of users.
- Dive into the laws governing IT so you can help the organization staying compliant.


## Inspiration

- [Being a software writer not a software engineer](https://www.youtube.com/watch?v=9LfmrkyP81M)
- [The values behind Svelte(Kit)](https://github.com/sveltejs/svelte/discussions/10085)
- DRY vs WET: [watch](https://www.deconstructconf.com/2019/dan-abramov-the-wet-codebase) or [read](https://dev.to/wuz/stop-trying-to-be-so-dry-instead-write-everything-twice-wet-5g33)
- [Getting things done by working in small steps](https://thomasdeneuville.com/cult-of-done-manifesto/)
- [Good to be reminded about agile principles every now and then](https://agilemanifesto.org/principles.html)
- The balance between design patterns and duct-tape, in [long-read](https://martinfowler.com/articles/designDead.html), or a [shorter version](https://simpleprogrammer.com/dont-get-obsessed-design-patterns/), or a [rant](http://qualityisspeed.blogspot.com/2014/08/why-i-dont-teach-solid.html)
