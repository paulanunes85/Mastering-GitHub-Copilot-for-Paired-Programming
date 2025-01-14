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

## Leitura pré-requisito:
- [Introduction to prompt engineering with GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Using GitHub Copilot with Python](https://learn.microsoft.com/en-us/training/modules/introduction-copilot-python/?WT.mc_id=academic-113596-abartolo)

## Requisitos

1. Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Abra [this repository with Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

## 💪🏽 Exercício

**Clique com o botão direito no botão Codespaces a seguir para abrir seu Codespace em uma nova aba**
 
[![Abrir GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

A API já tem um único endpoint para gerar um token. Vamos atualizar a API adicionando um novo endpoint que aceita texto e retorna uma lista de tokens.

### 🛠 Passo 1: Adicionar um modelo Pydantic

Vá para o arquivo `main.py`, navegue até o final do código fornecido, selecione **Ctrl + I (PC)** ou **Cmd + I (Mac)** e copie o seguinte na caixa de chat do GitHub Copilot fornecida para que ele possa gerar um modelo `Pydantic` para você:

```
Create a Pydantic model so that I can use it in a new route that will accept JSON with text as a key which accepts a string.
```

```
Crie um modelo Pydantic para que eu possa usá-lo em uma nova rota que aceitará JSON com texto como uma chave que aceita uma string.
```

O modelo gerado deve ser semelhante a este:

```python
    class TextData(BaseModel):
        text: str
```

> [!NOTA]
> Você pode ver alguns avisos do linter no editor (identificáveis com sublinhados vermelhos pontilhados) que podem ser ignorados. Estes incluem linhas longas ou até mesmo novas linhas que não são necessárias. Sinta-se à vontade para corrigi-los, embora isso não deva afetar a execução correta do seu aplicativo.

### 🔎 Passo 2: Gerar um novo endpoint

Em seguida, gere um novo endpoint com o GitHub Copilot adicionando o comentário na parte inferior do arquivo `main.py` sob a última rota.

```python
# Create a FastAPI endpoint that accepts a POST request with a JSON body containing a single field called "text" and returns a checksum of the text 
```

```python
# Crie um endpoint FastAPI que aceita uma solicitação POST com um corpo JSON contendo um único campo chamado "text" e retorna um checksum do texto
```

Você pode receber uma sugestão que usa um módulo ou biblioteca que não foi importado. Se isso acontecer, você pode pedir ao GitHub Copilot para ajudá-lo a importar o módulo correto selecionando o código gerado e usando Command+I (Apple) ou Control+I (Windows) e adicionando um prompt para adicionar as importações ausentes. Este pequeno pop-up é chamado de chat inline e é outra maneira de interagir com o GitHub Copilot.

### 🐍 Passo 3: Explicar o código

A rota `generate()` cria um ID de token pseudo-aleatório usando uma única linha que pode ser difícil de entender completamente. Selecione toda a função, clique com o botão direito na seleção, selecione o item de menu Copilot e, em seguida, a opção _"Explain This"_ . A interface de chat do GitHub Copilot será aberta à esquerda e fornecerá uma 

Finalmente, verifique se o novo endpoint está funcionando, testando-o acessando o endpoint `/docs` e confirmando que o endpoint aparece.


🚀  Parabéns, através do exercício, você não apenas usou o Copilot para gerar código, mas também fez isso de uma maneira interativa e divertida! Você pode usar o GitHub Copilot não apenas para gerar código, mas também para escrever documentação, testar suas aplicações e muito mais.


### 💡 Passo 4: Usando Comandos de Barra

Agora que você usou o GitHub Copilot para gerar e explicar código, você também pode explorar algumas outras abordagens alternativas para realizar tarefas de desenvolvedor. Esses desafios extras ajudarão você a se aprofundar em outros recursos do GitHub Copilot além dos que você já conhece. Para esses desafios extras, você usará a interface de chat. Clique no ícone de chat do GitHub Copilot na barra lateral esquerda se ainda não estiver aberto.


**Gerar documentação**
 
Com `main.py` aberto, use a interface de chat com o seguinte texto:

```
/docs I need to document the routes for these API Routes. Help me produce documentation I can put in the README.md file of this project
```

```
/docs Eu preciso documentar as rotas para essas rotas de API. Ajude-me a produzir documentação que eu possa colocar no arquivo README.md deste projeto
```

A parte `/docs` do prompt é chamada de _"comando de barra"_ e é um recurso específico do GitHub Copilot que permite escrever documentação. Se os resultados parecerem bons, adicione-os a uma nova seção do seu arquivo README.md.


**Gerar testes**
 
O código atual não possui testes. Para este desafio, você usará o comando de barra `/tests`. Com `main.py` aberto, use a interface de chat com o seguinte prompt:

```
/tests help me write a test for the generate() route using the FastAPI test client and the Pytest framework. Help me understand where I should put the test file, how to add the Pytest dependency to my project, and how to run the tests
```

```
/tests ajude-me a escrever um teste para a rota generate() usando o cliente de teste FastAPI e o framework Pytest. Ajude-me a entender onde devo colocar o arquivo de teste, como adicionar a dependência Pytest ao meu projeto e como executar os testes
```

O comando de barra `/tests` guiará você na escrita de um novo teste para sua rota e fornecerá tudo o que você precisa para verificar seu trabalho.


**Desafio do Workspace**
 
Finalmente, você terá a chance de usar um agente. Agentes são um recurso especial do GitHub Copilot no Visual Studio Code que permitem que um contexto específico seja compartilhado com o GitHub Copilot. Para este desafio final, você usará o agente `@workspace`, que inclui arquivos do workspace atual para fornecer mais contexto. Você resolverá um problema relacionado a como executar todo o aplicativo. Neste caso, você melhorará o README.md para obter mais detalhes que abrangem vários arquivos. Usar `@workspace` ajuda a fornecer mais contexto sem precisar abrir muitos arquivos.

Para este desafio final, você não precisa ter nenhum arquivo aberto. Use o seguinte prompt na janela de chat do GitHub Copilot:

```
@workspace I want to provide instructions on how to run this application using the uvicorn webserver, I also need to provide instructions on how to install the dependencies properly and what are some characteristics of the FastAPI framework. I will use this to improve the README.md file
```

```
@workspace Eu quero fornecer instruções sobre como executar este aplicativo usando o servidor web uvicorn, também preciso fornecer instruções sobre como instalar as dependências corretamente e quais são algumas características do framework FastAPI. Vou usar isso para melhorar o arquivo README.md
```

O resultado deve ser uma explicação muito boa sobre o FastAPI, como executar o aplicativo e como instalar as dependências. Um relatório no topo da resposta pode incluir todas as referências usadas para determinar quais arquivos ele precisava usar para fornecer o contexto correto para o GitHub Copilot.


## Avisos Legais

A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.

As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/

A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
