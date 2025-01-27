# Design Patterns e Aplicações

## Contextualização

Um código pode ser escrito de qualquer maneira e o computador irá entendê-lo, seja ele bem estruturado, dividido em pastas, com arquivos e classes organizados com padrões bem definidos, ou mesmo tudo misturado em um único arquivo com mais de 10 mil linhas. No entanto, essa flexibilidade não se aplica aos programadores. Para nós, humanos, a organização e a clareza são essenciais. Quando o código é bem estruturado, fica mais fácil identificar onde algo pode ser encontrado ou estar errado, o que agiliza a resolução de problemas. Além disso, um código organizado é crucial para manutenções futuras e refatorações, evitando que o sistema se torne um emaranhado difícil de entender e modificar.

Em muitos projetos reais, a falta de estrutura resulta em uma grande dor de cabeça. Imagine o seguinte, um desenvolvedor precisa corrigir um erro em um sistema que foi desenvolvido a 10 anos atrás, e nenhum padrão de organização foi seguido e muito menos documentado.

Não seria surpresa se não soubesse por onde começar tentando entender onde o problema está, ou até mesmo precisar abrir inúmeros arquivos ou rolar por milhares de linhas de código desordenado, o que gera um enorme desperdício de tempo e aumenta as chances de cometer erros. Isso não só afeta a eficiência do trabalho, mas também a qualidade do software.

Ou seja, um programador não programa apenas para a máquina, mas para outros programadores. A organização e a padronização do código tornam o desenvolvimento mais ágil e eficiente, porque facilitam a comunicação entre os membros da equipe. Quando o código segue um padrão bem definido, qualquer desenvolvedor, mesmo que não tenha sido responsável pela implementação original, consegue entender rapidamente o que está acontecendo e onde ele pode contribuir. Isso torna o trabalho mais colaborativo e reduz o tempo necessário para lidar com problemas ou alterações no sistema.

Vamos a seguinte situação. Cinco pessoas se reúnem para criar um projeto e cada uma escreve o código do seu próprio jeito. Veja como as classes estão sendo nomeadas:

```java
class account_user { }

class accountUser { }

class AccountUser { }

class accountuser { }

class ACCOUNTUSER { }
```

Consegue perceber algo? Não há um padrão claro de nomenclatura. Cada programador escolheu um estilo diferente, sem se preocupar com a uniformidade do código. Embora quem tenha escrito cada classe saiba o que ela faz, será que os outros membros da equipe terão a mesma facilidade para entender? A resposta, provavelmente, é não. É claro, estamos falando de códigos simples, mas o mesmo se aplica para classes com dezenas e centenas de linhas.

Quando cada desenvolvedor usa sua própria forma de escrever nomes de arquivos, pastas, classes, variáveis, dentre outros, o código se torna desorganizado e difícil de entender. Isso não apenas prejudica a compreensão de quem não escreveu o código, mas também pode causar confusão e aumentar o tempo tentando entender o trabalho dos outros. Esse tempo perdido poderia ser melhor aproveitado implementando novas funcionalidades ou corrigindo erros.

Porém, e se toda classe que for declara usar a nomenclatura PascalCase, onde a primeira letra de cada palavra é maiúscula e as demais minúsculas, sem espaços entre as palavras? Por exemplo, a classe que antes estava nomeada de qualquer forma, agora ficaria assim:

```java
class AccountUser { }
```

Ao definir um padrão como esse, a equipe garante que todos os desenvolvedores têm um ponto de partida comum para nomear e organizar o código. Não apenas melhora a legibilidade como facilita a colaboração, pois todos sabem exatamente como o código está estruturado. Além disso, a manutenção do projeto se torna muito mais simples, visto que a padronização permite que qualquer programador saiba onde procurar o que precisa no sistema, mesmo que não tenha sido o responsável pela criação.

É nesse contexto que os design patterns (padrões de projeto) entram em cena. Eles são soluções comprovadas e bem documentadas para problemas recorrentes que surgem no desenvolvimento de software. Ao aplicar esses padrões, garantimos que o código siga uma estrutura organizada e que soluções eficazes sejam reutilizadas ao longo do projeto. Com isso, os padrões tornam o código mais previsível, facilitando a localização de problemas, sem a necessidade de abrir inúmeros arquivos ou rolar por um único arquivo gigante e desorganizado. 

