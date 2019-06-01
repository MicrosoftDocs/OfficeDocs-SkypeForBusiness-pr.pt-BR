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
description: Baixe o guia de capacitação do site para planejar a implementação de suas equipes e acelerar e otimizar a adoção, a percepção de qualidade e a satisfação do usuário.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65878cc54973b67a604b08d3579553bca6ca8e4a
ms.sourcegitcommit: ff777b61573b9d90e2d49c49b41fad654eeb3af7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/31/2019
ms.locfileid: "34652734"
---
# <a name="deploy-my-service"></a>Implantar meu serviço

Este artigo oferece uma visão geral dos requisitos para a implantação adequada dos serviços de voz em nuvem. Seguindo a orientação prescritiva para a implantação de serviços de voz na nuvem, você pode garantir que tenha êxito em conta de todos os requisitos e gerar resultados reproduzíveis.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Guias de habilitação de sites para cargas de trabalho de voz do Microsoft Teams

Use este guia estratégico para ajudar sua organização a planejar e executar a distribuição com êxito dos recursos de voz do Microsoft Teams em uma base site a site.

Incluindo todas as atividades necessárias, linhas do tempo recomendadas e links para a orientação correspondente para cada atividade, este guia estratégico aborda a orientação de ponta a ponta para ajudar a garantir uma implantação de voz bem-sucedida do teams para um determinado site, com foco em fatores importantes para o usuário.

Ao completar as atividades neste guia estratégico, sua organização pode:

-   Planeje e agende com eficiência a distribuição de suas equipes.

-   Acelerar e otimizar a adoção pelo usuário.

-   Reduza as necessidades de suporte e aumente a satisfação do usuário.

> [!NOTE]
> Este artigo e o guia estratégico associado não têm a finalidade de descrever todas as etapas de configuração técnica necessárias para a habilitação de serviços ou o fornecimento de Tom de discagem para um site específico. Em vez disso, eles se concentram em atividades e tarefas recomendadas para os usuários integrados facilmente e têm a necessidade de começar a consumir cargas de trabalho de voz do teams por meio de uma transição rápida e tranqüila com uma alta taxa de adoção e minimizar os requisitos de suporte. Para obter orientação técnica sobre como configurar melhor seu ambiente para a voz do Teams, consulte as listas de verificação de integração para [configurar as cargas de trabalho de voz](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), configurando o [Roteamento direto nas equipes](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [recursos essenciais](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)do Teams, [rede para equipes](onboarding-checklist-configure-networking.md)e habilitando o [Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco guias

O foco do guia estratégico é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz do teams. Atividades e tarefas são agrupadas nas seguintes áreas de foco:

-   Validação da preparação do serviço
    - Audioconferência
    - Planos de Chamadas
    - Roteamento Direto

-   Habilitação do usuário

-   Pontos de extremidade

-   Uso e qualidade

-   Adotar

O [Guia de ativação do site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma pasta de trabalho do Microsoft Excel. Cada uma dessas cinco áreas de foco é uma planilha separada na pasta de trabalho, e cada tarefa de implantação e atividade é agrupada em uma dessas planilhas.

![Captura de tela do guia de capacitação do site] (media/deploy-my-service-image1.png "Captura de tela do guia estratégico")

> [!NOTE]
> Você criará uma instância separada do guia estratégico para cada site em escopo para a distribuição da sua equipe.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Como usar o guia estratégico

Independentemente do tamanho e da complexidade do local, a habilitação de cada site exige que você planeje suas tarefas e atividades desde o início e as execute em ordem ideal, antes, durante e depois da distribuição de serviço real. Recomendamos que você siga estas etapas ao planejar e executar sua própria jornada para a Microsoft Teams Voice.

1. Baixe o [Guia de capacitação do site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para voz do Microsoft Teams.

2. Crie uma cópia separada do guia estratégico para cada site.

3. Na guia da planilha chamada **guia estratégico para {sitename-código}**, substitua **{SiteName-código}** pelo nome do site e/ou código do site relevante.

4. Digite o **nome do site, o código do site**e a **data de lançamento planejada**, conforme ilustrado abaixo. Essa é uma etapa crítica, pois ele ajusta os prazos recomendados para cada atividade no guia estratégico.

   ![Exemplo com o nome do site, o código do site e a data de lançamento planejada] (media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, NY01 de código de site e data de lançamento planejada de 20 de março de 18")

5. Examine cada atividade, execute as ações necessárias e atualize o status enquanto percorre a linha do tempo. O status é representado graficamente, conforme descrito abaixo:
  
   - ![Ilustração de uma marca](media/deploy-my-service-image3.png) de seleção verde **Sim ou não aplicável (verde):** a atividade foi concluída ou não é aplicável para este site, e nenhuma ação adicional é necessária.</li>
   - ![Ilustração de um ponto](media/deploy-my-service-image4.png) de exclamação amarelo <strong>a atividade ainda não foi concluída (amarela):</strong> a atividade ainda não foi concluída e deve ser atualizada para Sim ou não em seu cronograma.</li>
   - ![Ilustração de um X vermelho indicando não](media/deploy-my-service-image5.png) <strong>(vermelho):</strong> a atividade não pode ser concluída devido a um problema e deve ser transportada para a reunião de status do projeto.</li></ul>

6. O status é acumulado dentro de cada seção, e o título da seção é formatado com um desses indicadores de status. O **status semanal** também é atualizado automaticamente.

![Captura de tela de roll-ups de status semanal no guia estratégico] (media/deploy-my-service-image6.png "Captura de tela de roll-ups de status semanal no guia estratégico")

> [!TIP]
> Repita as etapas acima para todos os locais que você tem.

> [!IMPORTANT]
> Algumas etapas podem não ser aplicáveis a todos os locais e sites. Se uma atividade específica não for relevante para um site, você deverá selecionar **não aplicável** para esta atividade. **Não exclua** linhas no guia estratégico; Se fizer isso, as fórmulas de acúmulo de status não funcionarão.<br/><br/>
Preste atenção às atividades que podem levar mais tempo do que você planejou, como portabilidade de números e atividades de compras. Essas atividades podem afetar negativamente a linha do tempo de implantação do site. Certifique-se de revisar e atualizar a lista de atividades e a linha do tempo associada semanalmente e apresentá-las em [reuniões de Comitê](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) de direcionamento para garantir que os interessados estejam cientes do status de cada site e dos possíveis desvios do cronograma de implantação.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida se o guia de habilitação de site é necessário para a sua implantação.</li><li>Decida quem será responsável por personalizar o guia de viabilização do site para o Microsoft Teams para cada site que você implantar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o guia de capacitação do site</a>.</li><li>Personalize o guia de viabilização de sites para seu primeiro site.</li><li>Repita conforme necessário para sites adicionais.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->