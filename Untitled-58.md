


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
export service="localhost:1521/FREEPDB1"

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


export username=VECDEMO
export password=Oracle4U
export service="localhost:1522/FREEPDB1"
export ollamaurl="http://localhost:11434"


Simplificación Administrativa basada en IA


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
               "url": "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"
            }
          }
        ]
      }
    ],
    "max_tokens": 300
  }'




--------------------------------------------


        # Prompt
        template = """Lo siguiente es el uso del contexto y la pregunta final es la respuesta concisa. La respuesta es la ocasión, la respuesta es la ocasión.。
            {context}
            Preguntar: {question}
            Respuesta :"""

        #prompt_template = '''[INST] <<SYS>>
        #You are a friendly chatbot who always responds in the style of a pirate
        #<</SYS>>
        #{prompt}[/INST]
        #'''

        # 
        question_prompt = PromptTemplate(
            template=template, 
            input_variables=["question"] 
        )

        # RAG
        qa = RetrievalQA.from_chain_type(
            llm=llm,
            chain_type="stuff",
            retriever=ovs.as_retriever(search_kwargs={'k': 5}),
            return_source_documents=True,
            chain_type_kwargs={"prompt": question_prompt}
        )



# First Version
def call_llama3(modelname, prompt):
    # First Version
    # return ollama.chat(model='llama3', messages=[{'role':'user', 'content': prompt}])['message']['content']
    #return ollama.chat(model=modelname, messages=[{'role':'user', 'content': prompt}])['message']['content']
    # client = Client(host='http://localhost:11434')
    client = Client(host=llama_url)
    return client.chat(model=modelname, messages=[{'role':'user', 'content': prompt}])['message']['content']





Simplificación Administrativa basada en IA

Para el Congreso de Extremadura me piden una foto tuya, que ya la tengo del evento de la Universidad y un título de tu Ponencia, en la que mostraríamos el caso de uso de Patrimonio Cultural

 

¿Qué te parece el título “Simplificación Administrativa basada en IA”? si se te ocurre algún otro bienvenido sea



IA a gran escala: Escalando tus modelos con OCI Superclusters, GPUs y NVIDIA



1. Introducción a OCI Superclusters <br></div><div>
- ¿Qué son los Superclusters?<br></div><div>
- Beneficios clave para la IA<br></div><div>
- Comparación con otras soluciones en la nube<br></div><div>
2. GPUs NVIDIA y su papel en la IA<br></div><div>
- Arquitecturas de las GPUs NVIDIA relevantes para la IA<br></div><div>
- Frameworks de deep learning soportados<br></div><div>
- Optimizaciones específicas para OCI<br></div><div>
3. Caso de uso: Entrenamiento de modelos de lenguaje grande<br></div><div>
- Desafíos del entrenamiento a gran escala<br></div><div>
- Cómo OCI Superclusters agiliza este proceso<br></div><div>
- Resultados y métricas<br></div><div>
4. Caso de uso: Inferencia en tiempo real<br></div><div>
- Requisitos para la inferencia en producción<br></div><div>
- Optimizaciones para la latencia y el rendimiento<br></div><div>
- Implementación de servicios de IA<br></div><div>
5. Preguntas y respuestas<br></div><div><br></div><div>
¿Qué se va a aprender?&nbsp;
Superclusters + GPU + NVIDIA</div>



<iframe width="975" height="548" src="https://www.youtube.com/embed/YkrUpvWgdeE" title="OCI Supercluster: The Infrastructure Driving Generative AI at Scale" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Andrew

"Olivier Francois Xavier Perard" <olivier.perard@oracle.com>; 

"Angus Myles" <angus.myles@oracle.com>; 
"Enrique Diaz Galan" <enrique.diazgalan@oracle.com>; 
"Oscar Bernacer" <oscar.bernacer@oracle.com>; 
"Pascal GIRAUD" <pascal.giraud@oracle.com>; 
"Ervan Pouliquen" <ervan.pouliquen@oracle.com>; 
"Sara Larragueta Gonzalo" <sara.larragueta@oracle.com>; 
"Mark Newall" <mark.newall@oracle.com>; 
"Riccardo Ottolenghi" <riccardo.ottolenghi@oracle.com>; 
"Sergio Saez Fernandez" <sergio.saez@oracle.com>; 
"Begona Diaz Agudo" <begona.diaz@oracle.com>; 


"Javier Herrera" <javier.herrera@oracle.com>; 
"Ivan Rodriguez Diaz" <ivan.rodriguez.diaz@oracle.com>; 

"Filippos Boufis" <filippos.boufis@oracle.com>; 
"Faisal Hasan" <faisal.hasan@oracle.com>




In ExaCC, the policies on Database for previous version of 19c have changed from January 2024
If a customer has "Upgrade Support" (previously named "Market Driven Support" or MDS), the automatic processes of EXACC detect this support option and allow the deployment of previous DB ( pre-19c). 

You have the info in einstein: https://einstein.oracle.com/q/cloud-support-for-legacy-11-2-0-4-12-1-0-2-12-2-0-1-databas-2699

If you have this support option, you can deploy until 11.2.0.4 patch April 2021.If you want to deploy other patch for this version, download from MOS, and apply manually in EXACC; los automatismos seguirán funcionando




For Oracle Forms, the last version is 12.2.1.19.

To migrate to Forms 12c, I have done in 2 customers "Ahorramas" and RIU with lots of problems.

You can find the Support tickets here:
3-33937968461, related to Bug 34001741 - FORMS HANGS OR CRASHES WHEN LOV OR EDITOR FILL PATTERN SET TO "NONE"
3-33909272871, related to error 422 when you compile PL/SQLs in Oracle Forms and corrected in the patch 35687821


Yesterday, we have had a meeting with the Telefonica GCTIO and I wanted to inform you that our customer has expressed a keen interest in organizing a 3-day technical workshop. The primary focus of this workshop will be to explore, in detail, the integration of their core network with OCI DRCC. Additionally, they would like to deploy and test a network function, either from Nokia or Ericsson, on OCI.

The goal of this workshop is to demonstrate a complete end-to-end solution, showcasing the integration process of the network function with their core network. They are particularly interested in observing the seamless orchestration and deployment capabilities within OCI’s environment.

This presents a great opportunity for us to deepen our engagement with the customer and highlight OCI’s robust infrastructure for telecommunications.

Please let me know your thoughts or if any further details are needed.


pip install llama-stack

llama model list

llama model list --show-all

llama model download --source meta --model-id  MODEL_ID

