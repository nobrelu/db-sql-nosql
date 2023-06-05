# DataStax Academy

https://www.datastax.com/dev/academy

## DS101: Introduction to Apache Cassandra™

https://academy.datastax.com/#/dashboard


### Introdução: Relational Overview

Problemas quando se tenta escalar bancos de dados relacionais
Como o Cassandra funciona internamente e suas diferentes distribuições

Small data
Medium data - ACID - Relational RDBMS - Scales Vertically - "PostgreSQL/MySQL"

RDBMS and Big Data - ACID Replication - replication lag
Data deve estar desnormalizada
Sharding - Shards - data is all over the place - desnormalize

Scaling is pain
ACID - no consistent
re-sharding is a manual process
desnormalize for perfomance
high availabitity is complicated

**Lessons Learned** 

Consistency is not pratical
Manual sharding and rebalancing is hard
Every moving part makes systems more complex 
scaling up is expensive - to more machines
scatter / gather no good



### Introdução: Cassandra Overview

Apache Cassandra is fast distributed database built for high  availability and linear scalability
able to get predictable performance
NO SPOF
Multi-DC
Commodity Hardware
Easy to manage operationally
Not a drop in replacement for RDBMS

low latency - clusters scales up
peer to peer technology - no failover

HASH RINGS - data model in cassandra - ver slide
primary key -> partition key -> use to insert data in cassandra - consistent hashing function


CAP Tradeoffs

Teoria de CAP - impossivel ter consistent and highly available
latency makes consistency inpractiocal
cassandra chooses availability ante partition tolerance over consistency


Replication

Data is replicated automatically
you pick number of servers
replication factor RF
sempre replicada
se maquina cair, dados perdidos sao repostos por hinted handoff  (transferência sugerida)


cassandra é uma coleção de tabelas similar a um schema e oracle db mysql
replications is a synchronously


Consistency Levels

Per query consistency
ALL 
QUORUM 
ONE
how maney replicas for query to respond OK 


quando usar:
QUORUM  - mais devagar para ler e gravar - higher consistency
ONE - rapido para ler e gravar dados - low consistency - more availability  


MULTI DC

typical usage: clientes write to local DC, replicates async to others DCs
Replications factor per keyspace per datacenter  - super  higher availability  
datacenters can be physical or logical 

OLTP - fast read to applications 
one data server to serving OLAP


### Introdução: Cassandra Internals and Choosing a Distribution


Como o Cassandro le e escreve

The Write Path

Quando você envia uma escrita para o cluster Cassandra - qualquer node
coordinator node
duas coisas acontecem:
commit log é um aprendice para o memtable (memoria representation) - only data structure
ai ele responde para o coordinator "nos gravamos seu dado"

cassandra é mto rápido para gravar dados

every write includes a timestamp

memtable flushed (grava) to disk periodically - sstable

nova memtable é criada em memória

deletes are a special write case, called a "tombstone"


Cassandra doesn't do any updates in place or deletes.
you never get this delete in place

Cassandra não faz nenhuma atualização ou exclusão.
você nunca consegue essa exclusão no lugar


sstable são imutáveis
logs is immutable

O que cassandra realmente faz?
when you delete data is it writes a special kind of record called a tombstone

que uma marca que basicamente diz "não tem mais dado aqui"



SSTable


O que acontece quando temos muitas SSTables gravando no disco?

SSTable são imutaveis arquivos no disco

Quando escrevem na SStable no disco, haverá um processo de compactação, small access tables
Cada escrita contem um timestamp de quando foi escrito
partition is spread across multiple sstables
same column can be multiple sstables
merged through compaction, olny lastest timestamp is kept
deletes are wrtitten as tombstones
easy backups



READS

Leituras no Cassandra são muito similares com as gravações.
Vai ter um coordinator para aquele request (request key)
ele deverá ter que procurar em multiplas sstables
os dados sao recolhidos das multiplas sstables e mergeados utilizando memoria de acordo com o timestamp

depende do disco que vc escolhe, ssd/hd tem grande impactado na leitura / perfomance
a compactação tbm impacta

para consistencia, cassandra faz algo em background
read_repáir_chance -  garantir q esta lendo o mais atualizado possivel
sync information















