---
layout: default
title: All changelogs
---

# All documentation changelogs
{: .fs-8 .mb-5 }

{% for log in site.data.changelog.logs reversed %}
<dl>
    <dt>{{ log.name }}</dt>
    <dd>
    {% for change in log.changes %}
        <p>{{ change }}</p>
    {% endfor %}
    </dd>
</dl>
{% endfor %}