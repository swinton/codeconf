# RUST'S COMMUNITY AUTOMATION

Emily Dunham, @QEDunham
Devops, Mozilla research

- Rust
	- 1.0, May 2015
	- 79% loved
	- Famous for being welcoming
- Automation tools
	- Allows a small team to support a huge community
	- 2 ways:
		- Social processes
			- Code of conduct, rules, how they are enforced
		- Helpful team of robots :robot:
			- Automatic reminders, e.g. when posting to subreddit
			- Some people are excluded, as they don’t want to work within code of conduct
			- Trade-off, get the people contributing who otherwise would be excluded
- Communication is mandatory
	- RFC process in public GitHub repo
	- Time invested, pain of rejection are positively correlated
- Appreciation
	- Call out people in the community (friend of the tree) for doing something awesome, worthy of recognition (nasty code cleanup)
- If you get the chance to get in on the ground floor, set up the processes at the beginning, with community values, for example. Can’t enforce later on.
- :robot: **The robots**
	- The *not rocket science rule*
		- Automatically maintain a repo of code that always passes all the tests
	- https://GitHub.com/servo/homu
		- Automatically fast forwards master to tested state, guarantees master always passes all tests
		- Having a bot neutralizes *code review conflict*
		- Starting out:
			- Travis
			- Protected branches feature of GitHub 
				- No-one can force push
				- Required status before merge
	- Automatically welcome new contributors
		- Bootstrap
			- PR and issue templates
			- Hooks that nag you
	- Perpetual contributors, needing mentorship
		- Scrape tags
		- Rust Starters
		- Bootstrap
			- Clean up your repo
				- README, CONTRIBUTING, …
				- Issue tags + documentation
			- Automate your pipeline
	- TL;DR
		- Not rocket science rule
		- ?
		- Mark, share introductory bugs

___
## Metadata
```

Tue Jun 28 12:02:14 PDT 2016
```

