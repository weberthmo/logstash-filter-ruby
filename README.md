<h1 align="center">Tratamento de dados usando Logstash com filter Ruby
</h1>

## 🧐 Sobre <a name = "sobre"></a>

Padronização e anonimização de dados para disponibilização de API. 

## 🏁 Iniciando <a name = "getting_started"></a>

Essas instruções fornecerão a você uma cópia do projeto para execução em sua máquina local para fins de desenvolvimento e teste.

## Pré-requisitos

- Ter um computador 😅
- [Docker](https://www.docker.com/) - Virtualização de aplicações no conceito de “containers”.
- Host com logstash instalado. [Como instalar Logstash](https://www.elastic.co/guide/en/logstash/current/installing-logstash.html) - Muito simples não será abordado aqui.

## Instalação

- Realize o clone desse repossitório
  
```
git clone https://github.com/weberthmo/logstash-filter-ruby.git
```

- Na raiz do projeto execute o seguinte comando para criação dos containers Elastic e Kibana:

```
docker-compose up -d
```
- Acesse o kibana através da url:

```
http://localhost:5601/app/dev_tools#/console
```

- Ainda no Kibana, crie o Index de origem:

```
PUT origem
```
- Ainda no Kibana, adicione os seguintes documentos ao índice "origem" usando o arquivo "documentos_exemplo.json".
  
- Copie o arquivo "api.conf" para seu host Logstash. Esse é nosso arquivo de pipeline.


- Execute o seguinte comando no terminal do Host Logstash para processamento da pipeline de criação do índice "destino":

```
/usr/share/logstash/bin/logstash -f ./api.conf
```

- Acesse novamente o Kibana e visualize o índice "destino" criado na etapa anterior executando o seguinte comando:

```
GET destino/_search
```

- Para visualizar o índice "origem":

```
GET origem/_search
```




## ⛏️ Construindo usando <a name = "built_using"></a>

- [Elasticsearch](https://www.elastic.co/guide/en/elasticsearch/reference/current/install-elasticsearch.html) - Base de dados.
- [Logstash](https://www.elastic.co/guide/en/logstash/current/installing-logstash.html) - Ingestão de dados.
- [Kibana](https://www.elastic.co/guide/en/kibana/current/install.html) - Interface de usuário para visualização de dados Elasticsearch.
- [Docker](https://www.docker.com/) - Virtualizar de aplicações no conceito de “containers”.

## ✍️ Autor <a name = "autor"></a>

- [@weberthmo](https://github.com/weberthmo) 🚀