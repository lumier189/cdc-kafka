# Change Data Capture (CDC) com Kafka

Este repositório contém um projeto de exemplo pronto para ser executado, permitindo que você teste o uso de **Change Data Capture (CDC)** com Kafka.

Se você está iniciando no Kafka, recomendo assistir ao vídeo abaixo para entender os conceitos básicos:

🎥 [Introdução ao Kafka com FullCycle](https://www.youtube.com/watch?v=o5yviW6QSrE&list=PL5aY_NrL1rjt_AZxj11kQjiTNLGg4ZaZA&ab_channel=FullCycle)

---

## Pré-requisitos

- Docker instalado

---

## Como executar o projeto

### 1. Subir os serviços com Docker

Dentro de cada pasta, você verá um arquivo `docker-compose`:

- **kafka-server**
- **kafka-connect**

Primeiro, suba o serviço **kafka-server**, e, logo após, o **kafka-connect**.

### 2. Configurar o Conector MySQL

Certifique-se de ter o arquivo `mysql-connector.json` configurado com as informações necessárias para conectar ao seu banco de dados. Em seguida, registre o conector com o comando abaixo:

```bash
curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" \
http://localhost:8083/connectors/ -d @mysql-connector.json
```

### 3. Interfaces disponíveis

- **Kafka UI**: Interface para gerenciar e visualizar os dados no Kafka.  
  **URL**: [http://localhost:8080](http://localhost:8080)  
  **Credenciais**: admin / admin

![image](https://github.com/lumier189/cdc-kafka/assets/108551838/d63d96e2-c55c-4224-9f45-770121e103d1)

- **Connector UI**: Interface para gerenciar os conectores.  
  **URL**: [http://localhost:8080](http://localhost:8080)  
  **Credenciais**: admin / admin

![image](https://github.com/lumier189/cdc-kafka/assets/108551838/7cc314b1-be6c-48d9-bf37-ebd390c33a23)
---

## Configuração do Conector MySQL

Detalhes dos campos necessários para o conector podem ser encontrados na documentação oficial do **Debezium MySQL Connector**.

Caso utilize uma base de dados existente, é necessário configurar as permissões e variáveis no MySQL para que o conector tenha acesso para leitura e transferência dos dados.

### Permissões necessárias no MySQL

Execute os seguintes comandos para conceder as permissões:

```sql
GRANT SELECT, RELOAD, SHOW DATABASES, REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'user' IDENTIFIED BY 'password';
SHOW GRANTS FOR 'user'@'%';
```
**Disclaimer**: O comando pode variar de acordo com a versão do MySQL utilizada.