Eles ajudam a criar um código mais limpo, eficiente e fácil de modificar, proporcionando uma base sólida que pode ser entendida e mantida por qualquer desenvolvedor que entre no projeto.
Cada design pattern terá as suas regras e casos onde serão aplicados, não são obsolutos, a equipe ou desenvolvedor pode escolher o que melhor o atende.

## Design Patterns no Java

Os Design Patterns faram uso de recursos característicos da linguagem Java, então vamos recapitular brevemente:

- Herança: Permite a reutilização de código e a criação de novas funcionalidades sem a modificação do código original. Facilita a extensão de comportamentos através de subclasses, tornando o código mais modular e reutilizável.

- Polimorfismo: Garante flexibilidade ao possibilitar o tratamento uniforme de objetos de diferentes tipos. Esse princípio facilita a substituição de comportamentos em tempo de execução, permitindo que algoritmos ou processos sejam intercambiáveis sem modificar o código base.

- Encapsulamento: Assegura a proteção e o controle sobre os detalhes internos das classes, promovendo a modularização e ocultação da complexidade. Ao restringir o acesso aos dados internos, o encapsulamento facilita a manutenção e evita alterações inesperadas.

Por meio desses recursos, são estabelecidos padrões e regras de desenvolvimento, visando:

- Padronizar o código: Garantem que os desenvolvedores sigam práticas comuns, promovendo consistência no design e facilitando o trabalho em equipe. Isso também ajuda na comunicação entre diferentes equipes e facilita a integração de sistemas.

- Tornar o código mais flexível e escalável: A estrutura modular e a capacidade de adicionar novos comportamentos sem modificar o código existente aumentam a adaptabilidade do sistema a novas necessidades e mudanças.

- Promover a manutenção eficiente: A clareza na estrutura e a separação de responsabilidades facilitam o entendimento do sistema, tornando-o mais fácil de manter e corrigir. A utilização de **Design Patterns** minimiza o risco de erros e melhora a qualidade do código.

- Reduzir o acoplamento e aumentar a coesão: Ao aplicar Design Patterns, os sistemas se tornam mais desacoplados e as classes mais coesas. Isso significa que mudanças em um módulo terão um impacto mínimo em outros, o que facilita futuras modificações e testes.

- Facilitar a reutilização e extensibilidade: A adoção de padrões bem definidos promove a criação de componentes reutilizáveis que podem ser facilmente integrados em diferentes partes do sistema ou até mesmo em novos projetos.

### Tipos de Design Patterns no Java

1. Padrões Criacionais

Tratam da criação de objetos de forma que o sistema seja independente do processo de criação. Eles permitem flexibilizar a maneira como os objetos são criados, mantendo o código desacoplado da instância concreta desses objetos. Isso facilita a manutenção e a extensão do sistema, permitindo alterar a forma de criação de objetos sem impactar outras partes do sistema.

Singleton: garante que uma classe tenha apenas uma instância em todo o sistema e fornece um ponto de acesso global a essa instância. Isso é útil quando se quer limitar o número de instâncias de uma classe, como em situações de gerenciamento de recursos compartilhados (por exemplo, conexões de banco de dados):

```java
public class Main {
  public static void main(String[] args) {
    Singleton singleton1 = Singleton.getInstance();
    Singleton singleton2 = Singleton.getInstance();

    System.out.println(singleton1 == singleton2);
  }
}

class Singleton { 
  private static Singleton instance;

  private Singleton() {
  }

  public static Singleton getInstance() {
    if (instance == null) {
      instance = new Singleton();
    }

    return instance;
  }
}
```

Prototype: cria novos objetos clonando um objeto existente. Ao invés de criar um objeto do zero, você pode duplicar um protótipo, o que pode ser mais eficiente, especialmente quando o processo de criação é complexo ou custoso em termos de tempo e recursos.

```java
public class Main {
  public static void main(String[] args) {
    Car sedan = new Sedan();
    Car sedanClone = sedan.clone();
    sedan.drive();
    sedanClone.drive();

    Car suv = new SUV();
    Car suvClone = suv.clone();
    suv.drive();
    suvClone.drive();
  }
}

interface Car extends Cloneable {
  Car clone();

  void drive();
}

class Sedan implements Car {
  public void drive() {
    System.out.println("Driving a Sedan");
  }

  public Car clone() {
    try {
      return (Car) super.clone();
    } catch (CloneNotSupportedException e) {
      return null;
    }
  }
}

class SUV implements Car {
  public void drive() {
    System.out.println("Driving an SUV");
  }

  public Car clone() {
    try {
      return (Car) super.clone();
    } catch (CloneNotSupportedException e) {
      return null;
    }
  }
}
```

