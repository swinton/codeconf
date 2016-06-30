# RUST: SYSTEMS PROGRAMMING FOR WEB DEVELOPERS

Herman Radtke, @hjr3

- Rust, how web developers can become systems programmers
- Rust, Mozilla, C++ space
- Web Developer + Rust = Systems Programmer
- Rust makes systems programming more accessible
- History
	- Rails > PHP, but not the case
	- PHP still prevalent
	- But Ruby, devops
- UI Dev + Node = Full stack engineer (lol)
- Modern web stack, growing in complexity
	- Microservices, …
	- C components, some Java, some Go
- Knowledge gap, few people supporting, lots of people using
	- Documentation suffers
	- Burnout
	- Tactical, not long-term
	- Use cases missed
- Barriers to systems programming entry
	- No gc, need to manage memory
	- Thread safety
	- Expressiveness
- Rust to the rescue!
	- Memory safety without gc
	- Concurrency without data races
	- Abstraction without overhead
- First 2 solved with ownership, codified in Rust compiler
	- *Compiler as teacher*
	- Side effect: Contribute with confidence
		- Problem: write a patch that works for you, but blows up spectacularly for someone else
		- Rust compiler gives you confidence to contribute back to the community
- Expressiveness
	- Before Rust 1.0, contributions from Katz + 1 (Ruby)
	- Syntax changed, now first class consideration
	- Zero cost abstractions (*mullet driven development* :smile:)
- Optional correctness
	- Reputation, compiler hard to work with?
	- Don’t *have* to handle all error conditions
	- Opt out of correctness, wrap in an *unsafe block* :warning: :bomb:
- Foreign function interface
	- Interface between (Ruby, Python, PHP, Node) and Rust
- C, lingua franca
	- Write Rust, interface with C, C++
- Notion: systems programming is hard, because systems are hard
	- Solve hard problem with a compiler
	- Use human brain for optimization

___
## Metadata
```

Tue Jun 28 12:01:42 PDT 2016
```

