# 01 - Introdução ao Javascript e ao GIT

## O que é Javascript?
[JavaScript](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript) (abreviado como "JS") é uma linguagem de programação dinâmica cheia de recursos que quando aplicada em um documento HTML que pode fornecer interatividade dinâmica em sites.

- https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Guide

### HTML
Um documento HTML é um documento de texto simples estruturado com elementos. Elementos são acompanhados de abertura e fechamento de tags. Cada tag começa e termina com colchetes angulares (`<>`). Existem algumas tags vazias ou sem conteúdo que não podem incluir qualquer texto, como por exemplo a tag `<img>`.

``` html
<html>
    <head></head>
    <body></body>
</html>
```

Para utilizarmos scripts no [HTML (HyperText Markup Language)](https://developer.mozilla.org/pt-BR/docs/Web/HTML), precisamos primeiramente incluir uma chamada de um arquivo Javascript e colocar o código nela. A tag `script` pode ser inserida dentro da tag `head`, porém por questões de performance, é aconselhável inserí-la no final do `body`.

``` html
<html>
    <head></head>
    <body>
        <main></main>
        <script src="./script.js"></script>
    </body>
</html>
```

``` javascript
document.getElementsByTagName('body')[0].innerHTML = "Hello World"
```

- https://developer.mozilla.org/pt-BR/docs/Glossario/HTML
- https://developer.mozilla.org/pt-BR/docs/HTML/Introduction
- https://developer.mozilla.org/pt-BR/docs/Web/HTML/Element

### O `document`
Para cada página carregada no browser, existe um objeto Document. A interface Document serve como um ponto de entrada para o conteúdo da Página (a árvore DOM, incluindo elementos como `<body>` e `<table>`) e provê funcionalidades globais ao documento (como obter a URL da página e criar novos elementos no documento).

`document.getElementById`

`document.querySelector`

`document.addEventListener`

https://developer.mozilla.org/pt-BR/docs/Web/API/Document

### A `window`
O objeto window representa uma janela que contém um elemento [DOM (Document Object Model)](https://developer.mozilla.org/pt-BR/docs/DOM/Referencia_do_DOM); a propriedade document aponta para o documento DOM document carregado naquela janela. Uma janela para um dado documento pode ser obtido usando a propriedade document.defaultView.

`window.console`

`window.document`

`window.location`

https://developer.mozilla.org/pt-BR/docs/Web/API/Window

## GIT
Git é um sistema de controle de versão de arquivos. Através deles podemos desenvolver projetos na qual diversas pessoas podem contribuir simultaneamente no mesmo, editando e criando novos arquivos e permitindo que os mesmos possam existir sem o risco de suas alterações serem sobrescritas.

Se não houver um sistema de versão, imagine o caos entre duas pessoas abrindo o mesmo arquivo ao mesmo tempo. Uma das aplicações do git é justamente essa, permitir que um arquivo possa ser editado ao mesmo tempo por pessoas diferentes. Por mais complexo que isso seja, ele tenta manter tudo em ordem para evitar problemas para nós desenvolvedores.

Para usar o Git, basta baixá-lo aqui: https://git-scm.com/downloads

### Commit
Antes de falarmos de commits, precisamos falar fo `git add`: Este comando adiciona o(s) arquivo(s) em um lugar que chamamos de INDEX, que funciona como uma área do git no qual os arquivos possam ser enviados ao reposiório. É importante saber que ADD não está adicionando um arquivo novo ao repositório, mas sim dizendo que o arquivo (sendo novo ou não) está sendo preparado para entrar na próxima revisão do repositório.
EX: 
- `git add .`: Adiciona todos os arquivos.
- `git add "index.html"`: Adiciona somente o arquivo desejado.

Agora vamos ao `commit`:

Este comando realiza o que chamamos de “commit”, que significa pegar todos os arquivos que estão naquele lugar INDEX que o comando `add` adicionou e criar uma revisão com um número e um comentário, que será vista por todos.
Ex: `git commit -m "comentário qualquer"`

### Push
Além disso, temos o `git push`: Push (empurrar) é usado para publicar todos os seus commits para o repositório. Neste momento poderá ser solicitado a sua senha:
Ex: `git push origin master`

Extra: `git status` exibe o status do seu repositório atual.

### Branchs
Suponha que o seu projeto seja um site html, e você deseja criar uma nova seção no seu código HTML, mas naquele momento você não deseja que estas alterações estejam disponíveis para mais ninguém, só para você. Isso é, você quer alterar o projeto (incluindo vários arquivos nele), mas ainda não quer que isso seja tratado como “oficial” para outras pessoas, então você cria um branch (como se fosse uma cópia espelho) e então trabalha apenas nesse branch, até acertar todos os detalhes dele.

No git, o conceito de branch é algo muito simples e fácil de usar. Mas quando que temos que criar um branch? Imagine que o seu site está pronto, tudo funcionando perfeitamente, mas surge a necessidade de alterar algumas partes dele como forma de melhorá-lo. Além disso, você precisa manter estas alterações tanto no computador de casa quanto do trabalho. Com isso temos um problema, se você começa a alterar os arquivos em casa, para na metade da implementação, e precisa terminar no trabalho, como você iria comitar tudo pela metade e deixar o site incompleto?

Para isso existe o conceito de branch, que é justamente ramificar o seu projeto em 2, como se cada um deles fosse um repositório, e depois juntá-lo novamente.

Use o seguinte comando de terminal para criar um branch:

`git checkout -b 'hotfix'`, onde hotfix é nome da branch nova.

Mudar de branch:

`git checkout master`, onde master é o nome da branch já existente.


### MRs
Os MRs (Merge requests) permitem que você troque as alterações feitas no código-fonte e colabore com outras pessoas no mesmo projeto.

Um MR é a base do GitLab como plataforma de colaboração de código e controle de versão. É tão simples quanto o nome implica: um pedido para mesclar(`merge`) um `branch` em outro.

Com os MRs do GitLab, você pode:

- Compare as mudanças entre duas branches.
- Revisar e discutir as modificações propostas em linha.
- Live preview das alterações.
- Impedir que o MR seja mesclado antes de estar pronta com os WIP MRs.
- Resolver conflitos de mesclagem da interface do usuário.
- Solicitar aprovações.
- Etc.

#### Docs:
- https://git-scm.com/
- https://tableless.com.br/tudo-que-voce-queria-saber-sobre-git-e-github-mas-tinha-vergonha-de-perguntar/
- https://docs.gitlab.com/ee/user/project/merge_requests/

## Treinamento GIT
- https://learngitbranching.js.org/

## Desafio
O desafio será criar um arquivo HTML **COM O BODY VAZIO**, ou alguma tag vazia dentro `body` como a tag `main`, e inserir 10 formas diferentes do texto "Hello World". Pode ser invertido, de cabeça para baixo, de trás para a frente e etc. Tentem utilizar mais JavaScript do que CSS, a preferência será o JavaScript.

- De um [Fork](https://docs.gitlab.com/ee/gitlab-basics/fork-project.html) no repositório: [01 - Introdução ao Javascript e Git](https://gitlab.com/acct.fateclab/dev-turma-1-sem-2021/01-introducao-ao-javascript-e-git);
- Agora você deve clonar o repositório localmente, há um botão azul "Clone" no seu repositório do GitLab, clique nele e use a URL com **HTTPS**. 
- Agora localmente abra uma pasta e use o botão direito do Mouse para abrir o "Git Bash", com esse atalho você chegará na pasta que quer mais rapidamente pelo terminal.
- Use o comando `git clone url-copiada-do-gitlab` para que a estrutura de pastas do repositório seja clonada na sua pasta
- Crie uma pasta `desafio` e coonclua o enunciado acima com os tópicos visto em aula;
- **Faça [commits](https://git-scm.com/docs/git-commit) para cada forma diferente de exibição do texto;**
- Assim que terminar dê Push:
    - Para o primeiro push: `git push -u origin nome-da-sua-branch`
    - Para os demais: `git push`
- Crie um Merge Request na interface do GitLab, acesse o menu "Merge Requests" e crie um, configure o "Target Branch" para o repositório original para que seu App seja avaliado e revisado e para que possamos te dar um feedback.
- **O nome do Merge Request deve ser o seu nome completo.**

Para se destacar na execução:
- Crie uma branch `seu-nome/introducao-ao-javascript` no seu repositório;
- Personalize a página com CSS;

Veja alguns métódos para arrays e loops que pode ajudar:

- [for](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for)
- [for of](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/for...of)
- [while](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/while)
- [do while](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Statements/do...while)
- [forEach](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/forEach)
- [map](https://developer.mozilla.org/pt-BR/docs/Web/JavaScript/Reference/Global_Objects/Array/map)

[Exemplo](https://gitlab.com/acct.fateclab/turma-1-sem-2019/01-introducao-ao-react/uploads/e6c97069b69eda9443f205ddae7f9fcc/exemplo.PNG)
