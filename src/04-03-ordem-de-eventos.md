# 4.3 Ordem de Eventos

Uma consideração importante com a arquitetura orientada a eventos é se seu aplicativo requer eventos entregues em uma ordem específica (eventos ordenados) ou se a ordem não importa (eventos não ordenados). A ordem geralmente é garantida dentro de um escopo específico.

Você pode optar por construir com um serviço que garanta a ordem, como Amazon Kinesis Data Streams ou Amazon SQS FIFO (_First-In-First-Out_). O Amazon Kinesis Data Streams preserva a ordem nas mensagens em um _shard_. No Amazon SQS FIFO, a ordem é preservada em um ID de grupo de mensagens. No entanto, é importante entender que a ordem garantida apresenta desvantagens quando comparada a eventos não ordenados, como aumento de custo e possíveis gargalos nas operações.

Outros serviços, como o Amazon EventBridge e as filas padrão do Amazon SQS, oferecem "ordenação de melhor esforço". Isso significa que seu aplicativo deve assumir que receberá mensagens fora de ordem. Para muitas aplicações, isso não será um problema. No entanto, se seu aplicativo exigir ordem, é simples de se mitigar.

Construir sistemas para lidar com eventos fora de ordem pode aumentar a resiliência do seu aplicativo. Isso garante que seu aplicativo não falhe por engano caso o evento seja enviado fora de ordem. Por exemplo, se seu aplicativo tiver pedidos de clientes, você pode assumir que não pode receber um evento `OrderUpdated` antes de um evento `OrderCreated`.

Você pode lidar com isso criando um _registro de transação parcial_ em um banco de dados quando um evento `OrderUpdated` é recebido, enquanto espera o evento `OrderCreated` ser recebido. Você pode então gerar um relatório operacional com detalhes de transações incompletas para revisar e descobrir problemas. Em vez de assumir que os eventos estarão em ordem e, caso contrário, falharão, você pode criar para lidar com eventos fora de ordem e aumentar a tolerância a falhas e a escalabilidade de seu aplicativo.
