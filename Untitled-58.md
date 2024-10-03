


operard@MacBook-Pro podman % ./setup.sh         
Machine "podman-machine-default" stopped successfully
Starting machine "podman-machine-default"

This machine is currently configured in rootless mode. If your containers
require root permissions (e.g. ports < 1024), or if you run into compatibility
issues with non-podman clients, you can switch using the following command:

	podman machine set --rootful

API forwarding listening on: /var/folders/kb/jznn9w2n1bs3kjyyxdbnmydh0000gn/T/podman/podman-machine-default-api.sock

The system helper service is not installed; the default Docker API socket
address can't be used by podman. If you would like to install it, run the following commands:

        sudo /opt/homebrew/Cellar/podman/5.2.2/bin/podman-mac-helper install
        podman machine stop; podman machine start

You can still connect Docker API clients by setting DOCKER_HOST using the
following command in your terminal session:

        export DOCKER_HOST='unix:///var/folders/kb/jznn9w2n1bs3kjyyxdbnmydh0000gn/T/podman/podman-machine-default-api.sock'

Machine "podman-machine-default" started successfully
error: "qemu-user-static" is already provided by: qemu-user-static-2:8.2.2-1.fc40.aarch64. Use --allow-inactive to explicitly require it.
Machine "podman-machine-default" stopped successfully
Starting machine "podman-machine-default"



podman machine ssh "${PODMAN_MACHINE_NAME}" 'sudo rpm-ostree install qemu-system-aarch64'



https://github.com/containers/podman/releases/tag/v5.0.0

./setup-x86_64.sh --cpus 4 --memory 8192 --disk-size 24


export ORACLE_BASE=/opt/oracle
export ORACLE_HOME=/opt/oracle/product/23ai/dbhomeFree
export INSTALL_FILE_1=oracle-database-free-23ai-1.0-1.el8.x86_64.rpm
export PWD_FILE=setPassword.sh
export CREATE_DB_FILE=createDB.sh
export USER_SCRIPTS_FILE=runUserScripts.sh
export CONF_FILE=oracle-free-23ai.conf
export CHECK_SPACE_FILE=checkSpace.sh
export CHECK_DB_FILE=checkDBStatus.sh
export SETUP_LINUX_FILE=setupLinuxEnv.sh
export DECRYPT_PWD_FILE=decryptPassword.sh
export CONFIG_TCPS_FILE=configTcps.sh
export INSTALL_DIR=/install
export ORACLE_DOCKER_INSTALL=true
export CHECKPOINT_FILE_EXTN=.created
export PATH=/opt/oracle/product/23ai/dbhomeFree/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
export CRYPTOGRAPHY_OPENSSL_NO_LEGACY=1
export SETUPTC=setup.sh
export BLOBREADER=blobReader.py
export CREATE_TC_SVCS_SCRIPT=createService.sh
export CREATE_BLOB_SCRIPT=createBlob.sh
export REGISTER_TC_SVCS_SCRIPT=registerService.sh
export ENABLE_ARCHIVELOG=true
export ENABLE_FORCE_LOGGING=true
export ORACLE_SID=FREE
export ORACLE_PDB=FREEPDB1
export ORACLE_PWD=Oracle4U
export AUTO_MEM_CALCULATION=false
export CMD_EXEC=cmdExec
export DEMO_APP=demoapp.sql
export MAIN_PY=main.py
export COMMON_PY=oracommon.py
export ENV_PY=oraenv.py
export FACTORY_PY=orafactory.py
export GSM_PY=oragsm.py
export LOGGER_PY=oralogger.py
export MACHINE_PY=oramachine.py
export PCATALOG_PY=orapcatalog.py
export SHARD_PY=orapshard.py
export SCATALOG_PY=orascatalog.py
export SSHARD_PY=orasshard.py
export RUN_SHARD_FILE=runOraShardSetup.sh
export RUN_FILE=runOracle.sh
export PYTHON_FILE=/usr/bin/python
export PYTHON3_FILE=/usr/libexec/platform-python3.6
export SHARD_SETUP=false


podman machine init --cpus 4 --memory=8170


podman pull --arch=arm64 container-registry.oracle.com/database/free:latest

podman run -it --name 23aidb --entrypoint /bin/bash container-registry.oracle.com/database/free:latest




mkdir /Users/operard/Desktop/dev/models



