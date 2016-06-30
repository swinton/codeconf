# TWITTER HERON IN PRACTICE

@louis_fumaosong, @heronstreaming

- Twitter == real time y’all :metal:
- ~~Apache Storm~~ **Heron** == real time data processing framework :muscle:
	- [github.com/twitter/heron](https://github.com/twitter/heron)
	- Development happens on GitHub :boom: :octocat:
- Heron terminology
	- Topology
		- A DAG, involving spouts and bolts, data flows from spouts through bolts
	- Spouts
		- Source of data
	- Bolts
		- Process data
		- Horizontally scalable
- Architecture:
	- Submit topology to scheduler, scheduler handles everything else
	- Containerized?
- Apache Storm originally, now Heron in production for 2 years, now fully replaced Apache Storm
- Use cases:
	- Realtime ETL
	- Realtime BI
	- Realtime trends
	- Realtime…
		- Ops, media, …
	- Realtime
- Microstream engine… small sub-systems
- Stragglers (Bad host) handling
	- drop data
	- throttle senders
	- detect, reschedule stragglers

___
## Metadata
```

Wed Jun 29 15:21:52 PDT 2016
```

