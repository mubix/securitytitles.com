---
layout: fullwidth
title: Security Consulting Professional Titles
---

<div class="intro-section">

<h1>Security Consulting Professional Titles</h1>

<p>
Standardized job titles, responsibilities, and expectations for security consulting professionals. This covers the Big 4 consulting career ladder (Deloitte, EY, KPMG, PwC), mid-tier and boutique consultancies, MSSPs, and the growing vCISO and Fractional CISO market.
</p>

<p><strong>How to use these tables:</strong> Levels are displayed as columns for easy vertical comparison. The attribute column stays fixed while you scroll horizontally.</p>

<nav class="toc-nav" id="table-of-contents">
  <strong>Jump to:</strong>
  <ul>
    <li><a href="#security-consultant">Security Consultant (Big 4 Ladder)</a></li>
    <li><a href="#virtual-ciso-vciso">Virtual CISO (vCISO)</a></li>
    <li><a href="#fractional-ciso">Fractional CISO</a></li>
  </ul>
</nav>

</div>

{% for role in site.data.consultant %}
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
    
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: Big Tech (Mag7)</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_bigtech }}</td>
      {% endfor %}
    </tr>
  </tbody>
</table>
</div>

<a href="#table-of-contents" class="back-to-top">&#8593; Back to navigation</a>

</div>

{% endfor %}

<div class="footer-section" markdown="1">

## About This Framework

### Consulting Career Context

| Track | Focus | Typical Employers |
|-------|-------|-------------------|
| **Security Consultant** | Multi-client advisory, assessments, program development | Big 4 (Deloitte, EY, KPMG, PwC), Accenture, Optiv, Coalfire, boutique firms |
| **Virtual CISO (vCISO)** | Part-time CISO services through a firm, 5-15 clients | MSSPs, vCISO firms (CISO Global, Omega Systems), consultancies |
| **Fractional CISO** | Independent part-time CISO, 2-5 clients, deeper engagement | Independent practice, small boutiques |

### vCISO vs. Fractional CISO

| Dimension | vCISO | Fractional CISO |
|-----------|-------|-----------------|
| **Employment** | Employed by a firm or MSSP | Independent or small boutique |
| **Client assignment** | Assigned by the firm; may serve 5-15+ clients | Self-selected; typically 2-5 clients |
| **Engagement depth** | Often advisory and compliance-focused | Deeper integration; C-suite participation |
| **Revenue model** | Salary + bonus; firm bills for your time | Direct retainer; keeps full revenue |
| **Typical background** | 10-15+ years; firm provides methodology | 15-25+ years; former full-time CISO |

### Salary Notes

| Sector | Notes |
|--------|-------|
| **US Government** | Based on General Schedule (GS) and SES pay scales. Government consulting pay is typically lower than private sector. |
| **US Startup** | Reflects venture-backed companies and smaller consultancies. May include equity at partner level. |
| **US Corporate** | Reflects Big 4 and large consultancy compensation. Partner compensation includes profit-sharing. |
| **Big Tech (Mag7)** | Total compensation at Alphabet, Amazon, Apple, Meta, Microsoft, Nvidia, Tesla. Security consulting roles are rare at Big Tech; these ranges reflect internal security advisory equivalents. |

All salary figures are estimates based on market data and may vary significantly by geography, firm size, and individual negotiation. Big 4 Partner compensation is highly variable based on practice performance and profit-sharing.

### Contributing

This is an open-source effort to standardize security titles. [Join the discussion](https://github.com/mubix/securitytitles.com/discussions) to help improve these frameworks.

</div>
