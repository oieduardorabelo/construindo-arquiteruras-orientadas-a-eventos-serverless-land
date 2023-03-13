# 1.3 Acoplamento forte vs. acoplamento fraco

Ao criar um novo aplicativo, os clientes costumam criar aplicativos fortemente acoplados com componentes conectados diretamente. Aplicativos fortemente acoplados são fáceis de começar e simples de operar em pequena escala. À medida que o aplicativo cresce em escala e complexidade, essas conexões diretas podem se tornar difíceis de gerenciar. Aplicativos fortemente acoplados podem ter pontos únicos de falha, impactando a escalabilidade do aplicativo. Os desenvolvedores precisam se coordenar de perto para fazer alterações em componentes interdependentes, diminuindo a velocidade de lançamento de novos recursos.

[O acoplamento](https://www.enterpriseintegrationpatterns.com/patterns/messaging/Chapter1.html) é a medida da dependência que cada componente de um aplicativo tem um do outro. Sistemas fortemente acoplados podem ser particularmente eficazes se o aplicativo tiver poucos componentes ou se uma única equipe ou desenvolvedor possuir todo o controle do aplicativo. No entanto, quando os componentes estão mais fortemente acoplados, torna-se cada vez mais provável que uma alteração ou problema operacional em um componente se propague para os outros.

![](https://serverlessland.com/assets/images/eda/coupled-systems.png)

Para sistemas complexos, o acoplamento forte pode ter desvantagens. Quando os componentes são totalmente interdependentes, pode ser difícil fazer alterações isoladas em um único componente sem afetar os outros. Isso pode desacelerar o processo de desenvolvimento e reduzir a velocidade de produzir novos recurso.

Componentes fortemente acoplados também podem afetar a escalabilidade e a disponibilidade de um aplicativo. Se dois componentes dependerem das respostas síncronas um do outro, uma falha em um fará com que o outro falhe. Essas falhas podem reduzir a tolerância geral a falhas do aplicativo.

Reduzir o acoplamento é o ato de reduzir a interdependência entre os componentes e a consciência que cada componente deve ter um do outro. As arquiteturas orientadas a eventos alcançam acoplamento fraco por meio de comunicação assíncrona de eventos. Isso acontece quando um componente não precisa de outro para responder. Em vez disso, o primeiro componente pode enviar um evento e continuar seu processo sem impactar o segundo componente, case ele atrase ou falhe.

![](https://serverlessland.com/assets/images/eda/event-broker.png)

Ao se comunicar com eventos, os componentes precisam apenas estar cientes dos eventos independentes. Eles não exigem conhecimento do componente transmissor ou do comportamento de qualquer outro componente (por exemplo, tratamento de erros, lógica de repetição). Desde que o formato do evento permaneça o mesmo, as alterações em um único componente não afetarão os outros. Isso permite fazer alterações em um aplicativo com menos risco. Quando eventos assíncronos abstraem componentes uns dos outros, aplicativos complexos se tornam mais resilientes e acessíveis.

---

O acoplamento forte apresenta desvantagens para sistemas complexos com muitas equipes envolvidas. Quando os componentes de um aplicativo complexo são totalmente interdependentes, pode ser difícil e arriscado alterar um componente e, ao mesmo tempo, garantir que essas alterações não afetem outros componentes. Isso pode desacelerar o processo de desenvolvimento e reduzir a velocidade de produzir novos recurso. Componentes fortemente acoplados também podem afetar a escalabilidade e a disponibilidade do aplicativo. Se dois componentes dependem de respostas síncronas um do outro, uma falha em um componente causará uma falha no outro. Esses pontos únicos de falha reduzem a tolerância a falhas do aplicativo.

Por exemplo, um aplicativo de comércio eletrônico pode ter vários serviços (pedidos, cobrança, remessa, estoque) e fazer uma cadeia síncrona de chamadas para esses serviços.

![](https://serverlessland.com/assets/images/eda/synchronous-chain-of-calls.png)

Uma falha em um desses serviços...

![](https://serverlessland.com/assets/images/eda/synchronous-service-failure.png)

...afetará todos os outros serviços.

![](https://serverlessland.com/assets/images/eda/synchronous-failure-impact.png)
