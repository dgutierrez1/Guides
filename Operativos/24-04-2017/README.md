Notes

Change command name:<br>
`# PS1='client@\W>'`

-ELK Stack

Install screen and vim: <br>
`# sudo yum install screen vim -y`

Script to execute:<br>

##CLIENT
`# sudo yum install screen vim -y`<br>
`#      echo '[sensu]`<br>
`name=sensu
baseurl=https://sensu.global.ssl.fastly.net/yum/$releasever/$basearch/
gpgcheck=0
enabled=1' | sudo tee /etc/yum.repos.d/sensu.repo`<br>
`#     yum install sensu -y`<br>
`#      sensu-install -p sensu-plugin`<br>
`#      yum install httpd -y`<br>


##SERVER
   `yum install screen vim -y`<br>
      `echo '[sensu]
name=sensu
baseurl=https://sensu.global.ssl.fastly.net/yum/$releasever/$basearch/
gpgcheck=0
enabled=1' | sudo tee /etc/yum.repos.d/sensu.repo` <br>
      `yum install sensu -y` <br>
      `sensu-install -p sensu-plugin`<br>
      `sensu-install -p sensu-plugins-slack`<br>
      `su -c 'rpm -Uvh http://download.fedoraproject.org/pub/epel/7/x86_64/e/epel-release-7-9.noarch.rpm'`<br>
      `yum install erlang -y`<br>
      `yum install redis -y`<br>
      `yum install socat -y`<br>
      `su -c 'rpm -Uvh http://www.rabbitmq.com/releases/rabbitmq-server/v3.6.9/rabbitmq-server-3.6.9-1.el7.noarch.rpm'`<br>
      `service rabbitmq-server start`<br>
      `rabbitmqctl add_vhost /sensu`<br>
      `rabbitmqctl add_user sensu password`<br>
      `rabbitmqctl set_permissions -p /sensu sensu ".*" ".*" ".*"`<br>
      `rabbitmq-plugins enable rabbitmq_management`<br>
      `chown -R rabbitmq:rabbitmq /var/lib/rabbitmq/`<br>
      `rabbitmqctl add_user test test`<br>
      `rabbitmqctl set_user_tags test administrator`<br>
      `rabbitmqctl set_permissions -p / test ".*" ".*" ".*"`<br>
