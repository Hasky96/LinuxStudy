# LinuxStudy
유튜브 "이것이 리눅스다" 강좌
CENTOS

* 가상머신 사용 4대의 가상머신 활용
	- VMWare 활용
	- VMWare WorkStation Pro 활용 (스냅숏, 가상 네트워크)
	- https://cafe.naver.com/thisislinux 교재
	
	
* 가상머신의 장점 
	
	- 1대의 컴퓨터로만으로 실무 환경과 유사하게 구성 가능!
	- 운영체제의 특정 시점을 저장하는 스냅숏 기능
	- 하드웨어를 자유롭게 장착해서 테스트 할 수 있다.
	- Suspend 다음 사용할 때 현재 상태를 이어서 구동
	
	
* 실습
	- 인터넷
		- PowerShell => ipconfig /all => VMnet8 정보 => IPv4
		
		- 192.168.111.2 : 게이트웨이 겸 DNS 서버
		- 192.168.111.1 : HOST OS
	
	- centos 자동업데이트 사용중지
	```shell
	#gsettings set org.gnome.software download-updates false
	#systemctl dsable dnf-makecache.service
	#systemctl dsable dnf-makecache.timer
	```
	- dnf를 이용하여 원하는 버전 fix
	```this.repo
	[BaseOS]
	name=CentOS-$releasever - Base
	baseurl=https://archive.kernel.org/centos-vault/8.0.1905/BaseOS/x86_64/os/
		  http://linuxsoft.cern.ch/centos-vault/8.0.1905/BaseOS/x86_64/os/
	gpgcheck=0

	[AppStream]
	name=CentOS-$releasever - AppStream
	baseurl=https://archive.kernel.org/centos-vault/8.0.1905/AppStream/x86_64/os/
		  http://linuxsoft.cern.ch/centos-vault/8.0.1905/AppStream/x86_64/os/
	gpgcheck=0

	[extras]
	name=CentOS-$releasever - Extras
	baseurl=https://archive.kernel.org/centos-vault/8.0.1905/extras/x86_64/os/
		  http://linuxsoft.cern.ch/centos-vault/8.0.1905/extras/x86_64/os/
	gpgcheck=0

	[centosplus]
	name=CentOS-$releasever - Plus
	baseurl=https://archive.kernel.org/centos-vault/8.0.1905/centosplus/x86_64/os/
		  http://linuxsoft.cern.ch/centos-vault/8.0.1905/centosplus/x86_64/os/
	gpgcheck=0

	[PowerTools]
	name=CentOS-$releasever - PowerTools
	baseurl=https://archive.kernel.org/centos-vault/8.0.1905/PowerTools/x86_64/os/
		  http://linuxsoft.cern.ch/centos-vault/8.0.1905/PowerTools/x86_64/os/
	gpgcheck=0
	
	```
	