https://llama3-2-lightweight.llamameta.net/*?Policy=eyJTdGF0ZW1lbnQiOlt7InVuaXF1ZV9oYXNoIjoieWFweWNxeGw0ZTE4MGhsMDl1Zzd4a2tyIiwiUmVzb3VyY2UiOiJodHRwczpcL1wvbGxhbWEzLTItbGlnaHR3ZWlnaHQubGxhbWFtZXRhLm5ldFwvKiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTcyNzYyNTYyNH19fV19&Signature=aVWNn1PKouc1EQvNsAbo1GLQ5BW%7EKlSBIhp0iQIQvg%7EsB0OYkhTbNaUgWuGhH4ZKvirbAbwrxuLa0rpj4dn%7ENyelYb1izstmFYnDCETIiQDnHoeVfgcB44y-h73kW%7EYed2om4BKrryu3w00bO%7EoAZRnocHewOYTvH4yMnhiBWWB1I2CLxMJUEsQ5IAa6aeAV1%7EbkUyt%7Eg%7EF1-OpK723aiccf%7ErPmxHmYJtkCFiwuRlCsuuZDJtucFDjDLxZDBIchSUho0l-rMTMELacUeyQbbgughWcXYIKwUc1%7E3E5ioHzlzBZXhVykD44T2oLZbkvlBQSd8vDxTThwvIa-0yvf5g__&Key-Pair-Id=K15QRJLYKIFSLZ&Download-Request-ID=1262419888082684


https://llama3-1.llamameta.net/*?Policy=eyJTdGF0ZW1lbnQiOlt7InVuaXF1ZV9oYXNoIjoicnl2MHF3Z2ZlNm83bDFwamd5b2lzY2k2IiwiUmVzb3VyY2UiOiJodHRwczpcL1wvbGxhbWEzLTEubGxhbWFtZXRhLm5ldFwvKiIsIkNvbmRpdGlvbiI6eyJEYXRlTGVzc1RoYW4iOnsiQVdTOkVwb2NoVGltZSI6MTcyNzYyNTYyNH19fV19&Signature=nWA%7El0XkSF6PdWPJ0VRmsqTZZxzPrWxXZI4t3hwy616RBm0HwSNvtwXcxgB-0-54AMf1FX-N3p2tUXumauCMcTWoMx00C7DnAGbLtHQGqMlyEWuW1aqKecxYFEaOFBOaubcF7HrAgPD5MGjXJEZTpjvwQUEayeA6tV6dcSbLq5QVHnxrzRw8nhq1YZTp17HJdLp9TmtRfBti8LFTYDa6DyYM45%7EMJ6erioPSaXhK8sIP7Y%7EgjElFJ2FeYErT5WnK8ClUFVc4ThAfqqRubH8bccvBTATlKmCdbaZJ8TYnPAH154NnVqVvBymFZSdpijty3nT42CPKA2W0cSumsH-QGA__&Key-Pair-Id=K15QRJLYKIFSLZ&Download-Request-ID=1606903917376685



curl 'https://dc.oracleinfinity.io/v3/wh3g12c3gg' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: text/plain;charset=UTF-8' \
  -H 'Origin: https://reg.rf.oracle.com' \
  -H 'Referer: https://reg.rf.oracle.com/' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: no-cors' \
  -H 'Sec-Fetch-Site: cross-site' \
  -H 'User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' \
  --data-raw '{"events":[{"wt.page_scroll_depth":100,"wt.dl":"71","dcsdat":1727457406828,"dcssip":"reg.rf.oracle.com","dcsuri":"/flow/oracle/ocw24/catalog/page/catalog","dcsref":"https://reg.rf.oracle.com/flow/oracle/ocw24/catalog/page/catalog/session/1719967755139001U0Au","wt.tz":2,"wt.bh":19,"wt.ul":"en-US","wt.cd":30,"wt.sr":"1512x982","wt.jo":"No","wt.ti":"Content Catalog - Sessions","wt.js":"Yes","wt.bs":"1482x752","wt.ssl":"1","wt.es":"reg.rf.oracle.com/flow/oracle/ocw24/catalog/page/catalog","wt.tv":"1.0.4","wt.ce":"1","wt.co_f":"dd0a9e3a-87b8-4d58-a8b5-4b1927e72284","ora.tag_id":"oracle","ora.tag_config":"production","ora.c_id":"dd0a9e3a-87b8-4d58-a8b5-4b1927e72284","ora.elq.vid":"20DE8F5219BB4975947E77A77790C93A","ora.eloqua_flag":"1","wt.cg_l1":"flow","wt.cg_l2":"oracle","wt.cg_l3":"ocw24","wt.cg_l4":"catalog","wt.cg_l5":"page","wt.cg_l6":"catalog"}]}' ;
curl 'https://dc.oracleinfinity.io/wh3g12c3gg/dcs.gif?wt.hm_scrolldepth=100&wt.hm_scrolldepthtype=regular&wt.dl=125&wt.hm_timespan=132246&dcsdat=1727457539068&dcssip=reg.rf.oracle.com&dcsuri=%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&dcsref=https%3A%2F%2Freg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog%2Fsession%2F1719967755139001U0Au&wt.tz=2&wt.bh=19&wt.ul=en-US&wt.cd=30&wt.sr=1512x982&wt.jo=No&wt.ti=Content%20Catalog%20-%20Sessions&wt.js=Yes&wt.bs=1482x752&wt.ssl=1&wt.es=reg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&wt.tv=1.0.4&wt.ce=1&wt.co_f=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.tag_id=oracle&ora.tag_config=production&ora.c_id=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.elq.vid=20DE8F5219BB4975947E77A77790C93A&ora.eloqua_flag=1&wt.cg_l1=flow&wt.cg_l2=oracle&wt.cg_l3=ocw24&wt.cg_l4=catalog&wt.cg_l5=page&wt.cg_l6=catalog' \
  -H 'Accept: image/avif,image/webp,image/apng,image/svg+xml,image/*,*/*;q=0.8' \
  -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'Connection: keep-alive' \
  -H 'Referer: https://reg.rf.oracle.com/' \
  -H 'Sec-Fetch-Dest: image' \
  -H 'Sec-Fetch-Mode: no-cors' \
  -H 'Sec-Fetch-Site: cross-site' \
  -H 'User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' ;
curl 'https://dc.oracleinfinity.io/wh3g12c3gg/dcs.gif?wt.hm_winx=210&wt.hm_winy=521&wt.hm_targetx=0&wt.hm_targety=0&wt.hm_scrolldx=0&wt.hm_scrolldy=1359.5&wt.hm_x=210&wt.hm_y=1880.5&wt.hm_width=356&wt.hm_height=1619&wt.hm_scaled_x=26&wt.hm_scaled_y=49&wt.hm_target_id=%23widget-page-session-details&wt.hm_targetw=356&wt.hm_targeth=1619&wt.hm_resolution=50&wt.hm_selectortype=default&wt.dl=125&wt.hm_timespan=133281&dcsdat=1727457540103&dcssip=reg.rf.oracle.com&dcsuri=%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&dcsref=https%3A%2F%2Freg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog%2Fsession%2F1719967755139001U0Au&wt.tz=2&wt.bh=19&wt.ul=en-US&wt.cd=30&wt.sr=1512x982&wt.jo=No&wt.ti=Content%20Catalog%20-%20Sessions&wt.js=Yes&wt.bs=1482x752&wt.ssl=1&wt.es=reg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&wt.tv=1.0.4&wt.ce=1&wt.co_f=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.tag_id=oracle&ora.tag_config=production&ora.c_id=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.elq.vid=20DE8F5219BB4975947E77A77790C93A&ora.eloqua_flag=1&wt.cg_l1=flow&wt.cg_l2=oracle&wt.cg_l3=ocw24&wt.cg_l4=catalog&wt.cg_l5=page&wt.cg_l6=catalog' \
  -H 'Accept: image/avif,image/webp,image/apng,image/svg+xml,image/*,*/*;q=0.8' \
  -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'Connection: keep-alive' \
  -H 'Referer: https://reg.rf.oracle.com/' \
  -H 'Sec-Fetch-Dest: image' \
  -H 'Sec-Fetch-Mode: no-cors' \
  -H 'Sec-Fetch-Site: cross-site' \
  -H 'User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' ;
