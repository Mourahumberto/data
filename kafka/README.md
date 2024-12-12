# APACHE KAFKA
- A plataforma líder para real-time data streaming
[kafka-cluster.webp]

### Arquitetura kafka: key components
1.  **Kafka Topics:** Tópicos representão um stream específico dos registros, onde categorizamos os dados. Os producers publicam nesses tópicos e os consumers lem desses tópicos. Os tópicos habilitam a organização segmentar seus dados dentro do ecossistema do kafka.  
EX: Um exemplo seria um banco onde todos os pagamentos de boletos do app são guardados e processados por um topico chamado "boletos"
2. **Kafka Producers:** Os producers no kafka são responsávei por publicar registros dentro dos tópicos kafka. Eles enviam para o topic específico definido.
Ex: uma parte do sistema envia para o topico "transactions" toda vez que um cliente usar o cartão.
3. **Kafka Consumers:** Os consumers lem dos tópicos os dados registrados pelos producers.
4. **Kafka Consumer Groups and Consumer Offsets::** """Kafka introduces the concept of consumer groups, which allows for the parallel processing of records within a topic. Consumer groups consist of multiple consumers that work together to consume records from a topic. Each consumer within a group processes a subset of the topic’s partitions. Consumer offsets track the progress of a consumer within a topic and ensure reliable and efficient data consumption.
Example: Multiple consumers in the “sales-analytics” and “fraud-detection” groups process different subsets of transaction records, keeping track of their progress using consumer offsets."""
5. **Kafka Partitions:** Tópicos são quebrados em partitions, quer dizer que um tópico pode sewr quebrado em vários pedacinhos "partitions" dessa forma pode ser escrito e lido de forma paralela
[replication image]
6. **Kafka Brokers:** Os kafka brokers são os works do cluster que juntos formam o cluster. Cada broker é responsável por um conjunto de partitions de um topic. Os brokers garantem a tolerancia a falhas escalabilidade e resiliência do cluster.
7. **Kafka Topic replication:** Para a ssegurar a durabilidade e a resiliência a falhas o kafka suporta replication. Topics replicados mantem cópias dos partitions em vários brokers dependendo do número de replicas desejadas. Assim caso um boker falhe terá cópia em outro.
EX: o topic "transections" tem fator de replicação então caso um broker falhe ele tem seus dados em outro broker.