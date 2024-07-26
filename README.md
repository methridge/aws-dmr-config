# DMR Reflector Server Setup

Ansible playbooks/roles/etc. to setup the DMR reflector sever.

## Base Roles

- `methridge.apt-upgrade`
    - Package maintenance update, upgrade, remove unused and cleanup
- `methridge.base-utils`
    - Install Common required packages
    - packages installed by this role
        - chrony
        - git
        - gpg
        - net-tools
        - unzip
        - zip
- `methridge.lighttpd`
    - Installs lighttpd and related packages
    - packages installed:
        - lighttpd
        - logrotate
        - javascript-common
        - php-cgi
        - php-common
    - Configure lighttpd webserver
        - Enable FastCGI option
        - Enable FastCGI-PHP option
        - Disable Unconfigured sites option
    - Start service
    - Handler to Re-Start service if configuration changes
- `methridge.python-all`
    - Install Python All and Dev meta packages
    - packages installed:
        - python3-all
        - python3-all-dev
- `methridge.mrtg`
    - Install MRTG and SNMPd packages
    - packages installed:
        - mrtg
        - rrdtool
        - snmp
        - snmpd
    - Handlers to re-start services for:
        - mrtg
        - snmpd
- `methridge.php-test`
    - Install PHP info test page
        - create directory `/var/www/html/kris`
        - upload php info test page to directory `test.php`
- `methridge.dvswitch-repo`
    - Add DVSwitch package repo and install apps
        - Add DVSwitch gpg key
        - Add repo location to apt list
        - Install packages:
            - analog-bridge
            - mmdvm-bridge

### TODO:
Packages to Install??
ircddbgateway
nxdngateway
nxdnparrot
p25gateway
p25parrot
ysfgateway
ysfparrot
