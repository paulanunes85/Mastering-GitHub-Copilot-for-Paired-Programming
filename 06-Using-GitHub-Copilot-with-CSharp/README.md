<header>

# Usando o GitHub Copilot com C#

O GitHub Copilot é a primeira ferramenta de desenvolvedor com IA em grande escala do mundo que acelera significativamente a escrita de código, fornecendo sugestões de autocompletar enquanto você trabalha. Neste módulo, focaremos em usar o poder do GitHub Copilot para aumentar a eficiência da sua codificação em C#.

Como desenvolvedor, seu objetivo é aumentar a produtividade e acelerar os processos de codificação. O GitHub Copilot atua como seu programador em par com IA, oferecendo sugestões com base no contexto e nos padrões de código. Ao final deste módulo, você não apenas saberá como configurar o GitHub Copilot no Codespaces, mas também como gerar e implementar sugestões de código de forma eficaz.

Prepare-se para mergulhar em um cenário do mundo real! Você modificará um repositório C# usando o GitHub Copilot para criar um endpoint de API. Este projeto lhe dará uma experiência valiosa no desenvolvimento de um aplicativo web C# que serve uma API HTTP, gerando informações de previsão do tempo pseudo-aleatórias.


</header>

- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Como usar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos C# que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot Business ou Enterprise. Inscreva-se para Copilot Free para VS Code apenas para fim de treinamento [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este curso pode ser concluído em menos de uma hora.

Ao final deste módulo, você adquirirá as habilidades para:

- Criar prompts para gerar sugestões do GitHub Copilot
- Aplicar o GitHub Copilot para melhorar seus projetos.

## Leitura pré-requisito:
- [Introdução à engenharia de prompts com GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot?WT.mc_id=academic-113596-abartolo)

- [O que é a extensão GitHub Copilot para Visual Studio?](https://learn.microsoft.com/en-us/visualstudio/ide/visual-studio-github-copilot-extension?view=vs-2022&WT.mc_id=academic-113596-abartolo)

## Requisitos

1. Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)