curl 'https://px.ads.linkedin.com/wa/' \
  -H 'accept: *' \
  -H 'accept-language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'content-type: text/plain;charset=UTF-8' \
  -H 'cookie: bcookie="v=2&b54c3432-4a65-4f01-8bff-3abff325644b"; li_gc=MTsyMTsxNzIzODEwNTg4OzI7MDIxij+zpGNzJkZ/F8cks/mv92veOr4u6CrErtGkut/JwEM=; li_sugr=ecc98483-6779-4faa-b905-03f719b18511; _guid=439155f2-ae40-46a2-a1e6-b8db400f695b; ar_debug=1; AnalyticsSyncHistory=AQIjMESLdCobTAAAAZIsjALdrDNKCNkxZ0aNmUbCp8G03pH2wJP8zXgeEmSVo4KI-RjojAuxy0PzrIAiUh8iaw; lms_ads=AQEQwLZxOND2hQAAAZIsjASRBbkyYj5wAsJ3pLtOGBrAYiZ1B0cBxDIeTw2aMHiF6FQAfJqOe-pTeVqRE8HdxC7y9OvIlUHr; lms_analytics=AQEQwLZxOND2hQAAAZIsjASRBbkyYj5wAsJ3pLtOGBrAYiZ1B0cBxDIeTw2aMHiF6FQAfJqOe-pTeVqRE8HdxC7y9OvIlUHr; lang=v=2&lang=en-us; liap=true; UserMatchHistory=AQIDo889jDzT0gAAAZI0MfvqLIhxdUhut7N35qk5pOAP4xGDFDR1QMUc1lcoxQux6YIPMQx5ieEgxb5p2gkxki0x1u6anNBJML-CSwPteXj3WnzEgz9Xp7tJXIjwcnpllKM9UF9OLmub1K9aIJzGIIAQvdJEze_n8y3pY4qJM6JqqfN-9a4W8F7P6QUVG-FMejUFnhfO8VTg_CbvVvACf9Wen9hOsvvVBmrfCwlP0lJjD8haGaZcNNOEFCHZgj-c4xRCk6sBLpEdMsq7fIzmWbR8ShnSXaL-qqybV9f-e23fhSmmoheV-wJ6iaCKJ8rhLxgRLK82eTMV94yEaoBYz2V5Of3C4YMqpHT08yjUqrzXoft3fQ; li_mc=MTsyMTsxNzI3NDU3MDEyOzI7MDIxTJyHGtyrW4dw41Y8wrOAtJ1IJckDgymtWRa0Pln4CLw=; __cf_bm=91OQW5.B5FaZPJV8Uj89QKOrISPvTT6KLCvt2BmA3zY-1727457284-1.0.1.1-kVmUlfr.Zurb2eZX2fTYBr0e17GbwR4lh_5VCRccRb6vw3PLr7sCt6JCYpIhLiI4YOHzbZNSiMgRWP5SbqLkDQ; lidc="b=VB30:s=V:r=V:a=V:p=V:g=4626:u=2090:x=1:i=1727457498:t=1727537886:v=2:sig=AQFiM8qvrQwPMlBqjTNcMZgWMEd-dthl"' \
  -H 'origin: https://reg.rf.oracle.com' \
  -H 'priority: u=1, i' \
  -H 'referer: https://reg.rf.oracle.com/' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' \
  -H 'sec-fetch-dest: empty' \
  -H 'sec-fetch-mode: cors' \
  -H 'sec-fetch-site: cross-site' \
  -H 'user-agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  --data-raw '{"pids":[89045],"scriptVersion":172,"time":1727457543917,"domain":"reg.rf.oracle.com","url":"https://reg.rf.oracle.com/flow/oracle/ocw24/catalog/page/catalog/session/1719587813187001onK8","pageTitle":"Content Catalog - Sessions","websiteSignalRequestId":"d8c80590-7aa7-8f38-ab68-b9ea3f235246","isTranslated":false,"liFatId":"","liGiant":"","misc":{"psbState":-4},"isLinkedInApp":false,"hem":null,"signalType":"CLICK","href":"","domAttributes":{"elementSemanticType":null,"elementValue":null,"elementType":null,"tagName":"A","backgroundImageSrc":null,"imageSrc":null,"imageAlt":null,"innerText":"AI-led transformation - Rethink everything.pdf","elementTitle":null,"cursor":"pointer"},"innerElements":[{"elementSemanticType":"IMAGE","elementValue":null,"elementType":null,"tagName":"svg","backgroundImageSrc":null,"imageSrc":null,"imageAlt":null,"elementTitle":null,"cursor":"pointer"}],"elementCrumbsTree":[{"tagName":"div","nthChild":3,"id":"rf-content","classes":["rf-accessibility","rf-workflow","rfComp-canvas"]},{"tagName":"div","nthChild":0,"id":"special-div","classes":["special-div"]},{"tagName":"div","nthChild":0,"classes":["rf-workflow-body-content","rfwf-body-content"]},{"tagName":"div","nthChild":0,"classes":["page-builder-display-reset","rf-accessibility"]},{"tagName":"div","nthChild":1,"classes":["flex-box-section-full"]},{"tagName":"div","nthChild":0,"classes":["flex-box-section-full-interior"]},{"tagName":"div","nthChild":0,"classes":["flex-box-section"],"attributes":{"data-path":"children[1]"}},{"tagName":"div","nthChild":0,"classes":["flex-box-child","rf-grid-layout-100"],"attributes":{"data-path":"children[1].children[0]"}},{"tagName":"div","nthChild":0},{"tagName":"div","nthChild":0,"id":"rf-catalog","classes":["rf-widget"],"attributes":{"data-widgetid":"1712160686020003GgYw"}},{"tagName":"div","nthChild":0,"id":"widget-page-session-details","classes":["recommended","session-details-page"]},{"tagName":"div","nthChild":1,"classes":["session-details-container"]},{"tagName":"div","nthChild":0,"attributes":{"data-test":"component-container"}},{"tagName":"div","nthChild":1},{"tagName":"div","nthChild":0},{"tagName":"div","nthChild":11,"classes":["rf-attribute","sessionFiles-component"],"attributes":{"data-test":"sessionFiles-component"}},{"tagName":"div","nthChild":0,"classes":["download-file-link","session-files-component"]},{"tagName":"ul","nthChild":1},{"tagName":"li","nthChild":0},{"tagName":"a","nthChild":0}],"isFilteredByClient":false}' ;
