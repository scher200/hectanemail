## Hectane Mailer
# A repacement for /usr/sbin/sendmail -t -i that works

This is compatible with docker containers (including superslim Alpine Linux)

# 1
(If you like, you can get the supercool original hecatane executable from the hectane/hecatane repository itself.)
```
cd / (or any other place)
git clone https://github.com/scher200/hecatanemail
chmod +x /hectane/*
```
and start the executable in the background: 
```
/hectane/hectane -smtp-addr='' -bind=localhost:8025 -username=yourusername -password=yourpassword -debug=1 &
```
And configure /hecatane/hecatanemail script at the top the first class

# 2
Change these line into your php.ini or put them in a file in your /etc/php(5/7)/conf.d/ directory:
```
[mail function]
;sendmail_path=/usr/sbin/sendmail -t -i <-- you may remove or ; this line if it is out there
sendmail_path=/hectane/hectanemail
```

# 3
Resart your apache2/nginx .. and enjoy your php mail being deliverd now!# hectanemail
