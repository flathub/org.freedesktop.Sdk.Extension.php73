# org.freedesktop.Sdk.Extension.php73

This extension adds PHP support to Flatpak.

PHP installs to `/usr/lib/sdk/php73` inside the sandbox.

Example Visual Studio Code Configuration

```json
"php.validate.executablePath": "/usr/lib/sdk/php73/bin/php",
"php.executablePath": "/usr/lib/sdk/php73/bin/php",
```

Includes

* [php](https://php.net/) (7.3.7)
* [composer](https://github.com/composer/composer) (1.8.6)
* [xdebug](https://xdebug.org/) (2.7.2)

You can use your own ini files in the config folder for each Flatpak. e.g. for Visual Studio Code
`~/.var/app/com.visualstudio.code/config/php/7.3/ini` or `/var/config/php/7.3/ini` from a sandboxed shell.

#### Troubleshooting
`/usr/bin/env: ‘php’: No such file or directory`

Run `. /usr/lib/sdk/php73/enable.sh` or add `/usr/lib/sdk/php73/bin` to your $PATH.

#### Modules

```bash
bash-4.4$ php -m
[PHP Modules]
bcmath
calendar
Core
ctype
curl
date
dba
dom
exif
fileinfo
filter
ftp
gd
hash
iconv
intl
json
libxml
mbstring
mysqlnd
openssl
pcntl
pcre
PDO
pdo_sqlite
Phar
posix
Reflection
session
SimpleXML
sockets
SPL
sqlite3
standard
sysvmsg
sysvshm
tokenizer
wddx
xdebug
xml
xmlreader
xmlwriter
zip
zlib

[Zend Modules]
Xdebug
```
#### Build
```bash
flatpak-builder --repo repo _build org.freedesktop.Sdk.Extension.php73.json --force-clean
```
