# adl (apache directory listing)
# Copy or move  the _htaccess file to .htaccess and adl should work
mv _htaccess .htaccess
If and only if your apache2 configurations has the following:

<pre>
# Debian 10*
# Place this file in /etc/apache2/sites-available
# Make sure to create a logs directory in "mkdir /var/www/html/logs"
<VirtualHost *:80>
        #ServerAdmin webmaster@localhost
        DocumentRoot /var/www/html
        <Directory "/var/www/html">
                Options +Indexes
                 IndexOptions FancyIndexing VersionSort NameWidth=*
                AllowOverride All
                Require all granted
        </Directory>

        ErrorLog /var/www/html/logs/error.log
        LogFormat "%h %l %u %t \"%r\" %>s %b" common
        CustomLog /var/www/html/logs/access_log common
</VirtualHost>
</pre>
