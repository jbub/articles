# Django web deployment notes

Things not to forget when deploying a django web application.

## Checklist

### Django related
* 404, 500 pages
* cron for deleting sessions: manage.py cleanup
* DEBUG = False
* check and test emails, edit ADMINS and MANAGERS
* cache headers
* cache static files

### Lighttpd

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
* meta tags





