---
layout: default
title: Home
nav_order: 1
last_modified_date: 2024-09-20 11:39
---

#### Release Candidate 2
{: #top }

# Jump King Workshop Documentation
{: .mt-0 .fs-8 }

This is the official in-depth documentation for creating all kinds of user-generated content for Jump King.
{: .fs-6 .fw-300 .my-4 }

<h2 style="display:inline-block;">What's new</h2>
{% assign count = 0 %}
{% for log in site.data.changelog.logs reversed %}
{% assign count = count | plus: 1 %}
{% if count <= 3 %}
<dl>
    <dt>{{ log.name }}</dt>
    <dd>
    {% for change in log.changes %}
        <p>{{ change }}</p>
    {% endfor %}
    </dd>
</dl>
{% endif %}
{% endfor %}
{% if count > 3 %}
<a class="btn" href="{{ site.baseurl }}/changelogs/" style="margin-left: 10em;">Older changes</a>
{% endif %}

<br>

{: .disclaimer }
> The current documentation is currently **not complete** and it *could be* subject to variation, since Jump King is back in active development. Any further modification of the documentation will be listed above.

## Usage

On the **left side** of your screen you can find the **table of contents**, from there you can navigate to all the different details you might need. If you ever need something specific, you can use the **search bar up top** your screen to find what you need.

## Getting started

Head over in the [Getting started]({{ site.baseurl }}/getting-started/) page to get started on your journey!
