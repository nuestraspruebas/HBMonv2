**HBmonitor is a "web dashboard" for HBlink by N0MJS.**

***This is version of HBMonitor V2 by SP2ONG 2019-2021***

The main difference between HBMonitor v1 and v2 is the layout, i.e. the main page shows condensed 
information and on the subpages, you can see the individual content that was shown on v1

I recommend not running HBmonitor on the same computer as HBlink3

HBmonitor tested on Debian v9 and v10

This version of HBMonv2 requires a web server like apache2, lighttpd and 
php support running on the server. SSL support is available in your configuration
webserver apache2 etc.


    cd /opt
    git clone https://github.com/sp2ong/HBMonv2.git
    cd HBMonv2
    chmod +x install.sh
    ./install.sh
    cp config-SAMPLE.py config.py
    edit config.py and change what you necessary

    If you use OpenBridge links please put in config.py in OPB_FILTER 
    NETWROK ID for each defined link in your server.  

    You need to copy the contents of the /opt/HBMonv2/html directory to 
    the web server directory. Suppose your web server is available 
    as http://dmrserver.org, copy the file to for example /var/www/html

    If you copy files to /var/www/html/hbmon, HBMonitor will be 
    accessible from http://dmrserver.org/hbmon

    You can copy to /var/www/hbmon and start HBMonitor access by configuring 
    virtual the web server for subdomains e.g. hbmon.dmrserver.org 
    the access will then be http://hbmon.dmrserver.org 

    In the html/include/ directory there is a config.php file in which you 
    set the color theme and name for your Dashboard. 

    In the html directory there is a buttons.html file that you can tune to menu keys 
    
    The logo image you can replace with file image in html directory  img/logo.png
    cp utils/lastheard /etc/cron.daily/
    chmod +x /etc/cron.daily/lastherad
    cp utils/hbmon.service /lib/systemd/system/
    systemctl enable hbmon
    systemctl start hbmon
    systemctl status hbmon
    forward TCP port 9000 and web server port in firewall
    
    Please setup your SYSTEM INFO subpage with the following instruction:
    
    https://github.com/sp2ong/HBMonv2/tree/main/sysinfo
    
    Please remember the table lastheard displays only station transmissions 
    that are longer than 2 seconds.

    If you want to have more than the last 15 entries in the Lastherad table
    change in the monitor.py file line from
      if n == 15:
    to for example:
      if n == 20:
    
    In directory sysinfo/ you can find info on how to setup display SYSTEM Info data in Monitor. 

    I recommend that you do not use the BRIDGE_INC = True option to display bridge information 
    (if you have multiple bridges displaying this information will increase the CPU load, 
    try to use BRIDGES_INC = False in config.py) 

---

**hbmonitor3 by KC1AWV**

Python 3 implementation of N0MJS HBmonitor for HBlink https://github.com/kc1awv/hbmonitor3 

---

Copyright (C) 2013-2018  Cortney T. Buffington, N0MJS <n0mjs@me.com>

This program is free software; you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation; either version 3 of 
the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the 
GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program; if not, write to the Free Software Foundation, Inc., 51 Franklin Street, Fifth Floor, Boston, MA 
02110-1301  USA

---

