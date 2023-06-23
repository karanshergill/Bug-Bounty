# Passive Reconnaissance
Querying publicly available records.

 - `whois`: Queries a **WHOIS** database and provides information about registered *domain names*, *IP addresses*, and *autonomous system numbers*. It can retrieve details about the *ownership*, *registration date*, *expiration date*, *name servers*, and *contact information* associated with a particular **domain** or **IP address**.
 - `nslookup`: to query DNS servers
 - `dig`: to query DNS servers

---

## WHOIS
WHOIS is a request and response protocol that follows the RFC 3912 specification.
A WHOIS server listens on TCP port 43 for incoming requests.
The domain registrar is responsible for maintaining the WHOIS records for the domain names it is leasing.
The WHOIS server replies with various information related to the domain requested.

- Registrar: Via which registrar was the domain name registered?
- Contact info of registrant: Name, organization, address, phone, among other things. (unless made hidden via a privacy service)
- Creation, update, and expiration dates: When was the domain name first registered? When was it last updated? And when does it need to be renewed?
- Name Server: Which server to ask to resolve the domain name?

---
