---
layout: default
title: Offensive Security Professional Titles
---

# Offensive Security Professional Titles

This page provides standardized job titles, responsibilities, and expectations for offensive security professionals. Use these frameworks to understand career progression, set role expectations, and benchmark compensation.

**How to use these tables:**
- Levels are displayed as columns for easy vertical comparison
- Scroll horizontally on mobile devices to see all levels
- Click section headers to navigate directly to each role

---

## Table of Contents

- [Penetration Testing](#penetration-testing)
- [Red Teaming - Analyst](#red-teaming---analyst)
- [Red Teaming - Engineer](#red-teaming---engineer)
- [Purple Teaming](#purple-teaming)
- [Offensive Security Management](#offensive-security-management)

---

{% for role in site.data.offense %}
{% assign role_data = role[1] %}

<h2 id="{{ role_data.name | slugify }}">{{ role_data.name }}</h2>

<p><em>{{ role_data.description }}</em></p>

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
    <!-- General Description -->
    <tr>
      <td class="attribute-name"><strong>General Description</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.general_description }}</td>
      {% endfor %}
    </tr>
    
    <!-- Primary Responsibilities -->
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
    
    <!-- Required Skills -->
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
    
    <!-- Preferred Skills -->
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
    
    <!-- Mentorship Requirements -->
    <tr>
      <td class="attribute-name"><strong>Mentorship Requirements</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.mentorship_requirements }}</td>
      {% endfor %}
    </tr>
    
    <!-- Impact Scope -->
    <tr>
      <td class="attribute-name"><strong>Impact Scope</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.impact_scope }}</td>
      {% endfor %}
    </tr>
    
    <!-- Autonomy and Decision Authority -->
    <tr>
      <td class="attribute-name"><strong>Autonomy &amp; Decision Authority</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.autonomy_decision_authority }}</td>
      {% endfor %}
    </tr>
    
    <!-- Communication and Stakeholder Responsibility -->
    <tr>
      <td class="attribute-name"><strong>Communication &amp; Stakeholder Responsibility</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.communication_stakeholder }}</td>
      {% endfor %}
    </tr>
    
    <!-- Degree or Equivalent Experience -->
    <tr>
      <td class="attribute-name"><strong>Degree or Equivalent Experience</strong></td>
      {% for level in role_data.levels %}
      <td>{{ level.degree_equivalent }}</td>
      {% endfor %}
    </tr>
    
    <!-- Applicable Certifications -->
    <tr>
      <td class="attribute-name"><strong>Applicable Certifications</strong></td>
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
    
    <!-- Typical Salary - US Government -->
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Government</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_government }}</td>
      {% endfor %}
    </tr>
    
    <!-- Typical Salary - US Startup -->
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Startup</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_startup }}</td>
      {% endfor %}
    </tr>
    
    <!-- Typical Salary - US Corporate -->
    <tr class="salary-row">
      <td class="attribute-name"><strong>Salary: US Corporate</strong></td>
      {% for level in role_data.levels %}
      <td class="salary-cell">{{ level.salary.us_corporate }}</td>
      {% endfor %}
    </tr>
  </tbody>
</table>
</div>

<p><a href="#table-of-contents">↑ Back to top</a></p>

---

{% endfor %}

## About This Framework

This standardization framework is designed to:

1. **Provide clarity** on role expectations at each level
2. **Enable fair compensation** through transparent salary benchmarking
3. **Support career development** by clearly defining progression paths
4. **Facilitate hiring** with consistent job descriptions and requirements

### Salary Notes

- **US Government**: Based on General Schedule (GS) and Senior Executive Service (SES) pay scales. Actual compensation varies by locality pay area.
- **US Startup**: Reflects venture-backed companies. Equity compensation can significantly increase total compensation.
- **US Corporate**: Reflects Fortune 500 and large enterprise compensation. May include bonus structures of 10-30%+.

All salary figures are estimates based on market data and may vary significantly by geography, company size, industry, and individual negotiation.

### Contributing

This is an open-source effort to standardize security titles. [Join the discussion](https://github.com/mubix/securitytitles.com/discussions) to help improve these frameworks.

---

<style>
.table-responsive {
  overflow-x: auto;
  margin-bottom: 1.5rem;
}

.role-table {
  width: 100%;
  border-collapse: collapse;
  font-size: 0.9rem;
  min-width: 1200px;
}

.role-table th,
.role-table td {
  border: 1px solid #ddd;
  padding: 12px 10px;
  vertical-align: top;
  text-align: left;
}

.role-table thead th {
  background-color: #2c3e50;
  color: white;
  font-weight: 600;
  position: sticky;
  top: 0;
}

.attribute-header {
  min-width: 180px;
  width: 180px;
}

.level-header {
  min-width: 200px;
  text-align: center !important;
}

.attribute-name {
  background-color: #f8f9fa;
  font-weight: 500;
  min-width: 180px;
  width: 180px;
}

.role-table tbody tr:nth-child(even) {
  background-color: #fafafa;
}

.role-table tbody tr:hover {
  background-color: #f0f7ff;
}

.compact-list {
  margin: 0;
  padding-left: 18px;
  font-size: 0.85rem;
}

.compact-list li {
  margin-bottom: 4px;
  line-height: 1.4;
}

.salary-row {
  background-color: #e8f5e9 !important;
}

.salary-row:hover {
  background-color: #c8e6c9 !important;
}

.salary-cell {
  font-weight: 500;
  color: #2e7d32;
  white-space: nowrap;
}

/* Responsive adjustments */
@media (max-width: 768px) {
  .role-table {
    font-size: 0.8rem;
  }
  
  .role-table th,
  .role-table td {
    padding: 8px 6px;
  }
  
  .attribute-header,
  .attribute-name {
    min-width: 140px;
    width: 140px;
  }
  
  .level-header {
    min-width: 160px;
  }
}

/* Print styles */
@media print {
  .table-responsive {
    overflow: visible;
  }
  
  .role-table {
    font-size: 0.7rem;
    min-width: auto;
  }
  
  .role-table th,
  .role-table td {
    padding: 4px;
  }
}
</style>