/Users/operard/Documents/customers/administracion/junta_extremadura/data

docker run -it --network airag --ip 10.22.1.11  -p 8501:8501 -v /Users/operard/database:/config -v /Users/operard/Documents/customers/administracion/junta_extremadura/data:/data --name airagdb23aiinbox --entrypoint /bin/bash localhost/airagdb23aiinbox:1.0.0.0.0


Test en LINUX:
-----------------
podman exec -it 23aidb sqlplus VECDEMO/Oracle4U@FREEPDB1

select table_name from user_tables;


/home/cloud-user/input

export username=VECDEMO
export password=Oracle4U
export service="localhost:1522/FREEPDB1"

python3 ovs_embed.py

python3 rag.py


=> DB

podman exec -it 23aidb sqlplus VECDEMO/Oracle4U@FREEPDB1

SQL> select table_name from user_tables;

TABLE_NAME
--------------------------------------------------------------------------------
JUNTA_EXT
AIRAGINBOX
OVS
VECTOR$IVF_IDX1$73611_73619_0$IVF_FLAT_CENTROIDS
VECTOR$IVF_IDX1$73611_73619_0$IVF_FLAT_CENTROID_PARTITIONS

SQL> select count(*) from OVS;

  COUNT(*)
----------
	91



Test en MacOSX:
-----------------


export username=VECDEMO
export password=Oracle4U
export service="10.22.1.12:1521/FREEPDB1"


export username=VECDEMO
export password=Oracle4U
export service="localhost:1522/FREEPDB1"

export model="/Users/operard/Desktop/dev/models/Meta-Llama-3-8B-Instruct.Q4_K_M.gguf"


export ollamaurl = "http://localhost:11434"


Modelos en Castellano:
------------------------



wget https://huggingface.co/Nichonauta/brasa-3.1-8b-it-v1-Q4_0-GGUF/blob/main/brasa-3.1-8b-it-v1-q4_0.gguf




podman run -d --name 23aidb --network airag --ip 10.22.1.12 -p 1522:1521 container-registry.oracle.com/database/free:latest

podman exec 23aidb ./setPassword.sh Oracle4U

podman exec -it 23aidb sqlplus / as SYSDBA

ALTER SESSION SET CONTAINER=FREEPDB1;
CREATE USER VECDEMO IDENTIFIED BY "Oracle4U" DEFAULT TABLESPACE users TEMPORARY TABLESPACE temp QUOTA UNLIMITED ON users;
GRANT CONNECT, RESOURCE TO VECDEMO;
GRANT DB_DEVELOPER_ROLE to VECDEMO;
COMMIT;


podman exec -it 23aidb sqlplus VECDEMO/Oracle4U@FREEPDB1


podman build  -f=Dockerfile --tag=oracle/llama3finetuning:1.0.0.0.0 .


podman run -it --network airag --ip 10.22.1.15 --name llama3finetuning -v /home/cloud-user:/data  localhost/oracle/llama3finetuning:1.0.0.0.0 createRAGDataset.py "VECDEMO" "Oracle4U" "10.22.1.12:1521/FREEPDB1" "JUNTA_OVS" "/data/pdf"


podman run -it --network airag --ip 10.22.1.15 --name llama3finetuning -v /home/cloud-user:/data --replace localhost/oracle/llama3finetuning:1.0.0.0.0 createRAGDataset.py "VECDEMO" "Oracle4U" "10.22.1.12:1521/FREEPDB1" "JUNTA_OVS2" "/data/pdf"


podman run -it --network airag --ip 10.22.1.15 --name llama3finetuning -v /home/cloud-user:/data  --entrypoint /bin/bash localhost/oracle/llama3finetuning:1.0.0.0.0 


podman tag localhost/oracle/llama3finetuning:1.0.0.0.0 operard/llama3finetuning:1.0.0.0.0

podman push operard/llama3finetuning:1.0.0.0.0





JSONLOADER
----------------

podman build  -f=Dockerfile --tag=oracle/jsonvector2db23ai:1.0.0.0.0 .

podman tag localhost/oracle/jsonvector2db23ai:1.0.0.0.0 operard/jsonvector2db23ai:1.0.0.0.0

docker exec -it 23aidb  /opt/oracle/product/23ai/dbhomeFree/python/bin/python3.12 csv2db.py load -f "/data/cartografia/xxxxx.csv" --dbtype oracle -t JUNTA_CSV -u JUNTEXTUSER -p "Oracle4U" -d "FREEPDB1" 




