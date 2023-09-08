# Glossário

Uma tabela de Termos e Ferramentas utilizados pela Plataforma de Dados

## Ambientes

A plataforma possui 3 ambientes: Desenvolvimento, Homologação  e Produção, que serão utilizados para programar, prototipar e produzir processos.

## Athena

Athena é um serviço baseado na nuvem da AWS que permite consultar dados no data lake usando SQL (Presto SQL).

## Bucket S3

O Amazon S3 armazena dados como objetos dentro de recursos chamados "buckets", que são equivalentes a pastas. O armazenamento de objetos mantém os blocos de dados que compõem um aquivo junto e adiciona todos os metadados associados a esse arquivos.

## Crawler

Um crawler é um processo que é projetado para ler através de uma coleção de dados e metadados, armazenando essas informações no AWS Glue Catalog. Essas informações abrangem a estrutura dos dados, como colunas, tipos de dados, partições, juntamento com informações sobre os arquivos individuais que contêm os dados, como seu formato e onde eles estão armazenados no S3.

## AWS Glue 

O Glue é um serviço baseado na nuvem da AWS  que utilizamos para ingerir dados no Data Lake e programar esses processos para serem executados automaticamente. Esses processos são chamados de *Glue Jobs*

## AWS Glue Catalog

É um local para armazenar a documentação e metadados sobre os conjuntos de dados dentro do data lake. Ajudando os usuários a descobrirem quais dados existem, entender o que os dados significam e descobrir quem é o proprietário dos dados.

## AWS Glue Jobs

Um Glue Job encapsula um script que se conecta com os dados de origem, processa-os e grava-os no destino dos dados. Normalmente, um Glue Job executa scripts de extração, transformação e carregamento (ETL). Podendo também executar scripts Python de uso geral. Os triggers(gatilhos) do AWS Glue podem iniciar trabalhos com base em uma programação ou evento, ou sob demandas.

## AWS Lambda

AWS Lambda é uma plataforma de computação sem servidor orientada a eventos fornecida pela Amazon Web Services, sendo um serviço de computação que executa código em resposta a eventos e gerencia automaticamente os recursos de computação exigidos pelo código.

## AWS S3

S3 é uma abreviação de Amazon Simple Storage Service, que fornece armazenamento escalável e baseado em nuvem. É um armazenado baseado em objetos e utilizado para armazenar todos os dados em nosso data lake.

## Camadas de Dados

Uma cadama de dados no conceito de Data Mesh representa um estário ou componente específico no ciclo de vida de gerenciamento de dados dentro de uma organização, cada um com funções e responsabilidades definidas, incluindo a camada SOR ( Source of Record), SOT(System of Truth) e SPEC(Shared Product Event Contract). Essas camadas ajudam a estruturar e organizar a gestão de dados distribuídos de forma mais eficaz, promovendo a colaboração e a escalabilidade.

## Camada SOR(Source of Record)
A camada SOR é onde os dados são originados e mantidos em sua forma mais bruta e não processada. Ela representa a fonte primária e confiável dos dados dentro de uma organização, muitas vezes ligada a sistemas de registro de dados.


## Camada SOT (System of Truth)
A camada SOT é onde os dados são refinados, transformados e agregados para criar uma versão mais processada e confiável dos dados. É onde a lógica de negócios e as regras de transformação são aplicadas aos dados para garantir que eles sejam consistentes e confiáveis.

## Camada SPEC (Shared Product Event Contract)
A camada SPEC refere-se aos contratos compartilhados e às interfaces padronizadas que permitem a comunicação e a colaboração entre as diferentes partes interessadas em relação aos dados. É onde as equipes definem como os dados serão consumidos, compartilhados e utilizados em toda a organização, estabelecendo acordos sobre o que os dados significam e como podem ser usados.


## Data Lake

Um data lake é um repositório centralizado projetado para armazenar, processar e garantir grandes quantidades de dados estruturados, semi-estruturados e não-estruturados.

## Data Mesh

Data Mesh é uma abordagem arquitetônica para a gestão de dados que propõe a descentralização e a distribuição de responsabilidades de dados em uma organização, tratando os dados como produtos. 



## Democratização de Dados

A democratização de dados é o processo de tornar os dados acessíveis e utilizavéis para o público mais amplo, permitindo que pessoas de diferentes áreas e niveis hierárquicos da organização possam tomar decisões informadas com base em informações precisas. Isso envolve a implementação de políticas e ferramentas que promovem o acesso e a compreensão dos dados em toda a empresa.

## Esquema

O esquema de uma tabela se refere à estrutura e à propriedades de uma tabela, incluindo informações como o nome da tabela, as colunas, os tipos de dados das colunas, as restrições de integridade, chaves primária, estrangeiras, e outras propriedades relacionadas a essa tabela.

## Github

Github é uma plataforma de hospedagem de código para controle de versão e colaboração. Utilizamos como um repositório para armazenar o código para a infraestrutura e os processos da plataforma de dados. Isto permite rastrear e testar quaisquer alterações no código.

