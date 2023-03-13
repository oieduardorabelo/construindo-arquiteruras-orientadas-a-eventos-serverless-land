# 2.2 Mensagens de Pub/Sub

[Sistema de mensagens Pub/Sub](https://www.enterpriseintegrationpatterns.com/PublishSubscribeChannel.html) é uma maneira pela qual os produtores enviam a mesma mensagem para muitos consumidores. Enquanto o sistema de mensagens ponto-a-ponto geralmente envia mensagens para apenas um consumidor, o sistema de mensagens de _assinatura de publicação_ (pub/sub) permite que você transmita mensagens e envie uma cópia para cada consumidor. O agente de eventos nesses modelos é frequentemente um roteador de eventos. Ao contrário das filas, os roteadores de eventos normalmente não oferecem persistência de eventos.

![](https://serverlessland.com/assets/images/eda/pub-sub-messaging.png)

Um tipo de roteador de evento é um tópico, um destino de mensagens que facilita integrações _hub-and-spoke_. Nesse modelo, os produtores publicam mensagens em um hub e os consumidores assinam os tópicos de sua escolha.

![](https://serverlessland.com/assets/images/eda/event-bus-messaging.png)

Outro tipo de roteador de eventos é um _event bus_, que fornece uma lógica de roteamento sofisticada. Enquanto os tópicos enviam todas as mensagens enviadas aos assinantes, os _event buses_ podem filtrar o fluxo de entrada de mensagens e enviá-las a diferentes consumidores com base nos atributos do evento.

Você pode usar o [Amazon Simple Notification Service](https://aws.amazon.com/sns/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc) (Amazon SNS) para criar tópicos e o [Amazon EventBridge](https://aws.amazon.com/eventbridge/) para criar _event buses_. O Amazon EventBridge oferece suporte a eventos persistentes por meio de sua [funcionalidade de arquivamento](https://docs.aws.amazon.com/eventbridge/latest/userguide/eb-archive-event.html). O [Amazon MQ](https://aws.amazon.com/amazon-mq/?amazon-mq.sort-by=item.additionalFields.postDateTime&amazon-mq.sort-order=desc) também oferece suporte a tópicos e roteamento.

https://www.youtube.com/watch?v=TXh5oU_yo9M