docker run -d --network junta-tier --ip 10.22.0.10 --name 23aidb -p 1522:1521 -v cfsdocker:/data \
-v /root/oradata:/opt/oracle/oradata \
-v /root/reco:/opt/oracle/reco \
-e ENABLE_ARCHIVELOG=true  \
docker.io/operard/jsonvector2db23ai:1.0.0.0.0



docker exec -it 23aidb sqlplus JUNTEXTUSER/Oracle4U@FREEPDB1



docker run -it --network junta-tier --ip 10.22.0.15 -v cfsdocker:/data --name llama3finetuning docker.io/operard/llama3finetuning:1.0.0.0.0 createRAGDataset.py "JUNTEXTUSER" "Oracle4U" "10.22.0.10:1521/FREEPDB1" "JUNTA_OVS" "/data/pdf"





docker exec -it 23aidb  /opt/oracle/product/23ai/dbhomeFree/python/bin/python3.12 csv2db.py load -f "/data/cartografia/xxxxx.csv" --dbtype oracle -t JUNTA_CSV -u JUNTEXTUSER -p "Oracle4U" -d "FREEPDB1" 


docker exec -it 23aidb  /opt/oracle/product/23ai/dbhomeFree/python/bin/python3.12 csv2db.py load -f "/data/cartografia/yacimiento_xxxxx.csv" --dbtype oracle -t JUNTA_YACIMIENTO -u JUNTEXTUSER -p "Oracle4U" -d "FREEPDB1" 



CMAKE_ARGS="-DLLAMA_METAL=on" FORCE_CMAKE=1 pip install --upgrade --force-reinstall llama-cpp-python --no-cache-dir


/Users/operard/Desktop/dev/models/Phi-3-mini-4k-instruct-q4.gguf



llm = Llama(
      #model_path="/Users/operard/Desktop/dev/models/Phi-3-mini-4k-instruct-q4.gguf",
      model_path="/Users/operard/Desktop/dev/models/Meta-Llama-3-8B-Instruct.Q4_K_M.gguf",
      #n_gpu_layers=10, # Uncomment to use GPU acceleration
      # seed=1337, # Uncomment to set a specific seed
      #n_ctx=2048, # Uncomment to increase the context window
      n_gpu_layers=-1,
      ctx_size=2048,
      temperature=0.8,
      top_p=0.9,
      max_tokens=128,
      stop=["\n", "Q:"],
      echo=True,
      verbose=True,
      seed=1234,
      model_kwargs={"use_fp16": True},
      generate_kwargs={"temperature": 0.7, "top_k": 50}
)




llama-server  \
    --model "/Users/operard/Desktop/dev/models/Meta-Llama-3-8B-Instruct.Q4_K_M.gguf" \
    --ctx_size 2048 -n -1 -b 256  \
    --temp 0.8 --repeat_penalty 1.1 -t 8


----------------


docker run -d --network airag --ip 10.22.1.11  -p 8501:8501 -p 11434:11434 -v /home/cloud-user/database:/config --name airagdb23aiinbox localhost/airagdb23aiinbox:1.0.0.0.0



[cloud-user@ordsrhel89 ollama]$ curl -fsSL https://ollama.com/install.sh | sh
>>> Installing ollama to /usr/local
>>> Downloading Linux amd64 bundle
######################################################################## 100.0%##O#- #                                                                   ######################################################################## 100.0%
>>> Adding ollama user to render group...
>>> Adding ollama user to video group...
>>> Adding current user to ollama group...
>>> Creating ollama systemd service...
>>> Enabling and starting ollama service...
Created symlink /etc/systemd/system/default.target.wants/ollama.service → /etc/systemd/system/ollama.service.
>>> The Ollama API is now available at 127.0.0.1:11434.
>>> Install complete. Run "ollama" from the command line.
WARNING: No NVIDIA/AMD GPU detected. Ollama will run in CPU-only mode.



11435

OLLAMA_HOST=127.0.0.1:11435 ollama serve &

ollama run llama3.1

streamlit run llama3_1_Db23ai.py --server.port=8501 --server.address=0.0.0.0


wget https://huggingface.co/Nichonauta/brasa-3.1-8b-it-v1-Q4_0-GGUF/blob/main/brasa-3.1-8b-it-v1-q4_0.gguf



