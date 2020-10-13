# Agentes - Introdução a inteligencia artificial

## Definição

Um agente é qualquer coisa capaz de perceber seu ambiente por meio de sensores e agir sobre esse ambiente por meio de atuadores.

Ex1: Um agente humano tem olhos, orelhas, e outros orgãos como sensores e mãos e pernas, trato vocal, entre outros como atuadores.

Ex2: Um agente robótico possui câmeras, detector de infravermelho... como sensores e como atuadores possui vários tipos de motores.

Ex3: Agentes de software utilizam-se da entrada do teclado (input de usuario), conteudo de arquivos e pacotes recebidos da rede como sensores e usam a tela, o disco rigido e o envio de pacotes a rede como atuadores.

### Percepção
O termo percepção é usado para se referir aos estimulos sensoriais que captam o estado atual do meio exterior do agente.

### Atuação
refere-se aos estimulos do agente que alteram o estado do meio exterior.

## Mapeamento de percepções em ações

### Sequencia de percepções
Trata-se da sequencia completa de tudo que o agente percebeu.

### Função do agente
Matematicamente falando, o compotamento do agente é dado pela função do agente, que mapeia sequencia de percepções dada para uma ação.

$ [f: P* -> A]$

onde P* é a sequencia de percepções e A é uma ação.

### Programa do agente
É uma implementação concreta que é executado em algum sistema (arquitetura) fisico(a) para produzir a função do agente.
- Agente = Arquitetura + Programa.

## Agente racional
Um agente racional é aquele que faz tudo certo - conceitualmente falando, toda entrada na tabela da função do agente é preenchida corretamente.

De maneira um pouco mais simplista, um agente racional pode ser qualquer coisa que tome decisões, seja uma pessoa, uma empresa, um robo ou um software.

A pergunta que fica com essas definições é, como saber se o agente realmente tomou a decisão correta?

Bem como sabemos, quando o agente é colocado em um ambiente, ele realiza uma sequencia de ações de acordo as suas percepções do ambiente. Esta sequecia de ações faz com que o ambiente passe por uma sequencia de estados.
Ex: Local sujo ateriormente, mas no momento atual ele esta limpo.
se a sequencia de estados é a esperada, então o agente tem boa performance.
Essa noção de resultado esperado é tomado como medida de desempenho,ela avalia qualquer sequencia de estados dados ao ambiente.
Se a medida de desempenho coincidir com o objetivo do agente, então, a ação do agente é retornada como "Correta".

Note que para cada sequecia de percepções possiveis, o agente deve selecionar uma ação que venha a maximizar sua medida de desempenho.

### Onisciencia, aprendizado e autonomia

É preciso saber destinguir entre racionalidade e onisciência. Um agente onisciente conhece o resultado real das suas açôes, e pode agir de acordo a elas.

A racionalidade não é o mesmo que perfeição. A racionalidade maximiza o desempenho esperado, enquanto que a perfeição maximiza o desempenho real.

Portanto, afirma-se que a racionalidade não exige onisciência porque a escolha racional só depende da sequencia de percepções até o momento.

O gente deve realizar ações em pról de modicar futuras percepções, tambem conhecido como **coleta de informações**.

Um tipo importante de coleta de informação é a **exploração** de um ambiente desconhecido. É requerido que um agente não apenas colete informações, mas também seja capaz de aprender o maximo possivel a partir do que ele percebe. Isso significa que a medida em que o agente for amadurecendo ele poderá
modificar o seu comportamento com base em sua experiencia, caracterizando o que chamamos de um **Agente Autonomo**.

Um agente que aprende tende a ter sucesso em uma ampla gama de ambientes.

## A natureza dos ambientes

### Especificando o ambiente de tarefa

Ao projetar um agente, o primeiro passo a sempre ser feito é especificar um ambiente de tarefa o tanto completo quanto possivel.

Um ambiente de taferas é um agrupamento dos termos: medida de desempenho, o ambiente e as sensores e atuadores do agente. Esse agrupamento é encontrado com mais frequencia em bibliografias com o acrônimo vindo do inglês **PEAS** (performance, Enviroinment, Actuators, Sensors).

### Propriedades do ambiente de tarefa

Há uma enorme gama de ambientes de tarefa que podem surgir na **Inteligência Artificial**, porem, podemos indentificar apenas um pequeno numero de ambientes de tarefa a serem divididos em categorias. Essas dimensões são importantes por que determinam o projeto apropriado do agente e a aplicabilidade de varias tecnicas de implementação de agentes.

