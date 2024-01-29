# H2

## Threat Model

Company name: PetFood

An online pet food store where customers can buy food online, and have it shipped to their home. Customers have private accounts on the website, and can have recurring subscriptions to food items so they do not need to do seperate orders, for example, each month.
PetFood operates out of multiple warehouse locations across Europe, with office spaces on-site at each warehouse, as well as a corporate location in Helsinki.

PetFood is currently operating with around 100 staff members across all the locations, and positions vary. Positions include, but are not limited to:
- warehouse logistics
- warehouse staff (packers)
- online customer service representatives
- quality assurance
- marketing
- E-commerce manager
- Finance manager
- IT manager
- HR manager
- Admin
- CEO

WHAT ARE WE WORKING ON?

PetFood manages a variety of assets, such as customer data, employee data, payment processing systems, inventory management systems and website infrastructure.

The highest prioritisation is the safe management of customer data and the handling of payments and payment information. Also maintaining the integrity of the website is crucial to the successful running of this company. 

The website server is managed by IT specialists only, whereas customer data needs to be accessed by multiple departments which leaves this as the most vulnerable asset. Stock levels are managed by warehouse staff, but data from this will be communicated to other departments, for example, when new stock is ordered and payment receipts are sent to the finance department.

![Data FLow Diagram](https://github.com/chelsea-12/chelseaexamples/blob/main/20240126_105743.jpg)

WHAT CAN GO WRONG?

Using STRIDE, I have come up with the following potential threats.

- Data breaches are the biggest concern - having someone gain access to customers personal information (name, address, phone number etc.) as well as their payment information
- Denial of service attacks on the website which can put the business fully out of operation and lead to a loss in sales
- Accessing the system through employee credentials and being able to see sensitive business information
- Accessing customer accounts and making fraudulent orders
- Payment fraud (i.e. not a valid payment method used) 
- Digital tampering with the stock management system which can cause chaos to the business
- Threat of theft from physical access to the warehouse

Highest risk value would be a data breach of sensitive customer data - is a breach of trust for the customers leading to a loss of sales and potential legal action. Second highest risk value is a DoS attack on the website - as this is a company that runs solely online, if the website is shut down it can lead to a huge loss in business even if for a short period of time.

Potential threat actors can be hackers looking for private information to sell or DoS attackers looking to shut down websites for financial gain. Phishing attacks on employees can also be a risk.

WHAT ARE WE GOING TO DO ABOUT IT?

- For potential payment frauds, it is best to mitigate this risk by transferring it to a certified payment specialist. Have payments on the website be made through this 3rd party provider that has a known and reputable track record for safety
- Customers and employees should need to authenticate when they log in/create an account
- This should be even more stringent for employees. Usernames should not contain personal information, and passwords should be hard to guess and changed monthly
- IT department should hold periodic cyber security training for all employees (not opening suspicious links to prevent phishing attacks!)
- IT department should keep security logs
- strong encryption protocols for data
- encrypt internal e-mails between employees
- Physical security of warehouse premises should be outsourced to a reputable security firm
- backup data on a secure, off-site location
- stock management system can be kept on the cloud (e.g. Salesforce) to transer risk to a reputable company
- ensure firewalls, anti-virus and anti-malware software are upto date
- continously monitor network traffic, and employ network segemenation
- make sure access to sensitive data is limited
- have an action plan in case any of the potential threats occurs so it can be dealt with as swiftly and efficiently as possible

  
DID WE DO A GOOD ENOUGH JOB?

To ensure a good job is being done:
- customer feedback/complaints should be followed closely in order to ensure there are no security concerns
- hold periodic cyber security training sessions (mimic a data breach/DoS attack and what are the responses to this)
- update the threat security diagram as and when needed
- ensure each potential threat has a solution, and that this solution works (and continues to work!)
- therefore, regular security audits are key

Sources that helped me write this threat model in addition to the four linked articles below include
- [Crowdstrike](https://www.crowdstrike.com/cybersecurity-101/threat-modeling/)
- [J.P.Morgan](https://www.jpmorgan.com/insights/cybersecurity/ransomware/12-tips-for-mitigating-cyber-risk)
- [NSA](https://www.nsa.gov/portals/75/documents/what-we-do/cybersecurity/professional-resources/csi-nsas-top10-cybersecurity-mitigation-strategies.pdf)

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
- additionally to this records should be kept of the collaboration and sketches: can do this in a drawing tool (and through this you can maybe even further answer the question 'what can go wrong'
- Data flow diagrams are important as threats tend to follow data. They are also easy to follow and draw.
- Data flow diagrams have 5 symbols: external entities which is anything outside your control (square), processes which are things under your control(round), data flows to connect things (arrows), data stores (drums) and trust boundary (dotted line)
- What can go wrong: sometimes we just need to give people a space to express what they are worried about, or sometimes we need to use certain techniques to figure this out
- One of these techniques or structures is called STRIDE: stride stands for Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privileges. These are each possible problems that can occur with any type of system, and it's important to think of at least one threat each from these
- What are we going to do about it: there should be a solution for each of the problems highlighted. Don't just forget about them or put them to the side, they must be treated as important
- Risk management and threat modeling go hand-in-hand
- Did we do a good job: would you recommend threat modeling to a colleague? The answer to this can answer the question 'did we do a good job?'

### Chapter 1 Dive in and threat model [(link)](https://www.oreilly.com/library/view/threat-modeling-designing/9781118810057/9781118810057c01.xhtml#c1)


- start with a simple diagram to see things clearly. Some people are already able to point out threats during this step
- within your diagram you should specify who controls what, and when you do this you can circle certain parts of the diagram with a trust boundary to more easily define the areas that are controlled by different people
- when things exit a trust boundary, they are most at risk of threat
- this article explains STRIDE in more detail than the previous article:
- Spoofing is pretending to be something or someone you are not. Tampering is modifying something you are not supposed to modify. Repudiation is claiming you did not do something (whether you did it or not). Denial of service is when you stop a system from providing it's service. Information disclosure is releasing information that people do not want released. Elevation of privilege is a user being able to do things they should not be allowed to.
- Using this whilst going through your diagram can help you to spot more threats
- If you're not sure where to start when identifying threats, start with external entities. It is important to never ignore a potential threat and to focus on the feasible threats (it's easy to come up with large hypothetical scenarios, but how feasible are they to happen?)
- Once you've figured out your threats, you can look at them in more detail and figure out what you are going to do. You can mitigate the threat (make it harder for people to take advantage of), eliminate the threat, transfer the threat (let someone more capable handle it), or accept the risk
- the chapter then goes into specific detail about how to deal with potential threats identified using STRIDE. I will highlight only one of each:
- Spoofing a person: ensure each person has a unique username and way to authenticate themselves when logging in
- Tampering with a file: use digital signatures or a keyed MAC
- Mitigating repudiation: ensure you keep security logs of everything
- Disclosure of files: ensure files are encrypted
- Network flooding (denial of service attacks): look for exhaustible resources and try to ensure the attacker's resource consumption is as high or higher than yours
- Memory corruption attacks (elevation of privilege): write code in a type-safe language
- the final task of threat modeling is checking your work and developing your diagram further if needed

### Threat modeling cheat sheet [(link)](https://cheatsheetseries.owasp.org/cheatsheets/Threat_Modeling_Cheat_Sheet.html)

- threat modeling requires a deep understanding of the system being evaluated, therefore improved visibility into a system is one advantage of threat modeling
- threat modeling allows security to be built into the system rather than bolted on
- in addition to STRIDE there is also PASTA and OCTAVE
- OCTAVE: Operationally critical threat, asset and vulnerability evaluation
- PASTA: Process for attack simulation and threat analysis
- the data flow diagram can also help to answer 'what are we building' so you can gain further clarity into the system being created, and therefore what issues may arise
- STRIDE and ATT&CK work well together: ATT&CK is a globally-accessible knowledge base of adversary tactics and techniques
- response to the threat follows: mitigate, eliminate, transfer, accept
- evaluating if you did a good job is the last step: did we accurately identify all possible threats, has the threat model been formally documented, can the agreed mitigations be tested?

## Security Hygiene

What security practices should everyone follow?
- different passwords for different accounts
- use strong passwords and multi-factor authentication
- store these passwords in a password vault that is preferably not on the cloud
- be cautious of clicking links online or in e-mails
- use anti-virus/malware software and keep it up to date
- use a VPN
- back up your data
- never leave your computer logged in and unattended, or don't forget to log out of private accounts on public computers
  
Find some more great tips [here](https://us.norton.com/blog/how-to/cybersecurity-basics)

What security practices are important, but may not be suited for the 'average joe'?
- browsing in private windows (may seem straight-forward, but not everyone knows this is a choice)
- Endpoint Detection and Response (EDR) (it is deployed on endpoints such as laptops, networks and work stations and is used to detect suspicious behaviours like network scanning or lateral network movement
- Managed Detection and Response platform (MDR) which is used to catch threats such a zero-day attacks
- e-mail hygiene to prevent phishing attacks: attachment sandboxing - opens attachments in a sandbox environment which is a protected virtual space that will not affect your actual computer
  
[Source](https://www.kroll.com/en/insights/publications/cyber/10-essential-cyber-security-controls)