curl 'https://dc.oracleinfinity.io/wh3g12c3gg/dcs.gif?wt.hm_winx=111&wt.hm_winy=465&wt.hm_targetx=20&wt.hm_targety=1540&wt.hm_scrolldx=0&wt.hm_scrolldy=1359.5&wt.hm_x=91&wt.hm_y=284.5&wt.hm_width=0&wt.hm_height=0&wt.hm_scaled_x=13&wt.hm_scaled_y=16&wt.hm_target_id=%23widget-page-session-details%20%3E%20DIV%3Anth-child(2)%20%3E%20DIV%3Anth-child(1)%20%3E%20DIV%3Anth-child(2)%20%3E%20DIV%3Anth-child(1)%20%3E%20DIV%3Anth-child(12)%20%3E%20DIV%3Anth-child(1)%20%3E%20UL%3Anth-child(2)%20%3E%20LI%3Anth-child(1)%20%3E%20A%3Anth-child(1)&wt.hm_targetw=0&wt.hm_targeth=0&wt.hm_resolution=50&wt.hm_selectortype=default&wt.dl=125&wt.hm_timespan=137097&dcsdat=1727457543919&dcssip=reg.rf.oracle.com&dcsuri=%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&dcsref=https%3A%2F%2Freg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog%2Fsession%2F1719967755139001U0Au&wt.tz=2&wt.bh=19&wt.ul=en-US&wt.cd=30&wt.sr=1512x982&wt.jo=No&wt.ti=Content%20Catalog%20-%20Sessions&wt.js=Yes&wt.bs=1482x752&wt.ssl=1&wt.es=reg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog&wt.tv=1.0.4&wt.ce=1&wt.co_f=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.tag_id=oracle&ora.tag_config=production&ora.c_id=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284&ora.elq.vid=20DE8F5219BB4975947E77A77790C93A&ora.eloqua_flag=1&wt.cg_l1=flow&wt.cg_l2=oracle&wt.cg_l3=ocw24&wt.cg_l4=catalog&wt.cg_l5=page&wt.cg_l6=catalog' \
  -H 'Accept: image/avif,image/webp,image/apng,image/svg+xml,image/*,*/*;q=0.8' \
  -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'Connection: keep-alive' \
  -H 'Referer: https://reg.rf.oracle.com/' \
  -H 'Sec-Fetch-Dest: image' \
  -H 'Sec-Fetch-Mode: no-cors' \
  -H 'Sec-Fetch-Site: cross-site' \
  -H 'User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' ;
