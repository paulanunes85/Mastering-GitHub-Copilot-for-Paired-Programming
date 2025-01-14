<header>

# Usando o GitHub Copilot com Python

O GitHub Copilot é a primeira ferramenta de desenvolvedor com IA em grande escala do mundo que acelera significativamente a escrita de código, fornecendo sugestões de autocompletar enquanto você trabalha. Neste módulo, focaremos em usar o poder do GitHub Copilot para aumentar a eficiência da sua codificação em Python.

Como desenvolvedor, seu objetivo é aumentar a produtividade e acelerar os processos de codificação. O GitHub Copilot atua como seu programador em par com IA, oferecendo sugestões com base no contexto e nos padrões de código. Neste módulo, você usará o GitHub Copilot com Codespaces para gerar e implementar sugestões de código de forma eficaz.

Prepare-se para mergulhar em um cenário do mundo real! Você modificará um repositório Python usando o GitHub Copilot para criar um formulário HTML interativo e um endpoint de API. Este projeto lhe dará uma experiência valiosa no desenvolvimento de um aplicativo web Python que serve uma API HTTP, gerando tokens pseudo-aleatórios para fins de identificação.

</header>

- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Usar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos Python que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot Business ou Enterprise. Inscreva-se para Copilot Free para VS Code apenas para fim de treinamento [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este módulo pode ser concluído em menos de uma hora.

Ao final deste módulo, você adquirirá as habilidades para:

- Criar prompts para gerar sugestões do GitHub Copilot
- Aplicar o GitHub Copilot para melhorar seus projetos.

## Prerequisite reading:
- [Introduction to prompt engineering with GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Using GitHub Copilot with Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## Requirements

1. Enable your [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Open [this repository with Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 Exercise

**Right click the following Codespaces button to open your Codespace in a new tab**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

The API already has a single endpoint to generate a token. Let's update the API by adding a new endpoint that accepts text and returns a list of tokens.

### 🛠 Step 1: Add a Pydantic model

Go to the `main.py` file, navigate to the bottom of the provided code, select **Ctrl + I (PC)** or **Cmd + I (Mac)** and copy the following into the provided GitHub Copilot Chat box so that it can generate a `Pydantic` model for you: 

```
Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string.
```

The generated model should look like this:

```python
    class TextData(BaseModel):
        text: str
```

> [!NOTE]
> You might see some linter warnings in the editor (identifiable with red dotted underlines) which can be ignored. These include long lines or even new lines that aren't needed. Feel free to address them, although these shouldn't affect your application from running correctly.

### 🔎 Step 2: Generate a new endpoint

Next, generate a new endpoint with GitHub Copilot by adding the comment at the very bottom of the `main.py` file under the last route.

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text 
```

You might get a suggestion that uses a module or library that wasn't imported. If you do, you can ask GitHub Copilot to help you import the right module by selecting the generated code and using Command+I (Apple) or Control+I (Windows) and add a prompt to add the missing imports. This small pop-out is called inline chat and is another way to interact with GitHub Copilot.

### 🐍 Step 3: Explain code

The `generate()` route creates a pseudo-random token ID using a single line that might be difficult to fully understand. Select the whole function, and then right click on the selection, then select the Copilot menu item, and then the _"Explain This"_ option. The GitHub Copilot chat interface will open to the left and provide you a useful explanation which you can use to interactively ask more questions.

Finally, verify the new endpoint is working by trying it out by going to the `/docs` endpoint and confirming that the endpoint shows up.

🚀 Congratulations, through the exercise, you haven't only used Copilot to generate code but also done it in an interactive and fun way! You can use GitHub Copilot to not only generate code, but write documentation, test your applications and more.

### 💡 Step 4: Using Slash Commands

Now that you've used GitHub Copilot to generate and explain code, you can also explore some other alternative approaches to perform developer tasks. These extra challenges will help you dive deeper into other GitHub Copilot features in addition to the ones you already know. For these extra challenges, you will use the Chat interface. Click on the GitHub Copilot Chat icon on the left sidebar if you don't have it open yet.

**Generate documentation**
 
With `main.py` open, use the chat interface with the following text:

```
/docs I need to document the routes for these API Routes. Help me produce documentation I can put in the README.md file of this project
```

The `/docs` part of the prompt is called a _"slash command"_ and it is a specific feature of GitHub Copilot that allows you to write documentation. If the results look good, add them to a new section of your README.md file.


**Generate tests**
 
The current code doesn't have any tests. For this challenge, you will use the `/tests` slash command. With `main.py` open, use the chat interace with the following prompt:

```
/tests help me write a test for the generate() route using the FastAPI test client and the Pytest framework. Help me understand where I should put the test file, how to add the Pytest dependency to my project, and how to run the tests
```

The `/tests` slash command will guide you through on writing a new test for your route and give you everything you need so that you can verify your work.

**Workspace challenge**
 
Finally, you will get a chance to use an _agent_. Agents are a special feature of GitHub Copilot in Visual Studio Code that allow specific context to be shared with GitHub Copilot. For this final challenge, you will use the `@workspace` agent which includes files from the current worspace to provide more context. You will solve a problem which is related to how to run the whole application. In this case, you will enhance the README.md for more specifics that span multiple files. Using `@workspace` helps provide more context without having to open many files.

For this final challenge, you aren't required to have any open files. Use the following prompt in the GitHub Copilot Chat window:

```
@workspace I want to provide instructions on how to run this application using the uvicorn webserver, I also need to provide instructions on how to install the dependencies properly and what are some characteristics of the FastAPI framework. I will use this to improve the README.md file
```

The result should be a very good explanation on FastAPI, how to run the application, and how to get dependencies installed. A report at the very top of the response may include all the references used to determine what files it needed to use to provide the right context for GitHub Copilot.



## Avisos Legais

A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.

As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/

A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
