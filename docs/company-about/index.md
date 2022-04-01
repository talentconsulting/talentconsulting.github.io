---
category: Company
pagetype: Index
icon: fas fa-address-card fa-2x
description: A bit about us and the roles currently available
order: 1
---

## About us
 
> The documents in this section detail how we got here and our international side of the business
 
{% assign pages = site.pages
  | where: "category", "Company"
  | where: "type", "About"
  | group_by: "type" %}
 
{% for page in pages %}
## {{ page.name }}

<div class="grid is-fibonacci">
    {% for item in page.items %}
        {% if item.pagetype != "Index"%}
    <div class="grid-item">
        <div class="columns is-mobile is-gapless has-box-shadow-heavy has-border-radius-large has-overflow-hidden is-relative"
            data-bi-name="card">
            <div class="column is-4">
                <div class="is-flex has-flex-align-items-center has-flex-justify-content-center is-full-height"
                    style="background-color: #018EAC;">
                    <span aria-hidden="true">
                        <i class="{{ item.icon }}"></i>
                    </span>
                </div>
            </div>
            <div class="column is-8 has-body-background">
                <div class="has-padding-medium">
                    <a href="{{ item.url | relative_url }}"  class="is-block stretched-link" data-linktype="absolute-path">
                        <h3 id="{{ item.title | remove: ' ' }}" class="is-size-large">{{ item.title }}</h3>
                        <p class="subIndex">{{item.description}}</p>
                    </a>
                </div>
            </div>
        </div>
    </div>
        {% endif %}
    {% endfor %}
</div>
{% endfor %}