curl 'https://events.rf.oracle.com/api/clickStore' \
  -H 'Accept: */*' \
  -H 'Accept-Language: en-US,en;q=0.9,es;q=0.8,fr;q=0.7' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/x-www-form-urlencoded; charset=UTF-8' \
  -H 'Cookie: s_fid=71CFB3AE96A408D5-2A6F91EC99199E7A; ORA_FPC=id=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284; _gcl_au=1.1.85941139.1724868999; ELOQUA=GUID=20DE8F5219BB4975947E77A77790C93A&FPCVISITED=1; atgRecVisitorId=11B3ZPWLZ7cWJnFGdPmgS_HW4z1Y25noMzN9rawT2pDBdbA4B28; FPC=id=0608165d-66b4-43cf-85fb-0e650ecdce6d; AMCVS_93263704532955710A490D44%40AdobeOrg=1; ora_session=set; s_cc=true; _ga=GA1.1.1450734823.1725829735; _ga_39ZQL0LH63=GS1.1.1725862691.2.1.1725863955.0.0.0; _abck=1A21FAA6033E34195562D019609952E9~0~YAAQH7U+F9+1M9qRAQAA5f4m8wzZ2kbvcBUPyQabENk+skso6MyYs3qU941pTv25+TM4NNhmqECCJLGERBCqGCIWsseNcBpmWS+ZRDB06+bguB5SBJaYNyflofLX3dYEfrjRUglOz7GVy3zJxiSaBr/pW0iR5rF365/0Qa+VtcaOLLm41TeEKobm8sHZSTKT0k8ywbki22rGgXqvN0I1Qgxu9aBWW4GKXcr+HOP1/wQvJMGVYhRK2FWTWVcsAj0xXSAcrdeG0jI2UmvyW36Ugl5p/FrGDs79mv9RRwlZgVaaXiAOgTC0O+pf7yHYzAj2bOvfU9IaKLJkJMfos3mwTrx1W9lFXaO1MzCpGFRdpwVbJCCSaKAVGD77ccbO1xrrNEPAcbiOtzCSWz8VeaaT4RZmfjAyhnEViPC8HhrZ7JzihtaHZYCmi7wnkPvMZuO0b1LuldQl2e0a~-1~-1~1726340878; s_eVar21=%3Aow%3Alp%3Acpo%3A%3A%3A%3ARC_DEVT230728P00017%3ALPD400301073; bm_lso=0EF8619CBA4600D108BD1E235F0E3038C1651920B8B3ADC21198B81A1A27B49B~YAAQH7U+F/p4SxSSAQAAj6kyLQH7LJsrn3UBLSWRd0tIu7v+U+D6703B15TnoIZkcPEseVGRbhmj9p153kZL0XfGHZrBytDCMw9PDdmYh0ODyd356/S3DNn+eIptRAF39bW/yKRtVuj4CSF7l1qZ8UPWEuZrBiR0VwG95WmPbuHh8EqT5pD5bKc9tNG3TBvDH1aysCDqjY8aYFaznfw3GBxmlnxshOHHWrs/CTRYXVTPv/MFu1q1lqYiQ/P89m6ZZnPAS2iXxnrSQcCvhGfXcy7VgRNQB+A1xNftx57jvIBubYmMI/HLGfOoX7DdUr3U8xz+L7JYvmleOSTI4Gu2rCN+MDaNwHitFt8EwhHY7A+h96I1A4wWRux/wzAep27/1uKV+J1CJyXoVixOq+Sy3QhFWlYIFAbSZBteqpiiCfDeQaV4aHYERMcfXN6gS31MRgD8mweiawFG/92eyA/GhFsOsnlKLZjZ59BeMsrWodizR8f/SnGiN+ayblaAwI7lpTQhqUKBXly4x8IDavV/XOAoj2Ns1TfqVc9hf68TfBtNHuBFOgAOj1XgK40r1kDMlyHKVZTkhKVjDP4FoATE^1727335148547; bm_s=YAAQH7U+F0PdRTGSAQAAJdrgMgKGqZ2rRDnHNMu2fkDOph0+wO4+W4SY6lH/Y+Gk3P53WYckjcGo25G1nlRAuaDaHy6g6kgHRCRXcoNljO/2YkSrfbxZo8hZI1BlRZpBPCgx8y/6w2YpDlOYgJHs+PVt6v40UtfZr1fQo2lMSfp6xdnaIrvTGuGcC07Idlrhaz5iTrb+KXotQLw5sZl4QKRLLy0gbM4BfSmxvFa/QMzGHo6gYqq3kzd/Ac6BLrlzD/AruRtW0N30dksQYKorzkFnTBArcL05WvB96DdrKErShmqL/ZuG1Gp3bslYVQ8uGx/QE0V+PDLPDbbvJXa26nLajPo=; notice_behavior=expressed,eu; notice_gdpr_prefs=0,1,2:cb8350a2759273dccf1e483791e6f8fd; notice_preferences=2:cb8350a2759273dccf1e483791e6f8fd; cmapi_gtm_bl=; cmapi_cookie_privacy=permit 1,2,3; ORA_PERS={"ids":["4055985002883040285","6324384103808243518"],"campaigns":{"5a574221-cb7b-47c3-ac7b-293f45578101":{"activeBlocks":["C1","C2"],"pointer":"E1"},"edfd9d7b-f6ac-41ee-9add-232597b14646":{"activeBlocks":["C1"],"pointer":"E1"},"a98691bd-a586-4470-9ec4-ef2474f8d3ba":{"activeBlocks":["C1","C2","C3"],"pointer":"E1"},"1f777a44-4a26-4fa4-870a-ee3a0f8c5cbd":{"activeBlocks":["c1","C2"],"pointer":"E1"},"25a1adfa-7dfe-400a-83fd-04f635862dda":{"activeBlocks":["C1","C2"],"pointer":"E1","event":"-4137955223049953571"},"1b06383a-0439-43cb-8088-1d004dfcb9b1":{"activeBlocks":["C2"],"pointer":"T2","event":"-4137955223049953571"},"7ab92038-41fc-4e05-a783-0826d466adb0":{"activeBlocks":["C1","C2"],"pointer":"E1"}},"hash":"TnD/cfQJVLi3mfZhcAm4aQdwi5rIJkEDeL3kpdBicsI="}; AMCV_93263704532955710A490D44%40AdobeOrg=1585540135%7CMCIDTS%7C19994%7CMCMID%7C22201730152700497652706826613346940968%7CMCAAMLH-1728056114%7C6%7CMCAAMB-1728056114%7CRKhpRz8krg2tLO6pguXWp5olkAcUniQYPHaMWWgdJ3xzPWQmdj0y%7CMCOPTOUT-1727458514s%7CNONE%7CMCAID%7CNONE%7CvVersion%7C4.4.0; ak_bmsc=2A9522FF2224E03CFE5A215CF48C2062~000000000000000000000000000000~YAAQG1UQYB4YEB6SAQAAUxpQNBlBgfaIhYh4IvkxokQU2oVVrR0u4N6b1DQP6uOciiGDwovHYhuy7d1ppDj5FXi/zzT3arGuiUH7V06LdSKkjoJrvyqQgyMZmmj1PAAHgrJeKlT8NQ69ceUYFF2+CRVsnRNK6tSk45+pMbxomyZ1gyWRvix1WzOecHRg2wphI+KC3ZkwoNO0xPzwzBy5WgHIrNqJG03cXHPEk7eXmDdQdYrL+dzcxovNAfGqK9J81riIpx6aZYjDKkQecwoy3/WJhaIsJYeTbyCPs4foppRdeD7MXOscRfTsgdah+ExDSf577/VlrmaYr0qhH2kzlV1bfR1kQkKYvOewEJshHgfS6frSkwGnECEcdBYnPtBZrXGO2vwRoafJ; s_ips=773; bm_sv=96544713A754550E83C3AC958F5D3A38~YAAQMLkUApraCjKSAQAAOuRQNBmXIIpe5E2V6nxjHz1saadDxlHjIoiBnlV3XyrI4HnrBHRLD4P2sH4axIi2RrY/eXg/5+U83hUkk5m1MZ8cPQXWgisyLDaP14mD71xFyFMm1Ae/+m1UV1kHlimtVDIabuLdziVa5T9eJbLKICAzJ66KHZOzZQJmXnu72+zCQJ4V2KgiP3zdZUYD0j8VnV50TSQyapqvF4gYpce+k8W2cPibWfGOBQ1jLy2cM8mx~1; s_tp=1041; s_ppv=mysites%253A%253A%252Fsearch%252F%2C74%2C74%2C74%2C773%2C1%2C1; TAsessionID=0911ed88-0bc4-4f64-9da8-da7ef354fd88|EXISTING; WTPERSIST=; RF.EVENTS.prd.SESSION=9ec7268d-7eed-4073-9d15-4282940a1389; 1586783053443001TvYm=1727457293192002ORWA; rfjwt=1c7d87c666ed48c1bb28c53b0e9b645f; rfjwt=1c7d87c666ed48c1bb28c53b0e9b645f; RT="z=1&dm=oracle.com&si=3380e2e9-ac85-4fd0-b694-aeb527216c3f&ss=m1klxe53&sl=0&tt=0&bcn=%2F%2F02179919.akstat.io%2F"; gpw_e24=https%3A%2F%2Freg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog; utag_main=v_id:01915a9291ca00142d6b7dceeb7805075002906d009dc$_sn:43$_se:18$_ss:0$_st:1727459293914$ses_id:1727457276769%3Bexp-session$_pn:4%3Bexp-session; s_tp=2024; s_ips=2024.5; s_ppv=https%253A%252F%252Freg.rf.oracle.com%252Fflow%252Foracle%252Focw24%252Fcatalog%252Fpage%252Fcatalog%252Fsession%252F1719587813187001onK8%2C100%2C100%2C100%2C2024.5%2C3%2C3; s_nr=1727457543922-Repeat; s_sq=oracleglobal%3D%2526c.%2526a.%2526activitymap.%2526page%253Dcloudworld%25253Aen-us%25253A%25252Fflow%25252Foracle%25252Focw24%25252Fcatalog%25252Fpage%25252Fcatalog%25252Fsession%25252F1719587813187001onk8%2526link%253DAI-led%252520transformation%252520-%252520Rethink%252520everything.pdf%2526region%253DBODY%2526pageIDType%253D1%2526.activitymap%2526.a%2526.c%2526pid%253Dcloudworld%25253Aen-us%25253A%25252Fflow%25252Foracle%25252Focw24%25252Fcatalog%25252Fpage%25252Fcatalog%25252Fsession%25252F1719587813187001onk8%2526pidt%253D1%2526oid%253DfunctionPr%252528%252529%25257B%25257D%2526oidt%253D2%2526ot%253DA%26oracleglobal-test%252Coraclecom-test%252Coracleinteractive-test%3D%2526c.%2526a.%2526activitymap.%2526page%253Dhttps%25253A%25252F%25252Fwww.oracle.com%25252Fai-infrastructure%25252F%2526link%253DNetworking%252520for%252520Supercluster%2526region%253DBODY%2526.activitymap%2526.a%2526.c' \
  -H 'Origin: https://reg.rf.oracle.com' \
  -H 'Referer: https://reg.rf.oracle.com/' \
  -H 'Sec-Fetch-Dest: empty' \
  -H 'Sec-Fetch-Mode: cors' \
  -H 'Sec-Fetch-Site: same-site' \
  -H 'User-Agent: Mozilla/5.0 (Linux; Android 6.0; Nexus 5 Build/MRA58N) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/129.0.0.0 Mobile Safari/537.36' \
  -H 'rfApiProfileId: k5qIfk5iZUYpPxKjzmX3F3RdivJ9F5ru' \
  -H 'rfAuthToken: 1c7d87c666ed48c1bb28c53b0e9b645f' \
  -H 'rfWidgetId: BNts4YIR7pc0gQNrWbKcxNYs4jHgTgoz' \
  -H 'sec-ch-ua: "Google Chrome";v="129", "Not=A?Brand";v="8", "Chromium";v="129"' \
  -H 'sec-ch-ua-mobile: ?1' \
  -H 'sec-ch-ua-platform: "Android"' \
  --data-raw 'clicks=%7B%22clicks%22%3A%5B%7B%22foreignType%22%3A%22sessionFile%22%2C%22foreignId%22%3A%221725032543322001ctpH%22%2C%22clickDate%22%3A%222024-09-27%2019%3A19%3A3%22%2C%22entityType%22%3A%22sessionDetails%22%2C%22entityId%22%3A%221719587813187001onK8%22%2C%22widgetApiToken%22%3A%22BNts4YIR7pc0gQNrWbKcxNYs4jHgTgoz%22%2C%22workflowId%22%3A%221706122668986079VScw%22%2C%22componentType%22%3A%22sessionV2%22%7D%5D%2C%22widgetApiTokens%22%3A%5B%22BNts4YIR7pc0gQNrWbKcxNYs4jHgTgoz%22%5D%2C%22workflowId%22%3A%221706122668986079VScw%22%2C%22unAuthClickIds%22%3A%5B%5D%2C%22rf%22%3Atrue%7D'



