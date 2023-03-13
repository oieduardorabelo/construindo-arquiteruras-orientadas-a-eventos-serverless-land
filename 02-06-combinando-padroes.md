# 2.6 Combinando padrões

Embora qualquer padrão individualmente possa atender aos seus requisitos, as arquiteturas orientadas a eventos geralmente combinam uma série de padrões que:

- Enviam a mesma mensagem para vários assinantes de um único tópico (_Fan out_).

![](https://serverlessland.com/assets/images/eda/fan-out-pattern.png)

- Filtra e encaminha eventos específicos para serem enviados a diferentes destinos

![](https://serverlessland.com/assets/images/eda/filter-route-pattern.png)

- Filtra eventos para encaminhá-los para uma fila de persistência

![](https://serverlessland.com/assets/images/eda/filter-queue-pattern.png)

- Orquestre fluxos de trabalho e emita eventos em etapas dentro do fluxo de trabalho

![](https://serverlessland.com/assets/images/eda/orchestrate-event-pattern.png)
