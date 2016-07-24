--> /usr/local/cpanel/3rdparty/bin/perl <(curl -sL https://raw.githubusercontent.com/cpanelsky/postmigration/master/postmigration.pl) -help

 Options:
     -help   -> This!

Accepts -local ( -ipdns -local )
     -ipdns  -> Check http status, IP's, DNS IP's
     -json   -> Print http/DNS data in JSON
     -all    -> DNS, Mail, http Status codes


Single option:
     -hosts  -> Show suggested /etc/hosts file
     -mail   -> Find mail accounts
     -tterr  -> Find pkgacct transfer errors





Example usage:

Run in the background, wait for results 
--> nohup bash -c '/usr/local/cpanel/3rdparty/perl/522/bin/perl <(curl -sL https://raw.githubusercontent.com/cpanelsky/postmigration/master/postmigration.pl) -ipdns -json -local | /usr/local/cpanel/3rdparty/perl/522/bin/json_xs 2>&1 > this.out' &

Download as module, include and use functions from
--> wget -O PostMigration.pm  https://raw.githubusercontent.com/cpanelsky/postmigration/master/postmigration.pl
--> /usr/local/cpanel/3rdparty/perl/522/bin/perl -I$(pwd) -e 'use PostMigration;$test = &PostMigration::http_web_request("www.google.com"); print $test;'
