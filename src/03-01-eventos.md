# 3.1 Eventos

Um evento é um sinal de que um estado mudou, como um item sendo colocado em um carrinho de compras em um site de comércio eletrônico ou um cliente enviando uma solicitação de cartão de crédito em um site bancário. Eventos ocorrem no passado, ex: `OrderCreated`, `ApplicationSubmitted`.

https://www.youtube.com/watch?v=5bsFBbIAdT4

Os eventos são imutáveis, o que significa que não podem ser alterados. Isso é útil em sistemas distribuídos porque não há alterações para manter a sincronização entre os componentes.

Os eventos são observados, em vez de direcionados. Quando um componente emite um evento, ele não o está enviando para um destino específico e não tem conhecimento dos componentes _downstream_ que podem consumir o evento.
