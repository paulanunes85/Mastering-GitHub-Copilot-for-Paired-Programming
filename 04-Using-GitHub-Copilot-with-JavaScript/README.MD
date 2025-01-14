<header>

# Usando o GitHub Copilot com JavaScript

Neste módulo, continuaremos a explorar as capacidades do GitHub Copilot e aprenderemos como usá-lo para melhorar sua experiência de codificação. Imagine escrever código mais rápido e com menos esforço—o GitHub Copilot torna isso uma realidade ao gerar sugestões com base no contexto de seus comentários e código.

Como um desenvolvedor em busca de maior produtividade, você embarcará em uma jornada para dominar as capacidades do GitHub Copilot, focando em sua aplicação no JavaScript. Ao final do módulo, você ganhará experiência em criar prompts que geram sugestões valiosas usando a extensão do GitHub Copilot no Visual Studio Code. Eleve suas habilidades de codificação ao usar o GitHub Copilot para aprimorar um projeto JavaScript, experimentando em primeira mão como este programador em par com IA oferece sugestões de autocompletar, transformando seu fluxo de trabalho de desenvolvimento.

Ao dominar o GitHub Copilot, você não apenas configurará repositórios no Codespaces, mas também utilizará eficientemente esta ferramenta de IA para melhorar seus projetos de codificação. Prepare-se para revolucionar sua experiência de codificação e aumentar sua produtividade nesta dinâmica aventura de aprendizado!

</header>


- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Usar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos JavaScript que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot Business ou Enterprise. Inscreva-se para Copilot Free para VS Code apenas para fim de treinamento [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este módulo pode ser concluído em menos de uma hora.


Ao final deste módulo, você adquirirá as habilidades para:

- Criar prompts para gerar sugestões do GitHub Copilot
- Aplicar o GitHub Copilot para melhorar seus projetos.


## Leitura pré-requisito:
- [Introdução a engenharia de prompt com GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Usando GitHub Copilot com JavaScript](https://learn.microsoft.com/training/modules/introduction-copilot-javascript/?WT.mc_id=academic-113596-abartolo)


## Requisitos

1. Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Abrir [este repositório com Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-javascript?quickstart=1)



## 💪🏽 Exercício

**Clique com o botão direito no botão Codespaces a seguir para abrir seu Codespace em uma nova aba**

[![Abrir GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=526682619)

Neste portfólio de modelo, temos um aplicativo web baseado em React pronto para você personalizar e implantar facilmente usando apenas seu navegador da web.

**Nota:** Por favor, desconsidere as instruções fornecidas dentro do GitHub Codespace. Para estes laboratórios, certifique-se de seguir as instruções encontradas aqui.


### 🛠 Passo 1: Personalize o aplicativo web

Personalize o portfólio com seus próprios links. Vá para src/App.jsx e atualize o siteProps com suas informações. A variável siteProps é um objeto JavaScript que contém pares de chave e valor usados para personalizar o site, deve parecer com isso:

```javascript
const siteProps = {
  name: "Alexandrie Grenier",
  title: "Web Designer & Content Creator",
  email: "alex@example.com",
  gitHub: "microsoft",
  instagram: "microsoft",
  linkedIn: "satyanadella",
  medium: "",
  twitter: "microsoft",
  youTube: "Code",
};
```
### 📖 Passo 2: Explique o código

Agora vamos usar o comando de barra para explicar o que uma parte do código faz. Destaque o seguinte código:

```javascript
};

const primaryColor = "#4E567E";
const secondaryColor = "#D2F1E4";

const App = () => {
  return (
    <div id="main">
      <Header />
      <Home name={siteProps.name} title={siteProps.title} />
      <About />
      <Portfolio />
      <Footer {...siteProps} primaryColor={primaryColor} secondaryColor={secondaryColor} />
    </div>
  );
};
```
Uma vez destacado, pressione Ctrl + I (Windows) ou Cmd + I (Mac) e digite /explain. Você deve receber uma resposta na janela do Copilot Chat semelhante a esta:

```
This JavaScript code is written in React, a popular library for building user interfaces. The code defines a functional component named App. The App component is the root component of your application. It's where all other components (Header, Home, About, Portfolio, Footer) are being called and rendered. The App component returns a JSX (JavaScript XML) structure, which looks similar to HTML. This JSX structure defines what the App component should render on the screen. In the JSX, there is a div with an id of "main". Inside this div, several components are being rendered: Header, Home, About, Portfolio, and Footer. The Home component is being passed two props: name and title, both of which are properties of the siteProps object. The Footer component is being passed several props. The ...siteProps syntax is using the JavaScript spread operator to pass all properties of siteProps as separate props. In addition to the siteProps, two more props are being passed: primaryColor and secondaryColor. These are defined as constants at the top of the file. Remember, props (short for properties) in React are how components talk to each other. If you think of components as functions, then props are the arguments to these functions. They are passed from the parent component (in this case, App) to the child components (Header, Home, About, Portfolio, Footer).
```
```
Este código JavaScript é escrito em React, uma biblioteca popular para construir interfaces de usuário. O código define um componente funcional chamado App. O componente App é o componente raiz da sua aplicação. É onde todos os outros componentes (Header, Home, About, Portfolio, Footer) são chamados e renderizados. O componente App retorna uma estrutura JSX (JavaScript XML), que se parece com HTML. Esta estrutura JSX define o que o componente App deve renderizar na tela. No JSX, há uma div com um id de "main". Dentro desta div, vários componentes estão sendo renderizados: Header, Home, About, Portfolio e Footer. O componente Home está recebendo dois props: name e title, ambos são propriedades do objeto siteProps. O componente Footer está recebendo vários props. A sintaxe ...siteProps está usando o operador spread do JavaScript para passar todas as propriedades de siteProps como props separadas. Além de siteProps, mais dois props estão sendo passados: primaryColor e secondaryColor. Estes são definidos como constantes no topo do arquivo. Lembre-se, props (abreviação de propriedades) em React são como os componentes se comunicam entre si. Se você pensar nos componentes como funções, então props são os argumentos dessas funções. Eles são passados do componente pai (neste caso, App) para os componentes filhos (Header, Home, About, Portfolio, Footer).
```

Vamos nos aprofundar um pouco mais. Observe como o Copilot Chat agora fornece uma sugestão de pergunta de acompanhamento para você fazer. Clique na pergunta sugerida pelo GitHub Copilot encontrada na parte inferior da janela, geralmente começando com "Qual é o propósito..." e revise a resposta fornecida. Por exemplo, se a pergunta sugerida pelo GitHub Copilot for a seguinte:

Qual é o propósito de usar props em componentes React?

Você deve obter uma resposta semelhante a esta:

```
Props (short for properties) in React are used for passing data from one component to another, just like function arguments. They are read-only and help to make components reusable and dynamic. In your code, for example, the Home component is passed name and title as props. This means that the Home component can use these values to display dynamic content. The Footer component is also passed several props, including all properties of siteProps and the primaryColor and secondaryColor constants. Here's an analogy: think of a component as a custom HTML element and props as the attributes of that element. Just like you can pass different attributes to an HTML element (like <img src="image.jpg" alt="An image">), you can pass different props to a React component (like <Home name="John" title="Developer" />). This makes your components more flexible and reusable. For instance, you could use the same Home component with different props to display different content.
```
```
Props (abreviação de propriedades) em React são usados para passar dados de um componente para outro, assim como argumentos de função. Eles são somente leitura e ajudam a tornar os componentes reutilizáveis e dinâmicos. No seu código, por exemplo, o componente Home recebe name e title como props. Isso significa que o componente Home pode usar esses valores para exibir conteúdo dinâmico. O componente Footer também recebe vários props, incluindo todas as propriedades de siteProps e as constantes primaryColor e secondaryColor. Aqui está uma analogia: pense em um componente como um elemento HTML personalizado e props como os atributos desse elemento. Assim como você pode passar diferentes atributos para um elemento HTML (como <img src="image.jpg" alt="Uma imagem">), você pode passar diferentes props para um componente React (como <Home name="John" title="Developer" />). Isso torna seus componentes mais flexíveis e reutilizáveis. Por exemplo, você poderia usar o mesmo componente Home com diferentes props para exibir diferentes conteúdos.
```

Você notou que depois de clicar na pergunta sugerida na janela do Copilot Chat, ele usou um comando semelhante ao seguinte para fazer a pergunta:

```
@workspace /explain Qual é o propósito de usar props em componentes React?
```

O agente @workspace, como o Copilot, preenche detalhes ausentes, ajudando quando os humanos negligenciam ou não descrevem completamente tudo o que veem. Quando solicitado, o Copilot adota uma abordagem diferente. Em vez de responder imediatamente, ele primeiro examina os arquivos e pastas no workspace em etapas:

1. Ele verifica os nomes dos arquivos/pastas para ver quais podem ser relevantes.
2. Ele lê o conteúdo dos arquivos, às vezes na íntegra, às vezes parcialmente devido a limites de memória.
3. Ele cria contexto a partir das informações coletadas.
4. Ele responde, usando tanto o contexto do prompt quanto as informações que reuniu.


### 🔎 Passo 3: Animar os ícones de mídia social com um prompt

Uma animação pode tornar a seção de mídia social mais atraente. Peça ajuda ao Copilot para animar os ícones. Vá até o final do arquivo e escreva o seguinte prompt no arquivo src/styles.css :

```css
/* add an amazing animation to the social icons */
```
```css
/* adicione uma animação incrível aos ícones sociais */
```

A sugestão do Copilot deve ser semelhante ao seguinte:

```css
img.socialIcon:hover {
  animation: bounce 0.5s;
  animation-iteration-count: infinite;
}

@keyframes bounce {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.2);
  }
  100% {
    transform: scale(1);
  }
}
```

### 🚀  Passo 4: Descubra como executar o aplicativo

Abra o chat do GitHub Copilot clicando no ícone de chat na barra lateral esquerda e use a seção de entrada para perguntar o seguinte:

```
@workspace Eu quero entender como posso executar este aplicativo React
```

Os prompts usam '@workspace', que é um recurso especial do chat do GitHub Copilot que permite incluir mais contexto para uma resposta mais completa. Experimente outras consultas usando o painel de chat para um fluxo de trabalho mais interativo.

### Conclusão

Seu site já deve estar em execução no seu Codespace, e a alteração será recarregada automaticamente na página. Para vê-las, passe o mouse sobre um dos seus ícones de mídia social no rodapé para ver a mágica!

**Nota:** Atualize a janela do navegador do Codespace se os efeitos de hover não funcionarem.

Parabéns, através do exercício, você usou o GitHub Copilot para gerar código e também fez isso de uma maneira interativa e divertida! Você pode usar o GitHub Copilot não apenas para gerar código, mas também para escrever documentação, testar suas aplicações e muito mais.
