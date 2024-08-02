# Install podman in MAC OSX M1

The installation process for podman is documented [Here](https://podman.io/docs/installation)


## install podman

To install podman in your MAC OSX M1, open a terminal and execute the next commands 'brew':

```Code
brew install podman


==> Auto-updating Homebrew...
Adjust how often this is run with HOMEBREW_AUTO_UPDATE_SECS or disable with
HOMEBREW_NO_AUTO_UPDATE. Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Downloading https://ghcr.io/v2/homebrew/portable-ruby/portable-ruby/blobs/sha256:49847c7a13f7094b211f6d0025900dd23716be07dac894a3d6941d7696296306
################################################################################################################################################# 100.0%
==> Pouring portable-ruby-3.3.3.arm64_big_sur.bottle.tar.gz
==> Auto-updated Homebrew!
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
age-plugin-se         codecov-cli           frizbee               kubectl-rook-ceph     nextdns               qshell                terramaid
ansible-creator       cortexso              ftnchek               kubelogin             nsync                 river                 testscript
ansible@9             cotila                gcc@13                kubernetes-cli@1.29   nvtop                 ronn-ng               tinymist
apache-flink-cdc      cyctl                 geni                  kubevpn               ocicl                 rust-parallel         tmt
asak                  cyme                  gensio                kuzu                  oils-for-unix         rustls-ffi            tofuenv
awsdac                dep-tree              go-size-analyzer      lando-cli             openbao               rustup                toipe
basti                 dillo                 godap                 libgit2@1.7           openfa                ryelang               topfew
batt                  displayplacer         gorilla-cli           libpeas@1             openjdk@21            sherlock              traefik@2
bigquery-emulator     dnsgen                h26forge              libvirt-python        otree                 soapyhackrf           typstyle
bootterm              ecs-deploy            haproxy@2.8           litmusctl             pedump                soapyremote           vedic
cahute                egctl                 iamb                  llama.cpp             podlet                span-lite             vexctl
chainhook             envelope              iowow                 llgo                  porter                stripe-cli            wcurl
chkbit                fastapi               jsontoolkit           mactop                poutine               stripe-mock           yara-x
chsrc                 fern-api              kaskade               mako                  pug                   task@2                zfind
clang-uml             flawz                 kconf                 mihomo                pulsarctl             tdb
cloudflare-cli4       forbidden             kubectl-cnpg          nerdfetch             qrtool                terrahash
==> New Casks
ableton-live-suite@10                              font-hedvig-letters-sans                           font-noto-serif-toto
airdash                                            font-hedvig-letters-serif                          font-noto-serif-vithkuqi
alcom                                              font-heebo                                         font-noto-serif-yezidi
anchor-wallet                                      font-henny-penny                                   font-noto-traditional-nushu
avbeam                                             font-hepta-slab                                    font-noto-znamenny-musical-notation


```

## Check the installation

Execute the next command 'podman':

```Code
podman
Manage pods, containers and images

Usage:
  podman [options] [command]

Available Commands:
  attach      Attach to a running container
  build       Build an image using instructions from Containerfiles
  commit      Create new image based on the changed container
  compose     Run compose workloads via an external provider such as docker-compose or podman-compose

...etc...

```

## Start the Podman Machine

After installing, you need to create and start your first Podman machine:
  
```Code

podman machine init

podman machine start
```

You should see some result like this:


```Code

Looking up Podman Machine image at quay.io/podman/machine-os:5.1 to create VM
Getting image source signatures
Copying blob 9dee86eab53b done   | 
Copying config 44136fa355 done   | 
Writing manifest to image destination
9dee86eab53bcbfdacfd1cd2940059e1ee4e4b62d4017176c937a08a5b58f633
Extracting compressed file: podman-machine-default-arm64.raw: done  
Machine init complete
To start your machine run:

	podman machine start

Starting machine "podman-machine-default"

This machine is currently configured in rootless mode. If your containers
require root permissions (e.g. ports < 1024), or if you run into compatibility
issues with non-podman clients, you can switch using the following command:

	podman machine set --rootful

API forwarding listening on: /var/folders/kb/jznn9w2n1bs3kjyyxdbnmydh0000gn/T/podman/podman-machine-default-api.sock

The system helper service is not installed; the default Docker API socket
address can't be used by podman. If you would like to install it, run the following commands:

        sudo /opt/homebrew/Cellar/podman/5.1.2/bin/podman-mac-helper install
        podman machine stop; podman machine start

You can still connect Docker API clients by setting DOCKER_HOST using the
following command in your terminal session:

        export DOCKER_HOST='unix:///var/folders/kb/jznn9w2n1bs3kjyyxdbnmydh0000gn/T/podman/podman-machine-default-api.sock'

Machine "podman-machine-default" started successfully

```

## Verify the installation

You can then verify the installation information using:

```Code

podman info


host:
  arch: arm64
  buildahVersion: 1.36.0
  cgroupControllers:
  - cpu
  - io
  - memory
  - pids
  cgroupManager: systemd
  cgroupVersion: v2
  conmon:
    package: conmon-2.1.10-1.fc40.aarch64
    path: /usr/bin/conmon
    version: 'conmon version 2.1.10, commit: '
  cpuUtilization:
    idlePercent: 99.71
    systemPercent: 0.18
    userPercent: 0.11
  cpus: 4
  databaseBackend: sqlite
  distribution:
    distribution: fedora
    variant: coreos
    version: "40"
  eventLogger: journald
  freeLocks: 2048
  hostname: localhost.localdomain

...etc...

```



## Deploy Oracle Database

```Code
podman run -d --name 23aidb \
-p 1522:1521 \
container-registry.oracle.com/database/free:latest



Trying to pull container-registry.oracle.com/database/free:latest...
Getting image source signatures
Copying blob sha256:716b489ad5ad73d5f880665ae7e82af383bb6f6244a8d1adc99d28a0d1953225
Copying blob sha256:21def9023b6f2317d84cb01a4ac8821d3c4c254cc5260a9ee71881349a804619
Copying blob sha256:6d6e36f7c9fb22f17dc9a04ff1d01dec12d7b1a9e6c356c2f7f34e258653d8e9
Copying blob sha256:5e7b2cfeb7fa75f0d012c9b480b076d4755a5b1a30963d73fe89a4c786ec242f
Copying blob sha256:b4a24759beffd9fbe3a10fc6324248a2d49cf0142c56928a911a2d78d88e3ecb
Copying blob sha256:78bba54e9814efa4ccf924e298648cd6c5b1f8e104dd72c1b9349dd82c312316
Copying blob sha256:c23fd8c6cbee9740eeb18d373ed825f43e415bf34697b645f8748ed689469b79
Copying blob sha256:79dea26b3a5a9ad9f19426fab1897f381d502b971a0fcd788d7c6548a4637c49
Copying blob sha256:5dfbcf799df3a96f5d76daaaccbe8195148a9ff27c27feaeee2a163d1b5a2210
Copying blob sha256:154719a6257610561f2f9bbcc3e3668f5a8e1f6246d82c7236040f8b271defa0
Copying config sha256:7510f8869b041dbd0dc782e7432aeee37cc2fd28eb4496e3b03c4ba3c5c4218e
Writing manifest to image destination
WARNING: image platform (linux/amd64) does not match the expected platform (linux/arm64)
b682ef9aa78723842aeded0b6657e8f366118b1f63cc1a9c329a63b93da3f928
operard@MacBook-Pro airag % podman container ls
CONTAINER ID  IMAGE                                               COMMAND               CREATED         STATUS                    PORTS                             NAMES
b682ef9aa787  container-registry.oracle.com/database/free:latest  /bin/bash -c $ORA...  18 seconds ago  Up 19 seconds (starting)  0.0.0.0:1522->1521/tcp, 1521/tcp  23aidb

```


operard@MacBook-Pro airag % podman logs 23aidb
Password: su: Authentication failure
The Oracle base remains unchanged with value /opt/oracle
#####################################
########### E R R O R ###############
DATABASE SETUP WAS NOT SUCCESSFUL!
Please check output for further info!
########### E R R O R ###############
#####################################
The following output is now a tail of the alert.log:
FREEPDB1(3):Tablespace created: USERS ts# 6
FREEPDB1(3):Completed: CREATE SMALLFILE TABLESPACE "USERS" LOGGING  DATAFILE  '/opt/oracle/oradata/FREE/FREEPDB1/users01.dbf' SIZE 5M REUSE AUTOEXTEND ON NEXT  1280K MAXSIZE UNLIMITED  EXTENT MANAGEMENT LOCAL  SEGMENT SPACE MANAGEMENT  AUTO
FREEPDB1(3):ALTER DATABASE DEFAULT TABLESPACE "USERS"
FREEPDB1(3):Completed: ALTER DATABASE DEFAULT TABLESPACE "USERS"
ALTER PLUGGABLE DATABASE FREEPDB1 SAVE STATE
Completed: ALTER PLUGGABLE DATABASE FREEPDB1 SAVE STATE
2024-04-24T21:27:27.562404+00:00
ALTER SYSTEM SET local_listener='' SCOPE=BOTH;
ALTER PLUGGABLE DATABASE FREEPDB1 SAVE STATE
Completed: ALTER PLUGGABLE DATABASE FREEPDB1 SAVE STATE



### Install SQLCL

Download SQLCL latest

unzip /tmp/sqlcl-latest.zip 

/opt/oracle/sqlcl/bin/sql pdbadmin/We1c0m3_We1c0m3_@//10.0.0.81:1521/pdbmongo

/home/oracle/sqlcl/bin/sql pdbadmin/m#P52sap$V@localhost:1522/FREEPDB1

Install java11

 1021  sudo yum search java
 1022  sudo yum install java-11-openjdk-devel
 1023  /usr/lib/jvm/java-11-openjdk/bin/java


export JAVA_HOME=/usr/lib/jvm/java-11-openjdk


[oracle@ordsrhel89 bin]$ /home/oracle/sqlcl/bin/sql pdbadmin/m#P52sap$V@localhost:1522/FREEPDB1

Error: SQLcl requires Java 11 and above to run.
       Found Java version 8.
       Please set JAVA_HOME to appropriate version.

[oracle@ordsrhel89 bin]$ export JAVA_HOME=/usr/lib/jvm/java-11-openjdk
[oracle@ordsrhel89 bin]$ /home/oracle/sqlcl/bin/sql pdbadmin/m#P52sap$V@localhost:1522/FREEPDB1


SQLcl: Release 24.2 Production on Wed Jul 24 02:44:33 2024

Copyright (c) 1982, 2024, Oracle.  All rights reserved.

Connected to:
Oracle Database 23ai Free Release 23.0.0.0.0 - Develop, Learn, and Run for Free
Version 23.4.0.24.05

SQL> 

=> WORK !!!


# Select all tables
SELECT table_name FROM all_tables;


### Install python3 oracledb 


oracledb.exceptions.DatabaseError: DPI-1047: Cannot locate a 64-bit Oracle Client library: "libclntsh.so: cannot open shared object file: No such file or directory". See https://python-oracledb.readthedocs.io/en/latest/user_guide/initialization.html for help
Help: https://python-oracledb.readthedocs.io/en/latest/user_guide/troubleshooting.html#dpi-1047


instantclient-basiclite-linux.x64-23.4.0.24.05.zip


'/home/oracle/instantclient_23_4'
instantclient_23_4/




CREATE USER JUNTEXTUSER
IDENTIFIED BY Oracle4U
DEFAULT TABLESPACE users
TEMPORARY TABLESPACE temp
QUOTA UNLIMITED ON users;

GRANT CONNECT, RESOURCE TO JUNTEXTUSER;
GRANT DB_DEVELOPER_ROLE to JUNTEXTUSER;



### ###############################

[cloud-user@ordsrhel89 docker-alpine-libreoffice]$ podman pull alpine
Trying to pull docker.io/library/alpine:latest...
Getting image source signatures
Copying blob ec99f8b99825 done  
Copying config a606584aa9 done  
Writing manifest to image destination
a606584aa9aa875552092ec9e1d62cb98d486f51f389609914039aabd9414687
[cloud-user@ordsrhel89 docker-alpine-libreoffice]$ podman run -it alpine
/ # apk update
fetch https://dl-cdn.alpinelinux.org/alpine/v3.20/main/x86_64/APKINDEX.tar.gz
fetch https://dl-cdn.alpinelinux.org/alpine/v3.20/community/x86_64/APKINDEX.tar.gz
v3.20.1-47-gf11a40c5e1e [https://dl-cdn.alpinelinux.org/alpine/v3.20/main]
v3.20.1-46-g5090724b18b [https://dl-cdn.alpinelinux.org/alpine/v3.20/community]
OK: 24152 distinct packages available
/ # apk add python3.12
ERROR: unable to select packages:
  python3.12 (no such package):
    required by: world[python3.12]
/ # apk add python3
(1/17) Installing libbz2 (1.0.8-r6)
(2/17) Installing libexpat (2.6.2-r0)
(3/17) Installing libffi (3.4.6-r0)
(4/17) Installing gdbm (1.23-r1)
(5/17) Installing xz-libs (5.6.1-r3)
(6/17) Installing libgcc (13.2.1_git20240309-r0)
(7/17) Installing libstdc++ (13.2.1_git20240309-r0)
(8/17) Installing mpdecimal (4.0.0-r0)
(9/17) Installing ncurses-terminfo-base (6.4_p20240420-r0)
(10/17) Installing libncursesw (6.4_p20240420-r0)
(11/17) Installing libpanelw (6.4_p20240420-r0)
(12/17) Installing readline (8.2.10-r0)
(13/17) Installing sqlite-libs (3.45.3-r1)
(14/17) Installing python3 (3.12.3-r1)
(15/17) Installing python3-pycache-pyc0 (3.12.3-r1)
(16/17) Installing pyc (3.12.3-r1)
(17/17) Installing python3-pyc (3.12.3-r1)
Executing busybox-1.36.1-r29.trigger
OK: 50 MiB in 31 packages
/ # python3 --version
Python 3.12.3
/ # 




/usr/bin/libreoffice --invisible --headless --convert-to pdf:writer_pdf_Export --outdir "/tmp" "xxxxx.docx"

python3 /function/file2pdf.py "/tmp" "/tmp/Informe Santander Formato v3.docx" 



### #######################################
### Dockerfile for libreoffice
### #######################################


FROM alpine:latest
MAINTAINER operard<olivier.perard@oracle.com>

RUN apk update && apk add libreoffice

RUN apk --update --no-cache add python3 

RUN rm -rf /var/cache/apk/*

EXPOSE 8100

# replace default setup with a one disabling logos by default
ADD sofficerc /etc/sofficerc
ADD iniciar.sh /usr/bin/iniciar.sh

#VOLUME ["/tmp"]
#RUN mkdir /tmp

COPY *.docx /tmp/
ADD *.py /function/

RUN chmod +x /usr/bin/iniciar.sh

#ENTRYPOINT ["/usr/bin/iniciar.sh"]

### #######################################
### Dockerfile for python3.12
### #######################################

FROM python:3.12.2-slim

WORKDIR /app

COPY *.py .

COPY requirements.txt .

RUN pip install -r requirements.txt
VOLUME "/input"
VOLUME "/output"

CMD ["python3","extractpdf2collection.py","/input","/output"]



### #########################################################
### Dockerfile for libreoffice + extractpdf + db23ai
### #########################################################


FROM alpine:latest
MAINTAINER operard<olivier.perard@oracle.com>

RUN apk update && apk add libreoffice

RUN apk --update --no-cache add python3 

RUN rm -rf /var/cache/apk/*

# replace default setup with a one disabling logos by default
ADD sofficerc /etc/sofficerc
ADD iniciar.sh /usr/bin/iniciar.sh

RUN chmod +x /usr/bin/iniciar.sh

WORKDIR /app

COPY *.py .

COPY requirements.txt .

RUN pip install -r requirements.txt
VOLUME "/input"
VOLUME "/output"

CMD ["python3","extractpdf2collection.py","/input","/output"]


RUN python3 -m pip install PyPDF2
RUN python3 -m pip install sentence-transformers
RUN python3 -m pip install transformers
RUN python3 -m pip install langchain-community
RUN python3 -m pip install langchain
RUN python3 -m pip install langchain-huggingface



### #########################################################
### Dockerfile for libreoffice + extractpdf + db23ai
### #########################################################

FROM oraclelinux:8.9
MAINTAINER operard<olivier.perard@oracle.com>

RUN dnf update &&\
    dnf -y install oracle-epel-release-el8 &&\ 
    dnf -y install libreoffice &&\
    dnf -y install python3.12 python3.12-pip python3.12-setuptools python3.12-wheel &&\
    dnf clean all

RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.12

# replace default setup with a one disabling logos by default
ADD sofficerc /etc/sofficerc
ADD iniciar.sh /usr/bin/iniciar.sh

RUN chmod +x /usr/bin/iniciar.sh

WORKDIR /app

COPY *.py .

COPY requirements.txt .

RUN pip install -r requirements.txt
VOLUME "/input"
VOLUME "/output"

CMD ["python3","extractpdf2collection.py","/input","/output"]








RUN apk --update --no-cache add python3 


WORKDIR /function
RUN groupadd --gid 1000 fn && adduser --uid 1000 --gid fn fn

ARG release=23
ARG update=4

RUN microdnf -y install oracle-epel-release-el8 &&\
     microdnf -y install python3.11 python3.11-pip &&\
     microdnf -y install oracle-instantclient-release-el8 && \
     microdnf -y install oracle-instantclient-basic oracle-instantclient-devel && \
     microdnf remove oracle-epel-release-el8 &&\
     microdnf clean all

RUN mkdir /tmp/dbwallet
RUN chown -R fn:fn /tmp/dbwallet
ENV TNS_ADMIN=/tmp/dbwallet

ADD . /function/

RUN pip3 install --upgrade pip
RUN pip3 install --no-cache --no-cache-dir -r requirements.txt
RUN rm -fr /function/.pip_cache ~/.cache/pip requirements.txt func.yaml Dockerfile README.md

ENV PYTHONPATH=/python
#ENTRYPOINT ["/usr/local/bin/fdk", "/function/func.py", "handler"]





36  python3 --version
37  sudo dnf install python3.11
38  sudo dnf install python3.11-requests
39  sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.11
40  python3 --version
41  sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.11
42  sudo dnf install python3.11-requests
43  sudo update-alternatives --install /usr/bin/python3 python3 
44  ls /usr/local/bin
45  ls /usr/bin/
46  ls /usr/bin/python*
47  sudo update-alternatives --config python
48  python3 --version
49  sudo update-alternatives --config python3
50  python3 --version
51  python3
52  python
53  sudo dnf install python3.11-pip python3.11-setuptools python3.11-wheel
54  pwd
55  python3.11 -m venv --system-site-packages cohere



### #########################################################
### Dockerfile for libreoffice + extractpdf + db23ai
### #########################################################


podman rm extractpdf2db23ai
podman build  -f=Dockerfile --tag=oracle/extractpdf2db23ai:1.0.0.0.0 .
podman run -it --name extractpdf2db23ai  -v /home/cloud-user/input:/input  -v /home/cloud-user/output:/output  oracle/extractpdf2db23ai:1.0.0.0.0


#### Upload to docker.io

podman tag localhost/oracle/extractpdf2db23ai:1.0.0.0.0 operard/extractpdf2db23ai:1.0.0.0.0

podman push operard/extractpdf2db23ai:1.0.0.0.0

podman login docker.io


[cloud-user@ordsrhel89 ~]$ podman login docker.io
Username: operard
Password: 
Login Succeeded!
[cloud-user@ordsrhel89 ~]$ podman push operard/extractpdf2db23ai:1.0.0.0.0
Getting image source signatures
Copying blob bd04917099f4 done  
Copying blob c15afc54c51e done  
Copying blob a0c6dde5d101 done  
Copying blob 3756160ca107 done  
Copying blob e270436f9023 done  
Copying blob e69139bb204f done  
Copying blob 6fddc00e8d00 done  
Copying blob c12ccf3f8b5f done  
Copying config 937f11a9a8 done  
Writing manifest to image destination



docker pull docker.io/operard/extractpdf2db23ai:1.0.0.0.0



docker images
REPOSITORY                                    TAG          IMAGE ID      CREATED         SIZE
localhost/operard/extractpdf2db23ai           1.0.0.0.0    73e10ca1996c  16 minutes ago  9.66 GB


docker run -it --name extractpdf2db23ai  -v /home/cloud-user/input:/input  -v /home/cloud-user/output:/output  oracle/extractpdf2db23ai:1.0.0.0.0


docker run -it --name extractpdf2db23ai --pid=host --privileged -v /mnt/docker/input:/input:shared  -v /mnt/docker/output:/output:shared  docker.io/oracle/extractpdf2db23ai:1.0.0.0.0 



docker volume create --driver local \ 
--opt type=nfs \ 
--opt o=addr=nascsh.gobex.pri,rw \ 
--opt device=:/DocApex \ 
inputdocker




docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex/input' \
   --opt o='credentidals=/etc/docker.credenciales' \
   inputdocker

docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex/output' \
   --opt o='credentidals=/etc/docker.credenciales' \
   outputdocker

   cf703738514a



docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex/input' \
   --opt o='addr=nascsh.gobex.pri,username=uServidoresJava,password=Zurb4r4n2010,file_mode=0777,dir_mode=0777' \
   inputdocker
=> Not wowkring


docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex/input' \
   --opt o='username=uServidoresJava,password=Zurb4r4n2010,file_mode=0777,dir_mode=0777' \
   inputdocker
=>


docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex' \
   --opt o='username=uServidoresJava,password=Zurb4r4n2010,file_mode=0777,dir_mode=0777' \
   nfsdocker



docker run -it --name extractpdf2db23ai -v nfsdocker:/data b08d11446ea2




docker run -it --name testoli -v inputdocker:/data ubuntu

docker run -it --name testoli2 -v nfsdocker:/data ubuntu



docker volume create \
   --driver local \
   --opt type=cifs \
   --opt device='//nascsh.gobex.pri/DocApex/output' \
   --opt o='username=uServidoresJava,password=Zurb4r4n2010,file_mode=0777,dir_mode=0777' \
   outputdocker



   addr=nascsh.gobex.pri,


docker run -it --name extractpdf2db23ai --pid=host --privileged --mount source=inputdocker,destination=/input --mount source=outputdocker,destination=/output cf703738514a


docker run -it --name extractpdf2db23ai --mount source=inputdocker,destination=/input --mount source=outputdocker,destination=/output cf703738514a

docker run -it --name extractpdf2db23ai -v inputdocker:/input:ro  -v outputdocker:/output:rw cf703738514a


docker run -it --name extractpdf2db23ai -v "nfsdocker/input":/input:ro  -v "nfsdocker/output":/output:rw cf703738514a


docker run -it --name extractpdf2db23ai -v nfsdocker:/input  -v nfsdocker:/output cf703738514a

cf703738514a


cd /home/cloud-user/output
tar -czvf ../extremadura_vectors.tar.gz *



docker rm extractpdf2db23ai 

mkdir /home/cloud-user/input
cp * /home/cloud-user/input/.

mkdir /home/cloud-user/ouput



####

-v /home/cloud-user/input:/input  -v /home/cloud-user/output:/output

podman run -it --name extractpdf2db23ai  oracle/extractpdf2db23ai:1.0.0.0.0 extractpdf2collection.py "/home/cloud-user/input" "/home/cloud-user/output"



podman run -it --name extractpdf2db23ai -v /home/cloud-user/input:/data/input  -v /home/cloud-user/output:/data/output oracle/extractpdf2db23ai:1.0.0.0.0 extractpdf2collection.py "/data/input" "/data/output"



docker run -it --name extractpdf2db23ai -v nfsdocker:/data  operard/extractpdf2db23ai:1.0.0.0.0 extractpdf2collection.py "/data/input" "/data/output"


=> 

CIFS: Status code returned 0xc000006d STATUS_LOGON_FAILURE
[3024921.295007] CIFS: VFS: \\nascsh.gobex.pri Send error in SessSetup = -13
[3024921.295731] CIFS: VFS: cifs_mount failed w/return code = -13
[3024921.334960] podman0: port 2(veth1) entered disabled state




Traceback (most recent call last):
    File "/app/extractpdf2collection.py", line 204, in <module>
      sys.exit(main())  # next section explains the use of sys.exit
               ^^^^^^
    File "/app/extractpdf2collection.py", line 201, in main
      analyzeAndConvertAllFiles2(sys.argv[1], sys.argv[2])
    File "/app/extractpdf2collection.py", line 190, in analyzeAndConvertAllFiles2
      convert_file(src_file, dest_file)
    File "/app/extractpdf2collection.py", line 154, in convert_file
      doc = extractPdf2Vector(filepdf, filename)
            ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
    File "/app/extractpdf2collection.py", line 40, in extractPdf2Vector
      text = pdf_to_text(filepath)
             ^^^^^^^^^^^^^^^^^^^^^
    File "/app/extractpdf2collection.py", line 23, in pdf_to_text
      pdf_file = open(file_path, 'rb')
                 ^^^^^^^^^^^^^^^^^^^^^
  FileNotFoundError: [Errno 2] No such file or directory: '/tmp/PLN.pdf'




#### 


declare
  metadata VARCHAR2(4000) :=
          '{
      "tableName" : "MOVIMIENTOS_HISMO_AHORRO_0",
      "contentColumn" : {
        "name" : "DATA",
        "sqlType": "BLOB",
        "jsonFormat" : "OSON"
      },
      "keyColumn" : {
       "name" : "ID",
       "assignmentMethod" : "EMBEDDED_OID",
      "path" : "_id"
     },
     "versionColumn" : {
        "name" : "VERSION",
        "method" : "UUID"
     },
     "lastModifiedColumn" : {
        "name" : "LAST_MODIFIED"
     },
     "creationTimeColumn" : {
        "name" : "CREATED_ON"
     }
   }';
   create_time varchar2(255);
begin
  DBMS_SODA_ADMIN.CREATE_COLLECTION(
                   P_URI_NAME    => 'movimientos_hismo_ahorro_0',
                   P_CREATE_MODE => 'MAP',
                   P_DESCRIPTOR  => metadata,
                   P_CREATE_TIME => create_time);
end;

/


DECLARE
  coll    SODA_COLLECTION_T;
  idx     SODA_INDEX_LIST_T;
BEGIN
  coll := DBMS_SODA.open_collection('myCollectionName');
  idx := coll.list_indexes;
  DBMS_OUTPUT.put_line('Number of indexes: ' || idx.COUNT);

  if (idx.COUNT <> 0) then
    for i in idx.FIRST..idx.LAST
    loop
      DBMS_OUTPUT.put_line('Index ' || i || ': ');
      DBMS_OUTPUT.put_line(json_query(idx(i), '$' pretty));
    end loop;
  else
    DBMS_OUTPUT.put_line('No indexes defined on this collection');
  end if;
END;
/



for filename in os.listdir(input_dir):
    doc = ''
    if filename.endswith('.doc') or filename.endswith('.docx'):
        fileorig = os.path.join(input_dir, filename)
        # convert to pdf 
        file2pdf.convert_to('/tmp', fileorig)
        #
        filepdf = os.path.join('/tmp', os.path.basename(fileorig).split('.')[0] + '.pdf')
        doc = extractPdf2Vector(filepdf, filename)
        # Delete temporal file
        try:
            os.remove(filepdf)
        except FileNotFoundError:
            print(f"File '{filepdf}' not found.")
    elif filename.endswith('.pdf'):
        doc = extractPdf2Vector(os.path.join(input_dir, filename), filename)

    # Save  file to output
    if len(doc) > 0:
        output_file = os.path.join(output_dir, filename ) + '.json'
        print(output_file)
        with open (output_file, 'w') as f:
            json.dump(doc, f)