cat ocw_file_list | while read f1 f2
do
echo $f1 $f2
curl -o $f1 "$f2" \
  -H $'Cookie: s_fid=71CFB3AE96A408D5-2A6F91EC99199E7A; ORA_FPC=id=dd0a9e3a-87b8-4d58-a8b5-4b1927e72284; _gcl_au=1.1.85941139.1724868999; ELOQUA=GUID=20DE8F5219BB4975947E77A77790C93A&FPCVISITED=1; atgRecVisitorId=11B3ZPWLZ7cWJnFGdPmgS_HW4z1Y25noMzN9rawT2pDBdbA4B28; FPC=id=0608165d-66b4-43cf-85fb-0e650ecdce6d; AMCVS_93263704532955710A490D44%40AdobeOrg=1; ora_session=set; s_cc=true; _ga=GA1.1.1450734823.1725829735; _ga_39ZQL0LH63=GS1.1.1725862691.2.1.1725863955.0.0.0; _abck=1A21FAA6033E34195562D019609952E9~0~YAAQH7U+F9+1M9qRAQAA5f4m8wzZ2kbvcBUPyQabENk+skso6MyYs3qU941pTv25+TM4NNhmqECCJLGERBCqGCIWsseNcBpmWS+ZRDB06+bguB5SBJaYNyflofLX3dYEfrjRUglOz7GVy3zJxiSaBr/pW0iR5rF365/0Qa+VtcaOLLm41TeEKobm8sHZSTKT0k8ywbki22rGgXqvN0I1Qgxu9aBWW4GKXcr+HOP1/wQvJMGVYhRK2FWTWVcsAj0xXSAcrdeG0jI2UmvyW36Ugl5p/FrGDs79mv9RRwlZgVaaXiAOgTC0O+pf7yHYzAj2bOvfU9IaKLJkJMfos3mwTrx1W9lFXaO1MzCpGFRdpwVbJCCSaKAVGD77ccbO1xrrNEPAcbiOtzCSWz8VeaaT4RZmfjAyhnEViPC8HhrZ7JzihtaHZYCmi7wnkPvMZuO0b1LuldQl2e0a~-1~-1~1726340878; s_eVar21=%3Aow%3Alp%3Acpo%3A%3A%3A%3ARC_DEVT230728P00017%3ALPD400301073; bm_lso=0EF8619CBA4600D108BD1E235F0E3038C1651920B8B3ADC21198B81A1A27B49B~YAAQH7U+F/p4SxSSAQAAj6kyLQH7LJsrn3UBLSWRd0tIu7v+U+D6703B15TnoIZkcPEseVGRbhmj9p153kZL0XfGHZrBytDCMw9PDdmYh0ODyd356/S3DNn+eIptRAF39bW/yKRtVuj4CSF7l1qZ8UPWEuZrBiR0VwG95WmPbuHh8EqT5pD5bKc9tNG3TBvDH1aysCDqjY8aYFaznfw3GBxmlnxshOHHWrs/CTRYXVTPv/MFu1q1lqYiQ/P89m6ZZnPAS2iXxnrSQcCvhGfXcy7VgRNQB+A1xNftx57jvIBubYmMI/HLGfOoX7DdUr3U8xz+L7JYvmleOSTI4Gu2rCN+MDaNwHitFt8EwhHY7A+h96I1A4wWRux/wzAep27/1uKV+J1CJyXoVixOq+Sy3QhFWlYIFAbSZBteqpiiCfDeQaV4aHYERMcfXN6gS31MRgD8mweiawFG/92eyA/GhFsOsnlKLZjZ59BeMsrWodizR8f/SnGiN+ayblaAwI7lpTQhqUKBXly4x8IDavV/XOAoj2Ns1TfqVc9hf68TfBtNHuBFOgAOj1XgK40r1kDMlyHKVZTkhKVjDP4FoATE^1727335148547; bm_s=YAAQH7U+F0PdRTGSAQAAJdrgMgKGqZ2rRDnHNMu2fkDOph0+wO4+W4SY6lH/Y+Gk3P53WYckjcGo25G1nlRAuaDaHy6g6kgHRCRXcoNljO/2YkSrfbxZo8hZI1BlRZpBPCgx8y/6w2YpDlOYgJHs+PVt6v40UtfZr1fQo2lMSfp6xdnaIrvTGuGcC07Idlrhaz5iTrb+KXotQLw5sZl4QKRLLy0gbM4BfSmxvFa/QMzGHo6gYqq3kzd/Ac6BLrlzD/AruRtW0N30dksQYKorzkFnTBArcL05WvB96DdrKErShmqL/ZuG1Gp3bslYVQ8uGx/QE0V+PDLPDbbvJXa26nLajPo=; notice_behavior=expressed,eu; notice_gdpr_prefs=0,1,2:cb8350a2759273dccf1e483791e6f8fd; notice_preferences=2:cb8350a2759273dccf1e483791e6f8fd; cmapi_gtm_bl=; cmapi_cookie_privacy=permit 1,2,3; ORA_PERS={"ids":["4055985002883040285","6324384103808243518"],"campaigns":{"5a574221-cb7b-47c3-ac7b-293f45578101":{"activeBlocks":["C1","C2"],"pointer":"E1"},"edfd9d7b-f6ac-41ee-9add-232597b14646":{"activeBlocks":["C1"],"pointer":"E1"},"a98691bd-a586-4470-9ec4-ef2474f8d3ba":{"activeBlocks":["C1","C2","C3"],"pointer":"E1"},"1f777a44-4a26-4fa4-870a-ee3a0f8c5cbd":{"activeBlocks":["c1","C2"],"pointer":"E1"},"25a1adfa-7dfe-400a-83fd-04f635862dda":{"activeBlocks":["C1","C2"],"pointer":"E1","event":"-4137955223049953571"},"1b06383a-0439-43cb-8088-1d004dfcb9b1":{"activeBlocks":["C2"],"pointer":"T2","event":"-4137955223049953571"},"7ab92038-41fc-4e05-a783-0826d466adb0":{"activeBlocks":["C1","C2"],"pointer":"E1"}},"hash":"TnD/cfQJVLi3mfZhcAm4aQdwi5rIJkEDeL3kpdBicsI="}; AMCV_93263704532955710A490D44%40AdobeOrg=1585540135%7CMCIDTS%7C19994%7CMCMID%7C22201730152700497652706826613346940968%7CMCAAMLH-1728056114%7C6%7CMCAAMB-1728056114%7CRKhpRz8krg2tLO6pguXWp5olkAcUniQYPHaMWWgdJ3xzPWQmdj0y%7CMCOPTOUT-1727458514s%7CNONE%7CMCAID%7CNONE%7CvVersion%7C4.4.0; ak_bmsc=2A9522FF2224E03CFE5A215CF48C2062~000000000000000000000000000000~YAAQG1UQYB4YEB6SAQAAUxpQNBlBgfaIhYh4IvkxokQU2oVVrR0u4N6b1DQP6uOciiGDwovHYhuy7d1ppDj5FXi/zzT3arGuiUH7V06LdSKkjoJrvyqQgyMZmmj1PAAHgrJeKlT8NQ69ceUYFF2+CRVsnRNK6tSk45+pMbxomyZ1gyWRvix1WzOecHRg2wphI+KC3ZkwoNO0xPzwzBy5WgHIrNqJG03cXHPEk7eXmDdQdYrL+dzcxovNAfGqK9J81riIpx6aZYjDKkQecwoy3/WJhaIsJYeTbyCPs4foppRdeD7MXOscRfTsgdah+ExDSf577/VlrmaYr0qhH2kzlV1bfR1kQkKYvOewEJshHgfS6frSkwGnECEcdBYnPtBZrXGO2vwRoafJ; s_ips=773; bm_sv=96544713A754550E83C3AC958F5D3A38~YAAQMLkUApraCjKSAQAAOuRQNBmXIIpe5E2V6nxjHz1saadDxlHjIoiBnlV3XyrI4HnrBHRLD4P2sH4axIi2RrY/eXg/5+U83hUkk5m1MZ8cPQXWgisyLDaP14mD71xFyFMm1Ae/+m1UV1kHlimtVDIabuLdziVa5T9eJbLKICAzJ66KHZOzZQJmXnu72+zCQJ4V2KgiP3zdZUYD0j8VnV50TSQyapqvF4gYpce+k8W2cPibWfGOBQ1jLy2cM8mx~1; s_tp=1041; s_ppv=mysites%253A%253A%252Fsearch%252F%2C74%2C74%2C74%2C773%2C1%2C1; TAsessionID=0911ed88-0bc4-4f64-9da8-da7ef354fd88|EXISTING; WTPERSIST=; RF.EVENTS.prd.SESSION=9ec7268d-7eed-4073-9d15-4282940a1389; 1586783053443001TvYm=1727457293192002ORWA; rfjwt=1c7d87c666ed48c1bb28c53b0e9b645f; rfjwt=1c7d87c666ed48c1bb28c53b0e9b645f; RT="z=1&dm=oracle.com&si=3380e2e9-ac85-4fd0-b694-aeb527216c3f&ss=m1klxe53&sl=0&tt=0&bcn=%2F%2F02179919.akstat.io%2F"; gpw_e24=https%3A%2F%2Freg.rf.oracle.com%2Fflow%2Foracle%2Focw24%2Fcatalog%2Fpage%2Fcatalog; utag_main=v_id:01915a9291ca00142d6b7dceeb7805075002906d009dc$_sn:43$_se:18$_ss:0$_st:1727459293914$ses_id:1727457276769%3Bexp-session$_pn:4%3Bexp-session; s_tp=2024; s_ips=2024.5; s_ppv=https%253A%252F%252Freg.rf.oracle.com%252Fflow%252Foracle%252Focw24%252Fcatalog%252Fpage%252Fcatalog%252Fsession%252F1719587813187001onK8%2C100%2C100%2C100%2C2024.5%2C3%2C3; s_nr=1727457543922-Repeat; s_sq=oracleglobal%3D%2526c.%2526a.%2526activitymap.%2526page%253Dcloudworld%25253Aen-us%25253A%25252Fflow%25252Foracle%25252Focw24%25252Fcatalog%25252Fpage%25252Fcatalog%25252Fsession%25252F1719587813187001onk8%2526link%253DAI-led%252520transformation%252520-%252520Rethink%252520everything.pdf%2526region%253DBODY%2526pageIDType%253D1%2526.activitymap%2526.a%2526.c%2526pid%253Dcloudworld%25253Aen-us%25253A%25252Fflow%25252Foracle%25252Focw24%25252Fcatalog%25252Fpage%25252Fcatalog%25252Fsession%25252F1719587813187001onk8%2526pidt%253D1%2526oid%253DfunctionPr%252528%252529%25257B%25257D%2526oidt%253D2%2526ot%253DA%26oracleglobal-test%252Coraclecom-test%252Coracleinteractive-test%3D%2526c.%2526a.%2526activitymap.%2526page%253Dhttps%25253A%25252F%25252Fwww.oracle.com%25252Fai-infrastructure%25252F%2526link%253DNetworking%252520for%252520Supercluster%2526region%253DBODY%2526.activitymap%2526.a%2526.c' 
