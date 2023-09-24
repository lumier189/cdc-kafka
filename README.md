# cdc-kafka

Change Data Capture com kafka

Se é seu primeiro contato com o kafka recomendo dar uma conferida na introdução ao kafka com full-cycle

https://www.youtube.com/watch?v=o5yviW6QSrE&list=PL5aY_NrL1rjt_AZxj11kQjiTNLGg4ZaZA&ab_channel=FullCycle

Sobre o repositório, tem um projeto teste pronto pra rodar e testar o cdc com kakfa

docker kakfa -
docker connect -

curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" http://localhost:8083/connectors/ -d @mysql-connector.json 

acesse  http://localhost:8080
user/pw: admin


Detalhes campos conector: https://debezium.io/documentation/reference/stable/connectors/mysql.html 


kafka ui - http://localhost:8080/ admin admin
![image](https://github.com/lumier189/cdc-kafka/assets/108551838/d63d96e2-c55c-4224-9f45-770121e103d1)

connector ui - http://localhost:8080
![image](https://github.com/lumier189/cdc-kafka/assets/108551838/7cc314b1-be6c-48d9-bf37-ebd390c33a23)

connector rest API infos:
https://docs.confluent.io/platform/current/connect/references/restapi.html





caso queira usar uma database Já existente, ficar atendo as configurações necessárias para o connector poder ler e transferir os dados da database

IMPORTANTE: Os comandos podem ser diferentes dependendo da versão do bd

GRANT SELECT, RELOAD, SHOW DATABASES, REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'user' IDENTIFIED BY 'password';
SHOW GRANTS FOR 'contemplato'@'%'; 
show global variables like '%GTID%';
set @@global.binlog_row_value_options="" ; 
show global variables where variable_name = 'binlog_row_value_options'; 
