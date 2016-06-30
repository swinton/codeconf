# LET'S ENCRYPT: A FREE, AUTOMATED, AND OPEN CERTIFICATE AUTHORITY

Josh Aas

- A more secure, privacy respecting web
- What is HTTPS?
	- HTTP over a TLS conn (used to be SSL)
- Why is it important?
	- Used to be able to reason fairly easily about what we’re transmitting, e.g. credit card, SSN require encryption
	- Nowadays, even when a technology savvy person visits a website, hard to tell what we’re transmitting, can’t keep track
	- With enough metadata, can put together a pretty complete picture of someone
	- Therefore, secure things by default
- Developer expect integrity
- Can loose integrity if you communicate over an unencrypted channel
- :warning: Right now, the web **is not secure**
- Only 45% of Firefox page loads use HTTPS
- Let’s Encrypt wants to get this to :100:%
- **Problem: it’s hard :confused:**
	- 2 components to a secure connection
		- Encryption (scrambling)
		- Authentication (am I talking to the person I think I’m talking to?)
	- Encryption, pretty easy. Just a software stack, just protect your private keys
	- **Authentication** part is a **pain**
		- Got to get a cert from a cert authority (CA) :disappointed:
			- Where to go
			- What kind of cert
			- How to request
			- How to verify
			- Pay
			- How to install
			- Remember to renew
		- Too hard, impossible even, for everyone
		- Need to address the above, if the Web is ever going to achieve HTTPS everywhere
- Conclusion: a new CA the only option :bulb:
- What would a new CA look like?
- Cornerstones:
	- **Automated**, easy to use
		- Reliable
		- Scalable
	- **Free**
		- Cost excludes people
		- Any form of payment adds complexity, because :earth_americas:
	- **Transparent / open**
		- Trust
	- **Global**
		- The secure web is for everyone
- First, an organization, backers :moneybag:
- Need help from another CA, for root to propagate, for certs to be accepted (IdenTrust partner)
- ISRG founded, May 2013
- How *Let’s Encrypt* works
	- ACME protocol, Boulder implements ACME
	- Cert requested via ACME
- Cert types:
	- **DV**, validates the Domain
	- **OV**, DV + ties to a legal entity
	- **EV**, OV + deeper into the vetting process regarding org identity
- Let’s Encrypt only issues DV certs, only one that can be automated, only one that can scale
- ACME being standardized by IETF
- 90 day cert lifetimes
	- Short is really good for security, limits damage from key compromise
	- If you have a long-lived cert, better hope your private key doesn’t leak
- Phishing, malware
	- CAs not the right place to police this (for example, don’t want to censor if HTTPS becomes a requirement. And other reasons :grin:)
- Certificate transparency, every cert issued to public log, visible by all
	- Even more, all software used to run Let’s Encrypt openly available on GitHub 
	- Incident disclosure
	- Public benefit governance (exist for benefit of public)
- Global aspect :earth_americas: :earth_africa: :earth_asia:
	- Let’s Encrypt issues certs to every country in the world
- Launched Dec 3, 2015
- Currently have 3.6M certs out there
- WordPress.com using Let’s Encrypt by default, also Dreamhost
- Putting this into context:
	- Approx 92% of LE’s certs issued to domains that didn’t have certs before :boom: :tada:
- How long to :100:%?
	- Milestone: when web is more encrypted than not
- How to help:
	- If you are responsible for a website? Use HTTPS by default
	- Sponsor us

___
## Metadata
```

Tue Jun 28 17:21:48 PDT 2016
```