done




Genérame un documento de Resoluciones con las Secciones siguientes: Documentos Remitidos, Análisis de Tratamiento con Tramite, Valoración y Evaluación, Recomendaciones y Conclusiones


Genérame un documento de Resoluciones con las Secciones siguientes: Documentos Remitidos, Análisis de Tratamiento con sub-secciones (Tramite, Valoración y Evaluación), Recomendaciones y Conclusiones


Genérame un documento de Resoluciones con un informe las Secciones siguientes: Documentos Remitidos, Análisis de Tratamiento con sub-secciones (Tramite, Valoración y Evaluación), Recomendaciones y Conclusiones





Genérame un documento de Resoluciones con un informe favorable o no, despues de consultar los registros, inventarios, carta arqueológica y Catalógos de bienes culturales de la junta de Extremadura con las Secciones siguientes: nombre del document original, nombre del promotor, resultado favorable o no y referencia a los articulos 30 y 49 de la ley 2/1999.



podman run -d --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1522/FREEPDB1" -e dbtablename=AIRAGINBOX docker.io/operard/airagdb23aiinbox:1.0.0-arm64

podman run -d --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1522/FREEPDB1" -e dbtablename=AIRAGINBOX localhost/airagdb23aiinbox:1.0.0.0.0

podman run -d --name llama3gen --network airag --ip 10.22.1.13  -p 8501:8501 docker.io/operard/llama3generator:1.0.0.0.0


