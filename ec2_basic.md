### Basic Ec2
- Launch Insance
    + user data
        > `#!/bin/sh
      yum -y install httpd php
      chkconfig httpd on
      /etc/init.d/httpd start`