A seguir analisaremos as propriedades de varios ambientes de tarefa

#### Completamente observavel vs. Parcialmente observavel

Se os sensores do agente dão a ele acesso completo ao estado do ambiente a cada instante, então nós dizemos que esse ambiente de tarefa é completamente observavel.
Um ambiente de tarefas é efetivamente observavel se os sensores detectam todos os aspectos relevantes para a escolha da ação.por sua vez, a relevancia depende da medida de desempenho.

Um agente pode ser parcialmente observavel devido a ruidos e a sensores imprecisos ou por que partes do estado estão simplesmente faltando nos dados do sensor.
Quando o agente não possiu sensores, o ambiente é então tratado como inobservavel.

####  Agentes unicos vs. Multiagentes

De maneira simplista, um agente unico é o unico agente que está operando sozinho no ambiente.
Quando o ambiente está sendo operado por mais de um agente, então temos um ambiente de multiagentes
Os multiagentes podem ser **Competitivos** (Quando a maximização da medida de desempenho de um agente miniza a medida de desempenho de outro agente) e **Cooperativos** (Quando a ação de um agente maximiza a medida de desempenho de todos os agentes).

#### Deterministico vs. Estocastico

Se o proximo estado do ambiente é completamente determinado pelo estado atual e pela ação executada pelo agente, então dizemos que o ambiente é deterministico. caso contrario dizemos que ele é estocastico.

#### Episodico vs. Sequencial

Em um ambiente de tarefa episodico a experiencia do agente é dividida em episodios atomicos, em que cada episodio o agente recebe uma percepção e então executa uma ação.

A escolha da ação em cada episodio só depende do proprio episodio, portanto, é crucial que o episodio seguinte não dependa das ações executadas em episodios anteriores.

Em contra partida, em ambientes sequenciais, a decisão atual pode afetar todas as decisões futuras.

#### Estatico vs. Dinamico

Se o ambiente puder se alterar enquanto um agente está deliberando, dizemos que o ambiente é dinamico para esse agente.

O ambiente é estatico se ele não muda enquanto o agente pensa.
Se o ambiente não muda com a passagem do tempo, mas a medida de desempenho do agente se altera, dizemos que esse ambiente é semidinamico.

#### Discreto vs. Continuo

A distinção entre discreto e continuo aplica-se ao estado do ambiente ao modo como o tempo é tratado e ainda as persepções e ações do agente.
Um agente discreto possui um conjunto finito de estados, alem de um numero limitado de percepções e ações.

## A estrutura de Agentes ( Tipos de Agentes)

Agora veremos um pouco de como é o funcionamento interno dos agentes. O trabalho de IA é projetar o **programa do agente** que implementa a função do agente (Que mapeia as percepções em ações). Este programa é execultado em em dispositivo fisico equipado com sensores e atuadores podendo ser um computador de mesa, um carro robotico, etc. Esse conjunto é chamado de arquitetura. Como foi dito lá atrás, um Agente é formado pela arquitetura mais o programa do agente.

    Agente = Arquitetura + Programa
    
### Agentes dirigidos por tabela

O programa do agente dirigido por tabela acompanha a squencia de percepções e depois a utiliza para realizar a indexação em uma tabela de ações, a fim de decidir qual a melhor ação a ser feita.

É necessario construir uma tabela que contenha a ação necessaria pata cada sequencia de percepções possiveis.

    função AGENTE-DIRIGIDO-POR-TABELA(percepção) retorna UMA AÇÂO
        variaveis estaticas: percepções, uma sequencia, tabela inicialmente vazia
                             uma tabela de ações, indexada por sequências de percepções, 
                             inicialmente completamente especificada
        anexar percepção ao fim das percepções
        ação <- ACESSAR(percepções, tabela)
        retornar AÇÂO

É importante ressaltar que a abordagem de agentes dirigitos por tabela está sujeita ao fracasso, pois dependendo do problema essa abordagem poderá gerar tabelas enormes ao ponto de não existir dispositivo fisico que consiga armazena-las.
alem disso,o tempo para construir a tabela é muito longo e nenhum agente poderia aprender todas as entradas de tabela corretas de acordo a sua experiencia.
O tempo para aprender a tabela caso seja possivel tambem saria bastante longo.



        






