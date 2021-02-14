---
title: Implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Baixe o Caderno de Habilitação de Site para planejar a adoção do Teams e acelerar e otimizar a adoção do usuário, percepção de qualidade e satisfação.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae9a1e6abf7dbf97e625be4eb69a0ef95b1910da
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532568"
---
# <a name="deploy-my-service"></a>Implantar meu serviço

Este artigo apresenta uma visão geral dos requisitos para a implantação adequada de serviços de voz na nuvem. Seguindo as diretrizes de implantação dos serviços de voz na nuvem, você pode garantir que todos os requisitos são responsáveis por todos os requisitos e fornecer resultados repetidos.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Livro de reprodução de habilitação de site para cargas de trabalho de voz do Microsoft Teams

Use este livro de reprodução para ajudar sua organização a planejar e executar com êxito a adoção de recursos de voz do Microsoft Teams por site.

Incluindo todas as atividades necessárias, linhas do tempo recomendadas e links para as orientações correspondentes para cada atividade, este livro aborda orientações de ponta a ponta para ajudar a garantir uma implantação bem-sucedida de voz do Teams para um determinado site, com foco em fatores que são importantes para o usuário.

Ao concluir as atividades neste livro de reprodução, sua organização pode:

-   Planeje e agende efetivamente a sua adoção do Teams.

-   Acelere e otimize a adoção do usuário.

-   Reduza as necessidades de suporte e aumente a satisfação do usuário.

> [!NOTE]
> Este artigo e o manual de reprodução associado não se destinam a descrever todas as etapas de configuração técnicas necessárias para a habilitação do serviço ou fornecer um tom de discagem para um site específico. Em vez disso, eles se concentram em atividades e tarefas recomendadas para os usuários de integração facilmente e fazem com que eles comecem a consumir cargas de trabalho de voz do Teams por meio de uma transição rápida e tranquila com uma alta taxa de adoção, minimizando os requisitos de suporte. Para obter orientação técnica sobre como configurar melhor seu ambiente para a voz do Teams, confira as listas de verificação de integração para configurar cargas de trabalho de voz do [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurando o Roteamento Direto no [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)recursos principais do [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)rede para [o Teams](prepare-network.md)e habilitando o Microsoft [365 ou o Office 365.](onboarding-checklist-enable-office-365.md)

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco do livro de reprodução

O foco do livro de reprodução é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz do Teams. Atividades e tarefas são agrupadas nas seguintes áreas de foco:

-   Validação da preparação do serviço
    - Audioconferência
    - Planos de Chamadas
    - Roteamento Direto

-   Habilitar o usuário

-   Pontos de extremidade

-   Uso e qualidade

-   Adoção

O [Manual de Habilitação de Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma planilha do Microsoft Excel. Cada uma dessas cinco áreas de foco é uma planilha separada na pasta de trabalho, e cada tarefa e atividade de implantação é agrupada em uma dessas planilhas.

![Captura de tela do livro de reprodução de habilitação de site](media/deploy-my-service-image1.png "Captura de tela do livro de reprodução")

> [!NOTE]
> Você criará uma instância separada do playbook para cada site no escopo da sua adoção do Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Como usar o livro de reprodução

Independentemente do tamanho e da complexidade do local, a habilitação de cada site exige que você planeje suas tarefas e atividades cedo o suficiente e execute-as em ordem ideal antes, durante e após a ativação real do serviço. Recomendamos que você siga estas etapas enquanto planeja e executa sua própria jornada para o Microsoft Teams Voice.

1. Baixe o [Manual de Habilitação](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) de Site para Voz (Playbook) para o Microsoft Teams Voice.

2. Crie uma cópia separada do livro de reprodução para cada site.

3. Na guia da planilha chamada **Playbook para {SiteName-Code},** substitua **{SiteName-Code}** pelo nome do site relevante e/ou código do site.

4. Insira o **nome do site, o código do site** e a data de início **planejada,** conforme ilustrado abaixo. Essa é uma etapa crítica, pois ajusta os prazos recomendados para cada atividade no playbook.

   ![Exemplo com o nome do site, código do site e data de início planejado](media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código de site NY01 e data de início planejado de 20 de março-18")

5. Revise cada atividade, tome as ações necessárias e atualize o status conforme você passa pela linha do tempo. O status é representado graficamente, conforme descrito abaixo:
  
   - ![Ilustração de uma marca de seleção verde Sim ou não aplicável ](media/deploy-my-service-image3.png) **(verde):** a atividade foi concluída ou não é aplicável para este site e nenhuma ação é necessária.</li>
   - ![Ilustração de um ponto de exclamação amarelo A atividade ainda não foi concluída ](media/deploy-my-service-image4.png) <strong>(amarela):</strong> a atividade ainda não foi concluída e deve ser atualizada para Sim ou Não no cronograma.</li>
   - ![Ilustração de um X vermelho indicando não (vermelho): a atividade não pode ser concluída devido a um problema e deve ser transportada para a reunião ](media/deploy-my-service-image5.png) <strong></strong> de status do projeto.</li></ul>

6. O status é roll up em cada seção e o título da seção é formatado com um desses indicadores de status. **O status semanal** também é atualizado automaticamente.

![Captura de tela das roll-ups de status semanais no livro de reprodução](media/deploy-my-service-image6.png "Captura de tela das roll-ups de status semanais no livro de reprodução")

> [!TIP]
> Repita as etapas acima para todos os locais que você tem.

> [!IMPORTANT]
> Algumas etapas podem não ser aplicáveis a todos os locais e sites. Se uma atividade específica não for relevante para um site, você deverá selecionar **Não aplicável** para essa atividade. **NÃO EXCLUA** linhas no livro de reprodução; se você fizer isso, as fórmulas de roll-up de status não funcionarão.<br/><br/>
Preste atenção às atividades que podem levar mais tempo do que você planejou, como atividades de portação e aquisição de números. Essas atividades podem afetar negativamente a linha do tempo de implantação do site. Revise e atualize a lista de atividades e a linha [](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) do tempo associada semanalmente e apresente-as em reuniões de comitê de direção para garantir que os participantes estão cientes do status de cada site e de possíveis desvios do cronograma de implantação.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida se o Manual de Habilitação de Site é necessário para sua implantação.</li><li>Decida quem será responsável por personalizar o Manual de Habilitação de Site do Microsoft Teams para cada site que você implantar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o Livro de Reprodução de Habilitação de Site.</a></li><li>Personalize o Manual de Habilitação de Site para seu primeiro site.</li><li>Repita conforme necessário para sites adicionais.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->