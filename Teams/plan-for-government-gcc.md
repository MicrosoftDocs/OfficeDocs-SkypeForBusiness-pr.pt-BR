---
title: Planejar for Microsoft 365 governamental - implantações GCC - Microsoft Teams
author: lolajacobsen
ms.author: lehewe
manager: serdars
ms.date: 07/26/2018
ms.topic: article
ms.service: msteams
ms.reviewer: lehewe
description: Diretrizes para profissionais de TI para as implantações do Office 365 de unidade nas entidades que manipular dados sujeitos a uma regulamentação do governo dos EUA
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 430b6c6de5468442f7a290b07b28eb59d276e00c
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23885768"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a>Planejar Microsoft 365 governamental - implantações GCC

Neste guia se destina a profissionais de TI que estão orientando a implantações do Office 365 em US federal, estado, entidades governamentais local, tribal ou região ou outras entidades que lidam com dados que estão sujeito a regulamentos do governo e requisitos, onde o uso da Microsoft 365 governamental - GCC é apropriado para atender a esses requisitos.

> [!NOTE]
> Se sua organização já tiver atendidos Microsoft 365 governo - requisitos de qualificação GCC e aplicadas para e foi aceita no programa, poderá ignorar as etapas 1 a 4 e ir diretamente para a etapa 5 para começar sua implantação. 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a>Etapa 1. Determine se a sua organização precisa governo de 365 da Microsoft - GCC e atende aos requisitos de qualificação. 

Fornece do governo Microsoft 365 - ambiente GCC cumprimento dos EUA requisitos do governo para serviços de nuvem, incluindo FedRAMP moderadas e requisitos para justiça criminal e sistemas de informação de imposto federal (tipos de dados CJI e FTI).

Além de usufruir os recursos e capacidades do Office 365, organizações se beneficiam os seguintes recursos que são exclusivos para o Microsoft 365 governamental - GCC:

-   Conteúdo do cliente da sua organização logicamente é separado do conteúdo do cliente no Office 365 serviços comerciais da Microsoft.
-   Conteúdo do cliente da sua organização é armazenado nos Estados Unidos.
-   Acesso ao conteúdo de cliente da sua organização é restrito a equipe da Microsoft filtrada.
-   Microsoft 365 governamental - GCC cumpre certificações e referências são necessárias para clientes conosco setor público.

Você pode encontrar mais informações sobre o Microsoft 365 governamental - GCC oferecendo clientes governamentais conosco em [que planos do Office 365 governamental](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).

A [Descrição do serviço Office 365 US governamentais](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em torno de atender aos requisitos de conformidade dentro dos Estados Unidos.

> [!Tip]
> Talvez você queira os índices de informações na descrição do serviço de transferência em uma pasta de trabalho do Excel e adicionar duas colunas: **relevante para minha organização Y/N** e **atende às necessidades da minha organização Y/N**. Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atenda às necessidades da sua organização.


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Pontos de decisão|<ul><li>Decida se o Microsoft 365 governamental - GCC é adequado para sua organização.</li><li>Confirme se sua organização atende aos requisitos de qualificação.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Entenda os recursos fornecidos pelo Microsoft 365 governamental - GCC.</li></ul>|

> [!Note]
> Microsoft 365 governamental - GCC só está disponível nos Estados Unidos. Clientes do governo não – dos EUA podem escolher um número de [planos do Office 365 governamental](https://products.office.com/en/government/compare-office-365-government-plans).

## <a name="step-2-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a>Etapa 2. Entenda quais recursos estão atualmente indisponível ou desabilitado por padrão. 

Para acomodar os requisitos de nossos clientes de nuvem do governo, há algumas diferenças entre Microsoft 365 governamental - GCC e planos de empresa. Os recursos listados na tabela a seguir não estão disponíveis.

| Recurso                     | Motivo            |
|-----------------------------|-------------------|
| Chamada e a gravação de reunião  | Gravação depende Microsoft Stream, que estarão disponíveis nos planos do governo no futuro. |
| Aplicativos       | Aplicativos (por exemplo, conectores, guias e bots) não estarão disponíveis inicialmente, mas estamos trabalhando para disponibilizá-los assim que a barra de conformidade FedRAMP moderadas atendem a todos os seus componentes. |
| Um canal de email             | A arquitetura do recurso atual não é suportada nos planos do governo. |
| Presença unificada            | Estamos Finalizar trabalho para clientes empresariais primeiro para esse recurso importante. Ele estará disponível para clientes do governo no futuro. |
| Chat interoperabilidade entre equipes & SfB usuários            | Interoperação é dependente no serviço de presença unificada (UPS) e não pode funcionar até GCC equipes inquilinos habilitados para um no-break. |

| Notificações de email | A arquitetura do recurso atual não é compatível com os planos do governo conosco. Trabalho está em andamento para disponibilizar esse recurso para os clientes do governo conosco plano no futuro. |


|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida se o Microsoft 365 governamental - GCC conjunto de recursos atende às necessidades da sua organização.</li></ul> |
| ![](media/audio_conferencing_image9.png)<br/>Próxima etapa|<ul><li>Compreenda as configurações de segurança padrão.</li></ul>|

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a>Etapa 3. Compreenda o governo Microsoft 365 - configurações de segurança padrão GCC.

É recomendável que você leve hora de revisar cuidadosamente suas [configurações de segurança e administração](enable-features-office-365.md) antes de modificá-los e considere impactos em conformidade antes de fazer qualquer alteração de configurações de segurança padrão.

|    |     |
|-----------|------------|
| ![](media/audio_conferencing_image7.png) <br/>Ponto de decisão|<ul><li>Decida que se você vai modificar quaisquer das padrão Microsoft 365 governamental - configurações de segurança GCC, resolvendo primeiro compreender os impactos de quaisquer alterações você pode fazer.</li></ul> |

## <a name="step-4-apply-for-microsoft-365-government---gcc"></a>Etapa 4. Aplicar Microsoft 365 governamental - GCC

Tendo decidiu que esse serviço é certo para sua organização, inicie o processo de [aplicação para esse serviço aqui](https://products.office.com/government/eligibility-validation).

## <a name="step-5-plan-for-governance"></a>Etapa 5. Plano de governança

Determine os requisitos de governança e como você pode atender a eles. Vá para [Planejar a governança em equipes](plan-teams-governance.md) para obter mais informações.

## <a name="step-6-deploy-teams-for-collaboration"></a>Etapa 6. Implantar equipes para colaboração

Depois que você fez onboarded ao Microsoft 365 governo - GCC, você pode seguir a abordagem de implantação padrão do uso [FastTrack](https://fasttrack.microsoft.com/fasttrack-faq) e seu parceiro escolhido para integrado ao serviço.

Quando você estiver pronto, implante equipes para [Habilitar a colaboração dentro da sua organização por meio de equipes e canais](teams-overview.md). Certifique-se de que se comprometer com sua equipe de adoção e gerenciamento de alterações ou os campeões equipes.

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a>Etapa 7. Implantar equipes para reuniões e voz

Isso também é um ótimo momento para usar equipes com seu grupo das partes interessadas mais largo para iniciar o planejamento para a distribuição dos [recursos de voz de nuvem](cloud-voice-deployment.md)e reuniões.