1. Familiarize-se com [usar repositório com Codespaces](https://github.com/github/dotnet-codespaces)

## 💪🏽 Exercício

**Clique com o botão direito no botão Codespaces a seguir para abrir seu Codespace em uma nova aba**
 
[![Abrir no GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://codespaces.new/github/dotnet-codespaces)

O repositório **"GitHub Codespaces ♥️ .NET 8"** constrói uma API de Previsão do Tempo usando APIs Mínimas, abre o Swagger para que você possa chamar e testar a API e exibe os dados em um aplicativo web usando Blazor com .NET 8.

Vamos revisar os passos para atualizar o aplicativo BackEnd de Previsão do Tempo adicionando um novo endpoint que solicita uma localização específica e retorna a previsão do tempo para essa localização.


### 🗒️ (Passo Opcional 1): Familiarize-se com o repositório "GitHub Codespaces ♥️ .NET 8"

Uma vez que você abrir o repositório no Codespaces, você encontrará uma nova janela do navegador com um Codespace totalmente funcional. Tudo neste repositório está contido dentro deste único Codespace. Por exemplo, no painel do explorador, podemos ver o código principal para o projeto BackEnd e o projeto FrontEnd.

![Novo Codespace com o repositório em execução](./005OpenRepoInCodeSpaces.png)

Para executar o projeto BackEnd, vá para o painel "Run and Debug" e selecione o projeto "BackEnd".

![Abrir program.cs no projeto BackEnd](./006RunBackEndProject.png)

Inicie a depuração do projeto selecionado. O projeto da API de Previsão do Tempo, nosso projeto BackEnd, agora estará em execução na porta 8080. Podemos copiar a URL publicada do painel **Ports**.

![Copiar a URL do aplicativo a partir do painel de portas](./007ProjectRunningOpenInNewTab.png)

O aplicativo BackEnd publicou um endpoint chamado `weatherforecast` que gera dados de previsão aleatórios. Para testar o aplicativo em execução, você pode adicionar `/weatherforecast` à URL publicada. A URL final deve ser semelhante a esta:


```bash
https://< your url>.app.github.dev/weatherforecast
```

O aplicativo em execução em um navegador deve ser assim:

![testar execução da API](./008TestRunningApi.png)

Agora vamos adicionar um ponto de interrupção em nosso aplicativo para depurar cada chamada à API. Vá para o arquivo `Program.cs` no projeto BackEnd. O arquivo está no seguinte caminho `SampleApp\BackEnd\Program.cs`.

Adicione um ponto de interrupção na linha 24 (pressione F9) e atualize o navegador com a URL para testar o endpoint. O navegador não deve mostrar a previsão do tempo, e no Editor do Visual Studio podemos ver como a execução do programa foi pausada na linha 24.

![debug the running application.](./009DebugBackEndDemo.png)

Pressionando F10, podemos depurar passo a passo até a linha 32, onde podemos ver os valores gerados. O aplicativo deve ter gerado valores de previsão do tempo para os próximos 5 dias. A variável `forecast` contém um array com esses valores.

![debug the running application.](./010DebugForecastValue.png)

Você pode parar a depuração agora.

Parabéns! Agora você está pronto para adicionar mais recursos ao aplicativo usando o GitHub Copilot.


### 🗒️ (Passo Opcional 2): Familiarize-se com os Comandos de Barra do GitHub Copilot

À medida que começamos a trabalhar em nossa base de código, geralmente precisamos refatorar algum código ou obter mais contexto ou explicações sobre ele. Usando o Chat do GitHub Copilot, podemos ter conversas orientadas por IA para realizar essas tarefas.

Abra o arquivo `Program.cs` no projeto BackEnd. O arquivo está no seguinte caminho `SampleApp\BackEnd\Program.cs`.

Agora vamos usar um comando de barra no GitHub Copilot para entender um trecho de código. Selecione as linhas 22-35, pressione `CTRL + I` para abrir o chat inline e digite `/explain`.


![Use slash command to explain a piece of code](./011SlashCommandExplain.gif)

No Painel de Chat, o GitHub Copilot criará uma explicação detalhada do código selecionado. Uma versão resumida seria assim:

```
The selected C# code is part of an ASP.NET Core application using the minimal API feature. It defines a GET endpoint at "/weatherforecast" that generates an array of WeatherForecast objects. Each object is created with a date, a random temperature, and a random summary. The endpoint is named "GetWeatherForecast" and has OpenAPI support for standardized API structure documentation.
```
```
O código C# selecionado faz parte de um aplicativo ASP.NET Core usando o recurso de API mínima. Ele define um endpoint GET em "/weatherforecast" que gera um array de objetos WeatherForecast. Cada objeto é criado com uma data, uma temperatura aleatória e um resumo aleatório. O endpoint é nomeado "GetWeatherForecast" e tem suporte OpenAPI para documentação de estrutura de API padronizada.
```

**Comandos de barra** são comandos especiais que você pode usar no chat para realizar ações específicas no seu código. Por exemplo, você pode usar:
- `/doc` para adicionar um comentário de documentação
- `/explain` para explicar o código
- `/fix` para propor uma correção para os problemas no código selecionado
- `/generate` para gerar código para responder à sua pergunta

Vamos usar o comando `/tests` para gerar testes para o código. Selecione as linhas 39-42, pressione `CTRL + I` para abrir o chat inline e digite `/tests` (ou selecione o comando de barra /tests) para gerar um novo conjunto de testes para este registro.

![Use slash command to generate tests for the selected piece of code](./012SlashCmdTests.gif)

Neste ponto, o GitHub Copilot sugerirá uma nova classe. Você precisa primeiro pressionar [Create] para criar o novo arquivo.

Uma nova classe `ProgramTests.cs` foi criada e adicionada ao projeto. Esses testes estão usando XUnit, no entanto, você pode pedir para gerar testes usando outra biblioteca de testes unitários com um comando como este `/tests use MSTests for unit testing`.

***Importante:** Não vamos usar o arquivo de teste neste projeto. Você deve excluir o arquivo de teste gerado para continuar.*

Finalmente, vamos usar o `/doc` para gerar documentação automática para o código. Selecione as linhas 39-42, pressione `CTRL + I` para abrir o chat inline e digite `/doc` (ou selecione o comando) para gerar a documentação para este registro.

![Use slash command to generate the documentation for a piece of code](./013SlashCmdDoc.gif)

O chat inline, o Painel de Chat e os comandos de barra fazem parte das ferramentas incríveis que suportam nossa experiência de desenvolvimento com o GitHub Copilot. Agora estamos prontos para adicionar novos recursos a este aplicativo.

### 🗒️ Passo 1: Gerar um novo Registro que inclua o nome da cidade

Vá para o arquivo `Program.cs` no projeto BackEnd. O arquivo está no seguinte caminho `SampleApp\BackEnd\Program.cs`.


![open program.cs in the BackEnd project](./011OpenBackEndProject.png)

Navegue até o final do arquivo e peça ao Copilot para gerar um novo registro que inclua o nome da cidade.

```csharp
// create a new internal record named WeatherForecastByCity that request the following parameters: City, Date, TemperatureC, Summary
```

```csharp
// crie um novo registro interno chamado WeatherForecastByCity que solicita os seguintes parâmetros: City, Date, TemperatureC, Summary
```

O código gerado deve ser semelhante a este:

```csharp
// create a new internal record named WeatherForecastByCity that request the following parameters: City, Date, TemperatureC, Summary
internal record WeatherForecastByCity(string City, DateOnly Date, int TemperatureC, string? Summary)
{
    public int TemperatureF => 32 + (int)(TemperatureC / 0.5556);
}
```
```csharp
//  crie um novo registro interno chamado WeatherForecastByCity que solicita os seguintes parâmetros: City, Date, TemperatureC, Summary
internal record WeatherForecastByCity(string City, DateOnly Date, int TemperatureC, string? Summary)
{
    public int TemperatureF => 32 + (int)(TemperatureC / 0.5556);
}
```

Você pode ver o prompt funcionando na próxima animação:

![open program.cs in the BackEnd project](./014AddNewRecord.gif)


### 🔎 Passo 2: Gerar um novo endpoint para obter a previsão do tempo para uma cidade

Agora vamos gerar um novo endpoint de API semelhante a `/weatherforecast` que também inclua o nome da cidade. O nome do novo endpoint de API será **`/weatherforecastbycity`**.

***Importante:** Você deve colocar o código após a linha '.WithOpenApi();', que começa na linha 36. Lembre-se também de pressionar TAB em cada nova linha sugerida até que todo o endpoint esteja definido.*

Em seguida, gere um novo endpoint com o GitHub Copilot adicionando o comentário:

```csharp
// Create a new endpoint named /WeatherForecastByCity/{city}, that accepts a city name in the urls as a paremeter and generates a random forecast for that city
```
```csharp
// Crie um novo endpoint chamado /WeatherForecastByCity/{city}, que aceita um nome de cidade na URL como um parâmetro e gera uma previsão aleatória para essa cidade
```

No exemplo a seguir, adicionamos algumas linhas em branco extras após o endpoint anterior e, em seguida, o GitHub Copilot gerou o novo endpoint. Uma vez que o código principal do Endpoint foi gerado, o GitHub Copilot também sugeriu código para o nome do endpoint (linha 49) e a especificação OpenAPI (linha 50). Lembre-se de aceitar cada uma dessas sugestões pressionando [TAB].

![Copilot ghost suggestion for the new endpoint](./020GeneratedCode.gif)

***Importante**: Este prompt gera várias linhas de código C#. É fortemente aconselhável verificar e revisar o código gerado para garantir que ele funcione da maneira desejada.*

O código gerado deve ser semelhante a este:

```csharp
// Create a new endpoint named /WeatherForecastByCity/{city}, that accepts a city name in the urls as a paremeter and generates a random forecast for that city
app.MapGet("/WeatherForecastByCity/{city}", (string city) =>
{
    var forecast = new WeatherForecastByCity
    (
        city,
        DateOnly.FromDateTime(DateTime.Now),
        Random.Shared.Next(-20, 55),
        summaries[Random.Shared.Next(summaries.Length)]
    );
    return forecast;
})
.WithName("GetWeatherForecastByCity")
.WithOpenApi();
```
```csharp
// Crie um novo endpoint chamado /WeatherForecastByCity/{city}, que aceita um nome de cidade na URL como um parâmetro e gera uma previsão aleatória para essa cidade
app.MapGet("/WeatherForecastByCity/{city}", (string city) =>
{
    var forecast = new WeatherForecastByCity
    (
        city,
        DateOnly.FromDateTime(DateTime.Now),
        Random.Shared.Next(-20, 55),
        summaries[Random.Shared.Next(summaries.Length)]
    );
    return forecast;
})
.WithName("GetWeatherForecastByCity")
.WithOpenApi();
```


### 🐍 Passo 3: Testar o novo endpoint

Finalmente, verifique se o novo endpoint está funcionando iniciando o projeto a partir do painel Run and Debug. Selecione Run and Debug e, em seguida, selecione o projeto BackEnd.

![Open Run and Debug panel and select BackEnd project](./030RunAndDebugTheBackEndProject.png)

Agora pressione Run e o projeto deve ser compilado e executado. Uma vez que o projeto esteja em execução, podemos testar a URL original usando a URL do seu Codespace e o endpoint original:


```bash
https://< your code space url >.app.github.dev/WeatherForecast
```

E o novo endpoint também estará pronto para ser testado. Aqui estão algumas URLs de exemplo com diferentes cidades:

```bash
https://< your code space url >.app.github.dev/WeatherForecastByCity/Toronto

https://< your code space url >.app.github.dev/WeatherForecastByCity/Madrid

https://< your code space url >.app.github.dev/WeatherForecastByCity/<AnyCityName>
```

Ambos os testes em execução devem ser assim:

![Open Run and Debug panel and select BackEnd project](./032TestAndDebugUsingUrls.png)


🚀 Parabéns, através do exercício, você não apenas usou o GitHub Copilot para gerar código, mas também fez isso de uma maneira interativa e divertida! Você pode usar o GitHub Copilot não apenas para gerar código, mas também para escrever documentação, testar suas aplicações e muito mais.


## Avisos Legais

A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)

Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.

As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/

A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
