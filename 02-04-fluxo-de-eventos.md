# 2.4 Fluxo de Eventos (Event Streaming)

O uso de streams, ou fluxos contínuos de eventos ou dados, é outro método de abstrair produtores e consumidores. Em contraste com os roteadores de eventos, embora comparáveis ​​às filas, os fluxos geralmente exigem que os consumidores pesquisem novos eventos. Os consumidores mantêm sua lógica de filtragem exclusiva para determinar quais eventos desejam consumir enquanto rastreiam sua posição no fluxo.

Fluxos de eventos (_event streams_) são fluxos contínuos de eventos (_continuous flows of events_), que podem ser processados ​​individualmente ou em conjunto durante um período de tempo. Um aplicativo de compartilhamento de viagens, que transmite as mudanças de localização de um cliente como eventos, é um exemplo de transmissão de eventos. Cada evento `"LocationUpdated"` existe como um ponto de dados significativo usado para atualizar visualmente a localização do cliente em um mapa. Ele também pode analisar eventos de localização ao longo do tempo para fornecer informações, como a velocidade do motorista.

![](https://serverlessland.com/assets/images/eda/event-streaming-messaging.png)

Os fluxos de dados diferem dos fluxos de eventos porque sempre interpretam os dados ao longo do tempo. Neste modelo, pontos de dados individuais, ou registros, não são úteis de forma independente. Os aplicativos de fluxo de dados são frequentemente usados ​​para manter os dados após um enriquecimento opcional ou para processar os dados durante um período de tempo predefinido para obter análises em tempo real. Um exemplo pode ser o streaming de dados do sensor do dispositivo IoT. Os registros de leitura de sensores individuais podem não ser valiosos sem contexto, mas os registros coletados durante um período de tempo podem ajudar a contar uma história mais rica.

[Amazon Kinesis Data Streams](https://aws.amazon.com/kinesis/data-streams/) e Amazon Managed Streaming for [Apache Kafka (Amazon MSK)](https://aws.amazon.com/msk/) podem ser usados ​​para fluxos de eventos e casos de uso de streaming de dados.
