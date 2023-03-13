# 3.3 Consistência Eventual (_Eventual Consistency_)

Em uma arquitetura orientada a eventos, os eventos são cidadãos de primeira classe e o gerenciamento de dados é descentralizado. Como resultado, os aplicativos geralmente são [eventualmente consistentes](https://en.wikipedia.org/wiki/Eventual_consistency), o que significa que os dados podem não estar perfeitamente sincronizados no aplicativo, mas acabarão se tornando consistentes em tempo.

A consistência eventual pode complicar as coisas ao processar transações, lidar com dados duplicados e determinar o estado geral exato do sistema. Alguns componentes em muitos aplicativos são mais adequados do que outros para lidar com dados eventualmente consistentes.
