# 2.5 Conectando fontes de eventos

Muitos aplicativos têm fontes de eventos externas, incluindo aplicativos SaaS, como aplicativos de negócios responsáveis ​​por executar a folha de pagamento, armazenar registros ou emissão de bilhetes. Você também pode ingerir eventos de um aplicativo ou banco de dados existente em execução na sua empresa. As arquiteturas orientadas a eventos podem usar eventos de todas essas fontes.

Quando os aplicativos emitem eventos de negócios, uma maneira comum de propagar os eventos é com um conector ou intermediário de mensagem(_connector or message broker_). Esses conectores conectam aplicativos SaaS ou fontes locais e enviam eventos para um fluxo ou roteador, permitindo que os consumidores os processem. Você pode usar fontes de [eventos de parceiros do Amazon EventBridge](https://aws.amazon.com/eventbridge/integrations/) para enviar eventos de aplicativos SaaS integrados na sua conta para seus aplicativos da AWS.

Recursos extras:

- [Building a mainframe connector with Amazon MQ or Amazon MSK](https://aws.amazon.com/blogs/architecture/mainframe-offloading-and-modernization-using-mainframe-data-to-build-cloud-native-services-with-aws)
