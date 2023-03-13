# 3.5 Testes e depuração

Arquitetura orientada a eventos podem produzir efeitos colaterais que podem ser mais difíceis de detectar no teste de integração. Uma boa prática é consultar a [Pirâmide de Testes](https://martinfowler.com/articles/practical-test-pyramid.html), que recomenda muitos testes de unidade que podem ser executados isoladamente e um número menor de casos de teste de integração ou ponta-a-ponta. O teste de contrato verifica se dois sistemas (como dois micro-serviços) podem se comunicar entre si, tornando-o uma estratégia de teste ideal para aplicativos orientados a eventos.

A depuração de aplicativos orientados a eventos também apresenta novos desafios em comparação com aplicativos monolíticos. Com diferentes sistemas e serviços passando eventos entre si, muitas vezes é um desafio registrar e reproduzir o estado exato de vários serviços quando ocorre um erro.
