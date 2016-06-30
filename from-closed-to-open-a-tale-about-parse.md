# FROM CLOSED TO OPEN, A TALE ABOUT PARSE

@flovilmart

- Parse, the *mobile backend as a service* (mBaaS)
	- Free backend. Can scale with $.
	- Schema-less, easy to implement changes in models
	- Security with ACL
- Client SDKs *the gateway* to the service. Service itself *opaque*
- Timeline
	- Aug 2011, started
	- 2013, acquired by Facebook
	- Mid 2015, open source SDKs
	- Early 2016, Parse Server, Dashboard
	- Jan 2017, end of service
- Lots of open source Parse libraries (iOS, Android, PHP, Arduino, …)
	- Dashboard written in React.js, architecture is :sparkles:
- To open source…
	- From 1M users to 1 (one) (software **you** run)
	- Product shift, different requirements. Chain reaction…
		- Technology shift
		- Audience shift
	- Lots of complaints, e.g. too long to set up, needs to fit in smallest tier of IaaS provider
- `parse-server`
	- Under the hood
		- It’s an express.js app, with command line interface
		- ES6, small memory footprint (~150MB RAM)
	- Open source:
		- in 5 months:
			- 10k stars, 500 PRs, 1300 issues closed, 2500 forks 
		- Technology shift, platform agnostic?
		- Front-end devs (mobile, web) no back-end experience, never touched a database
- Audience shift:
	- Existing users:
		- Front-end focused, care about continuity of service, don’t want to rewrite
	- New users:
		- Full stack, care about API / SDK, flexibility, ease of use
	- SaaS
		- Business, want to make $$$ :moneybag:
- Moving forward:
	- Designed to be extensible, from the ground up, through modules
	- Live queries
	- Native social auth, not just Twitter / Facebook, currently 8 supported
	- PostgreSQL (CockroachDB)

___
## Metadata
```

Wed Jun 29 12:22:45 PDT 2016
```

