---
title: Implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Baixe o Guia estratégico habilitação de Site para planejar sua distribuição de equipes e acelerar e otimizar a adoção de usuário, percepção de qualidade e satisfação.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 397917e8e5e2fc2c2707e9bbad67e031d96c09dc
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400856"
---
# <a name="deploy-my-service"></a>Implantar meu serviço

Este artigo fornece uma visão geral dos requisitos de adequadamente implantando serviços de nuvem de voz. Seguindo a orientação prescritiva para a implantação de serviços de voz de nuvem, você pode assegurar com êxito para todos os requisitos de conta e fornecer resultados repetidos.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guia estratégico de habilitação de site para cargas de trabalho do Microsoft Teams voz

Use este guia estratégico para ajudar sua organização com êxito planejar e executar a distribuição dos recursos de voz do Microsoft Teams em uma base de site por site.

Incluindo necessárias todas as atividades, recomendado cronogramas e links para orientação correspondente para cada atividade, este playbook aborda a orientação de ponta a ponta para ajudar a garantir uma implantação bem-sucedida de voz de equipes para um determinado site, concentrando-se em fatores importantes para o usuário.

Ao concluir as atividades deste playbook, sua organização pode:

-   Efetivamente, planeje e agende a distribuição de equipes.

-   Acelerar e otimizar a adoção dos usuários.

-   Reduzir as necessidades de suporte e aumentar a satisfação do usuário.

> [!NOTE]
> Este artigo e o playbook associado não são destinados para descrever cada etapa de configuração técnicos necessários para habilitação de serviços ou fornecer um tom de discagem a um site específico. Em vez disso, eles se concentrar em atividades e tarefas recomendadas aos usuários onboard facilmente e fazê-las a começar a consumir cargas de trabalho de voz de equipes por meio de uma transição rápida e suave com uma taxa de adoção alta, enquanto minimiza os requisitos de suporte. Para obter orientações técnicas sobre como configurar melhor de voz de equipes em seu ambiente, consulte as listas de verificação para [configuração de cargas de trabalho de voz de equipes](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [Configurando o roteamento direta em equipes](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), inclusão [equipes principais recursos](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [de rede para equipes](onboarding-checklist-configure-networking.md)e a [ativação do Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco de playbook

O foco do playbook é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz de equipes. Atividades e tarefas estão agrupadas nas seguintes áreas de foco:

-   Validação da preparação do serviço
    - Audioconferência
    - Planos de Chamadas
    - Roteamento Direto

-   Habilitação de usuário

-   Pontos de extremidade

-   Uso e qualidade

-   Adoção

O [Site Playbook de habilitação para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma pasta de trabalho do Microsoft Excel. Cada uma dessas áreas de foco de cinco é uma planilha separada na pasta de trabalho, e cada tarefa de implantação e a atividade são agrupados em um dessas folhas.

![Captura de tela de playbook] (media/deploy-my-service-image1.png "Captura de tela de playbook")

> [!NOTE]
> Você criará uma instância separada do playbook para cada site no escopo para a distribuição de equipes.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Como usar o playbook

Independentemente do tamanho e complexidade do local, permitindo que cada site requer que você planeje suas tarefas e atividades antecipado suficiente — e executá-los na ordem ideal — antes, durante e depois da distribuição de serviço real. Recomendamos que você siga estas etapas ao planejar e executar sua própria jornada Voice Teams da Microsoft.

1. Baixe o [Guia estratégico de habilitação de Site para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para equipes da Microsoft Voice.

2. Crie uma cópia separada do playbook para cada site.

3. Na guia da planilha chamado **Playbook para {nome_do_site código}**, substitua **{Nome_do_site código}** com o nome do site relevante e/ou o código do site.

4. Insira o **nome do Site, o código do Site**e a **Data de início planejado**, conforme ilustrado abaixo. Isso é uma etapa importante, porque ele ajusta os prazos recomendados para todas as atividades no playbook.

   ![Exemplo com o nome do site de Nova York, código de site NY01 e a data de início planejada de 20-Mar-18] (media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código de site NY01 e a data de início planejada de 20-Mar-18")

5. Revisar cada atividade, execute as ações necessárias e atualizar o status conforme você percorrer a linha do tempo. Status é representada graficamente, conforme descrito abaixo:
   <ul>
   <li>![Marca de seleção verde](media/deploy-my-service-image3.png) <strong>Sim ou não aplicável (verde):</strong> a atividade foi concluída, ou não for aplicável para este site e nenhuma outra ação será necessária.</li>
   <li>![Ponto de exclamação amarelo](media/deploy-my-service-image4.png) <strong>a atividade não será concluída ainda (amarelado):</strong> a atividade ainda não tiver sido concluída e deve ser atualizada para Sim ou não em sua agenda.</li>
   <li>![X vermelho](media/deploy-my-service-image5.png) <strong>Nenhuma (vermelho):</strong> a atividade não pode ser concluída devido a um problema e deve ser transmitida para a reunião de status do projeto.</li></ul>

6. O status é acumulado dentro de cada seção e o cabeçalho de seção é formatado com um desses indicadores de status. **Status semanais** também é atualizado automaticamente.

![Captura de tela dos semanal status acúmulos de playbook] (media/deploy-my-service-image6.png "Captura de tela dos semanal status acúmulos de playbook")

> [!TIP]
> Repita as etapas acima para todos os locais que você tem.

> [!IMPORTANT]
> Algumas etapas podem não ser aplicáveis a todos os sites e locais. Se uma atividade específica não é relevante para um site, você deve selecionar **não aplicável** para esta atividade. **Não exclua** qualquer linhas no playbook; Se fizer isso, as fórmulas de acúmulo de status não funcionarão.<br/><br/>
Preste atenção às atividades que podem levar mais tempo do que o planejado, como o número de porta e atividades de compras. Essas atividades podem afetar negativamente o cronograma de implantação do site. Certifique-se de revisar e atualizar a lista de atividade e a linha do tempo associada semanalmente e apresentá-las em [reuniões comitê de orientação](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para assegurar que os participantes estão cientes do status de cada site e quaisquer possíveis desvios da agenda de implantação.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/>Pontos de decisão</td><td><ul><li>Decida se o Site habilitação de Playbook é necessária para sua implantação.</li><li>Decida quem será responsável por Personalizando o Playbook de habilitação de Site for Microsoft Teams para todos os sites que você vai implantar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/>Próximas etapas</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o Playbook de habilitação do Site</a>.</li><li>Personalize o Playbook de habilitação de Site para o seu primeiro site.</li><li>Repita conforme necessário para outros sites.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->