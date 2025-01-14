<header>

# Criando um Mini Jogo com GitHub Copilot

Nosso foco neste módulo é aproveitar o poder do GitHub Copilot para criar um minijogo clássico de pedra, papel e tesoura. Esta experiência prática não apenas aprimorará suas habilidades de programação, mas também melhorará sua capacidade de desenvolver aplicativos de console em Python. A melhor parte? Utilizaremos o GitHub Codespaces, eliminando a necessidade de configurar seu ambiente de desenvolvimento. Com o GitHub Copilot como seu programador em par com IA, você pode se concentrar no desenvolvimento do aplicativo enquanto colabora perfeitamente com seu assistente de código.

</header>

- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Aproveitar o GitHub Copilot para criar código e adicionar comentários ao seu trabalho.
- **O que você construirá:** Arquivos Python que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot Business ou Enterprise. Inscreva-se para Copilot Free para VS Code apenas para fim de treinamento [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este curso pode ser concluído em menos de uma hora.
  
Ao final deste módulo, você adquirirá as habilidades para:

- Experimentar o GitHub Codespaces como um ambiente de desenvolvimento.
- Desenvolver rotinas de entrada e saída em um aplicativo de console Python.
- Usar o GitHub Copilot como assistente.

## Leitura pré-requisito:
- [Introdução à engenharia de prompts com GitHub Copilot](https://learn.microsoft.com/training/modules/introduction-prompt-engineering-with-github-copilot//?WT.mc_id=academic-113596-abartolo)
- [Challenge project - Build a minigame with GitHub Copilot and Python](https://learn.microsoft.com/training/modules/challenge-project-create-mini-game-with-copilot/?WT.mc_id=academic-113596-abartolo)
- Learn Live: Build a minigame console app with GitHub Copilot (Video below)
- [![Learn Live: Build a minigame console app with GitHub Copilot](https://mediusimg.event.microsoft.com/video-53275/b508053c0b/thumbnail.jpg?sv=2018-03-28&sr=c&sig=k6NthrPwnvBfDPNAEBQaYaVzlJavZ8pnWuP6OcKm4Bs%3D&se=2028-11-18T05%3A23%3A52Z&sp=r)](https://ignite.microsoft.com/sessions/aeaf1e85-65e2-497d-aaf5-724d85213aa1?WT.mc_id=academic-113596-abartolo)
  

## Requisitos

- Habilite seu [GitHub Copilot service](https://github.com/github-copilot/signup)

## 💪🏽 Exercício

**Clique com o botão direito no botão "Iniciar Curso" para abrir seu Codespace em uma nova abab**
 
[![Iniciar Curso](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=copilot-codespaces-vscode&owner=%40me&name=skills-copilot-codespaces-vscode&description=My+clone+repository&visibility=public)

Você já aprendeu um pouco sobre o GitHub Codespaces e o GitHub Copilot e como eles funcionam. Neste exercício de desafio, seu objetivo é desenvolver um minijogo em Python usando o GitHub Copilot.

#### Testando seu GitHub Codespace

1. Acesse seu Codespaces e crie um novo arquivo chamado app.py no Visual Studio Code.

    **Nota:** Pode ser necessário instalar a extensão Python no Visual Studio Code se ela não estiver instalada atualmente.

2. Digite o seguinte comentário:

   ```python
   # write 'hello world' to the console
   ```
      ```python
   # escreva 'hello world' no console
   ```
      
3. O GitHub Copilot deve completar o código para você e fornecer o seguinte resultado:
   
   ```python
   # write 'hello world' to the console
   print('hello world')
   ```
    ```python
   # escreva 'hello world' no console
    print('hello world')
   ```

4. Execute o aplicativo com o comando python app.py no terminal e verifique se o resultado é semelhante à seguinte mensagem do console:

   ```bash
   hello world
   ```
   
### Criando a lógica do jogo

Agora que você verificou que o Codespaces está funcionando com o GitHub Copilot, seu próximo passo é desenvolver a lógica do minijogo em Python com a ajuda do GitHub Copilot com base nas seguintes especificações:

O vencedor do jogo é determinado por três regras simples:

- **Pedra** vence tesoura.
- **Tesoura** vence papel.
- **Papel** vence pedra.

#### Considerações sobre a interação do jogos

O computador será seu oponente e pode escolher aleatoriamente um dos elementos (**pedra**, **papel** ou **tesoura**). Sua interação com o jogo será através do console (Terminal).

- O jogador pode escolher uma das três opções: pedra, papel ou tesoura e deve ser avisado se inserir uma opção inválida.
- A cada rodada, o jogador deve inserir uma das opções da lista e ser informado se ganhou, perdeu ou empatou com o oponente.
- Ao final de cada rodada, o jogador pode escolher se deseja jogar novamente.
- Exibir a pontuação do jogador ao final do jogo.
- O minijogo deve lidar com entradas do usuário, colocando-as em minúsculas e informando o usuário se a opção for inválida.

No seu GitHub Codespaces, siga as instruções fornecidas para configurar prompts que o GitHub Copilot possa entender e usar para ajudá-lo a construir o minijogo. Lembre-se de que o GitHub Copilot depende de comentários para entender o contexto e fornecer sugestões úteis enquanto você trabalha em seu projeto.

#### Verifique seu trabalho

1. Execute o minijogo no console com o comando python app.py.
2. No prompt, digite uma das opções do jogo: pedra, papel ou tesoura.
3. O minijogo deve informar ao jogador se ele ganhou, perdeu ou empatou com o oponente.
4. Escolha continuar jogando.
5. No prompt, digite tela.
6. O minijogo deve informar ao jogador se a opção inserida é inválida.
7. Repita os passos 2 e 4 para jogar algumas rodadas e escolha não continuar jogando.
8. Verifique se o minijogo é encerrado e se exibe sua pontuação, informando o número de vitórias e rodadas.

Parabéns por concluir este exercício de desafio! Você criou um minijogo de console em Python usando o GitHub Copilot.

## Avisos Legais
 
A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)
 
Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.
 
As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/
 
A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
