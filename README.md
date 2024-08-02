# AI RAG Demo for Beginners Hands-On Lab

AI RAG Demo with Cohere and Oracle Generative AI could be deployed in PODMAN/DOCKER in your PC or VM in your tenancy.

## AI RAG Deployment in VM

You can find the information [here](./installvmragdemo.md)


## AI RAG Deployment in PODMAN in your PC

1. If you must install podman in your MAC OSX M1, Click the next link:

    [Deploy in your MAC](./install_podman_macosx.md)

2. Deploy **AI RAG Docker** page. 
    
    You must download the docker image in your podman.

```Code

podman pull docker.io/operard/airagdemo:1.0.0.0.0

```


## Starting The Web Application

To see the results of the lab, you'll need to start the web server using Terminal.

1. In the menu at the top of the page, select **File->New->Terminal**.
2. Enter the following commands, hitting return after each one (feel free to copy and paste)

        cd /home/opc/redbull-analytics-hol/beginners/web
        source /home/opc/redbullenv/bin/activate
        python3 app.py
3. Open a web browser to the public IP of your Chatbot RAG Demo AI, but use port 8501:

        http://xxx.xxx.xxx.xxx:8501

    The Public IP is the one at which you're currently accessing Chatbot, which we copied from the Running Instances step above.
