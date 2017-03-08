#### ELK - Log centralizado


##### Objetivo

Manter log de forma centralizada



##### Dependências

docker 1.13


##### Como utilizar

* git clone https://github.com/robertvilvert/elk.git
* cd elk
* docker stack deploy  --compose-file docker-compose.yml stk_elk




##### Configurando o cliente

Você pode usar fileBeat ou enviar seus logs diretamente do docker.


Exemplo com filebeat para Nginx

```

filebeat.prospectors:
- input_type: log
  paths:
    - /var/log/nginx/*.log
  document_type: nginx-access


fields:
  env: production
  name: server-name
  realip: ip-do-servidor

output.logstash:
  hosts: ["ip-do-logstash:5044"]



```


##### OBS
As confs estão preparadas para Parser de Nginx e Jboss. Mas você pode alterar de acordo com sua necessidade.
