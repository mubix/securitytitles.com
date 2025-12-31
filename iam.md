---
layout: fullwidth
title: IAM Professional Titles
---

<div class="intro-section">

<h1>Identity and Access Management Professional Titles</h1>
<br>
This page provides standardized job titles, responsibilities, and expectations for IAM professionals. These roles ensure secure identity lifecycle management, authentication, privileged access control, and identity threat detection across the enterprise.
<br>
<b>How to use these tables:</b>
<br>
<ul>
  <li>Levels are displayed as columns for easy vertical comparison</li>
  <li>The attribute column stays fixed while you scroll horizontally</li>
  <li>Scroll horizontally to compare across all levels</li>
</ul>

<nav class="toc-nav" id="table-of-contents">
  <strong>Jump to:</strong>
  <ul>
    <li><a href="#iga-analyst">IGA Analyst</a></li>
    <li><a href="#access-management-engineer">Access Management Engineer</a></li>
    <li><a href="#pam-engineer">PAM Engineer</a></li>
    <li><a href="#directory-services-engineer">Directory Services Engineer</a></li>
    <li><a href="#ciam-engineer">CIAM Engineer</a></li>
    <li><a href="#iam-architect">IAM Architect</a></li>
    <li><a href="#identity-security-analyst">Identity Security Analyst</a></li>
    <li><a href="#identity-security-engineer">Identity Security Engineer</a></li>
  </ul>
</nav>

</div>

{% for role in site.data.iam %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

<div class="table-responsive">
<table class="role-table">
  <thead>
    <tr>
      <th class="attribute-header">Attribute</th>
      {% for level in role_data.levels %}
      <th class="level-header">{{ level.title }}</th>
      {% endfor %}
    </tr>
  </thead>
  <tbody>
    <tr>
      <td class="attribute-name"><strong>General Description</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.general_description }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Primary Responsibilities</strong></td>
      {% for level in role_data.levels %}
      <td>
        <ul class="compact-list">
          {% for resp in level.primary_responsibilities %}
          <li>{{ resp }}</li>
          {% endfor %}
        </ul>
      </td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Required Skills</strong></td>
      {% for level in role_data.levels %}
      <td>
        <ul class="compact-list">
          {% for skill in level.required_skills %}
          <li>{{ skill }}</li>
          {% endfor %}
        </ul>
      </td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Preferred Skills</strong></td>
      {% for level in role_data.levels %}
      <td>
        <ul class="compact-list">
          {% for skill in level.preferred_skills %}
          <li>{{ skill }}</li>
          {% endfor %}
        </ul>
      </td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Mentorship Requirements</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.mentorship_requirements }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Impact Scope</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.impact_scope }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Autonomy &amp; Decision Authority</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.autonomy_decision_authority }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Communication &amp; Stakeholders</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.communication_stakeholder }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Degree / Experience</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.degree_equivalent }}</td>
      {% endfor %}
    </tr>
    
    <tr>
      <td class="attribute-name"><strong>Certifications</strong></td>
      {% for level in role_data.levels %}
      <td>
        <ul class="compact-list">
          {% for cert in level.certifications %}
          <li>{{ cert }}</li>
          {% endfor %}
        </ul>
      </td>
      {% endfor %}
    </tr>
    
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Gov't</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_government }}</td>
      {% endfor %}
    </tr>
    
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Startup</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_startup }}</td>
      {% endfor %}
    </tr>
    
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Corporate</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_corporate }}</td>
      {% endfor %}
    </tr>
  </tbody>
</table>
</div>

<a href="#table-of-contents" class="back-to-top">↑ Back to navigation</a>

</div>

{% endfor %}

<div class="footer-section" markdown="1">

## About This Framework

This standardization framework is designed to:

1. **Provide clarity** on role expectations at each level
2. **Enable fair compensation** through transparent salary benchmarking
3. **Support career development** by clearly defining progression paths
4. **Facilitate hiring** with consistent job descriptions and requirements

### IAM Domain Overview

| Domain | Focus | Key Technologies |
|--------|-------|------------------|
| **IGA (Identity Governance & Administration)** | Lifecycle management, provisioning, role management, certification, SoD | SailPoint, Saviynt, Oracle Identity Governance |
| **Access Management** | Authentication, MFA, SSO, federation, adaptive access | Okta, Azure AD/Entra, Ping, ForgeRock |
| **PAM (Privileged Access Management)** | Privileged accounts, vaulting, session recording, JIT access | CyberArk, BeyondTrust, Delinea |
| **Directory Services** | AD, LDAP, identity stores, synchronization | Active Directory, Azure AD, LDAP directories |
| **CIAM (Customer Identity)** | Customer authentication, social login, consent, privacy | Auth0, Okta CIC, ForgeRock, Ping |
| **IAM Architecture** | Cross-domain integration, enterprise identity strategy, zero trust | Spans all domains |
| **Identity Security (ITDR)** | Identity threat detection, credential attack detection, identity analytics | CrowdStrike, Microsoft, Semperis, specialized ITDR |

### Expanding IAM Specializations

These specializations scale with level across the core tracks:

| Specialization | Where It Appears |
|----------------|------------------|
| Machine Identity & Service Accounts | Senior+ across IGA, PAM, Architect |
| Secrets Management | Senior+ PAM, Architect; DevSecOps overlap |
| Certificate & PKI Management | Senior+ Directory Services, Architect |
| Identity Proofing / Verification | Senior+ CIAM, IGA |
| Authorization Management (OPA, XACML) | Senior+ Access Management, Architect |
| Cloud IAM (AWS, Azure, GCP) | Mid+ across most tracks |
| SaaS Access Management | Senior+ IGA, Architect |

### Related Functions

| Function | Relationship to IAM |
|----------|---------------------|
| **Security Engineering** | Implements security controls; IAM provides identity infrastructure |
| **GRC** | Defines compliance requirements; IAM implements and evidences controls |
| **SOC** | Monitors for threats; Identity Security provides identity-specific detection |
| **IT Operations** | Manages infrastructure; IAM manages identity layer |

### Salary Notes

| Sector | Notes |
|--------|-------|
| **US Government** | Based on General Schedule (GS) and Senior Executive Service (SES) pay scales. Actual compensation varies by locality pay area. |
| **US Startup** | Reflects venture-backed companies. Equity compensation can significantly increase total compensation. |
| **US Corporate** | Reflects Fortune 500 and large enterprise compensation. May include bonus structures of 10-30%+. |

All salary figures are estimates based on market data and may vary significantly by geography, company size, industry, and individual negotiation.

### Contributing

This is an open-source effort to standardize security titles. [Join the discussion](https://github.com/mubix/securitytitles.com/discussions) to help improve these frameworks.

</div>