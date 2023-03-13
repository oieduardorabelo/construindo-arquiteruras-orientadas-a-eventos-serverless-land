# 4.2 Idempotência

[Idempotência](https://en.wikipedia.org/wiki/Idempotence) é a propriedade de uma operação que pode ser aplicada várias vezes sem alterar o resultado da aplicação após a execução inicial. Você pode executar com segurança uma "operação idempotente" várias vezes sem efeitos colaterais, como duplicação ou inconsistência de dados.

A idempotência é um conceito importante para arquiteturas orientadas a eventos porque elas provavelmente usarão mecanismos de repetição. Por exemplo, ao invocar de forma assíncrona uma função do AWS Lambda com um evento em que a função falha inicialmente, o Lambda possui [lógica de repetição integrada](https://docs.aws.amazon.com/lambda/latest/dg/invocation-retries.html) e invocará a função novamente. Isso aumenta a resiliência do seu aplicativo, mas também significa que uma mensagem pode ser processada várias vezes pela função. Esta é uma consideração importante ao gerenciar pedidos, pagamentos ou qualquer tipo de transação que deva ser tratada apenas uma vez.

![](https://serverlessland.com/assets/images/eda/idempotency-key.png)

Você pode optar por construir todos os seus serviços como idempotentes. Isso é útil ao lidar com eventos duplicados para que qualquer operação possa ser executada várias vezes sem efeitos colaterais. No entanto, essa abordagem pode aumentar a complexidade do seu aplicativo. Outra opção seria incluir um identificador único em cada evento como uma [chave de idempotência](https://aws.amazon.com/blogs/compute/handling-lambda-functions-idempotency-with-aws-lambda-powertools/).

Depois que o evento for processado, atualize a camada persistência de dados com os resultados. Se algum novo evento chegar com a mesma chave de idempotência, retorne o resultado da solicitação inicial.
