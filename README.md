<img style="display:block;margin:auto;" src="cover2.jpg">

##Tradução do livro "The Principles of Object-Oriented Javascript"

### Notas

Embora este seja um livro comercial, é sabido que este livro nunca chegará nas terras Tupiniquins.
Por esse motivo, decidi traduzir esse livro, que será de enorme ajuda a todos os estudantes de javascript, ja que esse livro aborda o conteúdo mais importante da linguagem.

Vale notar que o padrão ECMAScript 6 substitui o metódo de prototipação pelo uso da palavra-chave "class", já conhecida de outras linguagens, mas ,por enquanto, isso está longe de ser implementado e entender como a prototipação funciona no JavaScript ainda é muito importante.


# Introdução

Muitos desenvolvedores associam programação orientada a objetos com linguagens que são tipicamente ensinadas nas escolas, como C++ e Java, que possuem a orientação a objetos baseada em classes. Antes que você possa fazer qualquer coisa nessas linguagens, você precisa criar uma classe, mesmo que você esteja apenas escrevendo um programa simples na tela de comando.

Os padrões de design da indústria da programação reenforçarão o conceito baseado em classes. Mas JavaScript não usa classes, e esse é um dos principais motivos pelo qual as pessoas ficam confusas quando tentam aprender JavaScript depois de C++ ou Java.

Linguagens orientadas a objetos possuem algumas caracteristicas:

*Encapsulamento :* Dados podem ser agrupados juntos com funcionalidades que operam direto nesses dados. Essa é, basicamente, a definição de um Objeto.

*Agregação :* Um objeto pode referenciar outro objeto.

*Herança :* Um objeto recém-criado possui as mesmas características que outro objeto sem duplicar as mesmas funcionalidades explicitamente.

*Polimorfismo :* Uma interface pode ser implementada por multiplos objetos.

JavaScript possue todas essas características, mas como a linguagem não possue o conceito de classes, algumas dessas características não são implementadas da maneira que você imaginaria. A um primeiro olhar, um programa em JavaScript pode até parecer como a programação procedural que você escreveria em C. Se você pode escrever uma função e passar para ela algumas variáveis, você irá ter um script funcional que aparamentemente não possui objetos. Um olhar mais profundo na linguagem, no entanto, revela a existência de objetos através do uso da notação do ponto (.).

Muitas linguagens orientadas a objetos usam a notação do ponto para acessar propriedades e metódos em objetos, e com JavaScript é sintaticamente o mesmo. Mas em JavaScript, você nunca irá precisar criar uma definição de classe, importar um pacote, ou incluir um arquivo de cabeçalho. Você apenas começar a escrever com os tipos de dados que você quer, e você pode agrupá-los de várias maneiras. Você pode certamente escrever um programa em JavaScript de um modo procedural, mas o verdadeiro poder da linguagem aparece quando você utiliza as vantagens de sua natural orientação a objetos. Esse é o assunto desse livro.

Não se engane: Muitos conceitos que você pode ter aprendido em linguagens orientadas a objetos mais tradicionais não se aplicam necessáriamente em JavaScript. Enquanto muito desses conceitos confudem iniciantes, enquanto você lê, você irá descobrir que a natureza de tipagem fraca de JavaScript permite a você escrever menos código para realizar as mesmas tarefas que você escreveria com mais código em outras linguagens. Você pode simplesmente começar a escrever código sem planejar as classes que você precisa antes de começar. Precisa de um objeto com propriedades específicas? Simplesmente crie um objeto para isso onde você quiser. Você esqueceu de adicionar um método em um objeto? Sem problemas - apenas adicione depois.

Nesse livro, você aprenderá a forma única com que JavaScript lida com a orientação a objetos. Deixe para trás as noções de classes e herança baseada em classes e aprenda sobre a herança baseada em protótipos e construtores de funções que se comportam semelhantemente. Você aprenderá como criar objetos, definir seus próprios tipos, usar herança, e aproveitar as vantagens do uso de objetos ao máximo. Resumindo, você aprenderá tudo que você precisa saber para entender e escrever JavaScript de forma profissional. Divirta-se!

## Público desse livro

O propósito desse livro é ser um guia para aqueles que ja entendem programação orientada a objetos mas desejam saber como isso funciona exatamente em JavaScript. Familiaridade com Java, C#, ou programação orientada a objetos em outras linguagens são um indicador forte de que esse livro é para você.

Em particular, esse livro é feito para 3 grupos de leitores:

- Desenvolvedores que possuem familiaridade com os conceitos de programação orientada a objetos e desejam aplicar eles ao JavaScript
- Desenvolvedores Node.js que desejam estruturar seu código mais eficientemente
- Iniciantes em JavaScript que desejam um conhecimento mais profundo da linguagem

