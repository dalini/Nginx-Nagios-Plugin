Version 1.2, 2012, Wilhelm Murdoch (http://www.thedrunkenepic.com/), original credit 2009, Mike Adolphs (http://www.matejunkie.com/)

check_nginx.sh is a Nagios plugin to check whether nginx is running.
It also parses the nginx's status page to get requests and
connections per second as well as requests per connection. You
may have to alter your nginx configuration so that the plugin
can access the server's status page.
The plugin is highly configurable for this reason. See below for
available options.

check_nginx.sh -H localhost -P 80 -p /var/run -n nginx.pid 
  -s nginx_statut -o /tmp [-w INT] [-c INT] [-S] [-N]

Options:
  -H/--hostname)
     Defines the hostname. Default is: localhost
  -P/--port)
     Defines the port. Default is: 80
  -p/--path-pid)
     Path where nginx's pid file is being stored. You might need
     to alter this path according to your distribution. Default
     is: /var/run
  -n/--name_pid)
     Name of the pid file. Default is: nginx.pid
  -N/--no-pid-check)
     Turn this on, if you don't want to check for a pid file
     whether nginx is running, e.g. when you're checking a
     remote server. Default is: off
  -s/--status-page)
     Name of the server's status page defined in the location
     directive of your nginx configuration. Default is:
     nginx_status
  -S/--secure)
     In case your server is only reachable via SSL, use this
     this switch to use HTTPS instead of HTTP. Default is: off
  -w/--warning)
     Sets a warning level for requests per second. Default is: off
  -c/--critical)
     Sets a critical level for requests per second. Default is:
     off
  -au/--auth-user)
     If your Nginx status page requires basic authentication,
     use this to enter the user name.
  -ap/--auth-password)
     If your Nginx status page requires basic authentication,
     use this to enter the password.
