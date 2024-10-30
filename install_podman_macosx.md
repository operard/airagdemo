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


## Clean the podman deployment in MAC OSX

If you must clean your environment in order to reset it, use the next commands:

```Code

podman machine stop

podman machine reset

```




podman machine stop podman-machine-default
podman machine set -m 4096 podman-machine-default
podman machine start podman-machine-default


podman build -t localhost/database:23.5.0-free-arm64 -f Containerfile.free .

podman tag localhost/database:23.5.0-free-arm64 operard/database:23.5.0-free-arm64

podman push operard/database:23.5.0-free-arm64



podman network create --driver bridge --subnet 10.22.1.0/24 airag

podman run -d --name 23aidb --network airag --ip 10.22.1.12 -p 1522:1521 \
localhost/database:23.5.0-free-arm64



CREATE USER VECDEMO IDENTIFIED BY "Oracle4U" DEFAULT TABLESPACE users TEMPORARY TABLESPACE temp QUOTA UNLIMITED ON users;
GRANT CONNECT, RESOURCE TO VECDEMO;
GRANT DB_DEVELOPER_ROLE to VECDEMO;

podman exec -it 23aidb sqlplus VECDEMO/Oracle4U@FREEPDB1



# En mi PC MAC OSX M1

podman build  -f=Dockerfile --tag=operard/airagdb23aiinbox:1.0.0-arm64 .

podman push operard/airagdb23aiinbox:1.0.0-arm64

operard/airagdb23aiinbox:1.0.0-arm64



http://sitex.gobex.es/SITEX/calificacionexpedients/mostrardatossectoriales/2794/fd75adaf



