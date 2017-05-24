# Intro to Threat Modelling by David Lawrence and Ying Li (Docker)
 * Example Architecture (Django photo gallery)
 * `cryptography` python library
## Process
 1. Collect data
 2. Analyze data
 3. Remediate
## Collecting Data
 * List of external dependencies
 * Entry points
 * Assets (things we care about protecting)
 * Trust levels (tiers of access in system)
 * Data flows (diagrams that explain how data moves through system and shows trust boundaries)
### External deps
 * Third-party services (python core, new relic, cloudflare)
 * Deployment tools (docker)
 * Clients (modern web browsers)
### Entrypoints
 * Deliberate: WSGI server
 * Not deliberate: SQL server, file storage
### Assets
 * User data, files, API keys, CPU, bandwidth
### Trust Levels
 * Admin, moderator, registered user, anonymous user [usually the flow an attacker uses]
## Data Flows
 * Better to secure each component instead of just the entry points
## Analyzing Data (STRIDE)
### Spoofing
 * Brute force
 * CSRF
### Tampering
 * SQL injection
 * MITM
 * DNS poisoning
### Repudiation (need proof of malicious actions)
 * `rm -rf /var/log`
### Information Disclosure
 * Bad messaging
 * SQL injection
 * MITM
### Denial of Service
 * SQL injection
 * DDoS
### Elevation of Privilege
 * SQL injection
 * CSRF
## Prioritization
 * Impact vs Probability
  * Impact - how much damage can they do by taking advantage of vulnerability
  * Probability - how likely is it that someone can find and make use of vulnerability
 * DREAD
  * Damage potential
  * Reproducibility
  * Exploitability
  * Affected users
  * Discoverability
## Remediate
 1. Spoofing -> Authentication (who are you)
 2. Tampering -> integrity controls (validate input, checksums)
 3. Repudiation -> Non-repudiation (append-only logs, digital signatures)
 4. Information Disclosure -> encryption, redaction, configuration
 5. Denial of Service -> availability (more replicas, rate limiting, recovery protocol)
 6. Elevation of Privilege -> Authorization (defined auth model, least privilege, re-authentication)
