---
title: Conduzir um piloto de usuário para avaliar e testar como Microsoft Teams funcionará em sua organização
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Diretrizes para iniciar um Microsoft Teams para explorar tudo o que Teams pode oferecer à sua organização, enquanto você continua usando Skype for Business
ms.localizationpriority: medium
ms.custom: Teams-upgrade-guidance
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae69bab918a9c8bd542e5ec70a95df7544677d8d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823220"
---
# <a name="conduct-a-user-pilot"></a>Realizar um piloto de usuário

![Diagrama de jornada de atualização, realçando Implantação e Implementação.](media/upgrade-banner-deployment.png "Estágios do percurso de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação do seu percurso de atualização e compartilha insights para executar um piloto eficaz. Antes de continuar, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)

Ao implantar novas tecnologias, sua organização pode obter valor comercial, como economia de custos, conformidade de segurança, satisfação dos funcionários e eficiência operacional, mas também pode afetar a produtividade dos usuários e a infraestrutura organizacional (sua rede). Antes de habilitar a nova tecnologia em sua organização, realize um piloto de usuário formal. Assim como pintaria um pequeno patch de cor em uma parede antes de pintar a sala inteira, você testaria uma ampla distribuição em uma escala menor, realizando um piloto para validar a preparação técnica e do usuário, identificar e atenuar problemas e ajudar a garantir uma implementação bem-sucedida em toda a organização.

Para obter os resultados mais realistas, o piloto deve envolver usuários reais, imitar como eles se comunicam e colaboram e verificar as experiências técnicas e do usuário. Se sua organização estiver considerando executar o Skype for Business e o Teams lado a lado, atualizar para o Teams no futuro ou implantar novas funcionalidades, como uma chamada ou conferência, um piloto pode ajudar a identificar o caminho certo para sua organização. Às vezes considerado a Fase 1 de uma distribuição, o piloto ideal aproveita a preparação que você já iniciou e implementa seu plano definido com um grupo de usuários direcionado.

|&nbsp; | &nbsp;|
|---|---|
| ![Um ícone representando um ponto de decisão.](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Como você usará um piloto para informar a direção do projeto?</li></ul> |
| ![Um ícone representando o passo seguinte.](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Use as diretrizes abaixo para projetar e executar seu piloto formal.</li></ul>|

> [!Tip]
> Use os recursos piloto [de exemplo para](https://aka.ms/UpgradeSuccessKit) ajudar a projetar sua pesquisa de comunicação, plano de teste e comentários.

## <a name="1-outline-pilot-logistics"></a>1. Estrutura de tópicos logística piloto

Um piloto bem-sucedido definiu datas de início e de término e [definiu claramente as metas para](upgrade-define-project-scope.md#project-goals) medir o sucesso. Essas metas devem estar alinhadas com o escopo do seu projeto mais amplo, conforme documentado [](upgrade-define-project-scope.md)quando você definiu o escopo do projeto e será usada para informar o caminho para frente depois que o piloto terminar. Você também deve garantir que tenha incluído os stakeholders certos durante o projeto. Convém permitir tempo suficiente para executar o piloto e avaliar seu impacto: recomendamos um mínimo de 30 dias.

Comece pequeno e adicione ao piloto conforme apropriado, seja adicionando cargas de trabalho ou recursos ou usuários adicionais, dando tempo para avaliar os resultados e ajustar o piloto conforme você itera. Você pode até optar por executar pilotos subsequentes à medida que Teams novos recursos são lançados de acordo com o roteiro.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Selecione os participantes piloto e os cenários de teste

Uma das tarefas mais importantes do planejamento do piloto é uma seleção criteriosa dos participantes. Lembre-se Teams é otimizado para trabalho em equipe, portanto, certifique-se de selecionar participantes piloto não apenas com base em funções ou personas, mas também com base em seu projeto e no trabalho entre equipes. Um ótimo lugar para começar é pedir a seus stakeholders e gerentes de departamento projetos reais que você pode validar Teams. Um exemplo de um projeto baseado em função pode ser usar o Teams com sua organização de vendas para garantir que os representantes de campo possam acessar facilmente os recursos de que precisam e compartilhar insights com outros membros de campo. Um exemplo de trabalho baseado em projeto pode ser coordenar um evento de lançamento de produto com as equipes de marketing, treinamento, relações públicas e planejamento de eventos. Independentemente dos cenários selecionados, o piloto deve se estender para as principais pessoas em TI, treinamento e assistência técnica, para que você possa validar completamente a solução, otimizando totalmente os recursos de gerenciamento de projetos.

> [!Tip]
> Ao selecionar seus Teams do grupo piloto, inclua os principais usuários de Skype for Business. Verifique com esses usuários para entender como eles usam Skype for Business e, em seguida, crie um plano de teste para verificar se Teams pode atender às suas necessidades atuais.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Projete seu plano de teste e a pesquisa de comentários

Para obter uma experiência piloto bem-sucedida, dê aos participantes tarefas claramente definidas para serem concluídas, juntamente com uma maneira de compartilhar seus comentários. Agrupar tarefas para oferecer cenários do mundo real aos usuários, demonstrando a relevância para suas atividades diárias. Permita que os casos de uso definidos em [Avaliar preparação para alterações organizacionais](./upgrade-org-change-readiness.md) guiem seu plano de teste.

Sua organização pode optar por piloto de todas as funcionalidades de uma só vez ou usar uma abordagem gradual, por exemplo, colaboração piloto primeiro, depois reuniões e, em seguida, chat e chamadas. Verifique se você tem um canal de comentários aberto para acompanhar o progresso e medir os resultados. Usar uma pesquisa predefinida como uma maneira fácil de capturar e avaliar os resultados do piloto; o design da pesquisa deve ser baseado nos cenários e recursos em seu plano de teste.

## <a name="4-create-your-communications-plan"></a>4. Criar seu plano de comunicação

É crucial para o sucesso do piloto que você instrua os participantes piloto sobre o que está acontecendo, quando e por que e o que é esperado deles. Para impulsionar a excitação e a participação máxima, inclua mensagens de valor do usuário, além de links para treinamento e suporte, em que os usuários podem obter informações adicionais à medida que progridem por meio do piloto. Aqui estão alguns recursos de exemplo para começar a usar seu plano de comunicações piloto:

- [Recursos piloto](https://aka.ms/UpgradeSuccessKit), incluindo modelos de email e perguntas de pesquisa de comentários de exemplo
- [Alterne para Teams do Skype for Business](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964), um guia de início rápido projetado para ajudar Skype for Business usuários a começar a Teams

## <a name="5-conduct-your-pilot"></a>5. Conduzir seu piloto

Com toda a logística em vigor, agora você está pronto para começar seu piloto. Conduzir seu piloto inclui a comunicação com seus usuários, o monitoramento de sua rede e o uso para garantir que o desempenho da rede e a qualidade da chamada permaneçam íntegros, coletando comentários dos participantes e revisando tíquetes de assistência técnica para perguntas relacionadas ao Teams.

### <a name="tips-for-pilot-success"></a>Dicas para o sucesso do piloto

As dicas a seguir podem ajudar a garantir o sucesso do piloto:

- Antes de iniciar o piloto, confirme se todos os participantes piloto estão habilitados para o [modo de coexistência] apropriado
- (https://aka.ms/SkypeToTeams-SetCoexistence) você deseja validar.
- Semanalmente, em todo o piloto, reúna-se com os stakeholders do projeto para examinar os comentários dos usuários, os dados de uso, os dados de rede e os tíquetes de assistência técnica para garantir que o piloto esteja funcionando sem problemas. Faça os ajustes conforme necessário.

### <a name="suggested-timeline"></a>Linha do tempo sugerida

Veja uma sugestão de linha do tempo para um piloto de 30 dias:

- Uma semana antes do início do piloto: envie a comunicação inicial para os usuários piloto.
- Dia 1: Enviar comunicação inicial para usuários piloto.
- Dia 7: Realizar a primeira reunião semanal de ponto de verificação da equipe de projeto.
- Dia 14: Enviar comunicação de ponto médio para seus usuários piloto, realizar uma reunião semanal de ponto de verificação da equipe de projeto.
- Dia 21: Realizar uma reunião semanal de ponto de verificação da equipe de projeto.
- Dia 30: Enviar comunicação final aos usuários piloto.
- Dias 31 a 45: Avalie os resultados do piloto e planeje as próximas etapas.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Avaliar os aprendizados e avaliar seu plano de avanço

Após a conclusão do piloto, é hora de reunir todas as pesquisas de comentários, estatísticas finais de rede e tíquetes de suporte para análise em relação às suas metas e determinar se você implementará seu plano de avanço. Você pode descobrir que sua organização está pronta para uma implantação ampla ou deseja estender seu piloto para mais usuários ou deseja revisitar o piloto posteriormente depois que quaisquer preocupações identificadas tiverem sido atenuadas. Lembre-se de que o piloto é uma ótima maneira de prever resultados técnicos e de usuário em um _ambiente_ controlado; ser pensativo sobre saltar para a frente muito rapidamente.

Se os resultados indicarem:

- **Suas metas piloto (por exemplo, satisfação** do usuário e qualidade de rede) foram atingidas, você deve estar pronto para prosseguir com a próxima fase da distribuição. Dependendo das metas do seu projeto, isso pode ser um dos seguintes:
  - Estendendo o piloto para participantes adicionais
  - [Habilitando Teams juntamente Skype for Business (**modo Ilhas**) para algumas ou todas as suas organizações](./setting-your-coexistence-and-upgrade-settings.md)
  - [Atualizando usuários de Skype for Business para Teams (**Teams somente** modo) para algumas ou todas as suas organizações](./setting-your-coexistence-and-upgrade-settings.md)
- **Seu piloto não atingiu os resultados desejados (** por exemplo, satisfação do usuário e qualidade de rede), reserve um tempo para fazer os ajustes apropriados ao seu plano e reveja o piloto.

> [!Tip]
> Inscreva seus participantes piloto como campeões pares para ajudar a evangelizar e integrar novos usuários ao Teams. Os campeões pares podem facilmente se relacionar com outros usuários, compartilhar suas próprias experiências e aprendizados e oferecer suporte e diretrizes para seus colegas. Saiba mais sobre [os campeões](
https://adoption.microsoft.com/become-a-champion/) e como você pode usá-los em sua própria distribuição.