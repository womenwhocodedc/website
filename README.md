womenwhocodedc.com
=======

This is the repo for the public-facing DC chapter of Women Who Code. Edits to website should be made with feature branches. Other branches are as follows:

```master```: Branch kept in sync across members for changes others should have locally but aren't ready to go live yet.

```production```: Branch that has a webhook for Heroku. Don't automatically push to production, submit a pull request. Pushes to production should probably receive two :+1:s before getting submitted.

## Vhost
Craft is happier with a virtual host. I've aliased mine to ```womenwhocode.dev``` in my ```httpd-vhosts.conf``` file: 

  <VirtualHost *:80>
      ServerName womenwhocode.dev
      ServerAlias "womenwhocode.dev.192.168.7.72.xip.io"
      DocumentRoot '<path-to-craft>/site/public/'
      <Directory "<path-to-craft>/site/public/">
          Options Indexes FollowSymLinks
          AllowOverride All
          Order deny,allow
          Allow from all
      </Directory>
  </VirtualHost>