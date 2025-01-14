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
- [Introdução à engenharia de prompts com GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Using advanced GitHub Copilot features](https://learn.microsoft.com/training/modules/advanced-github-copilot/?WT.mc_id=academic-113596-abartolo)

## Requisitos

1. Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)
1. Abra [this repository with Codespaces](https://codespaces.new/MicrosoftDocs/mslearn-advanced-copilot)

## 💪🏽 Exercício

**Clique com o botão direito no botão Codespaces a seguir para abrir seu Codespace em uma nova aba**
 
[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/MicrosoftDocs/mslearn-copilot-codespaces-python)

A API atual não está expondo country/{country}, que precisa ser implementado para listar cidades. A rota deve permitir apenas solicitações HTTP GET com uma resposta JSON fornecendo informações sobre os máximos e mínimos históricos para aquele país, cidade e mês específico.

Como em qualquer implementação, essa adição deve incluir pelo menos uma função de teste para funcionar com o pytest runner e o framework de teste.

### 🛠 Passo 1: Adicionar uma nova rota 

No nosso primeiro exercício, criaremos uma nova rota em nossa API. Vá para o arquivo `main.py` e, usando o chat inline com o seguinte comando `ctrl + i` (no Windows) ou `cmd + i` (no Mac), peça ao GitHub Copilot para ajudá-lo a criar uma nova API que mostre as cidades de um país.

Use o seguinte prompt no chat inline:


```
Create a new route that exposes the cities of a country.
```
```
Crie uma nova rota que exponha as cidades de um país.
```

Este prompt deve fornecer algo semelhante a isto:


```python
# Create a new route that exposes the cities of a country:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())

```
```python
# Crie uma nova rota que exponha as cidades de um país:
@app.get('/countries/{country}')
def cities(country: str):
    return list(data[country].keys())

```


> [!NOTA]
> Tente sua nova rota e refine seu prompt até que o resultado seja o desejado.

### 🔎 Passo 2: Criar um teste
Agora que você criou uma nova rota, vamos criar um teste com o Copilot Chat para essa rota que usa a Espanha como país. Lembre-se de selecionar seu código e pedir ao Copilot Chat para ajudá-lo com esta API específica que acabamos de criar.

Use o seguinte prompt com o GitHub Copilot Chat:

```
/tests help me to create a new test for this route that uses Spain as the country.
```
```
/tests ajude-me a criar um novo teste para esta rota que usa a Espanha como país.
```

![Copilot Chat image example](https://raw.githubusercontent.com/MicrosoftDocs/mslearn-advanced-copilot/main/images/ideascopilot.png)


Depois que o Copilot o ajudar a criar seu teste, experimente. Se não estiver funcionando como esperado, sinta-se à vontade para compartilhar esses detalhes com o Copilot no chat. Por exemplo:

```
This test is not quite right, it is not including cities that doesn't exist. Only Seville is part of the API.
```
```
Este teste não está correto, não está incluindo cidades que não existem. Apenas Sevilha faz parte da API.
```

Ele deve fornecer outra solução. Continue tentando até obter o resultado desejado.

### 🐍 Passo 3: Usar um agente para escrever o projeto
Durante esta etapa, usaremos um agente (workspace) para escrever a documentação do projeto sobre como executá-lo. No GitHub Copilot Chat, tentaremos o seguinte prompt:

```> @workspace help me to use an agent to write the project documentation on how to run it .```

```> @workspace ajude-me a usar um agente para escrever a documentação do projeto sobre como executá-lo.```

Finalmente, verifique se o novo endpoint está funcionando testando-o acessando o endpoint `/docs` e confirmando que o endpoint aparece.


### 💡 Passo 4: Usando Comandos de Barra

Agora que você usou o GitHub Copilot para gerar e explicar código, você também pode explorar algumas outras abordagens alternativas para realizar tarefas de desenvolvedor. Esses desafios extras ajudarão você a se aprofundar em outros recursos do GitHub Copilot além dos que você já conhece. Para esses desafios extras, você usará a interface de chat. Clique no ícone do GitHub Copilot Chat na barra lateral esquerda se ainda não estiver aberto.

🚀 Parabéns, através do exercício, você usou o GitHub Copilot com muitos recursos diferentes que permitirão trabalhar melhor com diferentes projetos. Você usou interativamente alguns recursos para escrever testes, documentação e descobrir mais sobre o código existente.

## Avisos Legais
 
A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)
 
Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.
 
As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/
 
A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
