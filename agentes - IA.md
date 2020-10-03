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

