cd ~/eipi10/docker-study/tensorflow/cpu
docker build -t 127.0.0.1:9900/tensorflow:latest-py3 .
docker push 127.0.0.1:9900/tensorflow:latest-py3

cd ~/eipi10/docker-study/tensorflow/gpu
docker build -t 127.0.0.1:9900/tensorflow:latest-gpu-py3 .
docker push 127.0.0.1:9900/tensorflow:latest-gpu-py3

docker stack deploy -c docker-compose.yml tensorflow
docker exec -it tensorflow_cpu.1.$(docker service ps tensorflow_cpu -q -f "desired-state=running") bash

nvidia-docker run -it  --name ts-gpu-py3 --rm -v /home/grid/eipi10:/notebooks/eipi10 -p 18888:8888  127.0.0.1:9900/tensorflow:latest-gpu-py3  /run_jupyter.sh --allow-root --NotebookApp.token='xxw'
docker exec -it ts-gpu-py3 bash

jupyter notebook list
