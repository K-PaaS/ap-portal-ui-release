## 🚨 어플리케이션 플랫폼 기술지원 종료 
#### 어플리케이션 플랫폼 기술지원 종료 일정 : 2025년 1월 31일  
지원 종료일 전까지 기 보급된 어플리케이션 플랫폼 유지보수를 위한 업그레이드 버전 및 보안 패치 제공  
지원 종료 이후 보안문제가 발생하여도 기술지원이 불가  

## ap-portal-ui-release

### Application Platform Portal UI Release Configuration

  - haproxy : 1 machine
  - mariadb : 1 machine
  - ap-portal-webadmin : 1 machine
  - ap-portal-webuser : 1 machine

### Create Application Platform Portal UI Release
  - Download the latest Application Platform Portal UI Release
    ```
    $ git clone https://github.com/K-PaaS/ap-portal-ui-release.git
    $ cd ap-portal-ui-release
    ```
  - Download & Copy "source files" into the src directory
    ```
    ## download source files
    $ wget -O src.zip https://nextcloud.k-paas.org/index.php/s/x8bi9pqL6F4tbBG/download

    ## unzip download source files
    $ unzip src.zip

    ## final src directory
    src
      ├── apache2
      │   ├── apr-1.7.0.tar.gz
      │   ├── apr-util-1.6.1.tar.gz
      │   ├── expat-2.2.8.tar.gz
      │   ├── httpd-2.4.62.tar.gz
      │   └── pcre-8.43.tar.gz
      ├── haproxy
      │   └── haproxy-1.6.5.tar.gz
      ├── java
      │   └── server-jre-8u121-linux-x64.tar.gz
      ├── mariadb
      │   └── mariadb-10.5.17-linux-x86_64.tar.gz
      ├── ap-portal-webadmin
      │   └── ap-portal-webadmin.war
      └── ap-portal-webuser
          └── ap-portal-webuser.tar.gz
    ```
  - Create Application Platform Portal UI Release
    ```
    ## <VERSION> :: release version (e.g. 2.5.0)
    ## <RELEASE_TARBALL_PATH> :: release file path (e.g. /home/ubuntu/workspace/ap-portal-ui-release-<VERSION>.tgz)
    $ bosh -e <bosh_name> create-release --name=ap-portal-ui --sha2 --version=<VERSION> --tarball=<RELEASE_TARBALL_PATH> --force
    ```
### Deployment
- https://github.com/K-PaaS/portal-deployment
