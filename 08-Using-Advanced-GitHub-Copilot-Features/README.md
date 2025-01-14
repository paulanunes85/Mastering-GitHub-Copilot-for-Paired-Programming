<header>

# Usando Recursos Avançados do GitHub Copilot

O GitHub Copilot oferece mais do que apenas sugestões de código. Como Engenheiro de Software, você frequentemente se encontrará tentando entender o código existente e aprimorá-lo com documentação, testes e automação.

Neste módulo, você usará os recursos avançados do GitHub Copilot que permitirão trabalhar interativamente com seu código e aplicar sugestões e conhecimentos de forma eficiente.

Você usará uma API HTTP existente baseada em Python para fazer alterações, correções de bugs, documentação e testes para um novo endpoint que você implementará.

</header>

- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Usar recursos avançados do GitHub Copilot para testar, documentar e trabalhar com código.
- **O que você construirá:** Uma nova rota de API HTTP, juntamente com documentação e testes para verificar sua correção.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot Business ou Enterprise. Inscreva-se para Copilot Free para VS Code apenas para fim de treinamento [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este módulo pode ser concluído em menos de uma hora.

Ao final deste módulo, você adquirirá as habilidades para:

- Usar recursos avançados do GitHub Copilot, como chat inline, comandos de barra e agentes.
- Interagir com o GitHub Copilot com um contexto mais profundo sobre seu projeto e fazer perguntas sobre ele.

## Prerequisite reading:
- [Introduction to prompt engineering with GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Using advanced GitHub Copilot features](https://learn.microsoft.com/training/modules/advanced-github-copilot/?WT.mc_id=academic-113596-abartolo)

## Requirements

1. Enable your [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Open [this repository with Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-advanced-copilot)

## 💪🏽 Exercise

**Right click the following Codespaces button to open your Codespace in a new tab**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

The current API is not exposing country/{country} which needs to be implemented to list cities. The route should allow only GET HTTP requests with a JSON response providing information from the historical high and low for that country, city, and given month.

As with any implementation, this addition should include at least one test function to work with the pytest runner and test framework. 

### 🛠 Step 1: Add a new route 
On our first exercise we will create a new route in our API. Go to the main.py file, and by using the inline chat with the following command `ctrl` + `i` (on Windows) or  `cmd` + `i`(on Mac) ask GitHub Copilot to help you create a new API that shows you the cities of a country. 

Use the following prompt in inline-chat:

```
Create a new route that exposes the cities of a country.
```

This prompt should give you something similar like this:


```python
# Create a new route that exposes the cities of a country:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())

```

> [!NOTE]
> Try your new route and refine your prompt until the result is as desired.

### 🔎 Step 2: Create a test
Now that you have created a new route, let's create a test with Copilot Chat for this route that uses Spain as the country. Remember to select your code and ask Copilot Chat to help you with this specific API that we just have created.

Use the following prompt with GitHub Copilot Chat:

```
/tests help me to create a new test for this route that uses Spain as the country.
```

![Copilot Chat image example](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-advanced-copilot/main/images/ideascopilot.png)


Once Copilot has helped you to create your test, try it. If this is not functioning as expected, feel free to share those details with Copilot in the chat. For example:

```
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```

It should give you another solution. Keep trying until you achieve the desired result.

### 🐍 Step 3: Use an agent to write the project
During this step we will be using an agent (workspace) to write the project documentation on how to run this project. In the GitHub Copilot Chat, we will try the following prompt:

`> @workspace help me to use an agent to write the project documentation on how to run it .`

Finally, verify the new endpoint is working by trying it out by going to the `/docs` endpoint and confirming that the endpoint shows up.


### 💡 Step 4: Using Slash Commands

Now that you've used GitHub Copilot to generate and explain code, you can also explore some other alternative approaches to perform developer tasks. These extra challenges will help you dive deeper into other GitHub Copilot features in addition to the ones you already know. For these extra challenges, you will use the Chat interface. Click on the GitHub Copilot Chat icon on the left sidebar if you don't have it open yet.

🚀 Congratulations, through the exercise, you have used GitHub Copilot with many different features that will allow you to work better with different projects. You interactively used some features to write tests, documentation, and find more about existing code..

## Avisos Legais
 
A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)
 
Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.
 
As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/
 
A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
