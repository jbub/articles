# Django web deployment notes

Things not to forget when deploying a django web application.

## Checklist

### Django related
* 404, 500 pages
* cron cleanup job: manage.py cleanup
* set SESSION\_COOKIE\_AGE
* set ADMINS and MANAGERS
* DEBUG = False
* check and test emails
* cache headers
* cache static files
* set project domain and name in sites application

### Lighttpd related

* gzip
* expire headers
* logs
* project_name.conf
* include project_name.conf to projects.conf
* conf/project_name.conf

### Seo related
* analytics, webmaster tools
* favicons
* robots.txt
* sitemap.xml
* meta tags and headers

### Website related
* noscript message

### Applications

#### django-tinymce

In order to work with multiple domains or subdomains, following needs to be done.
* add document.domain to tiny\_mce\_popup.js
* add document.domain to templates with tinymce

```
{% extends "admin/change_form.html" %}

{% block extrahead %}
    <script type="text/javascript">document.domain = 'mydomain.com';</script>
    {{ block.super }}
{% endblock %}
```
	