---
title: Implantações do governo Microsoft 365-GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Orientação para profissionais de ti direcionar implantações do Microsoft 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA
localization_priority: Normal
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
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085605"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Plano para implantações do governo Microsoft 365-GCC

Esta orientação destina-se aos profissionais de ti que estão conduzindo implantações do Microsoft 365 em entidades federais, estaduais, tribal ou outras entidades do governo dos EUA, que lidam com dados sujeitos a normas e requisitos governamentais, em que o uso do Microsoft 365 governo-GCC é adequado para atender a esses requisitos. Novidades de 26 de março de 2020: não perca o nosso [Guia de início rápido para download para gcc](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).

> [!IMPORTANT]
> O Microsoft Teams está experimentando um grande pico em chamadas online e videoconferência/videoconferência devido ao coronavirus (COVID-19) Pandemic.<br/>
> 
>Em resposta ao aumento sem precedente em chamadas e para garantir a continuidade e a disponibilidade, a Microsoft está permitindo que os servidores de áudio/vídeo do Microsoft Teams GCC aproveitem a capacidade de processamento em nossos datacenters comerciais, bem como nos datacenters governamentais.<br/>
> 
>Esses servidores de áudio/vídeo residem nos servidores de limite de capacitação alta do Microsoft Azure FedRAMP nos Estados Unidos e não armazenam qualquer conteúdo do cliente. No entanto, esses servidores estão processando áudio e vídeo para chamadas e conferências e estão operando em nossos funcionários comerciais durante esse período provisório.<br/>
> 
>Qualificado, o pessoal em tela está monitorando esses servidores para obter acesso potencial a dados dos clientes ao analisar os logs interativos para esses servidores. Os funcionários qualificados atendem aos requisitos de GCC para acessar o conteúdo do cliente. Para obter detalhes sobre requisitos de triagem, consulte a [Descrição de serviço gcc](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).<br/>
> 
>Obrigado pelo seu suporte, pois seguimos as etapas para garantir que nossos serviços permaneçam disponíveis e confiáveis nestes momentos extraordinários.<br/>


> [!NOTE]
> Se a sua organização já atendeu aos requisitos de qualificação do governo Microsoft 365 e se aplicou e foi aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Etapa 1. Determine se a sua organização precisa do Microsoft 365 governo-GCC e atenda aos requisitos de qualificação. 

O ambiente Microsoft 365 governo-GCC fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem, incluindo FedRAMP moderado e requisitos para justiça criminal e sistemas de informações federais fiscais (tipos de dados CJI e FTI).

Além de desfrutar dos recursos e funcionalidades do Microsoft 365, as organizações se beneficiam dos seguintes recursos exclusivos do Microsoft 365 governo-GCC:

-   O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais da Microsoft 365 da Microsoft.
-   O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
-   O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.
-   O Microsoft 365 governo-GCC está em conformidade com certificações e capacitações necessárias para clientes do setor público dos EUA.

Você pode encontrar mais informações sobre a oferta do Microsoft 365 governo-GCC para clientes do governo dos EUA nos [planos do governo da microsoft 365](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Descrição do serviço governo dos EUA da Microsoft 365](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em relação aos requisitos de conformidade nos Estados Unidos.

> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**. Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Microsoft 365 governo-GCC é apropriado para sua organização.</li><li>Confirme se a sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> Microsoft 365 governo-GCC só está disponível nos Estados Unidos. Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Microsoft 365](https://products.office.com/en/government/compare-office-365-government-plans).


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Etapa 2. Solicitar o Microsoft 365 governo-GCC

Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação deste serviço aqui](https://products.office.com/government/eligibility-validation).

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Etapa 3. Compreenda as configurações de segurança padrão do governo Microsoft 365-GCC.

Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você modificará qualquer uma das configurações de segurança do governo padrão da Microsoft 365, resolvendo para compreender primeiro o impacto de todas as alterações que você possa fazer.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Etapa 4. Compreenda quais recursos estão indisponíveis no momento ou desabilitados por padrão.

Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre os planos Microsoft 365 governo-GCC e Enterprise. Consulte a tabela a seguir para ver os recursos disponíveis.

[Descrição do serviço do Microsoft Teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Depois que outras cargas de trabalho estiverem totalmente disponíveis na nuvem GCC, elas serão disponibilizadas no Teams quando todo o trabalho adicional de integração for concluído.


|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o conjunto de recursos do teams atende às necessidades da sua organização.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine suas necessidades de governança e como você pode atendê-las. Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md).</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar equipes para colaboração

Depois de ter sido integrado ao Microsoft 365 governo – GCC, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md). Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.

Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Etapa 7. Implantar equipes para reuniões e voz

Também é um ótimo momento para usar o Microsoft Teams com seu grupo de Stakeholder mais largo para começar a planejar reuniões e [recursos de voz na nuvem](cloud-voice-deployment.md).

