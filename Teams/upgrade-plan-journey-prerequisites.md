---
title: Pré-requisitos e dependências ambientais para atualizar para o Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para implantar o Teams em sua organização
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092189"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências ambientais do Teams

![Atualizar diagrama de jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme se você concluiu essas atividades de estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

O Teams combina vários serviços do Microsoft 365 e do Office 365 e, portanto, depende da implementação correta e da operação desses serviços. Esses serviços incluem— mas não estão limitados a — SharePoint Online, Exchange Online e OneDrive for Business.

Embora nem todos os serviços sejam necessários, é altamente recomendável implementar todos eles. Se você optar por não implementar determinados serviços, isso afetará a funcionalidade que o Teams pode oferecer à sua organização. Por exemplo, embora você não tenha que implementar o SharePoint Online, o Teams depende do SharePoint Online para determinada funcionalidade, como o compartilhamento de arquivos em conversas em grupo, portanto, a não implementação desse serviço reduzirá a funcionalidade oferecida pelo cliente.

Consulte os artigos a seguir para saber mais sobre os pré-requisitos e como o Teams interage com outras tecnologias:

- Se sua organização não implantou cargas de trabalho do Microsoft 365 ou office 365, consulte [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou Office 365, consulte [Perguntas frequentes sobre domínios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Se sua organização não tiver sincronizado identidades com o Azure Active Directory, consulte [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).

- Se sua organização não tiver o Exchange Online, consulte [Entenda como o Exchange e o Microsoft Teams interagem.](Exchange-Teams-interact.md)

- Se sua organização não tiver o SharePoint Online, consulte Entenda como o SharePoint Online e [o OneDrive for Business interagem com o Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Para saber como os [grupos do Microsoft 365 e o Microsoft Teams interagem](Office-365-groups.md).

- Se sua organização for uma instituição educacional e você usar um Sistema de Informações do Aluno, consulte [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.

- Se sua organização estiver considerando as opções de chamadas PSTN (Rede Telefônica Pública Comugada), consulte Voice - Phone System and [PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan](calling-plan-landing-page.md)is right for you , and Phone System Direct [Routing](direct-routing-landing-page.md).

- Para garantir que todos os requisitos de rede tenham sido atendidos antes de lançar o Teams, consulte [Prepare your organization's network for Microsoft Teams](prepare-network.md).

- Se você estiver usando o Conector do Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo do PowerShell do Teams e atualizar os scripts existentes do PowerShell. Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.

Depois de verificar se seu ambiente atende a todos os pré-requisitos aplicáveis, avalie seu ambiente [atual para o Teams](upgrade-plan-journey-evaluate-environment.md).