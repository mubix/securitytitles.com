---
layout: fullwidth
title: Specialized Security Professional Titles
---

<div class="intro-section">

<h1>Specialized Security Professional Titles</h1>

<p>
Standardized job titles, responsibilities, and expectations for specialized and cross-functional security professionals. These roles often span traditional offensive/defensive boundaries or focus on specific security domains.
</p>

<p><strong>How to use these tables:</strong> Levels are displayed as columns for easy vertical comparison. The attribute column stays fixed while you scroll horizontally.</p>

<nav class="toc-nav" id="table-of-contents">
  <strong>Jump to:</strong>
  <ul>
    <li><a href="#evm-analyst">EVM Analyst</a></li>
    <li><a href="#evm-engineer">EVM Engineer</a></li>
    <li><a href="#appsec-engineer">AppSec Engineer</a></li>
    <li><a href="#appsec-architect">AppSec Architect</a></li>
    <li><a href="#cloud-security-engineer">Cloud Security Engineer</a></li>
    <li><a href="#cloud-security-architect">Cloud Security Architect</a></li>
    <li><a href="#forensic-analyst">Forensic Analyst</a></li>
    <li><a href="#cti-analyst">CTI Analyst</a></li>
    <li><a href="#cti-engineer">CTI Engineer</a></li>
    <li><a href="#fraud-analyst">Fraud Analyst</a></li>
    <li><a href="#fraud-engineer">Fraud Engineer</a></li>
    <li><a href="#ot-security-engineer">OT Security Engineer</a></li>
    <li><a href="#ot-security-architect">OT Security Architect</a></li>
    <li><a href="#physical-security-engineer">Physical Security Engineer</a></li>
    <li><a href="#physical-security-architect">Physical Security Architect</a></li>
  </ul>
</nav>

</div>

<!-- Enterprise Vulnerability Management Section -->
<div class="domain-header domain-header--evm">
  <h2>Enterprise Vulnerability Management (EVM)</h2>
  <p>Strategic vulnerability identification, risk-based prioritization, and remediation enablement</p>
</div>

