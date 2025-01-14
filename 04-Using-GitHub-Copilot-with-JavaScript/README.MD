<header>

# Usando o GitHub Copilot com JavaScript

Neste módulo, continuaremos a explorar as capacidades do GitHub Copilot e aprenderemos como usá-lo para melhorar sua experiência de codificação. Imagine escrever código mais rápido e com menos esforço—o GitHub Copilot torna isso uma realidade ao gerar sugestões com base no contexto de seus comentários e código.

Como um desenvolvedor em busca de maior produtividade, você embarcará em uma jornada para dominar as capacidades do GitHub Copilot, focando em sua aplicação no JavaScript. Ao final do módulo, você ganhará experiência em criar prompts que geram sugestões valiosas usando a extensão do GitHub Copilot no Visual Studio Code. Eleve suas habilidades de codificação ao usar o GitHub Copilot para aprimorar um projeto JavaScript, experimentando em primeira mão como este programador em par com IA oferece sugestões de autocompletar, transformando seu fluxo de trabalho de desenvolvimento.

Ao dominar o GitHub Copilot, você não apenas configurará repositórios no Codespaces, mas também utilizará eficientemente esta ferramenta de IA para melhorar seus projetos de codificação. Prepare-se para revolucionar sua experiência de codificação e aumentar sua produtividade nesta dinâmica aventura de aprendizado!

</header>


- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Usar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos JavaScript que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot. Inscreva-se para 30 dias gratuitos An external link was removed to protect your privacy..
- **Tempo:** Este módulo pode ser concluído em menos de uma hora.


Ao final deste módulo, você adquirirá as habilidades para:

- Criar prompts para gerar sugestões do GitHub Copilot
- Aplicar o GitHub Copilot para melhorar seus projetos.


## PLeitura pré-requisito:
- [Introdução a engenharia de prompt com GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Usando GitHub Copilot com JavaScript](https://learn.microsoft.com/training/modules/introduction-copilot-javascript/?WT.mc_id=academic-113596-abartolo)


## Requisitos

1. Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Abrir [este repositório com Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-javascript?quickstart=1)



## 💪🏽 Exercise

**Right click the following Codespaces button to open your Codespace in a new tab**

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main&repo=526682619)

In this template portfolio, we have a React based web application ready for you to easily customize and deploy using only your web browser.

**Note:** Please disreguard the instructions given within the GitHub Codespace. For theis labs, be sure to follow the intructions found here.


### 🛠 Step 1: Customize the web app

Customize the portfolio with your own links. Go to `src/App.jsx` and update the `siteProps` with your information. The `siteProps` variable is a JavaScript object that holds key value pairs used to customize the site, it should look like this:

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
### 📖 Step 2: Explain the code

Now lets use the slash command to explain what a portion of the code does.  Highlight the following code:

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
Once highlighted, hit Ctrl + I (Windows) or Cmd + I (Mac) and enter **/explain**.  You should receive a response in the Copilot Chat window similar to this:

```
This JavaScript code is written in React, a popular library for building user interfaces. The code defines a functional component named App. The App component is the root component of your application. It's where all other components (Header, Home, About, Portfolio, Footer) are being called and rendered. The App component returns a JSX (JavaScript XML) structure, which looks similar to HTML. This JSX structure defines what the App component should render on the screen. In the JSX, there is a div with an id of "main". Inside this div, several components are being rendered: Header, Home, About, Portfolio, and Footer. The Home component is being passed two props: name and title, both of which are properties of the siteProps object. The Footer component is being passed several props. The ...siteProps syntax is using the JavaScript spread operator to pass all properties of siteProps as separate props. In addition to the siteProps, two more props are being passed: primaryColor and secondaryColor. These are defined as constants at the top of the file. Remember, props (short for properties) in React are how components talk to each other. If you think of components as functions, then props are the arguments to these functions. They are passed from the parent component (in this case, App) to the child components (Header, Home, About, Portfolio, Footer).
```

Lets dive a little deeper.  Notice how Copilot Chat now provides a follow up question suggestion for you to ask. Click on the question suggested by GitHub Copilot found at the bottom of the window usually starting with "What is the purpose..." and review the answer provided. As an example, should the question GitHub Copilot provide be the following:

What is the purpose of using props in React components? 

You should get an answer similar to this:

```
Props (short for properties) in React are used for passing data from one component to another, just like function arguments. They are read-only and help to make components reusable and dynamic. In your code, for example, the Home component is passed name and title as props. This means that the Home component can use these values to display dynamic content. The Footer component is also passed several props, including all properties of siteProps and the primaryColor and secondaryColor constants. Here's an analogy: think of a component as a custom HTML element and props as the attributes of that element. Just like you can pass different attributes to an HTML element (like <img src="image.jpg" alt="An image">), you can pass different props to a React component (like <Home name="John" title="Developer" />). This makes your components more flexible and reusable. For instance, you could use the same Home component with different props to display different content.
```

Did you notice after you clicked the suggested question in the Copilot Chat windows, it used a command similar to the following to ask the question:

```
@workspace /explain What is the purpose of using props in React components?
```

The @workspace agent, like Copilot, fills in missing details, helping when humans overlook or don't fully describe everything they see. When prompted, Copilot takes a different approach. Instead of immediately responding, it first examines the files and folders in the workspace in steps:

1. It checks the names of files/folders to see which could be relevant.
2. It reads the contents of files, sometimes in full, sometimes partially due to memory limits.
3. It creates context from the collected information.
4. It responds, using both the prompt's context and the information it gathered.


### 🔎 Step 3: Animate the social media icons with a prompt

An animation can make the social media section more eye-catching. Ask Copilot’s help to animate the icons. Jump to the end of the file and write the following prompt in the `src/styles.css` file:

```css
/* add an amazing animation to the social icons */
```

The suggestion from Copilot should look similar to the following:

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

### 🚀 Step 4: Find out how to run the app
Open GitHub Copilot chat by clicking on the chat icon on the left side bar and use the input section to ask the following:

```
@workspace I want to understand how can I run this React application
```

The prompts uses `@workspace` which is a special feature of GitHub Copilot chat that allows you to include more context for a more complete answer. Try out other queries using the chat panel for a more interactive workflow.

### Conclusion
Your site should already be running in your Codespace, and the change will reload onto the page automatically. To see them, hover over one of your social media icons in the footer to see the magic!

**Note:** Refresh the Codespace browser window if the hover effects do not work. 

Congratulations, through the exercise, you have use GitHub Copilot to generate code and also done it in an interactive and fun way! You can use GitHub Copilot to not only generate code, but write documentation, test your applications and more.
