# SCM and Branching Strategy


## Introdução

[Software Configuration Management (SCM)](https://en.wikipedia.org/wiki/Software_configuration_management) é a tarefa de rastrear e controlar as mudanças feitas em um software. Caso algo apresente problemas o SCM consegue determinar o que foi alterado e quem o alterou, além disso se tudo estiver ocorrendo bem o SCM pode determinar como replicar o cenário em vários hosts. Outro conceito importante é o de [Branching Strategy](https://www.perforce.com/blog/vcs/best-branching-strategies-high-velocity-development#:~:text=Branching%20strategies%20%E2%80%94%20like%20feature%20branching,the%20feedback%20they%20need%20quickly.), que significa definir as estratégias a serem seguidas ao usar um controle de versionamento como o Git. Isso permite orquestrar o trabalho em equipe de forma paralela.


## Git Flow

![Git Flow](https://miro.medium.com/max/700/1*9yJY7fyscWFUVRqnx0BM6A.png)

O GitFlow é uma *Branching Strategy* que facilita a resolução de conflitos, o trabalho coletivo e que bugs repetidos não ocorram. Aprensenta grandes vantagens quando há times grandes trabalhando.

*Branches*
* **Master** - Representa o código que está rodando em produção. Apartir dessa *branch* geramos as tags (marcação de pontos importantes no desenvolvimento).
* **Develop** - A *branch* de desenvolvimento dá origem as *branches* de features, onde serão implementadas as funcionalidades.
* **Realease** - Quando a *branch* de desenvolvimento tiver as *features* completas, criamos uma *branch* de *release*, começando assim o processo de lançamento de uma nova versão. Aqui são corrigidos os bugs relacionados apenas a própria **release**. E depois de corrigidos os bugs devemos enviar as alterações para a **master** e para a **develop**.
* **Hotfix** - Quando surgir um bug já em produção, uma *branch* de **hotfix** é criada e em seguida reenviada para a **master** e **develop**, assim todas as *features* se aproveitarão dessa correção.


## Trunk based development 

Ao contrário do GitFlow, no Trunk Development, as alterações do código são feitas direto na *master*, ou em *feature branches* com duração curta. Ao utilizar esse processo não significa que muitos error entrarão em produção, na verdade existem uma série de vantagens ao se utilizar essa *branching strategy*. Os benefícios de se usar essa estrátegia são adquiridos de forma indireta, pois para chegar em um desenvolvimento trunk based é preciso que o time saiba como trabalhar com o código sem quebrá-lo, como escrever bons testes e como trabalhar coletivamente de forma efetiva.


## Materias complementares

[GitHub Flow](http://scottchacon.com/2011/08/31/github-flow.html)

[Estratégias de ramificação, Conflitos e Pull Requests](https://www.alura.com.br/curso-online-git-github-branching-conflitos-pull-requests)

[Why I love Trunk Based Development (or pushing straight to master)](https://medium.com/@mattia.battiston/why-i-love-trunk-based-development-641fcf0b94a0)