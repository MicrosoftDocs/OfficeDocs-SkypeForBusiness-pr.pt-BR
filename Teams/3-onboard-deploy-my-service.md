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
description: Baixe o Playbook de Habilitação do Site para planejar sua Teams e acelerar e otimizar a adoção do usuário, a percepção de qualidade e satisfação.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b5c027da20c6c305fd5924cd6483c5cbd63b8ddd
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733536"
---
# <a name="deploy-my-service"></a>Implantar meu serviço

Este artigo apresenta uma visão geral dos requisitos para a implantação adequada dos serviços de voz na nuvem. Seguindo as diretrizes prescritivas para a implantação de serviços de voz na nuvem, você pode se certificar de que contabilização com êxito de todos os requisitos e resultados repetidos.

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a>Playbook de habilitação de site para Microsoft Teams de voz

Use este playbook para ajudar sua organização a planejar e executar com êxito a Microsoft Teams recursos de voz em um site por site.

Incluindo todas as atividades necessárias, cronogramas recomendados e links para orientações correspondentes para cada atividade, este manual aborda as diretrizes de ponta a ponta para ajudar a garantir uma implantação de voz Teams bem-sucedida para um determinado site, concentrando-se em fatores importantes para o usuário.

Ao concluir as atividades neste playbook, sua organização pode:

-   Planeje e agende efetivamente sua Teams de lançamento.

-   Acelere e otimize a adoção do usuário.

-   Reduza as necessidades de suporte e aumente a satisfação do usuário.

> [!NOTE]
> Este artigo e o playbook associado não se destinam a descrever cada etapa de configuração técnica necessária para habilitar o serviço ou fornecer tom de discagem para um site específico. Em vez disso, eles se concentram em atividades e tarefas recomendadas para os usuários de integração facilmente e fazem com que eles comecem a consumir cargas de trabalho de voz Teams por meio de uma transição rápida e suave com uma alta taxa de adoção, minimizando os requisitos de suporte. Para obter orientações técnicas sobre como configurar melhor seu ambiente para Teams voz, consulte as listas de verificação de integração para configurar [cargas](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)de trabalho de voz do Teams, configurando o [Roteamento](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)Direto em Teams , recursos principais do [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)rede para [Teams](prepare-network.md)e habilitando Microsoft 365 [ou Office 365](onboarding-checklist-enable-office-365.md).

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a>Áreas de foco de playbook

O foco da playbook é abordar os fatores que influenciam a percepção do usuário de uma implantação Teams voz. Atividades e tarefas são agrupadas nas seguintes áreas de foco:

-   Validação da preparação do serviço
    - Audioconferência
    - Planos de Chamadas
    - Roteamento Direto

-   Habilitar o usuário

-   Pontos de extremidade

-   Uso e qualidade

-   Adoção

O [Manual de Reprodução de Habilitação de Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma Microsoft Excel de trabalho. Cada uma dessas cinco áreas de foco é uma planilha separada na pasta de trabalho, e cada tarefa e atividade de implantação é agrupada em uma dessas planilhas.

![Captura de tela do playbook de habilitação do site.](media/deploy-my-service-image1.png "Captura de tela do playbook")

> [!NOTE]
> Você criará uma instância separada do playbook para cada site no escopo para sua Teams de lançamento.

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a>Como usar o playbook

Independentemente do tamanho e da complexidade do local, a habilitação de cada site exige que você planeje suas tarefas e atividades com antecedência suficiente e execute-as em ordem ideal antes, durante e após a ativação real do serviço. Recomendamos que você siga estas etapas enquanto planeja e executa sua própria jornada para Microsoft Teams voz.

1. Baixe o [Playbook de Habilitação](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) do Site para Voz (Playbook) para Microsoft Teams Voice.

2. Crie uma cópia separada do playbook para cada site.

3. Na guia para a planilha chamada **Playbook for {SiteName-Code}**, substitua **{SiteName-Code}** pelo nome de site relevante e/ou código do site.

4. Insira o **nome do site, o código do site** e a data de início **planejada,** conforme ilustrado abaixo. Esta é uma etapa crítica, pois ajusta os prazos recomendados para cada atividade no playbook.

   ![Exemplo com nome do site, código do site e data de início planejada.](media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código do site NY01 e data de início planejada de 20-Mar-18")

5. Revise cada atividade, tome as ações necessárias e atualize o status enquanto você passa pela linha do tempo. O status é representado graficamente, conforme descrito abaixo:
  
   - ![Ilustração de uma marca de verificação verde.](media/deploy-my-service-image3.png) **Sim ou não aplicável (verde):** A atividade foi concluída ou não é aplicável para este site e nenhuma ação é necessária.</li>
   - ![Ilustração de um ponto de exclamação amarelo.](media/deploy-my-service-image4.png) <strong>A atividade ainda não foi concluída (amarelo):</strong> A atividade ainda não foi concluída e deve ser atualizada para Sim ou Não em sua agenda.</li>
   - ![Ilustração de um X vermelho indicando não.](media/deploy-my-service-image5.png) <strong>Não (vermelho):</strong> A atividade não pode ser concluída devido a um problema e deve ser levada para a reunião de status do projeto.</li></ul>

6. O status é rolado para cima em cada seção e o título da seção é formatado com um desses indicadores de status. **O status semanal** também é atualizado automaticamente.

![Captura de tela das roll-ups de status semanais no playbook.](media/deploy-my-service-image6.png "Captura de tela das roll-ups de status semanais no playbook")

> [!TIP]
> Repita as etapas acima para todos os locais que você tem.

> [!IMPORTANT]
> Algumas etapas podem não ser aplicáveis a todos os locais e sites. Se uma atividade específica não for relevante para um site, selecione **Não aplicável** a essa atividade. **NÃO EXCLUa** nenhuma linha no playbook; se você fizer isso, as fórmulas de rolagem de status não funcionarão.<br/><br/>
Preste atenção às atividades que podem levar mais tempo do que você planejou, como atividades de portação de número e compras. Essas atividades podem afetar negativamente a linha do tempo de implantação do site. Certifique-se de revisar e atualizar a lista de atividades [](./envision-steering-committee-complete-guide.md) e a linha do tempo associada semanalmente e apresentá-las em reuniões do comitê de direção para garantir que as partes interessadas estão cientes do status de cada site e quaisquer possíveis desvios do cronograma de implantação.

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/>Pontos de decisão</td><td><ul><li>Decida se o Manual de Habilitação de Site é necessário para sua implantação.</li><li>Decida quem será responsável por personalizar o Playbook de Habilitação de Site para Microsoft Teams para cada site que você implantar.</li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/>Próximas etapas</td><td><ul><li><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o Playbook de Habilitação do Site.</a></li><li>Personalize o Playbook de Habilitação do Site para seu primeiro site.</li><li>Repita conforme necessário para sites adicionais.</li></ul></td></tr>
</table>

<!--ENDOFSECTION-->