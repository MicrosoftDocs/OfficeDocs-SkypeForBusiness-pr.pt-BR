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
description: Baixe o Playbook de Habilitação de Site para planejar a adoção do Teams e acelerar e otimizar a adoção do usuário, a percepção de qualidade e a satisfação.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112627"
---
# <a name="deploy-my-service"></a>Implantar meu serviço

Este artigo apresenta uma visão geral dos requisitos para a implantação adequada dos serviços de voz na nuvem. Seguindo as diretrizes prescritivas para a implantação de serviços de voz na nuvem, você pode se certificar de que contabilização com êxito de todos os requisitos e resultados repetidos.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook de habilitação de site para cargas de trabalho de voz do Microsoft Teams

Use este playbook para ajudar sua organização a planejar e executar com êxito a lançamento de recursos de voz do Microsoft Teams em uma base site a site.

Incluindo todas as atividades necessárias, cronogramas recomendados e links para as diretrizes correspondentes para cada atividade, este manual aborda as diretrizes de ponta a ponta para ajudar a garantir uma implantação de voz bem-sucedida do Teams para um determinado site, concentrando-se em fatores importantes para o usuário.

Ao concluir as atividades neste playbook, sua organização pode:

-   Planeje e agende efetivamente sua lançamento do Teams.

-   Acelere e otimize a adoção do usuário.

-   Reduza as necessidades de suporte e aumente a satisfação do usuário.

> [!NOTE]
> Este artigo e o playbook associado não se destinam a descrever cada etapa de configuração técnica necessária para habilitar o serviço ou fornecer tom de discagem para um site específico. Em vez disso, eles se concentram nas atividades e tarefas recomendadas para os usuários de integração facilmente e fazem com que eles comecem a consumir cargas de trabalho de voz do Teams por meio de uma transição rápida e suave com uma alta taxa de adoção, minimizando os requisitos de suporte. Para obter orientações técnicas sobre como configurar melhor seu ambiente para a voz do Teams, consulte as listas de verificação de integração para configurar cargas de trabalho de voz do [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurando Roteamento Direto no [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)recursos principais do [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)rede para [o Teams](prepare-network.md)e habilitando o Microsoft [365 ou o Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco de playbook

O foco da playbook é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz do Teams. Atividades e tarefas são agrupadas nas seguintes áreas de foco:

-   Validação da preparação do serviço
    - Audioconferência
    - Planos de Chamadas
    - Roteamento Direto

-   Habilitar o usuário

-   Pontos de extremidade

-   Uso e qualidade

-   Adoção

O [Playbook de Habilitação de Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma planilha do Microsoft Excel. Cada uma dessas cinco áreas de foco é uma planilha separada na pasta de trabalho, e cada tarefa e atividade de implantação é agrupada em uma dessas planilhas.

![Captura de tela do playbook de habilitação do site](media/deploy-my-service-image1.png "Captura de tela do playbook")

> [!NOTE]
> Você criará uma instância separada do playbook para cada site no escopo da sua adoção do Teams.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Como usar o playbook

Independentemente do tamanho e da complexidade do local, a habilitação de cada site exige que você planeje suas tarefas e atividades com antecedência suficiente e execute-as em ordem ideal antes, durante e após a ativação real do serviço. Recomendamos que você siga estas etapas ao planejar e executar sua própria jornada até a voz do Microsoft Teams.

1. Baixe o [Playbook de Habilitação do Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para o Microsoft Teams Voice.

2. Crie uma cópia separada do playbook para cada site.

3. Na guia para a planilha chamada **Playbook for {SiteName-Code}**, substitua **{SiteName-Code}** pelo nome de site relevante e/ou código do site.

4. Insira o **nome do site, o código do site** e a data de início **planejada,** conforme ilustrado abaixo. Esta é uma etapa crítica, pois ajusta os prazos recomendados para cada atividade no playbook.

   ![Exemplo com nome do site, código do site e data de início planejada](media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código do site NY01 e data de início planejada de 20-Mar-18")

5. Revise cada atividade, tome as ações necessárias e atualize o status enquanto você passa pela linha do tempo. O status é representado graficamente, conforme descrito abaixo:
  
   - ![Ilustração de uma marca de verificação verde Sim, ou não aplicável ](media/deploy-my-service-image3.png) **(verde):** a atividade foi concluída ou não é aplicável para este site e nenhuma ação é necessária.</li>
   - ![Ilustração de um ponto de exclamação amarelo A atividade ainda não foi concluída ](media/deploy-my-service-image4.png) <strong>(amarela):</strong> a atividade ainda não foi concluída e deve ser atualizada para Sim ou Não em sua agenda.</li>
   - ![Ilustração de um X vermelho indicando não (vermelho): a atividade não pode ser concluída devido a um problema e deve ser carregada para a reunião ](media/deploy-my-service-image5.png) <strong></strong> de status do projeto.</li></ul>

6. O status é rolado para cima em cada seção e o título da seção é formatado com um desses indicadores de status. **O status semanal** também é atualizado automaticamente.

![Captura de tela das roll-ups de status semanais no playbook](media/deploy-my-service-image6.png "Captura de tela das roll-ups de status semanais no playbook")

> [!TIP]
> Repita as etapas acima para todos os locais que você tem.

> [!IMPORTANT]
> Algumas etapas podem não ser aplicáveis a todos os locais e sites. Se uma atividade específica não for relevante para um site, selecione **Não aplicável** a essa atividade. **NÃO EXCLUa** nenhuma linha no playbook; se você fizer isso, as fórmulas de rolagem de status não funcionarão.<br/><br/>
Preste atenção às atividades que podem levar mais tempo do que você planejou, como atividades de portação de número e compras. Essas atividades podem afetar negativamente a linha do tempo de implantação do site. Certifique-se de revisar e atualizar a lista de atividades [](./envision-steering-committee-complete-guide.md) e a linha do tempo associada semanalmente e apresentá-las em reuniões do comitê de direção para garantir que as partes interessadas estão cientes do status de cada site e quaisquer possíveis desvios do cronograma de implantação.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida se o Manual de Habilitação de Site é necessário para sua implantação.</li><li>Decida quem será responsável por personalizar o Playbook de Habilitação de Site para o Microsoft Teams para cada site que você implantará.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o Playbook de Habilitação do Site.</a></li><li>Personalize o Playbook de Habilitação do Site para seu primeiro site.</li><li>Repita conforme necessário para sites adicionais.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->