## Github Actions 

O Github Actions é um serviço oferecido pelo GiiHub que permite automatizar fluxos de trabalho de desnvolvimento, permitindo a criação, teste e implatanção contínua de código diretamente pelo repositório do Gitthub, oferencendo de maneira flexível definições e execuções de ações personalizadas em resposta a eventos específicos no ciclo de vida do desenvolvimento do software.

## Governança de Dadpos

Governança de dados é um conjunto de regras e práticas que uma organização adota para garantir a qualidade e a conformidade dos dados, bem como a gestão eficaz deles em toda a empresa. Ela visa assegurar que os dados sejam usados de maneira responsável, confiável e alinhada aos objetivos estratégicos da organização.

## Ingestão de Dados

Este é o processos de trazer dados de sua fonte origem para o data lake. O processo exato dependerá do tipo de dados que estão sendo ingesridos e onde esses dados estão sendo armazenados. No entanto, cada processo de ingestão de dados resultará no armazenamento dos dados no S3, armazenados em um bucket específico para o serviço. Os dados serão particionados pelo ano, mes e dia em que foram inseridos e, opcionalemnte, serão executados em um cronograma para que os dados sejam carregados a cada dia.

## Insumos 

Se refere aos componentes, recursos, com  dados ou informações de entrada necessários para que o sistema automatizado realize suas tarefas. Esses insumos são fundamentais para o funcionamento e a automação de sistemas e processos tecnológicos.

## JSON

JSON (Javascript Object Notation) é um formato de dados leve e legível por humanos usado para representar estruturas de dados em forma de pares de chave-valor, com suporte para objetos aninhados e arrays. É amplamente utilizado para a troca de informações estruturadas entre sistemas e é fácil ser intepretado tanto por humanos quanto por máquinas. A complexidade é determinada pelo conteúdo e pela lógica dos dados representados, sendo também escalável para atender uma ampla gama de necessidades de representação de dados.


## Lake Formation

AWS Lake Formation é um serviço que simplifica a criação, gerenciamento e segurança de data lakes na AWS, permitindo que se construa facilmente repositório centralizados de dados brutos e processados para análises avançadas.

## Modelagem de dados 

Modelagem de dados é o processo de criar representações estruturadas e organizadas dos dados que uma organização usa, incluindo tabelas, relacionamentos e esquemas, a fim de facilitar a coleta, armazenamento, análise e recuperação eficiente das informações. 

## Objetos

O armazenamento de objetos, também chamado de armazenamento baseados em objetos, é uma abordagem para endereçar e manipular o armazenamento de dados como unidades discretas, chamada de objetos. Os objetos são mantidos dentro de um único repositório e não são aninhados como arquivos dentro de uma pasta dentro de outra pastas.

## Partição

O particionamento é a divisão de dados em seções, geralmente por data. Sendo utilizada para melhorar o desempenho e tornar os dados mais fáceis de gerenciar. Por exemplo, dados históricos de um serviço podem ser armazenados na plataforma em uma partição, e todos os dias, novos dados são adicionados em sua própria partição. Facilitando a  consulta, que só precisaria consultar as partições relevantes para seu trabalho, em vez de todo o conjunto de dados.

## Pipeline de dados

Uma pipeline de dados é um conjunto de ferramentas e processos usados para automatizar a movimentação e a transformação de dados entre um sistema de origem e um repositório de destino (por exemplo, um data lake).

## Plataforma de Dados

Uma plataforma de dados é uma solução de tecnologia integrada que permite que dados localizados em diferentes fontes de dados sejam governandos, acessados e entregues à usuários, aplicativos e outras tecnologias. Sendo composta por uma sério de diferentes elementos. 

## Portal E  A


## Pyspark

PySpark é uma interface para Apache Spark em Python.

## Python

Uma linguagem de programação de código aberto que é comumente usada para tarefas de dados, como limpeza de dados, transformação, análise e aprendizado de máquina.

## Spark

O Apache Spark é um mecanismo de código aberto usado para executar tarefas de processamento rapidamente em grandes conjuntos de dados. Há suporte para código escrito em Scala, Java, Python e R.

## Step Functions

O AWS Step Functions é um serviço de orquestração de fluxos de trabalho na nuvem da Amazon que permite coordernar e automatizar facilmente tarefas individuais ou serviços em uma séria de passos, tornando mais simples o desenvolvimento de aplicativos baseados em estados. Ele ajuda a criar, monitorar e gerenciar fluxos de trabalho escaláveis e eficientes usando uma linguagem declarativa que descreve as etapas e a lógica do processo de forma clara.

## Terraform

Terraform é a ferramenta de Infrastucture as Code (IaC), utilizada para gerencia e provisionar recursos de nuvem com o uso de arquivos de configuração como script. Permite fácil manutenção e criação dos diferentes recursos de nuvem para sistemas de grande escala de forma colaborativa.

