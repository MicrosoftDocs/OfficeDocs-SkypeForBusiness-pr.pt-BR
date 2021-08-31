---
title: Microsoft 365 Governo - GCC implantações
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Diretrizes para os profissionais de Microsoft 365 implantações em entidades que lidam com dados sujeitos à regulamentação do governo dos EUA
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: a3013b89ab384ca3f66c04bee06ccbbaf57445ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727600"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planejar Microsoft 365 Government - GCC implantações

Esta orientação é para profissionais de IT que estão conduzindo implantações do Microsoft 365 em entidades governamentais federais, estaduais, locais, tribais ou territoriais dos EUA ou outras entidades que lidam com dados sujeitos a regulamentos e requisitos governamentais, onde o uso do Microsoft 365 Government - GCC é apropriado para atender a esses requisitos. Novo 26 de março de 2020: Não perca nosso guia de Início Rápido baixável [para GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> Microsoft Teams está enfrentando um pico enorme em chamadas online e conferência de áudio/vídeo devido à pandemia de coronavírus (COVID-19).<br/>
> 
>Em resposta ao aumento sem precedentes de chamadas e para garantir a continuidade e a disponibilidade, a Microsoft está permitindo que Microsoft Teams GCC servidores de áudio/vídeo aproveitem a capacidade de processamento em nossos datacenters comerciais, bem como em nossos datacenters governamentais.<br/>
> 
>Esses servidores de áudio/vídeo residem nos servidores de limite Microsoft Azure FedRAMP High accreditation nos Estados Unidos e não armazenam conteúdo do cliente. No entanto, esses servidores estão processamento de áudio e vídeo para chamadas e conferências e estão operando sob nossa equipe comercial durante esse período provisório.<br/>
> 
>Equipes qualificadas e monitoradas estão monitorando esses servidores para acesso potencial aos dados do cliente, revendo os log-ons interativos para esses servidores. A equipe qualificada GCC requisitos para acesso ao conteúdo do cliente. Para obter detalhes sobre os requisitos de triagem, consulte [a GCC descrição do serviço](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Obrigado por seu suporte à medida que fazemos as etapas para garantir que nossos serviços permaneçam disponíveis e confiáveis nesses tempos extraordinários.<br/>


> [!NOTE]
> Se sua organização já tiver atendido aos requisitos de Microsoft 365 Government - GCC de qualificação e aplicados e aceitos no programa, você poderá ignorar as etapas 1 e 2 e ir diretamente para a etapa 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Etapa 1. Determine se sua organização precisa Microsoft 365 Governo - GCC e atende aos requisitos de qualificação. 

O Microsoft 365 Government - GCC fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem, incluindo FedRAMP Moderado e requisitos para a justiça criminal e sistemas de informações fiscais federais (tipos de dados CJI e FTI).

Além de aproveitar os recursos e recursos do Microsoft 365, as organizações se beneficiam dos seguintes recursos exclusivos do Microsoft 365 Government - GCC:

-   O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços de Microsoft 365 comerciais da Microsoft.
-   O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
-   O acesso ao conteúdo do cliente da sua organização é restrito à equipe da Microsoft.
-   Microsoft 365 Government - GCC está em conformidade com certificações e acreditações necessárias para clientes do Setor Público dos EUA.

Você pode encontrar mais informações sobre a oferta Microsoft 365 government - GCC para clientes do Governo dos EUA em planos Microsoft 365 [Government](https://products.office.com/government/compare-office-365-government-plans), incluindo requisitos [de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Microsoft 365 descrição](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) do serviço do Governo dos EUA descreve os benefícios da plataforma, que são centralizados em torno de atender aos requisitos de conformidade nos Estados Unidos.

> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma Excel de trabalho e adicionar duas colunas: relevantes para minha organização **Y/N** e atende às necessidades da minha organização **Y/N**. Em seguida, você pode revisar essa lista com seus colegas para confirmar se esse serviço atende às necessidades da sua organização.

|    |     |
|-----------|------------|
| ![Um ícone que representa pontos de decisão.](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se Microsoft 365 governo - GCC é apropriado para sua organização.</li><li>Confirme se sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> Microsoft 365 Government - GCC está disponível apenas nos Estados Unidos. Os clientes do Governo não-EUA podem escolher entre vários Microsoft 365 [do Governo.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Etapa 2. Aplicar para Microsoft 365 Government - GCC

Depois de decidir que esse serviço é o correto para sua organização, inicie o processo de [solicitação para esse serviço aqui](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Etapa 3. Entenda Microsoft 365 Government - GCC configurações de segurança padrão.

Recomendamos que você tenha tempo [](enable-features-office-365.md) para analisar cuidadosamente suas configurações de administração e segurança antes de modificá-las e considerar os impactos na conformidade antes de fazer alterações nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão.](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você modificará qualquer uma das configurações de segurança padrão Microsoft 365 Government - GCC, resolvendo primeiro entender o impacto de quaisquer alterações que você possa fazer.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Etapa 4. Entenda quais recursos estão indisponíveis ou desabilitados por padrão.

Para acomodar os requisitos de nossos clientes de nuvem do governo, há algumas diferenças entre Microsoft 365 Government - GCC e Enterprise planos. Consulte a tabela a seguir para ver quais recursos estão disponíveis.

[Microsoft Teams de serviço](/office365/servicedescriptions/teams-service-description)

> [!Note]
> Depois que outras cargas de trabalho estão totalmente disponíveis na nuvem GCC, elas se tornarão disponíveis no Teams quando todo o trabalho de integração adicional for concluído.


|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão.](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o conjunto Teams de recursos atende às necessidades da sua organização.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine seus requisitos de governança e como você pode atender a eles. Acesse [Plan for governance in Teams](plan-teams-governance.md) para obter mais informações.

|    |     |
|-----------|------------|
| ![Um ícone que representa um ponto de decisão.](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Determine e documente seus requisitos de governança, seguindo as diretrizes em [Plan for governance in Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar Teams colaboração

Depois de ter sido Microsoft 365 a GCC, siga o caminho de implantação recomendado descrito em [How to roll out Microsoft Teams](./deploy-overview.md). Certifique-se de se envolver com sua equipe de Gerenciamento de Alterações e adoção e Teams campeões.

Você também pode trabalhar com [FastTrack](https://www.microsoft.com/fasttrack) ou com seu parceiro escolhido para integrar o serviço.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Etapa 7. Implantar Teams reuniões e voz

Este também é um ótimo momento para usar o Teams com seu grupo de participantes mais amplo para começar a planejar a implantação de reuniões e recursos [de voz na nuvem.](./cloud-voice-landing-page.md)