curl --location 'http://127.0.0.1:11434/api/chat' \
--data '{
  "model": "mistral:latest", 
  "messages": [
    {
      "role": "system", 
      "content": "you are a salty pirate" 
    },
    {
      "role": "user", 
      "content": "why is the sky blue" 
    }
  ],
  "stream": false 
}'



curl --location 'http://localhost:11434/api/generate' \
--data '{
    "model": "llama3.1",
    "prompt": "what is the meaning of life?",
    "system": "talk like a pirate",
    "stream": false
}'




generame un contrato de alquiler de casa


curl --location 'http://localhost:11434/api/generate' \
--data '{
    "model": "llama3.1",
    "prompt": "generame un contrato de alquiler de casa",
    "system": "Hablame como un profesional",
    "stream": true
}'


time curl --location 'http://localhost:11434/api/generate' \
--data '{
    "model": "llama3.1",
    "prompt": "generame un contrato de alquiler de casa",
    "system": "Hablame como un profesional",
    "stream": false
}'




curl http://localhost:11434/v1/chat/completions \
  -H "Content-Type: application/json" \
  -d '{
    "model": "llama3.1",
    "messages": [
      {
        "role": "user",
        "content": [
          {
            "type": "text",
            "text": "What'\''s in this image?"
          },
          {
            "type": "image_url",
            "image_url": {
               "url": "iVBORw0KGgoAAAANSUhEUgAAAG0AAABmCAYAAADBPx+VAAAACXBIWXMAAAsTAAALEwEAmpwYAAAAAXNSR0IArs4c6QAAAARnQU1BAACxjwv8YQUAAA3VSURBVHgB7Z27r0zdG8fX743i1bi1ikMoFMQloXRpKFFIqI7LH4BEQ+NWIkjQuSWCRIEoULk0gsK1kCBI0IhrQVT7tz/7zZo888yz1r7MnDl7z5xvsjkzs2fP3uu71nNfa7lkAsm7d++Sffv2JbNmzUqcc8m0adOSzZs3Z+/XES4ZckAWJEGWPiCxjsQNLWmQsWjRIpMseaxcuTKpG/7HP27I8P79e7dq1ars/yL4/v27S0ejqwv+cUOGEGGpKHR37tzJCEpHV9tnT58+dXXCJDdECBE2Ojrqjh071hpNECjx4cMHVycM1Uhbv359B2F79+51586daxN/+pyRkRFXKyRDAqxEp4yMlDDzXG1NPnnyJKkThoK0VFd1ELZu3TrzXKxKfW7dMBQ6bcuWLW2v0VlHjx41z717927ba22U9APcw7Nnz1oGEPeL3m3p2mTAYYnFmMOMXybPPXv2bNIPpFZr1NHn4HMw0KRBjg9NuRw95s8PEcz/6DZELQd/09C9QGq5RsmSRybqkwHGjh07OsJSsYYm3ijPpyHzoiacg35MLdDSIS/O1yM778jOTwYUkKNHWUzUWaOsylE00MyI0fcnOwIdjvtNdW/HZwNLGg+sR1kMepSNJXmIwxBZiG8tDTpEZzKg0GItNsosY8USkxDhD0Rinuiko2gfL/RbiD2LZAjU9zKQJj8RDR0vJBR1/Phx9+PHj9Z7REF4nTZkxzX4LCXHrV271qXkBAPGfP/atWvu/PnzHe4C97F48eIsRLZ9+3a3f/9+87dwP1JxaF7/3r17ba+5l4EcaVo0lj3SBq5kGTJSQmLWMjgYNei2GPT1MuMqGTDEFHzeQSP2wi/jGnkmPJ/nhccs44jvDAxpVcxnq0F6eT8h4ni/iIWpR5lPyA6ETkNXoSukvpJAD3AsXLiwpZs49+fPn5ke4j10TqYvegSfn0OnafC+Tv9ooA/JPkgQysqQNBzagXY55nO/oa1F7qvIPWkRL12WRpMWUvpVDYmxAPehxWSe8ZEXL20sadYIozfmNch4QJPAfeJgW3rNsnzphBKNJM2KKODo1rVOMRYik5ETy3ix4qWNI81qAAirizgMIc+yhTytx0JWZuNI03qsrgWlGtwjoS9XwgUhWGyhUaRZZQNNIEwCiXD16tXcAHUs79co0vSD8rrJCIW98pzvxpAWyyo3HYwqS0+H0BjStClcZJT5coMm6D2LOF8TolGJtK9fvyZpyiC5ePFi9nc/oJU4eiEP0jVoAnHa9wyJycITMP78+eMeP37sXrx44d6+fdt6f82aNdkx1pg9e3Zb5W+RSRE+n+VjksQWifvVaTKFhn5O8my63K8Qabdv33b379/PiAP//vuvW7BggZszZ072/+TJk91YgkafPn166zXB1rQHFvouAWHq9z3SEevSUerqCn2/dDCeta2jxYbr69evk4MHDyY7d+7MjhMnTiTPnz9Pfv/+nfQT2ggpO2dMF8cghuoM7Ygj5iWCqRlGFml0QC/ftGmTmzt3rmsaKDsgBSPh0/8yPeLLBihLkOKJc0jp8H8vUzcxIA1k6QJ/c78tWEyj5P3o4u9+jywNPdJi5rAH9x0KHcl4Hg570eQp3+vHXGyrmEeigzQsQsjavXt38ujRo44LQuDDhw+TW7duRS1HGgMxhNXHgflaNTOsHyKvHK5Ijo2jbFjJBQK9YwFd6RVMzfgRBmEfP37suBBm/p49e1qjEP2mwTViNRo0VJWH1deMXcNK08uUjVUu7s/zRaL+oLNxz1bpANco4npUgX4G2eFbpDFyQoQxojBCpEGSytmOH8qrH5Q9vuzD6ofQylkCUmh8DBAr+q8JCyVNtWQIidKQE9wNtLSQnS4jDSsxNHogzFuQBw4cyM61UKVsjfr3ooBkPSqqQHesUPWVtzi9/vQi1T+rJj7WiTz4Pt/l3LxUkr5P2VYZaZ4URpsE+st/dujQoaBBYokbrz/8TJNQYLSonrPS9kUaSkPeZyj1AWSj+d+VBoy1pIWVNed8P0Ll/ee5HdGRhrHhR5GGN0r4LGZBaj8oFDJitBTJzIZgFcmU0Y8ytWMZMzJOaXUSrUs5RxKnrxmbb5YXO9VGUhtpXldhEUogFr3IzIsvlpmdosVcGVGXFWp2oU9kLFL3dEkSz6NHEY1sjSRdIuDFWEhd8KxFqsRi1uM/nz9/zpxnwlESONdg6dKlbsaMGS4EHFHtjFIDHwKOo46l4TxSuxgDzi+rE2jg+BaFruOX4HXa0Nnf1lwAPufZeF8/r6zD97WK2qFnGjBxTw5qNGPxT+5T/r7/7RawFC3j4vTp09koCxkeHjqbHJqArmH5UrFKKksnxrK7FuRIs8STfBZv+luugXZ2pR/pP9Ois4z+TiMzUUkUjD0iEi1fzX8GmXyuxUBRcaUfykV0YZnlJGKQpOiGB76x5GeWkWWJc3mOrK6S7xdND+W5N6XyaRgtWJFe13GkaZnKOsYqGdOVVVbGupsyA/l7emTLHi7vwTdirNEt0qxnzAvBFcnQF16xh/TMpUuXHDowhlA9vQVraQhkudRdzOnK+04ZSP3DUhVSP61YsaLtd/ks7ZgtPcXqPqEafHkdqa84X6aCeL7YWlv6edGFHb+ZFICPlljHhg0bKuk0CSvVznWsotRu433alNdFrqG45ejoaPCaUkWERpLXjzFL2Rpllp7PJU2a/v7Ab8N05/9t27Z16KUqoFGsxnI9EosS2niSYg9SpU6B4JgTrvVW1flt1sT+0ADIJU2maXzcUTraGCRaL1Wp9rUMk16PMom8QhruxzvZIegJjFU7LLCePfS8uaQdPny4jTTL0dbee5mYokQsXTIWNY46kuMbnt8Kmec+LGWtOVIl9cT1rCB0V8WqkjAsRwta93TbwNYoGKsUSChN44lgBNCoHLHzquYKrU6qZ8lolCIN0Rh6cP0Q3U6I6IXILYOQI513hJaSKAorFpuHXJNfVlpRtmYBk1Su1obZr5dnKAO+L10Hrj3WZW+E3qh6IszE37F6EB+68mGpvKm4eb9bFrlzrok7fvr0Kfv727dvWRmdVTJHw0qiiCUSZ6wCK+7XL/AcsgNyL74DQQ730sv78Su7+t/A36MdY0sW5o40ahslXr58aZ5HtZB8GH64m9EmMZ7FpYw4T6QnrZfgenrhFxaSiSGXtPnz57e9TkNZLvTjeqhr734CNtrK41L40sUQckmj1lGKQ0rC37x544r8eNXRpnVE3ZZY7zXo8NomiO0ZUCj2uHz58rbXoZ6gc0uA+F6ZeKS/jhRDUq8MKrTho9fEkihMmhxtBI1DxKFY9XLpVcSkfoi8JGnToZO5sU5aiDQIW716ddt7ZLYtMQlhECdBGXZZMWldY5BHm5xgAroWj4C0hbYkSc/jBmggIrXJWlZM6pSETsEPGqZOndr2uuuR5rF169a2HoHPdurUKZM4CO1WTPqaDaAd+GFGKdIQkxAn9RuEWcTRyN2KSUgiSgF5aWzPTeA/lN5rZubMmR2bE4SIC4nJoltgAV/dVefZm72AtctUCJU2CMJ327hxY9t7EHbkyJFseq+EJSY16RPo3Dkq1kkr7+q0bNmyDuLQcZBEPYmHVdOBiJyIlrRDq41YPWfXOxUysi5fvtyaj+2BpcnsUV/oSoEMOk2CQGlr4ckhBwaetBhjCwH0ZHtJROPJkyc7UjcYLDjmrH7ADTEBXFfOYmB0k9oYBOjJ8b4aOYSe7QkKcYhFlq3QYLQhSidNmtS2RATwy8YOM3EQJsUjKiaWZ+vZToUQgzhkHXudb/PW5YMHD9yZM2faPsMwoc7RciYJXbGuBqJ1UIGKKLv915jsvgtJxCZDubdXr165mzdvtr1Hz5LONA8jrUwKPqsmVesKa49S3Q4WxmRPUEYdTjgiUcfUwLx589ySJUva3oMkP6IYddq6HMS4o55xBJBUeRjzfa4Zdeg56QZ43LhxoyPo7Lf1kNt7oO8wWAbNwaYjIv5lhyS7kRf96dvm5Jah8vfvX3flyhX35cuX6HfzFHOToS1H4BenCaHvO8pr8iDuwoUL7tevX+b5ZdbBair0xkFIlFDlW4ZknEClsp/TzXyAKVOmmHWFVSbDNw1l1+4f90U6IY/q4V27dpnE9bJ+v87QEydjqx/UamVVPRG+mwkNTYN+9tjkwzEx+atCm/X9WvWtDtAb68Wy9LXa1UmvCDDIpPkyOQ5ZwSzJ4jMrvFcr0rSjOUh+GcT4LSg5ugkW1Io0/SCDQBojh0hPlaJdah+tkVYrnTZowP8iq1F1TgMBBauufyB33x1v+NWFYmT5KmppgHC+NkAgbmRkpD3yn9QIseXymoTQFGQmIOKTxiZIWpvAatenVqRVXf2nTrAWMsPnKrMZHz6bJq5jvce6QK8J1cQNgKxlJapMPdZSR64/UivS9NztpkVEdKcrs5alhhWP9NeqlfWopzhZScI6QxseegZRGeg5a8C3Re1Mfl1ScP36ddcUaMuv24iOJtz7sbUjTS4qBvKmstYJoUauiuD3k5qhyr7QdUHMeCgLa1Ear9NquemdXgmum4fvJ6w1lqsuDhNrg1qSpleJK7K3TF0Q2jSd94uSZ60kK1e3qyVpQK6PVWXp2/FC3mp6jBhKKOiY2h3gtUV64TWM6wDETRPLDfSakXmH3w8g9Jlug8ZtTt4kVF0kLUYYmCCtD/DrQ5YhMGbA9L3ucdjh0y8kOHW5gU/VEEmJTcL4Pz/f7mgoAbYkAAAAAElFTkSuQmCC"
            }
          }
        ]
      }
    ],
    "max_tokens": 300
  }'