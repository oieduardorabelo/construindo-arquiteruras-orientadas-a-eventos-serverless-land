# 3.4 Latência Variável

Os aplicativos orientados a eventos se comunicam através de várias redes e componentes, ao contrário dos aplicativos monolíticos, que executam todos os processos usando a mesma memória em um único dispositivo. Isso introduz latência variável. Embora seja possível projetar aplicativos orientados a eventos para minimizar a latência, os aplicativos monolíticos sempre podem ser otimizados para menor latência em detrimento da escalabilidade e acessibilidade.

Projetos que **exigem desempenhos consistentes de baixa latência não são bons candidatos** para ter uma arquitetura orientada a eventos.

Exemplos relevantes incluem aplicações de negociação de alta frequência em bancos (_high-frequency trading_) ou automação de robótica abaixo de um milissegundo em armazéns.