export dbuser=VECDEMO
export dbpassword=Oracle4U
export dbservice="10.22.1.12:1522/FREEPDB1"
export dbtablename=AIRAGINBOX

export




podman run -it --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1522/FREEPDB1" -e dbtablename=AIRAGINBOX --entrypoint /bin/bash localhost/airagdb23aiinbox:1.0.0.0.0



podman run -d  -p 8889:8888 -v /Users/operard/jupyter-data:/home/jovyan/work --network mynetwork --ip 10.22.1.75 docker.io/fcoalvrz/jupyter-onnx:latest start-notebook.py --NotebookApp.token='oracle12345'


podman run -d --name jupyter-onnx -p 8889:8888 -v /Users/operard/Desktop/dev/data:/home/jovyan/work  --network airag --ip 10.22.1.75 docker.io/fcoalvrz/jupyter-onnx:latest start-notebook.py --NotebookApp.token='oracle12345'




podman run -d --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501 -p 11434:11434  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1521/FREEPDB1" -e dbtablename=AIRAGINBOX -v /Users/operard/Documents/customers/administracion/junta_extremadura/data:/data localhost/operard/airagdb23aiinbox:1.0.0-arm64


export username=VECDEMO
export password=Oracle4U
export service="10.22.1.12:1521/FREEPDB1"


podman run -it --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1521/FREEPDB1" -e dbtablename=AIRAGINBOX --entrypoint /bin/bash -v /Users/operard/Documents/customers/administracion/junta_extremadura/data:/data localhost/operard/airagdb23aiinbox:1.0.0-arm64


An error occurred: 'st.session_state has no key "$$WIDGET_ID-60fb03dbad6d48b1736a8c995a6feef0-None". Did you forget to initialize it? More info: https://docs.streamlit.io/develop/concepts/architecture/session-state#initialization'


podman run -d --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501 -p 11434:11434  -e username=VECDEMO -e password=Oracle4U -e service="10.22.1.12:1521/FREEPDB1" -e dbtablename=AIRAGINBOX -e tablename=AIRAGINBOX  docker.io/operard/airagdb23aiinbox:1.0.0-arm64


podman run -it --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1521/FREEPDB1" -e dbtablename=AIRAGINBOX  docker.io/operard/airagdb23aiinbox:1.0.0-arm64

podman run -d --name airagdb23aiinbox --network airag --ip 10.22.1.11  -p 8501:8501  -e dbuser=VECDEMO -e dbpassword=Oracle4U -e dbservice="10.22.1.12:1521/FREEPDB1" -e dbtablename=AIRAGINBOX  docker.io/operard/airagdb23aiinbox:1.0.0-arm64


extract_text()


http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5147/7b9d8397672a8fcb92d48b5a10a2df43

http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5147/7b9d8397672a8fcb92d48b5a10a2df43
http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5332/ab70c83b4d54f550b5d78d6976395983




operard@MacBook-Pro extract_pdf % python3 extractpdfurl.py "/Users/operard/Downloads/18_Com_Cult_24_110_130_CC_F_.pdf"
['http://www.juntaex.es', 'http://sitex.gobex.es/SITEX/calificacionexpedients/mostrardatossectoriales/2794/fd75adaf', 'http://sitex.gobex.es/SITEX/calificacionexpedients/mostrardatossectoriales/2815/ad4af10d', 'https://sede.gobex.es/SEDE/csv/codSeguroVerificacion.jsf']
--> Execute webscrapping in :http://sitex.gobex.es/SITEX/calificacionexpedients/mostrardatossectoriales/2794/fd75adaf
--> Download next file : http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5147/7b9d8397672a8fcb92d48b5a10a2df43
content-type: application/octet-stream
content-disposition: attachment; filename="Serradilla_Const_edificio_uso_almacen_JesusMGines.zip.zip";
ffname: "Serradilla_Const_edificio_uso_almacen_JesusMGines.zip.zip";
Downloaded: http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5147/7b9d8397672a8fcb92d48b5a10a2df43
--> Download next file : http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5332/ab70c83b4d54f550b5d78d6976395983
content-type: application/octet-stream
content-disposition: attachment; filename="Inf_Serv_ProtecciÃ³n_24_110_CC.zip.zip";
ffname: "Inf_Serv_Protección_24_110_CC.zip.zip";
Downloaded: http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5332/ab70c83b4d54f550b5d78d6976395983
--> Execute webscrapping in :http://sitex.gobex.es/SITEX/calificacionexpedients/mostrardatossectoriales/2815/ad4af10d
--> Download next file : http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5219/b95d816c1b91d52544b4c24b9aef7f63
content-type: application/octet-stream
content-disposition: attachment; filename="Aldea_Cano_observatorio_astronomico_autocaravanas_Ecozona.7z.7z";
ffname: "Aldea_Cano_observatorio_astronomico_autocaravanas_Ecozona.7z.7z";
Downloaded: http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5219/b95d816c1b91d52544b4c24b9aef7f63
--> Download next file : http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5322/6e5ece605bbe997fabc0711ba0ea5a9d
content-type: application/octet-stream
content-disposition: attachment; filename="Doc_24_130_CC_Aldea_Cano.zip.zip";
ffname: "Doc_24_130_CC_Aldea_Cano.zip.zip";
Downloaded: http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5322/6e5ece605bbe997fabc0711ba0ea5a9d
--> Download next file : http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5368/a9dbf5a9a0aeb488c4cdb89aa81c8705
content-type: application/octet-stream
content-disposition: attachment; filename="Doc_expte._2024-130-CC.zip.zip";
ffname: "Doc_expte._2024-130-CC.zip.zip";
Downloaded: http://sitex.gobex.es/SITEX/calificacionexpedients/downloadFicheroExpediente/5368/a9dbf5a9a0aeb488c4cdb89aa81c8705
operard@MacBook-Pro extract_pdf % 


pip install pyunpack 
pip install patool
pip install zipfile


