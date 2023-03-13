# 4.1 Criando e Planejando Eventos

Um evento é um sinal de que um estado mudou. Um evento descreve algo que aconteceu no passado (por exemplo, `OrderCreated`) e é imutável ou não pode ser alterado.

Um **esquema de evento** representa a estrutura de um evento e informa sobre seus dados. Por exemplo, um evento `OrderCreated` pode incluir campos como ID do produto, quantidade e endereço de entrega. O esquema também diz que o ID do produto e a quantidade são números inteiros e o endereço de entrega é uma string de texto.

Um **registro de esquema** é um local compartilhado onde as equipes podem armazenar seus esquemas de eventos. O uso de um registro de esquema permite criar serviços que consomem eventos de outro serviço sem a necessidade de coordenação com seus desenvolvedores. Ao projetar esquemas de eventos, você pode optar por ter eventos esparsos ou eventos com descrições completas de estado. Um evento esparso tem muito poucos dados sobre o evento, talvez apenas o ID de evento.

![](https://serverlessland.com/assets/images/eda/sparse-full-event.png)

Ambos os tipos de eventos têm suas compensações. Ao emitir um evento esparso com muitos consumidores que buscam seus detalhes, todos os consumidores solicitarão mais dados de um serviço de uma só vez. Isso pode sobrecarregar o serviço ou banco de dados que contém as informações do evento.

O envio de descrições completas de estado com seus eventos exigirá que você considere a compatibilidade com versões anteriores. Os esquemas de eventos são muito parecidos com um contrato entre produtores e consumidores.

https://www.youtube.com/watch?v=uPljZ08sk2c

A alteração das informações do evento pode impactar os consumidores e deve ser evitada. Você também deve considerar o custo de calcular os valores em seus dados de evento. Quando você começa a construir seu aplicativo, os dados podem estar todos no mesmo local, como na mesma tabela em um banco de dados. À medida que seu aplicativo evolui, isso pode mudar. Você pode armazenar diferentes tipos de dados em diferentes locais ao longo do tempo, aumentando o custo para calcular os valores.

Embora a maioria dos eventos dos aplicativos caia em algum lugar entre descrições de estado esparsas e completas, esparsidade é um bom ponto de partida. Identifique os campos e valores que são compartilhados e usados ​​pela maioria dos consumidores e, em seguida, adicione-os primeiro ao seu esquema de evento. À medida que novos requisitos acontecem, você pode adicionar mais dados aos eventos, mas certifique-se de considerar a compatibilidade com versões anteriores de dados adicionais.
