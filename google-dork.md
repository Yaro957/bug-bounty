# Google dork cheatsheet

## Search filters
| Filter          | Description                                        | Example                              |
| :-------------- |:---------------------------------------------------| :------------------------------------|
| allintext      | Searches for occurrences of all the keywords given. | `allintext:"keyword"` |
| intext      | Searches for the occurrences of keywords all at once or one at a time. | `intext:"keyword"` |
| inurl      | Searches for a URL matching one of the keywords. | `inurl:"keyword"` |
| allinurl      | Searches for a URL matching all the keywords in the query. | `allinurl:"keyword"` |
| intitle      | Searches for occurrences of keywords in title all or one. | `intitle:"keyword"` |
| allintitle      | Searches for occurrences of keywords all at a time. | `allintitle:"keyword"` |
| site      | Specifically searches that particular site and lists all the results for that site. | `site:"www.google.com"` |
| filetype      | Searches for a particular filetype mentioned in the query. | `filetype:"pdf"` |
| link      | Searches for external links to pages. | `link:"keyword"` |
| numrange      | Used to locate specific numbers in your searches. | `numrange:321-325` |
| before/after      | Used to search within a particular date range. | `filetype:pdf & (before:2000-01-01 after:2001-01-01)` |
| allinanchor (and also inanchor)      | This shows sites which have the keyterms in links pointing to them, in order of the most links. | `inanchor:rat` |
| allinpostauthor (and also inpostauthor)      | Exclusive to blog search, this one picks out blog posts that are written by specific individuals. | `allinpostauthor:"keyword"` |
| related      | List web pages that are “similar” to a specified web page. | `related:www.google.com` |
| cache      | Shows the version of the web page that Google has in its cache. | `cache:www.google.com` |

## Examples

```
intext:"index of /"
Nina Simone intitle:”index.of” “parent directory” “size” “last modified” “description” I Put A Spell On You (mp4|mp3|avi|flac|aac|ape|ogg) -inurl:(jsp|php|html|aspx|htm|cf|shtml|lyrics-realm|mp3-collection) -site:.info
Bill Gates intitle:”index.of” “parent directory” “size” “last modified” “description” Microsoft (pdf|txt|epub|doc|docx) -inurl:(jsp|php|html|aspx|htm|cf|shtml|ebooks|ebook) -site:.info
parent directory DVDRip -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
parent directory MP3 -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
parent directory Name of Singer or album -xxx -html -htm -php -shtml -opendivx -md5 -md5sums
filetype:config inurl:web.config inurl:ftp
“Windows XP Professional” 94FBR
ext:(doc | pdf | xls | txt | ps | rtf | odt | sxw | psw | ppt | pps | xml) (intext:confidential salary | intext:"budget approved") inurl:confidential
ext:(doc | pdf | xls | txt | ps | rtf | odt | sxw | psw | ppt | pps | xml) (intext:confidential salary | intext:”budget approved”) inurl:confidential
```

## Operators

#### Search Term

This operator searches for the exact phrase within speech marks only.  This is ideal when the phrase you are using to search is ambiguous and  could be easily confused with something else, or when you’re not quite  getting relevant enough results back. For example:

```
"Tinned Sandwiches"
```

#### OR
This self explanatory operator searches for a given search term OR an equivalent term.

```
site:facebook.com | site:twitter.com
```

#### AND

```
site:facebook.com & site:twitter.com
```

#### Operators combinaison

```
(site:facebook.com | site:twitter.com) & intext:"login"
(site:facebook.com | site:twitter.com) (intext:"login")
```

#### Include results

This will order results by the number of occurrence of the keyword.

```
-site:facebook.com +site:facebook.*
```

#### Exclude results

```
site:facebook.* -site:facebook.com
```

#### Synonyms

Adding a tilde to a search word tells Google that you want it to bring back synonyms for the term as well. For example, entering “~set” will bring back results that include words like “configure”, “collection” and “change” which are all synonyms of “set”. Fun fact: “set” has the most definitions of any word in the dictionary.

```
~set
```

#### Glob pattern (*)

Putting an asterisk in a search tells Google ‘I don’t know what goes  here’. Basically, it’s really good for finding half remembered song  lyrics or names of things.

```
site:*.com
```

".mlab. com password"
"access_key"
"access token"
"amazonaws"
"api.googlemaps AIza"
"api_key"
"api_secret"
"apidocs"
"apikey"
"apiSecret"
"app_key"
"app_secret"
"appkey"
"appkeysecret"
"application_key"
"appsecret"
"appspot"
"auth"
"auth token"
"authorizationToken"
"aws access"
"aws_access_key_id"
"aws kev"
"aws_secret"
"aws token"
"AWSSecretKey"
"bashrc password"
"bucket_password"
"client secret"
"cloudfront"
"codecov token"
"config"
"conn. login"
"connectionstring"
"consumer_key"
"credentials"
"database_password"
"db_password"
"db_username"
"dbpasswd"
"dbpassword"
"dbuser"
"dot-files"
"dotfiles"
"encryption_key"
"fabricApiSecret"
"fb secret"
"firebase"
"ftp"
"gh_token"
"github_key"
"github_token"
"gitlab"
"gmail_password"
"gmail_username"
"herokuapp"
"internal"
"irc_pass"
"JEKYLL_GITHUB_TOKEN"
"key"
"keyPassword"
"ldap_password"
"ldap_username"
"login"
"mailchimp"
"mailgun"
"master_key"
"mydotfiles"
"mysql"
"node env"
"npmrc _auth"
"oauth token"
"pass"
"passwd"
"password"
"passwords"
"pem private"
"preprod"
"private_key"
"prod"
"pwd"
"pwds"
"rds . amazonaws. com password"
"redis_password"
"root_password"
"secret"
"secret . password"
"secret access_key"
"secret_key"
"secret token"
"secrets"

