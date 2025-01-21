- sudo apt install < package1 > < package2 > < package3 >
- sudo apt update
- sudo apt remove < package >
- sudo apt remove --purge < package >
	# enlève le package et efface sa configuration
- sudo apt autoremove # permet de nettoyer les packages orphelins


> [!NOTE] Title
> installer  prometheus, et grafana.
> 


> [!NOTE] curl
> You may try with `curl`.
> 
> To download the file into the current folder and install from the local file:
>
> ```
> curl -sLO https://apt.puppetlabs.com/puppetlabs-release-precise.deb && sudo dpkg -i puppetlabs-release-precise.deb
> ```
> 
> or download into `/var/cache/apt/archives/` and install from there:
>
> ```
> curl -sL -o/var/cache/apt/archives/puppetlabs-release-precise.deb https://apt.puppetlabs.com/puppetlabs-release-precise.deb && sudo dpkg -i /var/cache/apt/archives/puppetlabs-release-precise.deb
> ```


```Bash

adduser user  

sudo usermod -aG sudo user 

su user

sudo snap install grafana

sudo apt install -y prometheus

prometheus --version 
--------------------
prometheus, version 2.15.2+ds (branch: debian/sid, revision: 2.15.2+ds-2)
  build user:       pkg-go-maintainers@lists.alioth.debian.org
  build date:       20200113-10:10:54
  go version:       go1.13.7

sudo apt update
---------------
Hit:1 http://security.ubuntu.com/ubuntu focal-security InRelease
Hit:2 http://archive.ubuntu.com/ubuntu focal InRelease
Get:3 http://archive.ubuntu.com/ubuntu focal-updates InRelease [114 kB]
Hit:4 http://archive.ubuntu.com/ubuntu focal-backports InRelease
Fetched 114 kB in 1s (153 kB/s)
Reading package lists... Done
Building dependency tree       
Reading state information... Done
170 packages can be upgraded. Run 'apt list --upgradable' to see them.

apt list --upgradable

sudo apt remove -y prometheus

prometheus --version 
--------------------
bash: /usr/bin/prometheus: No such file or directory

sudo apt install -y prometheus

prometheus --version 
--------------------
prometheus, version 2.15.2+ds (branch: debian/sid, revision: 2.15.2+ds-2)
  build user:       pkg-go-maintainers@lists.alioth.debian.org
  build date:       20200113-10:10:54
  go version:       go1.13.7

sudo apt remove --purge prometheus

prometheus --version 
--------------------
bash: /usr/bin/prometheus: No such file or directory

sudo apt autoremove -y

sudo apt-cache search prometheus

sudo apt-cache show prometheus

dpkg -l dpkg -L prometheus
--------------------------
dpkg-query: no packages found matching -L
dpkg-query: no packages found matching prometheus
Desired=Unknown/Install/Remove/Purge/Hold
| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
||/ Name           Version         Architecture Description
+++-==============-===============-============-=================================
ii  dpkg           1.19.7ubuntu3.2 amd64        Debian package management system

sudo apt install prometheus

dpkg -l dpkg -L prometheus
--------------------------
*dpkg-query: no packages found matching -L
Desired=Unknown/Install/Remove/Purge/Hold
| Status=Not/Inst/Conf-files/Unpacked/halF-conf/Half-inst/trig-aWait/Trig-pend
|/ Err?=(none)/Reinst-required (Status,Err: uppercase=bad)
||/ Name           Version         Architecture Description
+++-==============-===============-============-==========================================
ii  dpkg           1.19.7ubuntu3.2 amd64        Debian package management system
ii  prometheus     2.15.2+ds-2     amd64        Monitoring system and time series database


```


## Install from APT repository[](https://grafana.com/docs/grafana/latest/setup-grafana/installation/debian/#install-from-apt-repository)

If you install from the APT repository, Grafana automatically updates when you run `apt-get update`.

|Grafana Version|Package|Repository|
|---|---|---|
|Grafana Enterprise|grafana-enterprise|`https://apt.grafana.com stable main`|
|Grafana Enterprise (Beta)|grafana-enterprise|`https://apt.grafana.com beta main`|
|Grafana OSS|grafana|`https://apt.grafana.com stable main`|
|Grafana OSS (Beta)|grafana|`https://apt.grafana.com beta main`|

> [!Note]
> Grafana Enterprise is the recommended and default edition. It is available for free and includes all the features of the OSS edition. You can also upgrade to the [full Enterprise feature set](https://grafana.com/products/enterprise/?utm_source=grafana-install-page), which has support for [Enterprise plugins](https://grafana.com/grafana/plugins/?enterprise=1&utcm_source=grafana-install-page).
Complete the following steps to install Grafana from the APT repository:

1.Install the prerequisite packages:

```bash
sudo apt-get install -y apt-transport-https software-properties-common wget
```

-Import the GPG key:

```bash
sudo mkdir -p /etc/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```
-To add a repository for stable releases, run the following command:

```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

-To add a repository for beta releases, run the following command:
```bash
echo "deb [signed-by=/etc/apt/keyrings/grafana.gpg] https://apt.grafana.com beta main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

-Run the following command to update the list of available packages:

```bash
# Updates the list of available packages
sudo apt-get update
```

-To install Grafana OSS, run the following command:

```bash
# Installs the latest OSS release:
sudo apt-get install grafana
```

-To install Grafana Enterprise, run the following command:

```bash
# Installs the latest Enterprise release:
sudo apt-get install grafana-enterprise
```