---
title: Implantações do Microsoft 365 Government - GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Diretrizes para profissionais de IT para impulsionar implantações do Microsoft 365 em entidades que lidam com dados sujeitos à regulamentação do governo dos EUA
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
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planejar implantações do Microsoft 365 Government - GCC

Essa orientação é para profissionais de IT que conduzem implantações do Microsoft 365 em entidades governamentais federais, estaduais, locais, locais, ltda ou metais ou outras entidades que lidam com dados sujeitos a requisitos e regulamentações governamentais, em que o uso do Microsoft 365 Government – GCC é apropriado para atender a esses requisitos. Novo 26 de março de 2020: Não perca nosso guia de Início Rápido para [GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)para download.

> [!IMPORTANT]
> O Microsoft Teams está enfrentando um grande aumento em chamadas online e conferência de áudio/vídeo devido à pandímica (COVID-19).<br/>
> 
>Em resposta ao aumento indevida de chamadas e para garantir a continuidade e a disponibilidade, a Microsoft está permitindo que os servidores de áudio/vídeo do Microsoft Teams aproveitem a capacidade de processamento em nossos datacenters comerciais, bem como em nossos datacenters governamentais.<br/>
> 
>Esses servidores de áudio/vídeo residem nos servidores de limite de alto credenciamento do Microsoft Azure FedRAMP nos Estados Unidos e não armazenam conteúdo do cliente. No entanto, esses servidores estão processando áudio e vídeo para chamadas e conferências e estão funcionando sob nossa equipe comercial durante esse período provisório.<br/>
> 
>Equipes qualificadas e com tela estão monitorando esses servidores para possíveis acessos aos dados do cliente, revendo os logoff interativos desses servidores. As pessoas qualificadas atendem aos requisitos de GCC para acesso ao conteúdo do cliente. Para obter detalhes sobre requisitos de seleção, consulte a descrição [do serviço GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)<br/>
> 
>Obrigado por seu suporte à medida que tomarmos medidas para garantir que nossos serviços permaneçam disponíveis e confiáveis nesses tempos excepcionalmente.<br/>


> [!NOTE]
> Se sua organização já atendeu aos requisitos de qualificação do Microsoft 365 Government - GCC e se aplicou e foi aceita no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Etapa 1. Determine se sua organização precisa do Microsoft 365 Government - GCC e atende aos requisitos de qualificação. 

O ambiente Microsoft 365 Government - GCC fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem, incluindo FedRAMP Moderado e requisitos para sistemas de informações fiscais criminais e federais (tipos de dados CJI e FTI).

Além de aproveitar os recursos e recursos do Microsoft 365, as organizações se beneficiam com os seguintes recursos exclusivos do Microsoft 365 Government - GCC:

-   O conteúdo do cliente da sua organização é logicamente separado do conteúdo do cliente nos serviços comerciais do Microsoft 365 da Microsoft.
-   O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
-   O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft com tela.
-   Microsoft 365 Government - GCC atende às certificações e aos credenciamentos necessários para clientes do Setor Público dos EUA.

Você pode encontrar mais informações sobre a oferta do Microsoft 365 Government - GCC para clientes do governo dos EUA em planos do [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluindo requisitos [de qualificação.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

A descrição do serviço do [Microsoft 365 US Government](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em torno de atender aos requisitos de conformidade nos Estados Unidos.

> [!Tip]
> Talvez você queira transferir as tabelas de informações na descrição do serviço para uma planilha do Excel e adicionar duas colunas: Relevantes para minha organização **Y/N** e atender às necessidades da minha organização **Y/N.** Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Microsoft 365 Government - GCC é apropriado para sua organização.</li><li>Confirme se sua organização atende aos requisitos de qualificação.</li></ul> |

> [!Note]
> O Microsoft 365 Government - GCC só está disponível nos Estados Unidos. Clientes do governo dos EUA podem escolher entre vários planos [do Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a>Etapa 2. Aplicar ao Microsoft 365 Government - GCC

Tendo decidido que esse serviço é o certo para sua organização, inicie o processo [de aplicação desse serviço aqui.](https://products.office.com/government/eligibility-validation)

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Etapa 3. Entenda as configurações de segurança padrão do Microsoft 365 Government - GCC.

Recomendamos que você tenha tempo [](enable-features-office-365.md) para revisar cuidadosamente as configurações de segurança e administrador antes de modificá-las e considerar os impactos na conformidade antes de fazer alterações nas configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se você modificará alguma das configurações de segurança padrão do Microsoft 365 Government - GCC, resolvendo primeiro entender o impacto das alterações que você pode fazer.</li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Etapa 4. Entenda quais recursos estão indisponíveis ou desabilitados por padrão.

Para acomodar os requisitos de nossos clientes de nuvem do governo, existem algumas diferenças entre os planos Microsoft 365 Government - GCC e Enterprise. Confira a tabela a seguir para ver quais recursos estão disponíveis.

[Descrição do serviço microsoft teams](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> Quando outras cargas de trabalho estão totalmente disponíveis na nuvem GCC, elas se tornarão disponíveis no Teams quando todo o trabalho de integração adicional for concluído.


|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o conjunto de recursos do Teams atende às necessidades da sua organização.</li></ul> |

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de gestão

Determine seus requisitos de governança e como você pode atender a eles. Vá para [Plano de governança no Teams](plan-teams-governance.md) para obter mais informações.

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Determine e documente seus requisitos de gestão, seguindo as diretrizes no [Plano de governança no Teams.](plan-teams-governance.md)</li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar o Teams para colaboração

Depois de integração com o Microsoft 365 Government – GCC, siga o caminho de implantação recomendado descrito em [Como lançar o Microsoft Teams.](How-to-roll-out-teams.md) Certifique-se de interagir com sua equipe de Adoção e Gerenciamento de Alterações e os campeões do Teams.

Você também pode trabalhar com [o FastTrack ou](https://www.microsoft.com/fasttrack) seu parceiro escolhido para integrar o serviço.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Etapa 7. Implantar o Teams para reuniões e voz

Este também é um ótimo momento para usar o Teams com seu grupo de participantes mais amplo para começar a planejar a implantação de reuniões e recursos [de voz na nuvem.](cloud-voice-deployment.md)

