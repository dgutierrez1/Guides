Notes

Change command name:<br>
`#PS1='client@\W>'`

-ELK Stack

Install screen and vim: <br>
`# sudo yum install screen vim -y`

Script to execute:<br>

`# sudo yum install screen vim -y`<br>
`#      echo '[sensu]`<br>
`name=sensu
baseurl=https://sensu.global.ssl.fastly.net/yum/$releasever/$basearch/
gpgcheck=0
enabled=1' | sudo tee /etc/yum.repos.d/sensu.repo`<br>
`#     yum install sensu -y`<br>
`#      sensu-install -p sensu-plugin`<br>
`#      yum install httpd -y`<br>
