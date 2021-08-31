---
title: Conduzir um piloto de usuário para avaliar e testar como o Microsoft Teams funcionará em sua organização
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Diretrizes para iniciar um Microsoft Teams piloto para explorar tudo o que Teams pode oferecer à sua organização, enquanto você continua a usar Skype for Business
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
ms.openlocfilehash: 521e5eb81d2688c924e3f2c76a25c86f6645b02d
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733290"
---
# <a name="conduct-a-user-pilot"></a>Realizar um piloto de usuário

![Atualizar diagrama de jornada, realçando Implantação e Implementação.](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")

Este artigo faz parte do estágio implantação e implementação da jornada de atualização e compartilha informações sobre como executar um piloto efetivo. Antes de prosseguir, confirme se você concluiu as seguintes atividades:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [Preparou seu ambiente](./upgrade-prepare-environment.md)
- [Preparou sua organização](./upgrade-prepare-organization.md)

Implantando novas tecnologias, sua organização pode perceber o valor de negócios, como economia de custos, conformidade com a segurança, satisfação dos funcionários e eficiências operacionais, mas também pode afetar a produtividade e a infraestrutura organizacional dos usuários (sua rede). Antes de habilizar a nova tecnologia em toda a sua organização, conduza um piloto de usuário formal. Assim como você pintaria um pequeno patch de cor em uma parede antes de pintar toda a sala, você testaria uma ampla implantação em uma escala menor, conduzindo um piloto para validar a preparação técnica e do usuário, identificar e atenuar problemas e ajudar a garantir uma implementação bem-sucedida em toda a organização.

Para obter os resultados mais realistas, o piloto deve envolver usuários reais, imitar como eles se comunicam e colaborar e verificar experiências técnicas e de usuário. Se sua organização está considerando executar Skype for Business e Teams lado a lado, atualizar para o Teams no futuro ou implantar uma nova funcionalidade como uma chamada ou conferência, um piloto pode ajudar a identificar o caminho certo para a sua organização. Às vezes considerado a Fase 1 de uma implantação, o piloto ideal aproveita a preparação que você já iniciou e implementa seu plano definido com um grupo direcionado de usuários.

| | |
|---|---|
| ![Um ícone que representa um ponto de decisão.](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Como você usará um piloto para informar a direção do projeto?</li></ul> |
| ![Um ícone que representa a próxima etapa.](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Use as diretrizes abaixo para projetar e executar seu piloto formal.</li></ul>|

> [!Tip]
> Use os recursos [piloto de exemplo para](https://aka.ms/UpgradeSuccessKit) ajudar a projetar suas comunicações, plano de teste e pesquisa de feedback.

## <a name="1-outline-pilot-logistics"></a>1. Estruturar a logística piloto

Um piloto bem-sucedido definiu datas de início e fim e metas [claramente definidas para](upgrade-define-project-scope.md#project-goals) medir o sucesso. Essas metas devem se alinhar ao escopo do seu projeto mais amplo, conforme documentado quando você definiu o escopo do projeto [e](upgrade-define-project-scope.md)será usada para informar seu caminho para frente depois que o piloto for final. Você também deve garantir que incluiu os participantes certos durante a duração do projeto. Você vai querer ter certeza de permitir tempo suficiente para executar o piloto e avaliar seu impacto: recomendamos um mínimo de 30 dias.

Comece pequeno e adicione ao piloto conforme apropriado, seja adicionando cargas de trabalho ou recursos ou usuários adicionais, ganhando tempo para avaliar os resultados e ajustar seu piloto à medida que você itera. Você pode até optar por executar pilotos subsequentes à medida que novos recursos Teams são lançados de acordo com o roteiro.

## <a name="2-select-your-pilot-participants-and-test-scenarios"></a>2. Selecione seus participantes piloto e cenários de teste

Uma das tarefas mais importantes do planejamento do piloto é uma seleção criteriosa dos participantes. Lembre-se de Teams é otimizado para o trabalho em equipe, portanto, não se esqueça de selecionar participantes piloto não somente com base em funções ou personas, mas também com base em seu projeto e no trabalho entre equipes. Um ótimo lugar para começar é pedir aos seus participantes e gerentes de departamento projetos reais que você pode validar Teams. Um exemplo de um projeto baseado em função pode ser usar o Teams com sua organização de vendas para garantir que os representantes de campo possam acessar facilmente os recursos necessários e compartilhar informações com outros membros do campo. Um exemplo de trabalho baseado em projeto pode estar coordenando um evento de lançamento de produto com as equipes de marketing, treinamento, relações públicas e planejamento de eventos. Independentemente dos cenários selecionados, o piloto deve estender-se às pessoas-chave em TI, treinamento e seu helpdesk, para que você possa validar completamente a solução enquanto otimiza totalmente os recursos de gerenciamento de projetos.

> [!Tip]
> Ao selecionar seus Teams do grupo piloto, certifique-se de incluir os principais usuários de Skype for Business. Verifique com esses usuários para entender como eles usam Skype for Business hoje e, em seguida, crie um plano de teste para verificar se os Teams podem atender às suas necessidades atuais.

## <a name="3-design-your-test-plan-and-feedback-survey"></a>3. Projete seu plano de teste e uma pesquisa de feedback

Para uma experiência piloto bem-sucedida, dê aos participantes tarefas claramente definidas para concluir, juntamente com uma maneira de compartilhar seus comentários. Agrupar tarefas em conjunto para oferecer cenários reais aos usuários, demonstrando relevância para suas atividades diárias. Permitir que os casos de uso definidos em Avaliar a preparação [de alterações organizacionais](./upgrade-org-change-readiness.md) orientem seu plano de teste.

Sua organização pode optar por pilotar todas as funcionalidades de uma só vez ou usar uma abordagem gradual, por exemplo, colaboração piloto primeiro, reuniões e, em seguida, chat e chamada. Verifique se você tem um canal de comentários aberto para acompanhar o progresso e medir os resultados. Use uma pesquisa predefinida como uma maneira fácil de capturar e avaliar resultados piloto; o design da pesquisa deve se basear nos cenários e recursos em seu plano de teste.

## <a name="4-create-your-communications-plan"></a>4. Crie seu plano de comunicação

É fundamental para o sucesso do piloto que você instrua os participantes piloto sobre o que está acontecendo, quando e por que e o que é esperado deles. Para impulsionar a emoção e a participação máxima, certifique-se de incluir mensagens de valor do usuário, além de links para treinamento e suporte onde os usuários podem obter informações adicionais à medida que eles passam pelo piloto. Aqui estão alguns recursos de exemplo para começar com seu plano piloto de comunicações:

- [Recursos piloto](https://aka.ms/UpgradeSuccessKit), incluindo modelos de email e perguntas de pesquisa de feedback de exemplo
- [Alternar para Teams de](https://support.office.com/article/Switch-to-Teams-from-Skype-for-Business-6295a0ae-4e8e-4bba-a100-64cc951cc964)Skype for Business , um guia de início rápido projetado para ajudar Skype for Business usuários a começar a Teams

## <a name="5-conduct-your-pilot"></a>5. Conduzir seu piloto

Com toda a logística pronta, agora você está pronto para começar seu piloto. A realização do piloto inclui a comunicação com seus usuários, o monitoramento da rede e do uso para garantir que o desempenho da rede e a qualidade da chamada permaneçam íntegrees, coletando comentários dos participantes e revendo tíquetes de ajuda para perguntas relacionadas ao Teams.

### <a name="tips-for-pilot-success"></a>Dicas para o sucesso piloto

As dicas a seguir podem ajudar a garantir o sucesso do piloto:

- Antes de iniciar o piloto, confirme se todos os participantes piloto estão habilitados para o [modo de coexistência] apropriado
- ( https://aka.ms/SkypeToTeams-SetCoexistence) você deseja validar.
- Semanalmente, em todo o piloto, encontre-se com os participantes do projeto para analisar comentários do usuário, dados de uso, dados de rede e tíquetes de suporte para garantir que o piloto está funcionando sem problemas. Faça quaisquer ajustes conforme necessário.

### <a name="suggested-timeline"></a>Linha do tempo sugerida

Veja uma sugestão de linha do tempo para um piloto de 30 dias:

- Uma semana antes do início piloto: Enviar comunicação inicial para usuários piloto.
- Dia 1: Enviar comunicação de início para usuários piloto.
- Dia 7: Realizar a primeira reunião semanal de ponto de verificação da equipe de projeto.
- Dia 14: Enviar comunicação de ponto médio para seus usuários piloto, realizar uma reunião semanal de ponto de verificação da equipe de projeto.
- Dia 21: realizar uma reunião semanal de ponto de verificação da equipe de projeto.
- Dia 30: Enviar comunicação final aos usuários piloto.
- Dias 31 a 45: Avalie os resultados piloto e planeje as próximas etapas.

## <a name="6-assess-learnings-and-evaluate-your-go-forward-plan"></a>6. Avalie os aprendizados e avalie seu plano de avanço

Após a conclusão do piloto, é hora de reunir todas as pesquisas de comentários, estatísticas de rede finais e tíquetes de suporte para análise em relação às suas metas e determinar se você implementará seu plano de avanço. Você pode descobrir que sua organização está pronta para uma ampla implantação, ou deseja estender seu piloto para mais usuários, ou você deseja revisitar o piloto posteriormente depois que quaisquer preocupações identificadas foram atenuadas. Lembre-se de que o piloto é uma ótima maneira de prever resultados técnicos e do usuário em um _ambiente controlado;_ seja cuidadoso sobre como avançar muito rapidamente.

Se os resultados indicarem:

- **Suas metas piloto (por exemplo, satisfação** do usuário e qualidade de rede) foram atingidas, você deve estar pronto para prosseguir com a próxima fase da distribuição. Dependendo das metas do seu projeto, isso pode ser um dos seguintes:
  - Estender o piloto a participantes adicionais
  - [Habil Teams ao lado Skype for Business (**modo Ilhas)** para alguns ou todos os da sua organização](./setting-your-coexistence-and-upgrade-settings.md)
  - [Atualizando usuários de Skype for Business para Teams (**Teams somente** modo) para alguns ou para toda a sua organização](./setting-your-coexistence-and-upgrade-settings.md)
- Seu piloto não atingiu os resultados que você queria **(por exemplo,** satisfação do usuário e qualidade de rede), de tempo para fazer os ajustes apropriados ao seu plano e revisitar seu piloto.

> [!Tip]
> Aliste seus participantes piloto como campeões pares para ajudar a evangelizar e a incluir novos usuários Teams. Os campeões de pares podem se relacionar facilmente com outros usuários, compartilhar suas próprias experiências e aprendizados e oferecer suporte e orientação aos colegas. Saiba mais sobre [campeões](https://go.microsoft.com/fwlink/?linkid=859068) e como você pode usá-los em sua própria lançamento.