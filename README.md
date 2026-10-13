# Cybersecurity Improvement Capstone Project

Authorised security assessment and improvement project completed in a simulated lab environment as part of the **Certificate IV in Cyber Security (22603VIC)** at RMIT University.

> **Team project** — a two-person RMIT capstone. I led documentation and system design; my project partner led penetration testing and system hardening, with both of us collaborating across all areas.

## Overview

The project assessed common enterprise security risks for a simulated small-business client and developed practical remediation and incident-response recommendations. It demonstrates my approach to **asset prioritisation, risk assessment, technical investigation, documentation and security improvement planning**.

All activity was performed in an authorised, isolated training lab. No testing was conducted against any system without explicit permission.

## Scenario

The simulated organisation required an assessment of its security posture, with a focus on phishing exposure, weak authentication, access control, vulnerable systems, malware risk and incident readiness.

## Objectives

- Identify and prioritise key assets and security risks
- Assess likely attack paths and control gaps
- Document findings using likelihood and impact
- Recommend practical remediation actions
- Develop incident-response and user-awareness measures

## Methods and tools

Testing was carried out in an isolated lab using industry-standard tooling: **Kali Linux, Nmap, Metasploit, BeEF, Hydra, Splunk, pfSense, Snort**, and Windows/Linux virtual machines.

---

## Risk Assessment

A structured risk assessment was completed first, to prioritise assets and direct testing effort toward the highest likelihood-and-impact areas.

<p>
<img src="screenshots/01-risk-matrix.png" alt="Risk matrix"><br>
<em>The likelihood × impact risk matrix used to rate each identified risk.</em>
</p>

<p>
<img src="screenshots/02-asset-prioritisation.png" alt="Asset prioritisation"><br>
<em>Business assets ranked by value and criticality so the assessment could focus where it mattered most.</em>
</p>

<p>
<img src="screenshots/03-risk-assessment.png" alt="Risk assessment"><br>
<em>Risk assessment of the prioritised assets, each scored by likelihood and impact.</em>
</p>

<p>
<img src="screenshots/04-gantt-chart.png" alt="Project plan"><br>
<em>The project plan and timeline for the engagement.</em>
</p>

---

## Testing Evidence

The screenshots below document the authorised testing against the lab targets, grouped by assessment area. Sensitive values (credentials, addresses and tokens) have been redacted.

### Assessment infrastructure & social-engineering testing

A browser-exploitation framework (BeEF) was stood up on a lab server to assess how easily a staff browser could be engaged through a single link, and a simulated email was used to measure user-awareness exposure.

<p>
<img src="screenshots/05-lab-server-create.jpg" alt="Lab server provisioning"><br>
<em>Provisioning the lab server that would host the browser-engagement framework.</em>
</p>

<p>
<img src="screenshots/06-lab-server-marketplace.jpg" alt="Lab server marketplace"><br>
<em>Selecting the framework image from the hosting provider's marketplace.</em>
</p>

<p>
<img src="screenshots/07-lab-server-user-setup.jpg" alt="Lab server user setup"><br>
<em>Configuring the lab server's limited user account (email address redacted).</em>
</p>

<p>
<img src="screenshots/08-lab-server-plan.jpg" alt="Lab server plan"><br>
<em>Choosing the server region and plan for the lab.</em>
</p>

<p>
<img src="screenshots/09-lab-server-label.jpg" alt="Lab server label"><br>
<em>Naming the lab server and setting its root password (masked by the provider).</em>
</p>

<p>
<img src="screenshots/10-lab-server-create-confirm.png" alt="Lab server create"><br>
<em>Confirming creation of the lab server.</em>
</p>

<p>
<img src="screenshots/11-lab-server-running.png" alt="Lab server running"><br>
<em>The lab server running, with its public address details redacted.</em>
</p>

<p>
<img src="screenshots/12-framework-config-path.png" alt="Framework configuration path"><br>
<em>Locating the framework's configuration file on the lab server.</em>
</p>

<p>
<img src="screenshots/13-framework-config.png" alt="Framework configuration"><br>
<em>The framework configuration file, with the default credentials redacted.</em>
</p>

<p>
<img src="screenshots/14-framework-hooking-page.png" alt="Framework landing page"><br>
<em>The framework's landing page, served from the lab host.</em>
</p>

<p>
<img src="screenshots/15-shortened-link.png" alt="Shortened test link"><br>
<em>A shortened link used to make the test URL less obvious to a user (destination redacted).</em>
</p>

<p>
<img src="screenshots/16-social-engineering-email.png" alt="Simulated awareness email"><br>
<em>A simulated awareness email used to measure how staff respond to an unexpected link (recipient redacted).</em>
</p>

<p>
<img src="screenshots/17-browser-telemetry.png" alt="Engaged browser telemetry"><br>
<em>Telemetry collected from an engaged test browser — a demonstration of how much information a single click can expose (addresses and token redacted).</em>
</p>

<p>
<img src="screenshots/18-framework-modules.png" alt="Framework command modules"><br>
<em>The range of modules available once a browser is engaged, illustrating the potential business impact.</em>
</p>

### Credential-exposure testing (look-alike sign-in page)

A look-alike sign-in page (zPhisher) was hosted in the lab to demonstrate how credential exposure can occur and to support the awareness-training recommendations.

<p>
<img src="screenshots/19-se-service-selection.png" alt="Test page service selection"><br>
<em>Selecting which service the look-alike sign-in page would imitate (lab only).</em>
</p>