{% for role in site.data.evm %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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

<!-- Application Security Section -->
<div class="domain-header domain-header--appsec">
  <h2>Application Security (AppSec / Product Security)</h2>
  <p>Secure software development, security testing, threat modeling, and developer enablement</p>
</div>

{% for role in site.data.appsec %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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

<!-- Cloud Security Section -->
<div class="domain-header domain-header--cloudsec">
  <h2>Cloud Security (CloudSec)</h2>
  <p>Multi-cloud security architecture, IAM, DevSecOps, and enabling secure cloud adoption</p>
</div>

{% for role in site.data.cloudsec %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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

<!-- Digital Forensics Section -->
<div class="domain-header domain-header--forensics">
  <h2>Digital Forensics</h2>
  <p>Evidence acquisition, artifact analysis, incident response forensics, and legal proceedings support</p>
</div>

{% for role in site.data.forensics %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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

<!-- Cyber Threat Intelligence Section -->
<div class="domain-header domain-header--cti">
  <h2>Cyber Threat Intelligence (CTI)</h2>
  <p>Threat actor tracking, organization-specific risk analysis, and intelligence-driven defense</p>
</div>

{% for role in site.data.cti %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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

<!-- Cyber Fraud Section -->
<div class="domain-header domain-header--fraud">
  <h2>Cyber Fraud</h2>
  <p>Fraud detection, investigation, prevention, and fraud platform engineering across financial crime and account security</p>
</div>

{% for role in site.data.fraud %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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
    <tr><td class="attribute-name"><strong>General Description</strong></td>{% for level in role_data.levels %}<td>{{ level.general_description }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Primary Responsibilities</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for resp in level.primary_responsibilities %}<li>{{ resp }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Required Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.required_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Preferred Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.preferred_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Mentorship Requirements</strong></td>{% for level in role_data.levels %}<td>{{ level.mentorship_requirements }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Impact Scope</strong></td>{% for level in role_data.levels %}<td>{{ level.impact_scope }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Autonomy &amp; Decision Authority</strong></td>{% for level in role_data.levels %}<td>{{ level.autonomy_decision_authority }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Communication &amp; Stakeholders</strong></td>{% for level in role_data.levels %}<td>{{ level.communication_stakeholder }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Degree / Experience</strong></td>{% for level in role_data.levels %}<td>{{ level.degree_equivalent }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Certifications</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for cert in level.certifications %}<li>{{ cert }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Gov't</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_government }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Startup</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_startup }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Corporate</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_corporate }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: Big Tech (Mag7)</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_bigtech }}</td>{% endfor %}</tr>
  </tbody>
</table>
</div>

<a href="#table-of-contents" class="back-to-top">&#8593; Back to navigation</a>

</div>

{% endfor %}

<!-- OT Security Section -->
<div class="domain-header domain-header--otsec">
  <h2>Operational Technology Security (OT Security)</h2>
  <p>ICS/SCADA security, industrial protocol protection, IT/OT convergence, and critical infrastructure defense</p>
</div>

{% for role in site.data.otsec %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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
    <tr><td class="attribute-name"><strong>General Description</strong></td>{% for level in role_data.levels %}<td>{{ level.general_description }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Primary Responsibilities</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for resp in level.primary_responsibilities %}<li>{{ resp }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Required Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.required_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Preferred Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.preferred_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Mentorship Requirements</strong></td>{% for level in role_data.levels %}<td>{{ level.mentorship_requirements }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Impact Scope</strong></td>{% for level in role_data.levels %}<td>{{ level.impact_scope }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Autonomy &amp; Decision Authority</strong></td>{% for level in role_data.levels %}<td>{{ level.autonomy_decision_authority }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Communication &amp; Stakeholders</strong></td>{% for level in role_data.levels %}<td>{{ level.communication_stakeholder }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Degree / Experience</strong></td>{% for level in role_data.levels %}<td>{{ level.degree_equivalent }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Certifications</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for cert in level.certifications %}<li>{{ cert }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Gov't</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_government }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Startup</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_startup }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Corporate</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_corporate }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: Big Tech (Mag7)</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_bigtech }}</td>{% endfor %}</tr>
  </tbody>
</table>
</div>

<a href="#table-of-contents" class="back-to-top">&#8593; Back to navigation</a>

</div>

{% endfor %}

<!-- Physical Security Section -->
<div class="domain-header domain-header--physec">
  <h2>Physical Security</h2>
  <p>Converged physical-cyber security engineering, access control systems, surveillance, and facility security architecture</p>
</div>

{% for role in site.data.physec %}
{% assign role_data = role[1] %}

<div class="table-section">

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p>{{ role_data.description }}</p>

{% if role_data.nice_mapping %}
<div class="nice-mapping">
  <span class="nice-label">NICE Framework:</span>
  {% for wr in role_data.nice_mapping.work_roles %}
  <span class="nice-role">{{ wr.id }} {{ wr.name }}</span>
  {% endfor %}
  {% if role_data.nice_mapping.work_roles.size == 0 %}
  <span class="nice-role">No direct mapping</span>
  {% endif %}
  <span class="nice-strength nice-strength--{{ role_data.nice_mapping.strength }}">{{ role_data.nice_mapping.strength }}</span>
  {% if role_data.nice_mapping.notes != "" %}
  <span class="nice-note">{{ role_data.nice_mapping.notes }}</span>
  {% endif %}
</div>
{% endif %}

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
    <tr><td class="attribute-name"><strong>General Description</strong></td>{% for level in role_data.levels %}<td>{{ level.general_description }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Primary Responsibilities</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for resp in level.primary_responsibilities %}<li>{{ resp }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Required Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.required_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Preferred Skills</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for skill in level.preferred_skills %}<li>{{ skill }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Mentorship Requirements</strong></td>{% for level in role_data.levels %}<td>{{ level.mentorship_requirements }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Impact Scope</strong></td>{% for level in role_data.levels %}<td>{{ level.impact_scope }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Autonomy &amp; Decision Authority</strong></td>{% for level in role_data.levels %}<td>{{ level.autonomy_decision_authority }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Communication &amp; Stakeholders</strong></td>{% for level in role_data.levels %}<td>{{ level.communication_stakeholder }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Degree / Experience</strong></td>{% for level in role_data.levels %}<td>{{ level.degree_equivalent }}</td>{% endfor %}</tr>
    <tr><td class="attribute-name"><strong>Certifications</strong></td>{% for level in role_data.levels %}<td><ul class="compact-list">{% for cert in level.certifications %}<li>{{ cert }}</li>{% endfor %}</ul></td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Gov't</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_government }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Startup</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_startup }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: US Corporate</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_corporate }}</td>{% endfor %}</tr>
    <tr class="salary-row"><td class="attribute-name"><strong>Salary: Big Tech (Mag7)</strong></td>{% for level in role_data.levels %}<td class="salary-cell">{{ level.salary.us_bigtech }}</td>{% endfor %}</tr>
  </tbody>
</table>
</div>

<a href="#table-of-contents" class="back-to-top">&#8593; Back to navigation</a>

</div>

{% endfor %}

<div class="footer-section" markdown="1">

## About This Framework

This standardization framework is designed to:

1. **Provide clarity** on role expectations at each level
2. **Enable fair compensation** through transparent salary benchmarking
3. **Support career development** by clearly defining progression paths
4. **Facilitate hiring** with consistent job descriptions and requirements

### Specialized Role Relationships

| Domain | Focus | Relationship |
|--------|-------|--------------|
| **EVM** | Infrastructure vulnerabilities, scanning platforms, risk prioritization | Partners with AppSec on application vulns found via DAST |
| **AppSec** | Application code, SSDLC, secure design, developer enablement | Partners with EVM on remediation tracking |
| **Cloud Security** | Cloud infrastructure, platform security, IAM | AppSec focuses on app logic; CloudSec on platform |
| **Digital Forensics** | Evidence acquisition, artifact analysis, legal support | Supports IR with deep-dive analysis; coordinates with legal |
| **CTI** | Threat actors, organization-specific risk, intel-driven defense | Feeds detection engineering; correlates internal data with external threats |
| **Cyber Fraud** | Account takeover, payment fraud, BEC, transaction fraud detection | Partners with SOC on alert triage; coordinates with legal on criminal referrals |
| **OT Security** | ICS/SCADA security, industrial protocols, IT/OT convergence | Partners with Security Engineering on network segmentation; coordinates with facilities |
| **Physical Security** | Converged physical-cyber, access control, surveillance systems | Partners with IT on network security for physical devices; coordinates with facilities |

### Salary Notes

| Sector | Notes |
|--------|-------|
| **US Government** | Based on General Schedule (GS) and Senior Executive Service (SES) pay scales. Actual compensation varies by locality pay area. |
| **US Startup** | Reflects venture-backed companies. Equity compensation can significantly increase total compensation. |
| **US Corporate** | Reflects Fortune 500 and large enterprise compensation. May include bonus structures of 10-30%+. |

All salary figures are estimates based on market data and may vary significantly by geography, company size, industry, and individual negotiation.

### Coming Soon

Additional specialized roles in development:
- Information Protection

### Contributing

This is an open-source effort to standardize security titles. [Join the discussion](https://github.com/mubix/securitytitles.com/discussions) to help improve these frameworks.

</div>
