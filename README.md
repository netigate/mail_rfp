## Request for Proposal - SMTP as a service

---

### API

All emails from our platform should be sent to an API endpoint.

**Required**

* Enough public IP addresses for sending ~6.000.000 emails per month
* API should support multiple emails on each POST request.
* API for collecting statistics.
* API Current mail queue size

**Preferred**
* Webhook callback when mail batch is complete.
* Time windows of delivery. Example, email batch X should only be delivered during office hours 0900-1700.
* Environment aware, if we push a batch of emails from our swedish environment. A web-hook should send a callback to that environment.

**Extra**

* Templating. We would favor a feature to send a template, and list of recipients with variables. 
* Statistics on public IP address reputation
* SPF, DKIM, DMARC checks
* ability to group public IPs in order to select which to use while pushing an batch of emails.
  Example would be to have a primary group for emails that are sent with *@netigate.se as FROM address. 
  And another group for customers using their own domains.
* Mail queue size based on batch ID.
* Mail batch deadline. if date X, stop sending emails from a certain batch. or a kill switch for a specific batch.
* Tracking recipient expected believability based on risk analyzes
* Monthly report on delievability based on target/source domain
---

### Public IP

We send roughly 5 million emails per month. However, the way we send emails is not nicely sorted out to (5 million divided by 31 days).  
Therefore, we do require that the supplier will track max quota to targeted domains (gmail, hotmail etc..).  
Day1 could be 900k, Day2 20k, Day3 100k.  

As of today, we do not offer a time frame for deliverance of larger email batches.  
But it would be expected that 1 million+ recipients would be completed within a reasonable time frame.  


---

### Penalties
Do you enforce any types on penalties on bounces, failed DNS checks, etc...  
any form of rules that must be followed in order to use your platform?

---

### External Domains

Our customers are allowed to send emails with their own domain as FROM addresses.  
Does this require manual configuration for enable additional domains?

---

### Privacy

* How long do you store data?
* Will you use our data, or our customers' data for your own purpose, and/or share this in any way with any of your partners/customers?
* GDPR compliance?
* ISO 27001 certification?