"secure"
"security_credentials"
"send. keys"
"send_keys"
"sendkeys"
"SF USERNAME salesforce"
"sf username"
"site.com" FIREBASE API JSON=
"site.com" vim_settings. xml
"slack_api"
"slack token"
"sql_password"
"ssh"
"ssh2_auth_password"
"sshpass"
"staging"
"stg"
"storePassword"
"stripe"
"swagger"
"testuser"
"token"
"x-api-key"
"xoxb "
"xoxp"
[WFClient] Password= extension:ica
access_key
bucket password
dbpassword
dbuser
extension: avastlic "support. avast. com"
extension:bat

extension: cfg
extension : env

extension: exs

extension: ini
extension: json api. forecast. io
extension: json googleusercontent client_secret
extension: json mongolab.com
extension : pem
extension: pem private
extension : ppk
extension:ppk private
extension : properties
extension: sh

extension: sls

extension : sql
extension: sql mysql dump
extension: sql mysql dump password
extension: yaml mongolab. com
extension: zsh
filename: .bash_history
Filename: .bash_history DOMAIN-NAME
filename :. bash profile aws
Filename: .bashrc mailchimp
Filename: .bashrc password
Filename: . cshrc
Filename: .dockercfg auth
filename: . env DB USERNAME NOT homestead
Filename: . env MAIL_HOST=smtp.gmail.com
Filename: .esmtprc password
Filename: .ftpconfig
filename: .git-credentials
filename: .history
Filename: .htpasswd
Filename: . netrc password
Eilename: .npmrc _auth
filename: .pgpass
Filename: . remote-sync. json
filename: .s3cfg
filename: .sh_history
filename: .tugboat NOT _tugboat
filename: netrc password
filename: apikey
filename: bash
filename: bash_history
filename:bash_profile
filename: bashrc
filename: beanstalkd. yml
filename: CCCam.cfg
filename: composer.json
filename: config
filename: config irc_pass
filename: config. json auths
filename: config .php dbpasswd
filename: configuration. php JConfig password
filename : connections

filename: connections.xml
filename: constants

filename: credentials

filename: credentials aws access_key_id
filename: cshrc

filename: database
filename:dbeaver-data-sources. xml
filename: deployment-config. json
filename : dhcpd. conf
filename: dockercfg
filename: environment
filename: express. conf
filename: express. conf path: .openshift
filename: filezilla.xml

filename: filezilla.xml Pass
filename:git-credentials
filename:gitconfig
filename: global
filename:history
filename:htpasswd
filename:hub oauth token
filename: id dsa
filename: id rsa
filename: id rsa or filename: id_dsa
filename: idea14. key
filename: known hosts
filename: logins. json
filename: makefile
filename:master. key path: config
filename: netrc
filename: npmrc
filename: pass
filename:passwd path:etc
filename: pgpass
filename: prod. exs
filename: prod. exs NOT prod. secret.exs
filename: prod. secret.exs
filename: proftpdpasswd
filename: recentservers. xml

filename: recentservers.xml Pass

filename: robomongo. json
filename:s3cfg
filename: secrets. yml password
filename: server.cfg
filename: server. cfg rcon password
filename: settings
filename: settings . py SECRET_KEY
filename: sftp-config. json
filename: sftp-config. json password
filename: sftp. json path: . vscode
filename: shadow
filename: shadow path:etc
filename: spec
filename: sshd_config
filename: token

filename: tugboat
filename: ventrilo srv.ini
filename: WebServers. xml
filename:wp-config
filename:wp-config.php
filename: zhrc
HEROKU API_KEY language: json
HEROKU API_KEY language: shell
HOMEBREW GITHUB API TOKEN language : shell
jsforce extension:js conn. login
language : yaml -filename: travis
msg nickserv identify filename:config
org: Target "AWS_ACCESS KEY ID"
org: Target "list_aws accounts"
org:Target "aws_access_key"
org: Target "aws_secret_key"
org: Target "bucket name"
org:Target "S3_ACCESS KEY ID"
org:Target "S3_BUCKET"
org:Target "S3 ENDPOINT"
org:Target "S3_SECRET ACCESS KEY"
password
path: sites databases password
private -language: java
PT TOKEN language: bash
redis password
root password
secret_access_key
SECRET KEY BASE=
shodan_api_key language : python
WORDPRESS DB PASSWORD=
xoxp OR xoxb OR xoxa
s3.yml

. exs

beanstalkd. yml
deploy. rake
.sls

AWS SECRET ACCESS KEY
API KEY

API SECRET

API TOKEN

ROOT PASSWORD

ADMIN PASSWORD
ADMIN PASSWORD

GCP SECRET

AWS SECRET
"private" extension:pgp
