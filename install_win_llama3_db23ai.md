# PODMAN Installation in Windows 

Here you can see the tutorial to install **Podman Desktop** in Windows.


## Step 1: PODMAN Desktop Installation

![Step 1](./images/win_slide1.png)

## Step 2: Click on SETUP

![Step 2](./images/win_slide2.png)

## Step 3: Execute DISM

![Step 3](./images/win_slide3.png)

Execute DISM Command desde PowerShell:

```Code
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
````

## Step 4: Execute PODMAN Setup

![Step 4](./images/win_slide4.png)

## Step 5:

![Step 5](./images/win_slide5.png)

## Step 6: PODMAN Setup in execution

![Step 6](./images/win_slide6.png)

## Step 7: PODMAN Setup in execution

![Step 7](./images/win_slide7.png)

## Step 8: Check PODMAN Setup 

![Step 8](./images/win_slide8.png)

## Step 9: Check PODMAN Installation.

![Step 9](./images/win_slide9.png)

## Step 10: Execute podman commands 

Execute:

```Code
podman ps

podman images
```

Download the images from OCI Repository for x86:

```Code
podman pull container-registry.oracle.com/database/free:latest

podman pull fra.ocir.io/frg6v9xlrkul/airagdb23aiinbox:1.0.0.0.0
```


![Step 10](./images/win_slide10.png)

## Step 11: Check log of container installation.

You can check the log during the DB23ai Container Installation:

```Code
podman logs -f 23aidb

```

![Step 11](./images/win_slide11.png)

## Step 12: Check both containers

After executing the BAT script, you could check in PODMAN Desktop the installation of the 2 containers:

![Step 12](./images/win_slide12.png)

## Step 13: Check both containers after days

After executing the BAT script, you could check in PODMAN Desktop the installation of the 2 containers:

![Step 13](./images/win_slide13.png)

