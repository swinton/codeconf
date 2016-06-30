# 12 FACTOR APPS AND KUBERNETES

@kelyseyhightower
One of the foremost contributors to the container community
(kubernetes.io)

- **The twelve-factor app** and *all this container stuff*
	- twelve-factor pattern becoming a requirement
	- When you write an app you should be able to deploy anywhere
- What is a scheduler?
	- Utility computing
	- 1-click deployment script?
		- Problem: resource considerations
	- **Tetris** to illustrate (OpenEmu), 1 click deploy and step away, wasted space
		- Scheduler is smarter about how workloads are managed, what servers are used
		- *Bit-packing*
		- Schedulers, like a good Tetris player, makes good use of the available space
- What about *non-startups*? Those companies that actually make money
	- Infrastructure not so pretty
- What’s required to do this *12-factor thing*?
	- **Good** practices, but not necessarily *best* practices
	- No deployment scripts
	- Focus on the workload
	- Like FedEx, put it in a box, :ship: it
		- If it breaks, that’s on you
		- This is where containers come in, don’t tell me about the app, put it in a box and ship it
- **The twelve factors**
	- Version control
	- Dependencies
		- Containers *take this factor to the next level*
		- Containers allow you to bring in your dependencies next to your app
	- Config
		- Store config solely in environment variables
			- Can be relaxed… Maybe the environment can be dynamic?
	- Backing services
	- …
	- [http://12factor.net/](http://12factor.net/)
- Free tip! Start up nicely (`log`), shut down cleanly (`SIGTERM`)
- **Deploy**
	- Have a container
	- Push it to docker hub, for example
	- Describe your app
		- e.g. `services/frontend.yaml`
		- `kubectl` to query, spawn, etc services
	- In Docker, where do you put your configuration files?
		- Filesystem that only lives in memory, injected into the application
	- A pod, ?a logical component for multiple containers?
- 

___
## Metadata
```

Tue Jun 28 11:03:22 PDT 2016
```

