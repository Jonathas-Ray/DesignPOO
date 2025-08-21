# Esse reposiório descreve 3 ténicas dentro de POO
<style>h3{color: blue;}</style>

## Herança
### Sobre o código na pasta:
- Nos códigos dessa pasta aos comportamentos estão na classe Pai e são herdados (como em Herança), mas foram criadas
sem conteúdo na classe Pai e sendo implementados com @override nas classes filhas, tendo cada uma sua própria
implementação de cada comportamento (uma prática não escalável). Além disso, para implementar variações da clase pai
que atendessem a necessidade de novas classes filhas foi preciso criar classses intermediárias (AnimalVoa herda de 
Animal), a classe Pai termina precisando ser generalizada demais além de criar a necessidade de uma árvore de heranças 
para atender a todas as variações.
- Na Herança se agrupa comportamentos para passar para as classes filhas evitando repetição de código e ao agrupar 
esses comportamentos comuns num único lugar se facilita alterações no código até certo ponto uma vez que a 
alteração feita na classe Pai se propaga para todas as classes filhas. 

## Composição / Associação
### Sobre o código na pasta:
- Nos códigos dessa pasta, os comportamentos estão em classes separadas e são iniciados dentro de cada objeto da classe
assim que ele é criado. Se nota também que a classe Pai já não existe nesse código, provavelmente porque ela só estava 
servindo no código para passar os comportamentos para outras classes. 
- Na composição os comportamentos são vindos de outras classes e inicializados dentro da própria classe ao criar o 
objeto. Isso causa rigidez, por exemplo: ao alterar, adicionar ou remover comportamentos, todos os objetos que tiverem 
a classe que compõe esses comportamentos precisam ser alterados, são quebras espalhadas por todo o código que ao 
tentarmos consertar geram erros novos que vamos precisar identificar e corrigir.
- Um objeto iniciado ao criar outro é um acoplamento, mas pode ser (e normalmente é) excessivamente forte feito dessa
maneira.

## Injeção de Dependencia
### Sobre o código na pasta:
- Aqui foram criadas classes de comportamentos para que ao criar cada animal fosse usado objetos da classe ao invés de 
criar o comportamento dentro da classe Animal, evitando forçar todos os animais a terem todos os comportamentos numa 
herança generalizada. Também evita criar dentro de cada animal (que é repetitivo e não escalável).
- Em seguida ele não inicia os comportamentos dentro da classe, mas sim recebe os comportamentos como parâmetro e 
atribui o que recebeu dentro do construtor aos objetos internos de cada animal. Esses Comportamentos ao serem alterados
agora mudam dentro de todos os animais (escalável).
- E então quando ele transfere a responsabilidade de criar os objetos fora de cada animal ele "condena" os erros a 
acontecerem num mesmo lugar (ou em poucos lugares) e isso facilita a correção desses erros/manutenção porque passa a 
ter uma visão sistêmica da "saúde" do código ao abrir a Main.