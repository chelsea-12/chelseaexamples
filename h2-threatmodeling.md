# H2

## Article Summaries

### Threat modeling manifesto [(link)](https://www.threatmodelingmanifesto.org)

- Four key questions of threat modeling: What are we working on? What can go wrong? What are we going to do about it? Did we do a good enough job?
- Threat modeling can help prevent issues before they have even occurred. If you threat model ahead of time, you can factor this into the planning of your system
- Threat modeling is for everyone, regardless of what system you are implementing. This is not something reserved just for tech professionals
- Relative values in threat modeling are important, such as: valuing continuous refinement over doing something once, and valuing a culture of finding and fixing problems rather than just complying with check box standards
- Patterns than benefit threat modeling include, but are not limited to: a wide variety of view points to better inform the situation, approaching the situation systematically, and allowing for creativity.
- Patterns that may hinder threat modeling can include: the belief that you must hold a certain skill set in order to threat model and over-focusing on a certain issue rather than looking at the bigger picture

### World's shortest threat modeling course [(link)](https://www.youtube.com/playlist?list=PLCVhBqLDKoOOZqKt74QI4pbDUnXSQo0nf)

- we threat model to anticipate problems when it's inexpensive to deal with them (i.e. if we leave them to later, they will be a lot more costly to deal with)
- the video re-iterates the importance of the four question model that I touched on in the previous article's summary
- What are we working on: collaboration and working together to help solve this question
- sketching and how this can help answer what we are working on, and lead into answering what can go wrong: this should be the first step as it's a non-permanent way to see the big picture
- additionally to this records should be kept of the collaboration and sketches: can do this in a drawing tool (and through this you can maybe even further asnwer the question 'what can go wrong'
- Data flow diagrams are important as threats tend to follow data. They are also easy to follow and draw.
- Data flow diagrams have 5 symbols: external entities which is anything outside your control (square), processes which are things under your control(round), data flows to connect things (arrows), data stores (drums) and trust boundary (dotted line)
- What can go wrong: sometimes we just need to give people a space to express what they are worried about, or sometimes we need to use certain techniques to figure this out
- One of these techniques or structures is called STRIDE: stride stands for Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privileges. These are each possible problems that can occur with any type of system, and it's important to think of at least one threat each from these
- What are we going to do about it: there should be a solution for each of the problems highlighted. Don't just forget about them or put them to the side, they must be treated as important
- Risk management and threat modeling go hand-in-hand
- Did we do a good job: would you recommend threat modeling to a colleague? The answer to this can answer the question 'did we do a good job?'

### Chapter 1 Dive in and threat model [(link)](https://www.oreilly.com/library/view/threat-modeling-designing/9781118810057/9781118810057c01.xhtml#c1)

- threat modeling gets easier with practice
- if you ever get confused with threat modeling, just refer back to key four questions
- start with a simple diagram to see things clearly. Some people are already able to point out threats during this step
- within your diagram you should specify who controls what, and when you do this you can circle certain parts of the diagram with a trust boundary to more easily define the areas that are controlled by different people
- when things exit a trust boundary, they are most at risk of threat
- this article explains stride in more detail than the previous article:
- Spoofing is pretending to be something or someone you are not
- Tampering is modifying something you are not supposed to modify
- Repudiation is claiming you did not do something (whether you did it or not)
- Denial of service is when you stop a system from providing it's service
- Information disclosure is releasing information that people do not want released
- Elevation of privilege is a user being able to do things they should not be allowed to
- Using this whilst going through your diagram can help you to spot more threats
- If you're not sure where to start when identifying threats, start with external entities. It is important to never ignore a potential threat and to focus on the feasible threats (it's easy to come up with large hypothetical scenarios, but how feasible are they to happen?)
- Once you've figured out your threats, you can look at them in more detail and figure out what you are going to do
- 

### Threat modeling cheat sheet [(link)](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)



## Security Hygiene

## Threat Model