Factory Method: define uma interface para a criação de objetos, mas deixa que as subclasses decidam qual classe instanciar. Ele facilita a criação de objetos sem acoplamento direto com suas classes concretas, permitindo maior flexibilidade e extensibilidade no sistema.

Abstract Factory: permite criar famílias de objetos relacionados, sem especificar suas classes concretas. Ele oferece uma interface para criar múltiplos tipos de objetos que compartilham uma mesma base, assegurando que as combinações de objetos sejam compatíveis entre si.

Builder: separa a construção de objetos complexos da sua representação final. Ele permite criar objetos passo a passo, oferecendo uma maneira de personalizar e construir diferentes variações de um mesmo tipo de objeto sem expor o processo de criação.


2. Padrões de projeto estruturais

Os padrões estruturais explicam como montar objetos e classes em estruturas maiores mas ainda mantendo essas estruturas flexíveis e eficientes.

- Adapter: é um padrão de projeto estrutural que permite objetos com interfaces incompatíveis colaborarem entre si.

- Bridge: é um padrão de projeto estrutural que permite que você divida uma classe grande ou um conjunto de classes intimamente ligadas em duas hierarquias separadas—abstração e implementação—que podem ser desenvolvidas independentemente umas das outras.

- Composite: é um padrão de projeto estrutural que permite que você componha objetos em estruturas de árvores e então trabalhe com essas estruturas como se elas fossem objetos individuais.

- Decorator: é um padrão de projeto estrutural que permite que você acople novos comportamentos para objetos ao colocá-los dentro de invólucros de objetos que contém os comportamentos.

- Facade: é um padrão de projeto estrutural que fornece uma interface simplificada para uma biblioteca, um framework, ou qualquer conjunto complexo de classes.

- Flyweight: é um padrão de projeto estrutural que permite a você colocar mais objetos na quantidade de RAM disponível ao compartilhar partes comuns de estado entre os múltiplos objetos ao invés de manter todos os dados em cada objeto.

- Proxy: é um padrão de projeto estrutural que permite que você forneça um substituto ou um espaço reservado para outro objeto. Um proxy controla o acesso ao objeto original, permitindo que você faça algo ou antes ou depois do pedido chegar ao objeto original.


3. Padrões Comportamentais

Padrões Comportamentais lidam com a comunicação e interação entre objetos, ajudando a aumentar a flexibilidade e reduzir o acoplamento entre os componentes do sistema, tornando o código mais modular e reutilizável.

Command: Encapsula uma solicitação como um objeto, permitindo sua execução ou reversão em momentos distintos, ideal para sistemas de controle e undo.

```java
public class Main {
  public static void main(String[] args) {
    Light light = new Light();
    Command command = new LightOnCommand(light);
    command.execute();
  }
}

interface Command {
  void execute();
}

class LightOnCommand implements Command {
  private Light light;

  public LightOnCommand(Light light) {
    this.light = light;
  }

  @Override
  public void execute() {
    light.turnOn();
  }
}

class Light {
  public void turnOn() {
    System.out.println("A luz está acesa!");
  }
}
```

Iterator: Fornece uma forma de acessar os elementos de uma coleção sem expor sua implementação interna, garantindo o desacoplamento do cliente com a estrutura interna.

```java
public class Main {
  public static void main(String[] args) {
    List<Integer> collection = new ArrayList<>();
    collection.add(1);
    collection.add(2);
    collection.add(3);
    collection.add(4);
    collection.add(5);

    Iterator<Integer> iterator = collection.iterator();
    while (iterator.hasNext()) {
      System.out.println(iterator.next());
    }
  }
} 
```

Chain of Responsibility: Permite que uma solicitação seja processada por uma cadeia de objetos, sem que eles saibam qual objeto a processará, facilitando a distribuição de responsabilidades

Observer: Define uma dependência entre objetos, notificando automaticamente todos os dependentes quando um objeto muda de estado, útil em sistemas de eventos e interfaces gráficas

Strategy: Define uma família de algoritmos, permitindo que um deles seja selecionado em tempo de execução, proporcionando flexibilidade em sistemas que requerem diferentes comportamentos


# Referência:
- https://refactoring.guru/pt-br/design-patterns
