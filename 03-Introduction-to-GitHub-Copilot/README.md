<header>

# Introdução ao GitHub Copilot

Neste módulo de aprendizado, vamos mergulhar no revolucionário cenário da programação em par com IA usando o GitHub Copilot, a primeira ferramenta de desenvolvedor com IA em grande escala projetada para aprimorar sua experiência de codificação.

O GitHub Copilot analisa o contexto de arquivos e comentários e a entrada de seu chat interativo para fornecer sugestões de autocompletar, permitindo que você escreva código mais rápido e com menos esforço. À medida que você se aprofunda neste módulo, desvendará as complexidades do GitHub Copilot, explorando suas capacidades no VS Code e no Codespaces.

Nossos objetivos de aprendizado são ambiciosos, mas alcançáveis. Ao final do módulo, você não apenas será capaz de articular o que é o GitHub Copilot e suas vantagens, mas também compreenderá sua disponibilidade para indivíduos e empresas. Obtenha insights sobre o futuro do GitHub Copilot e mergulhe em exercícios práticos para dominar sua utilização com o Visual Studio Code.

Como a pesquisa mostrou, o GitHub Copilot capacita os desenvolvedores a codificar mais rápido, focar na resolução de problemas substanciais, manter períodos mais longos de produtividade e experimentar maior satisfação em seu trabalho.

Nota: Embora este módulo use [Codespaces](https://github.com/codespaces), você pode usar o GitHub Copilot em uma variedade de outros ambientes, incluindo localmente com o Visual Studio Code.

</header>

- **Para quem é isso:** Desenvolvedores, Engenheiros DevOps, Gerentes de desenvolvimento de software, Testadores.
- **O que você aprenderá:** Como instalar o Copilot em um Codespace, aceitar sugestões de código, aceitar sugestões de comentários.
- **O que você construirá:** Arquivos Javascript que terão código gerado pelo Copilot AI para sugestões de código e comentários.
- **Pré-requisitos:** Para usar o GitHub Copilot, você deve ter uma assinatura ativa do GitHub Copilot. Inscreva-se para Copilot Free para VS Code [Copilot for free para VS Code](https://learn.microsoft.com/en-us/visualstudio/ide/copilot-free-plan?view=vs-2022).
- **Tempo:** Este curso pode ser concluído em menos de uma hora.

Ao final deste módulo, você será capaz de:

- Explicar o que é o GitHub Copilot e as vantagens que ele oferece.
- Entender a disponibilidade do GitHub Copilot para indivíduos e empresas.
- Discutir o futuro do GitHub Copilot.
- Aprender como começar a usar o GitHub Copilot e algumas configurações comuns.
- Desenvolver usando o GitHub Copilot com o Visual Studio Code através de exercícios práticos.


## Peitura pré-requisito:
- [IIntrodução ao GitHub Copilot](https://learn.microsoft.com/en-us/training/modules/introduction-to-github-copilot/?WT.mc_id=academic-113596-abartolo)
- O que é o GitHub Copilot? (Playlist de vídeos abaixo)
- [![O que é GitHub Copilot](https://img.youtube.com/vi/QG1E0SCqqW8/0.jpg)](https://learn.microsoft.com/shows/introduction-to-github-copilot/what-is-github-copilot-1-of-6/?WT.mc_id=academic-113596-abartolo)

### Como iniciar este curso

<!-- For start course, run in JavaScript:
'https://github.com/new?' + new URLSearchParams({
  template_owner: 'skills',
  template_name: 'copilot-codespaces-vscode',
  owner: '@me',
  name: 'skills-copilot-codespaces-vscode',
  description: 'My clone repository',
  visibility: 'public',
}).toString()
-->

[![Iniciar Curso](https://user-images.githubusercontent.com/1221423/235727646-4a590299-ffe5-480d-8cd5-8194ea184546.svg)](https://github.com/new?template_owner=skills&template_name=copilot-codespaces-vscode&owner=%40me&name=skills-copilot-codespaces-vscode&description=My+clone+repository&visibility=public)

1. Clique com o botão direito em **Iniciar curso** e abra o link em uma nova aba.
2. Na nova aba, a maioria dos prompts será preenchida automaticamente para você.
   - Para o proprietário, escolha sua conta pessoal ou uma organização para hospedar o repositório.
   - Recomendamos criar um repositório público, pois repositórios privados [use Actions minutes](https://docs.github.com/en/billing/managing-billing-for-github-actions/about-billing-for-github-actions?WT.mc_id=academic-113596-abartolo).
   - Role para baixo e clique no botão **Criar repositório** na parte inferior do formulário.
3. Após a criação do seu novo repositório, espere cerca de 20 segundos e atualize a página. Siga as instruções passo a passo no README do novo repositório.

<footer>

<!--
  <<< Author notes: Footer >>>
  Add a link to get support, GitHub status page, code of conduct, license link.
-->

---

Obtenha ajuda: [Post in our discussion board](https://github.com/orgs/skills/discussions/categories/code-with-copilot) &bull; [Review the GitHub status page](https://www.githubstatus.com/)

## Avisos Legais
 
A Microsoft e quaisquer colaboradores concedem a você uma licença para a documentação da Microsoft e outros conteúdos neste repositório sob a [Creative Commons Attribution 4.0 International Public License](https://creativecommons.org/licenses/by/4.0/legalcode),
veja [LICENSE](LICENSE) e concedem a você uma licença para qualquer código no repositório sob a  [MIT License](https://opensource.org/licenses/MIT), consulte
[LICENSE-CODE](LICENSE-CODE)
 
Microsoft, Windows, Microsoft Azure e/ou outros produtos e serviços da Microsoft referenciados na documentação podem ser marcas registradas ou marcas registradas da Microsoft nos Estados Unidos e/ou em outros países. As licenças para este projeto não concedem a você direitos de uso de quaisquer nomes, logotipos ou marcas registradas da Microsoft. As diretrizes gerais de marcas registradas da Microsoft podem ser encontradas em http://go.microsoft.com/fwlink/?LinkID=254653.
 
As informações de privacidade podem ser encontradas em https://privacy.microsoft.com/en-us/
 
A Microsoft e quaisquer colaboradores reservam todos os outros direitos, sejam sob seus respectivos direitos autorais, patentes, ou marcas registradas, seja por implicação, estoppel ou de outra forma.
