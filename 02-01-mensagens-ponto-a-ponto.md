# 2.1 Mensagens ponto-a-ponto

[Sistemas de mensagens ponto-a-ponto](https://www.enterpriseintegrationpatterns.com/PointToPointChannel.html) é um padrão no qual os produtores enviam mensagens normalmente destinadas a um único consumidor. O sistema de mensagens ponto-a-ponto geralmente usa filas de mensagens como seu agente de eventos. Em aplicativos de micro-serviços, mensagens ponto-a-ponto assíncronas entre micro-serviços são chamadas de ["tubos burros" (_dumb pipes_)](https://martinfowler.com/articles/microservices.html#SmartEndpointsAndDumbPipes).

![](https://serverlessland.com/assets/images/eda/point-to-point-messaging.png)

As filas são canais de mensagens que permitem a comunicação assíncrona entre um remetente e um destinatário. As filas fornecem um _buffer_ para mensagens caso o consumidor esteja indisponível ou precise controlar o número de mensagens processadas em um determinado momento. As mensagens persistem até que o consumidor as processe e exclua da fila.

Serviços como [Amazon Simple Queue Service](https://aws.amazon.com/sqs/) (Amazon SQS) e [Amazon MQ](https://aws.amazon.com/amazon-mq/?amazon-mq.sort-by=item.additionalFields.postDateTime&amazon-mq.sort-order=desc) são comuns no uso de filas de mensagens em arquiteturas orientadas a eventos. Você também pode usar [invocações assíncronas](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html) do [AWS Lambda](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html).

Em invocações síncronas, o chamador espera que a função do Lambda conclua sua execução e que a função retorne um valor. Em invocações assíncronas, o chamador coloca o evento em uma fila interna, que é então processada pela função Lambda.

Com este modelo, você não precisa mais gerenciar uma fila ou roteador intermediário. O chamador pode prosseguir depois de enviar o evento para a função AWS Lambda. A função pode enviar o resultado para um [destino](https://docs.aws.amazon.com/lambda/latest/dg/invocation-async.html#invocation-async-destinations), com configurações variando de sucesso ou falha. A fila interna entre o chamador e a função garante que as mensagens sejam armazenadas de forma durável.
