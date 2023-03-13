# 3.2 Componentes Principais de EDA

Existem vários componentes-chave em uma arquitetura orientada a eventos:

![](https://serverlessland.com/assets/images/eda/event-producer-broker-consumer.png)

- Um **produtor de eventos** publica eventos. Exemplos de produtores incluem sites front-end, micro-serviços, dispositivos IoT, serviços da AWS e aplicativos SaaS.

- Um **consumidor de evento** é um componente _downstream_ que executa ações baseadas nos eventos. Pode haver vários consumidores do mesmo eventos. Consumir eventos pode envolver iniciar um fluxo de trabalho, executar uma análise ou atualizar um banco de dados.

- Um **agente de eventos** (_event broker_) fica entre produtores e consumidores, permitindo que eles publiquem e consumam eventos compartilhados enquanto abstraem os dois lados um do outro. Os exemplos incluem roteadores de eventos que enviam eventos para destinos diversos e armazenamentos de eventos dos quais os consumidores podem extrair eventos.
