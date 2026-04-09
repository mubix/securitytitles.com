---
layout: fullwidth
title: Salary Heatmap
---

<div class="intro-section">

<h1>Salary Heatmap</h1>

<p>
Every role and level at a glance, color-coded by compensation band. Click any cell to jump to the full role detail. Filter by sector to see how pay differs across government, startups, and corporate employers.
</p>

<p style="background: var(--bg-tertiary); border: 1px solid var(--border-primary); border-radius: 6px; padding: 0.65rem 1rem; font-size: 0.85rem; color: var(--text-muted); max-width: var(--prose-max);">
<strong style="color: var(--text-secondary);">Note:</strong> This page is best viewed on a desktop or tablet. The heatmap compares 30+ roles across 7 career levels — a layout that doesn't translate well to phone-sized screens. On mobile, individual role pages provide a better experience.
</p>

</div>

<div class="heatmap-legend" id="heatmap-legend">
  <span class="table-controls-label">Scale:</span>
  <span class="hm-legend-swatch" data-band="1"></span><span class="hm-legend-label">&lt;$80k</span>
  <span class="hm-legend-swatch" data-band="2"></span><span class="hm-legend-label">$80-120k</span>
  <span class="hm-legend-swatch" data-band="3"></span><span class="hm-legend-label">$120-160k</span>
  <span class="hm-legend-swatch" data-band="4"></span><span class="hm-legend-label">$160-220k</span>
  <span class="hm-legend-swatch" data-band="5"></span><span class="hm-legend-label">$220-300k</span>
  <span class="hm-legend-swatch" data-band="6"></span><span class="hm-legend-label">$300-500k</span>
  <span class="hm-legend-swatch" data-band="7"></span><span class="hm-legend-label">$500k+</span>
</div>

<div class="heatmap-controls" id="heatmap-controls">
  <span class="table-controls-label">Sector:</span>
  <button class="tc-btn tc-active" data-sector="us_corporate">US Corporate</button>
  <button class="tc-btn" data-sector="us_startup">US Startup</button>
  <button class="tc-btn" data-sector="us_government">US Government</button>
  <button class="tc-btn" data-sector="us_bigtech">Big Tech (Mag7)</button>
</div>

<div class="table-responsive heatmap-table-wrap">
<table class="role-table heatmap-table" id="heatmap-table">
  <thead>
    <tr>
      <th class="attribute-header">Role</th>
      <th class="hm-level-col">Entry</th>
      <th class="hm-level-col">Junior</th>
      <th class="hm-level-col">Mid</th>
      <th class="hm-level-col">Senior</th>
      <th class="hm-level-col">Staff</th>
      <th class="hm-level-col">Sr. Staff</th>
      <th class="hm-level-col">Principal</th>
    </tr>
  </thead>
  <tbody>
    {% assign domains = "offense,defense,insider_threat,grc,privacy,iam,evm,appsec,cloudsec,forensics,cti,fraud,otsec,physec,leadership,consultant" | split: "," %}
    {% assign domain_labels = "Offensive Security,Defensive Security,Insider Threat,GRC,Privacy,IAM,EVM,AppSec,Cloud Security,Forensics,CTI,Cyber Fraud,OT Security,Physical Security,Leadership,Consulting" | split: "," %}
    {% assign domain_pages = "/offense,/defense,/defense,/grc,/grc,/iam,/specialized,/specialized,/specialized,/specialized,/specialized,/specialized,/specialized,/specialized,/leadership,/consultant" | split: "," %}

    {% for d in domains %}
      {% assign idx = forloop.index0 %}
      {% assign ddata = site.data[d] %}
      {% assign dlabel = domain_labels[idx] %}
      {% assign dpage = domain_pages[idx] %}

      <tr class="hm-domain-row">
        <td colspan="8" class="hm-domain-label" data-domain="{{ d }}">{{ dlabel }}</td>
      </tr>

      {% for role_entry in ddata %}
        {% assign role = role_entry[1] %}
        <tr class="hm-role-row" data-domain="{{ d }}">
          <td class="attribute-name hm-role-name">
            <a href="{{ dpage }}#{{ role.name | slugify }}">{{ role.name }}</a>
          </td>
          {% for level in role.levels %}
          <td class="hm-cell"
              data-gov="{{ level.salary.us_government }}"
              data-startup="{{ level.salary.us_startup }}"
              data-corp="{{ level.salary.us_corporate }}"
              data-bigtech="{{ level.salary.us_bigtech }}"
              data-title="{{ level.title }}">
            <a href="{{ dpage }}#{{ role.name | slugify }}" class="hm-cell-link">
              <span class="hm-salary" data-sector="us_corporate">{{ level.salary.us_corporate }}</span>
              <span class="hm-salary" data-sector="us_startup" style="display:none">{{ level.salary.us_startup }}</span>
              <span class="hm-salary" data-sector="us_government" style="display:none">{{ level.salary.us_government }}</span>
              <span class="hm-salary" data-sector="us_bigtech" style="display:none">{{ level.salary.us_bigtech }}</span>
              <span class="hm-title">{{ level.title }}</span>
            </a>
          </td>
          {% endfor %}
          {% assign remaining = 7 | minus: role.levels.size %}
          {% for i in (1..remaining) %}
          <td class="hm-cell hm-empty"></td>
          {% endfor %}
        </tr>
      {% endfor %}
    {% endfor %}
  </tbody>
</table>
</div>
