Hello-world project for building and deploying net-accessible web-app.

— Build Django web-app (http://docs.djangoproject.com/en/4.2/intro/tutorial01/)
BE( 1.Base —> 2.DB) —> 3.FEx2 —> 4.Tests —> 5.FE+x2 —> 6.Packaging
1. Setup basic html app (URLconf, views)
2. Setup sys tables, app models
3. Admin page, views (templates, non-hard urls, namespacing)
4. *skip*
5. Static, styles
6. *skip*


— Deploy (https://youtu.be/frEjX1DNSpc)
0.Domain —> 1.Server —> 2.Router Forwarding
0. Domain
- Static IP
- Buy domain (nic.ru)
- DNS host (cloudflare.com)
- Delegate DNS, Specify local IP

1. Server
1) Prerequisites:
- Web-app: Python, django
- wsgi interface: Visual C++ 14, mod-wsgi
- Web-server: Apache

2) Deploy:
- settings.py:
DEBUG = False
ALLOWED_HOSTS = ['localhost', '<domain>', '<specific localhost>']

- http.conf:
Listen 8080 #Listen local Port 
ServerName akad0.ru #Domain name

<Paste CMD output: 'mod_wsgi-express module-config'>
WSGIScriptAlias / <path to project's wsgi.py>
WSGIPythonPath <path to project folder (where manage.py lies)>

<Directory <path to wsgi.py's folder>>
  <Files wsgi.py>
    Require all granted
  </Files>
</Directory>

Alias /static <<path to collected static folder>>
  <Directory <path to collected static folder>>
    Require all granted
  </Directory>

- Collect static
CMD: python manage.py collectstatic

2. Router Forwarding
- Setup ports
Local IP Address is in windows connection properties.
Local port is the same as specified within httpd.conf
External specified by DNS (80 by default) - https://developers.cloudflare.com/fundamentals/get-started/reference/network-ports/



//Local IP points on the router — not the machine itself. Port does.
