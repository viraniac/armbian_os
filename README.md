<p align="center">
  <a href="#build-framework">
   <img src="https://raw.githubusercontent.com/armbian/build/master/.github/armbian-logo.png" alt="Armbian logo" width="144">
  </a><br>
  <strong>Armbian OS</strong><br>
<br>
<a href=https://github.com/armbian/os/actions/workflows/complete-artifact-matrix-all.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/complete-artifact-matrix-all.yml?logo=githubactions&label=Artifacts%20make&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os/actions/workflows/repository-update.yml><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/repository-update.yml?logo=githubactions&label=Repository%20update&style=for-the-badge&branch=main"></a>
<a href=https://github.com/armbian/os#latest-smoke-tests-results><img alt="GitHub Workflow Status" src="https://img.shields.io/github/actions/workflow/status/armbian/os/smoke-tests.yml?logo=githubactions&label=Smoke%20tests&style=for-the-badge&branch=main"></a>
</p>


## What does this project do?

- Builds quarterly [stable](https://www.armbian.com/download/), daily [rolling](https://github.com/armbian/os/releases/latest) and weekly [community](https://github.com/armbian/community/releases/latest) OS images
- Keeps build framework [packages artifacts](https://github.com/orgs/armbian/packages) cache up to date to secure fast rebuild process
- Keeps stable [apt.armbian.com](https://apt.armbian.com) and nightly [beta.armbian.com](https://beta.armbian.com) packages repository up to date
- Keep synchronizing the selection of [3rd party](external) applications with Armbian repositories
- Tests install of all packages added onto stable and testing Debian and Ubuntu releases
- Tests packages upgrade sucess on real hardware

## How to enable images?

Build lists are generated [automatic](https://github.com/armbian/os/blob/main/.github/workflows/recreate-matrix.yml#L59-L211C94) based on [support policy](https://docs.armbian.com/User-Guide_Board-Support-Rules/) and with help of [templates](userpatches/), .blacklist and .map files.

## When is this happening?

- Artifacts cache is updated every eight hours, starting at 0:00 AM UTC
- Repository update starts after artifacts cache update is done succesfully
- Smoke tests starts once per day at 5:30 AM UTC
- Nightly images are build once per day, at 2:00 AM UTC, or if [build config / template is changed](https://github.com/armbian/os/blob/main/userpatches/targets-release-nightly.yaml)
- Manually, when Armbian [release manager](https://github.com/orgs/armbian/teams/release-manager) executes a build action

## Latest smoke tests results:

- installs **kernels**, **device tree blob** and **headers**
- runs **network** (iperf) and **computing performance** tests (7z benchmark)
- store **armbianmonitor** logs

<!--START_SECTION:data-section-->
<table width="100%"><tr><td align="left"><a id=Board ID href=#Board ID><b>Board name</b></a></td><td align=center><b>Kernel version</b></td><td align=center><b>Support</b></td><td align=left><b>Logs</b></td><td align=right><b>Iperf</b></td><td align=right><b>7z -b</b></td><td align=right><b>Repo</b></td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/nuloqucuse><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>96</td><td align=right>3705</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1 href=#khadas-vim1>Khadas VIM1</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/joyanekiwa><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3697</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/jogovebune><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>837</td><td align=right>2644</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus href=#orangepizeroplus>Orange Pi Zero Plus</a></td><td align=center>6.7.2-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cixijinaga><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>830</td><td align=right>2597</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.6.14-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uhibahusid><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>232</td><td align=right>3373</td><td align=right>beta</td></tr><tr><td align="left"><a id=rockpi-e href=#rockpi-e>Rockpi E</a></td><td align=center>6.7.2-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uzozedesul><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>93</td><td align=right>3422</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/gerepaluta><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>867</td><td align=right>4297</td><td align=right>beta</td></tr><tr><td align="left"><a id=pineh64 href=#pineh64>Pine H64</a></td><td align=center>6.7.2-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ahigadaqok><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>869</td><td align=right>4350</td><td align=right>beta</td></tr><tr><td align="left"><a id=zeropi href=#zeropi>ZeroPi</a></td><td align=center>6.1.75-legacy-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/opitujuxaw><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>613</td><td align=right>2665</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/adeledugup><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5337</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim2pro href=#bananapim2pro>Banana Pi M2Pro</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/usoqicucuf><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5343</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard-2 href=#tinkerboard-2>Tinker Board 2</a></td><td align=center>6.6.14-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ixoqojobup><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>730</td><td align=right>6892</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/qubelofero><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>90</td><td align=right>3765</td><td align=right>beta</td></tr><tr><td align="left"><a id=lepotato href=#lepotato>Le potato</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/civekeyuro><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>93</td><td align=right>3773</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepi5 href=#orangepi5>Orange Pi 5</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/uqedonunac><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>15566</td><td align=right>beta</td></tr><tr><td align="left"><a id=tinkerboard href=#tinkerboard>Tinker Board</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepizero href=#orangepizero>Orange Pi Zero</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>607</td><td align=right>3049</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizero2 href=#orangepizero2>Orange Pi Zero2</a></td><td align=center>6.7.2-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>836</td><td align=right>3409</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cinokubobi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>960</td><td align=right>9648</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim3 href=#khadas-vim3>Khadas VIM3</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/epunetewun><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>950</td><td align=right>9670</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ukodadafel><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>4277</td><td align=right>beta</td></tr><tr><td align="left"><a id=tanix-tx6 href=#tanix-tx6>Tanix TX6</a></td><td align=center>6.7.2-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/radumehavu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>91</td><td align=right>4375</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepioneplus href=#orangepioneplus>Orange Pi One+</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/relucafuro><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>624</td><td align=right>4121</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.6.14-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/zanedokiji><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>6633</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopim4 href=#nanopim4>NanoPi M4</a></td><td align=center>6.7.2-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/izepoyosov><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>889</td><td align=right>6731</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim4 href=#khadas-vim4>Khadas VIM4</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/icigexajoh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5516</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapim5 href=#bananapim5>Banana Pi M5</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/xabobojuru><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5546</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopineo3 href=#nanopineo3>NanoPi Neo 3</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/iwovahekov><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>5340</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc4 href=#odroidc4>Odroid C4</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/noderijulu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>888</td><td align=right>5606</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=nanopi-r2s href=#nanopi-r2s>Nanopi R2S</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/luromozabo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>4011</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidc2 href=#odroidc2>Odroid C2</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/cezidibite><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>4014</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.13-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/bidabefoha><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2832</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.1-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/vuquxinaze><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>89</td><td align=right>2864</td><td align=right>beta</td></tr><tr><td align="left"><a id=bigtreetech-cb1 href=#bigtreetech-cb1>BigTreeTech CB1</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=orangepi-r1plus-lts href=#orangepi-r1plus-lts>Orange Pi R1 Plus LTS</a></td><td align=center>6.6.14-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ehanosejap><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>608</td><td align=right>1979</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.1.75-legacy-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/idefasuweh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>871</td><td align=right>4680</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.6.14-current-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/yowupudiqu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>579</td><td align=right>4674</td><td align=right>beta</td></tr><tr><td align="left"><a id=uefi-x86 href=#uefi-x86>UEFI x86</a></td><td align=center>6.7.2-edge-x86</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ubegokebat><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>840</td><td align=right>4783</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.6.14-current-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/zevupiximu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>890</td><td align=right>8648</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidn2 href=#odroidn2>Odroid N2</a></td><td align=center>6.7.2-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/ferekenola><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>8893</td><td align=right>beta</td></tr><tr><td align="left"><a id=khadas-vim1s href=#khadas-vim1s>Khadas VIM1S</a></td><td align=center>n/a</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><img src=https://img.shields.io/static/v1?label=&message=n/a&color=white></td><td align=right>n/a</td><td align=right>n/a</td><td align=right></td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.6.14-current-arm64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/pufizoceri><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>877</td><td align=right>3728</td><td align=right>beta</td></tr><tr><td align="left"><a id=jetson-nano href=#jetson-nano>Jetson Nano</a></td><td align=center>6.7.2-edge-arm64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/yohocokemo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>620</td><td align=right>3751</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/tutiforavo><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>870</td><td align=right>9581</td><td align=right>beta</td></tr><tr><td align="left"><a id=bananapicm4io href=#bananapicm4io>Banana Pi CM4IO</a></td><td align=center>6.4.13-edge-meson64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/fisigeveta><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>9550</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/gabemihiqe><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>580</td><td align=right>5301</td><td align=right>beta</td></tr><tr><td align="left"><a id=odroidm1 href=#odroidm1>Odroid M1</a></td><td align=center>6.6.4-edge-rk3568-odroid</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/woqogemiwu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>556</td><td align=right>5268</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.6.14-current-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/unajozoder><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>900</td><td align=right>6461</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r4s href=#nanopi-r4s>NanoPi R4S</a></td><td align=center>6.7.2-edge-rockchip64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/apohexayad><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>911</td><td align=right>6541</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.6.13-current-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/detilugedi><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>880</td><td align=right>5085</td><td align=right>beta</td></tr><tr><td align="left"><a id=rpi4b href=#rpi4b>Raspberry Pi 4</a></td><td align=center>6.7.1-edge-bcm2711</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/kovedubalu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>878</td><td align=right>5064</td><td align=right>beta</td></tr><tr><td align="left"><a id=udoo href=#udoo>Udoo</a></td><td align=center>6.6.14-current-imx6</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/odapakoheh><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>322</td><td align=right>2362</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/otujokaxiv><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2240</td><td align=right>15479</td><td align=right>beta</td></tr><tr><td align="left"><a id=nanopi-r6s href=#nanopi-r6s>NanoPi R6S</a></td><td align=center>5.10.160-legacy-rk35xx</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Standard&color=green></a></td><td align=left><a href=https://paste.armbian.com/otujokaxiv><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>2240</td><td align=right>15479</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.1.75-legacy-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/baqapexeja><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>50</td><td align=right>4023</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.6.14-current-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/osobivebuc><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>70</td><td align=right>3931</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepilite2 href=#orangepilite2>Orange Pi Lite 2</a></td><td align=center>6.7.2-edge-sunxi64</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/rumujowoho><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>58</td><td align=right>4105</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.6.14-current-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/ulezaqowek><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>39</td><td align=right>2611</td><td align=right>beta</td></tr><tr><td align="left"><a id=orangepizeroplus2-h3 href=#orangepizeroplus2-h3>Orange Pi Zero Plus 2</a></td><td align=center>6.7.2-edge-sunxi</td><td align=center><a href=https://docs.armbian.com/User-Guide_Board-Support-Rules/><img src=https://img.shields.io/static/v1?label=&message=Community&color=white></a></td><td align=left><a href=https://paste.armbian.com/buxexamimu><img src=https://img.shields.io/static/v1?label=&message=Log&color=blue></a></td><td align=right>35</td><td align=right>2652</td><td align=right>beta</td></tr></table>
<!--END_SECTION:data-section-->

## Would you like to join spare hardware to this automated testings?

All you need to do is:

- deploy any latest Armbian image to hardware
- provide IP address
- [contact us](https://www.armbian.com/contact/)

Device has to be always on and easily accesible for you to re-image in case of failed upgrade.

## Development

- [Pull request](https://github.com/armbian/build/pulls)
- [Weekly developers meetings](https://forum.armbian.com/events/)
- [Forums for developers](https://forum.armbian.com/forum/4-advanced-users-development/)

## Download prebuilt images

- [quarterly released **standard support** builds](https://www.armbian.com/download/?device_support=Standard%20support)
- [automatic released **rolling release** builds](https://github.com/armbian/os/releases/latest) (daily or when code changes)
- [weekly released **community maintained** builds](https://github.com/armbian/community/releases/latest)

## Support

- [Using Armbian](https://forum.armbian.com/forum/23-using-armbian/)

## Contact

- [Forums](https://forum.armbian.com) for Participate in Armbian
- IRC: `#armbian` on Libera.chat
- Discord: [https://discord.gg/armbian](https://discord.gg/armbian)
- Follow [@armbian](https://twitter.com/armbian) on X (formerly known as Twitter), [Fosstodon](https://fosstodon.org/@armbian) or [LinkedIn](https://www.linkedin.com/company/armbian).
- Bugs: [issues](https://github.com/armbian/build/issues) / [JIRA](https://armbian.atlassian.net/jira/dashboards/10000)
- Office hours: [Wednesday, 12 midday, 18 afternoon, CET](https://calendly.com/armbian/office-hours)