Esse não é um livro para iniciantes que nunca escreveram uma linha de JavaScript. Você precisa de um bom conhecimento sobre como escrever e executar códigos JavaScript para prosseguir com o livro.

## Organização

**Capítulo 1: Tipos primitivos e de referência** oferece uma introdução sobre os dois tipos de valores em JavaScript: primitivos e de referência. Você irá aprender como eles se diferenciam e como entender suas diferenças é importante para um conhecimento geral de JavaScript.

**Capítulo 2: Funções** explica os prós e contras de funções em JavaScript. Funções de primeira classe são o que deixam JavaScript interessante.

**Capítulo 3: Entendendo Objetos** detalha a criação de objetos em JavaScript. Objetos em JavaScript se comportam diferente de objetos em outras linguagens, então um conhecimento profundo sobre como objetos funcionam é vital pra dominar a linguagem.

**Capítulo 4: Construtores e Protótipos** expande a discussão sobre funções olhando mais especificamente nos construtores. Todos os construtores são funções, mas eles são usados de forma diferente. Esse capítulo explora essas diferenças ao mesmo tempo que fala sobre como criar seus próprios tipos.

**Capítulo 5: Herança** explica como a herança é feita em JavaScript. Embora JavaScript não possua classes, isso não significa que a herança seja impossível. Nesse capítulo, você aprenderá sobre herança prototípica e como ela difere da herança baseada em classes.

**Capítulo 6: Padrões de Objetos** discorre sobre padrões comuns de objetos. Há muitas maneiras de criar e compor objetos em JavaScript, e esse capítulo introduz você aos padrões mais populares para fazer isso.

# Capítulo 1: Tipos primitivos e de Referência

Muitos desenvolvedores aprenderem orientação a objetos trabalhando com linguagens baseadas em classes, como Java ou C#. Quando esses desenvolvedores começam a aprender JavaScript, eles ficam desorientados porquê JavaScript não possui um suporte formal para classes. Em vez de definir as classes desde o começo, com JavaScript você apenas cria as estruturas de dados a medida que você precisa delas. Como não há classes, em JavaScript também falta agrupamento de classes, comumente chamados de "pacotes (packages)". Onde em linguagens como Java, pacotes e nomes de classes definem ambos o tipo de objeto e o layout dos arquivos e pastas em seu projeto, programar em JavaScript é como começar com uma folha em branco: Você pode organizar as coisas do jeito que você quiser. Alguns desenvolvedores escolhem por copiar estruturas de outras linguagens, enquanto outros aproveitam a flexibilidade do JavaScript para estruturar de um jeito completamente novo. Para os iniciantes, essa flexibilidade pode ser confusa, mas uma vez que você se acostuma, você verá que JavaScript possui uma flexibilidade que se adapta as suas preferências facilmente.

Para facilitar a transição de linguagens orientadas a objetos tradicionais, em JavaScript os objetos são a parte central da linguagem. Quase todos os dados em JavaScript são ou um objeto ou são acessados através deles. De fato, até funções (em que linguagens tradicionalmente fazem você perder a cabeça para achar referências) são representadas como objetos em JavaScript, o que fazem delas *funções de primeira-classe*.

Trabalhando com objetos e os entender é a chave para entender JavaScript como um todo. Você pode criar objetos a qualquer hora e adicionar ou remover propriedades deles quando quiser. Pra melhorar, objetos JavaScript são extremamente flexiveis e possuem capacidades que criam únicos e interessantes padrões que simplesmente não são possíveis em outras linguagens.

Esse capítulo foca em como identificar e trabalhar com os 2 tipos de dados primários em JavaScript: dados primitivos e dados de referência. Embora ambos são acessados através de objetos, eles se comportam de maneira que fazem com que sejam importante entende-los.

## O que são tipos?

Embora JavaScript não possua o conceito de classes, ele utiliza dois tipos: primitivos e referências. *Tipos primitivos* são armazenados como simples tipos de dados. *Tipos de referência* são armazenados como objetos, que são realmente apenas referências para lugares da memória.

O truque é que JavaScript deixa você tratar tipos primitivos como tipos de referência para fazer com que a linguagem seja mais consistente para o desenvolvedor. Enquanto outras linguagens de programação distinguem entre tipos primitivos e de referência armazenando primitivos em stack e referencia no heap, JavaScript some completamente com esse conceito: Ele procura variáveis para um escopo particular com um **objeto variável**. Valores primitivos são armazenados diretamente no objeto variável, que servem de referência para um lugar na memória onde o objeto está armazenado. No entanto, como você verá mais tarde nesse capítulo, tipos primitivos e de referência se comportam um pouco diferente embora eles possam inicializar da mesma maneira. Claro, ainda há outras diferenças entre tipos primitivos e de referência.
