---
layout: fullwidth
title: Specialized Security Professional Titles
---

<div class="intro-section">

<h1>Specialized Security Professional Titles</h1>
<br>
This page provides standardized job titles, responsibilities, and expectations for specialized and cross-functional security professionals. These roles often span traditional offensive/defensive boundaries or focus on specific security domains.
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
    <li><a href="#evm-analyst">EVM Analyst</a></li>
    <li><a href="#evm-engineer">EVM Engineer</a></li>
    <!-- Future sections -->
    <!--
    <li><a href="#appsec">Application Security</a></li>
    <li><a href="#cloudsec">Cloud Security</a></li>
    <li><a href="#forensics">Digital Forensics</a></li>
    <li><a href="#cti">Cyber Threat Intelligence</a></li>
    <li><a href="#grc">GRC</a></li>
    <li><a href="#ot-security">OT Security</a></li>
    <li><a href="#physical-security">Physical Security</a></li>
    -->
  </ul>
</nav>

</div>

{% for role in site.data.evm %}
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

### Salary Notes

| Sector | Notes |
|--------|-------|
| **US Government** | Based on General Schedule (GS) and Senior Executive Service (SES) pay scales. Actual compensation varies by locality pay area. |
| **US Startup** | Reflects venture-backed companies. Equity compensation can significantly increase total compensation. |
| **US Corporate** | Reflects Fortune 500 and large enterprise compensation. May include bonus structures of 10-30%+. |

All salary figures are estimates based on market data and may vary significantly by geography, company size, industry, and individual negotiation.

### Coming Soon

Additional specialized roles in development:
- Application Security (AppSec)
- Cloud Security (CloudSec)
- Digital Forensics
- Cyber Threat Intelligence (CTI)
- Governance, Risk & Compliance (GRC)
- OT Security
- Physical Security

### Contributing

This is an open-source effort to standardize security titles. [Join the discussion](https://github.com/mubix/securitytitles.com/discussions) to help improve these frameworks.

</div>