<p>
<img src="screenshots/20-se-hosting-options.png" alt="Test page hosting options"><br>
<em>Hosting and link options for the look-alike page (lab only).</em>
</p>

<p>
<img src="screenshots/21-se-login-page.png" alt="Look-alike sign-in page"><br>
<em>The look-alike sign-in page as a user would see it — a clear demonstration of credential-exposure risk.</em>
</p>

<p>
<img src="screenshots/22-se-redirect.png" alt="Redirect after submission"><br>
<em>After submitting, the user is redirected to the genuine site, which is why this kind of page is easy to miss.</em>
</p>

### Endpoint testing

Endpoint handling of an untrusted download was assessed against a dedicated lab host to demonstrate the impact of missing endpoint protection and the value of user awareness.

<p>
<img src="screenshots/23-endpoint-test-setup.png" alt="Endpoint test setup"><br>
<em>Preparing the endpoint test file and a simple host to serve it, in the lab.</em>
</p>

<p>
<img src="screenshots/24-endpoint-redirect.png" alt="Endpoint redirect"><br>
<em>Redirecting the engaged browser to the test download.</em>
</p>

<p>
<img src="screenshots/25-endpoint-download.png" alt="Untrusted download on test host"><br>
<em>The untrusted file downloading on the test host, showing the gap left by missing endpoint protection.</em>
</p>

<p>
<img src="screenshots/26-handler-config.png" alt="Handler configuration"><br>
<em>The listener configured to receive the test connection.</em>
</p>

<p>
<img src="screenshots/27-endpoint-session.png" alt="Session on the test host"><br>
<em>A session established with the test host after the file was run — a demonstration of the impact of running untrusted files.</em>
</p>

<p>
<img src="screenshots/28-file-transfer.png" alt="File transfer from test host"><br>
<em>Locating and transferring a file from the test host (the file contained sample data only).</em>
</p>

<p>
<img src="screenshots/29-data-parsing-script.png" alt="Data-parsing helper script"><br>
<em>A short Python helper written to tidy the collected sample data.</em>
</p>

### Network & authentication testing

The lab network was scanned and authentication strength was tested to demonstrate the need for strong passwords, account lockout and MFA.

<p>
<img src="screenshots/30-network-scan.png" alt="Network scan"><br>
<em>An Nmap scan of the lab network to identify reachable hosts and services.</em>
</p>

<p>
<img src="screenshots/31-authentication-test.png" alt="Authentication test"><br>
<em>A Hydra authentication-strength test against a lab service (result redacted) — evidence of why strong passwords, lockout and MFA matter.</em>
</p>

<p>
<img src="screenshots/32-wordlist-generation.png" alt="Wordlist generation"><br>
<em>Generating a test wordlist with Crunch for the authentication test.</em>
</p>

<p>
<img src="screenshots/33-service-access.png" alt="Target service access"><br>
<em>Confirming access to the target lab service after the authentication test.</em>
</p>

### Software vulnerability testing

An intentionally outdated service (vsFTPd 2.3.4) on a lab target was used to demonstrate the risk of unpatched software and the importance of patch management.

<p>
<img src="screenshots/34-service-vuln-console.png" alt="Service test console"><br>
<em>Starting the console used to test the intentionally outdated lab service.</em>
</p>

<p>
<img src="screenshots/35-service-vuln-module.png" alt="Service test module selection"><br>
<em>Selecting the test module that matches the outdated service.</em>
</p>

<p>
<img src="screenshots/36-service-vuln-version.png" alt="Service test version"><br>
<em>Targeting the specific vulnerable version running in the lab.</em>
</p>

<p>
<img src="screenshots/37-service-vuln-run.png" alt="Service test run"><br>
<em>Running the test against the lab target.</em>
</p>

<p>
<img src="screenshots/38-service-vuln-access.png" alt="Service test access confirmed"><br>
<em>Access confirmed on the lab target, demonstrating the real risk of leaving software unpatched.</em>
</p>

---

## Key findings

The assessment identified risks relating to:

- Phishing and credential theft
- Weak authentication and limited MFA coverage
- Inadequate access control
- Outdated software and patching gaps
- Malware containment readiness
- Limited centralised logging and monitoring
- Backup and recovery preparedness

## Recommendations

The proposed improvement plan included:

- Implement MFA and strengthen authentication controls
- Apply least-privilege access and complete regular access reviews
- Establish patching and vulnerability-management processes
- Centralise logs in Splunk and configure monitoring alerts
- Use pfSense firewall controls and Snort intrusion detection
- Improve phishing reporting and staff awareness
- Test incident-response, backup and recovery procedures

## Supporting documentation

The following deliverables, produced alongside the assessment, are included in the [`docs/`](docs) folder:

- **[Incident Response Plan](docs/Incident-Response-Plan.docx)** — detection, containment, eradication and recovery procedures across the six incident-response phases.
- **[Phishing Awareness Training](docs/Phishing-Awareness-Training.docx)** — the staff social-engineering and phishing-awareness training material that supports the awareness recommendation.
- **[Technical Documentation](docs/Technical-Documentation.docx)** — end-user setup guide for the environment: virtualisation, Windows Server / Active Directory, DNS, email security (SPF / DKIM / DMARC) and pfSense firewall configuration.

## What I learned

This project strengthened my ability to connect technical findings to operational risk. I practised prioritising issues, documenting evidence, explaining risk clearly, and developing realistic remediation actions.

## Ethical statement

All activity was completed in an authorised, simulated training environment. No testing was conducted against systems without explicit permission. Sensitive values in the screenshots above have been redacted.
