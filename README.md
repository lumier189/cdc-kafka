# cdc-kafka

Change Data Capture com kafka

Se é seu primeiro contato com o kafka recomendo dar uma conferida na introdução ao kafka com full-cycle

https://www.youtube.com/watch?v=o5yviW6QSrE&list=PL5aY_NrL1rjt_AZxj11kQjiTNLGg4ZaZA&ab_channel=FullCycle

Sobre o repositório, tem um projeto teste pronto pra rodar e testar o cdc com kakfa

GRANT SELECT, RELOAD, SHOW DATABASES, REPLICATION SLAVE, REPLICATION CLIENT ON *.* TO 'user' IDENTIFIED BY 'password';
SHOW GRANTS FOR 'contemplato'@'%'; 
show global variables like '%GTID%';
set @@global.binlog_row_value_options="" ; 
show global variables where variable_name = 'binlog_row_value_options'; 
