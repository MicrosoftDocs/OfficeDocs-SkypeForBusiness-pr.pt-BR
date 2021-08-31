---
title: Pré-requisitos e dependências ambientais para atualização para Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para implantar Teams em sua organização
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f10df8849e6efe4e6ceac38cb46d118dff5a8ff8
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58725450"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências ambientais para Teams

![Atualize o diagrama de jornada, enfatizando o estágio de Preparação Técnica.](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme se você concluiu essas atividades de estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](./upgrade-define-project-scope.md)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

Teams combina vários serviços Microsoft 365 e Office 365 e, portanto, depende da implementação correta e da operação desses serviços. Esses serviços incluem, mas não estão limitados a SharePoint Online, Exchange Online e OneDrive for Business.

Embora nem todos os serviços sejam necessários, é altamente recomendável implementar todos eles. Se você optar por não implementar determinados serviços, isso afetará a funcionalidade que Teams pode oferecer à sua organização. Por exemplo, embora você não tenha que implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como o compartilhamento de arquivos em conversas em grupo, portanto, a não implementação desse serviço reduzirá a funcionalidade oferecida pelo cliente.

Consulte os artigos a seguir para saber mais sobre os pré-requisitos e como Teams interage com outras tecnologias:

- Se sua organização não implantou cargas de trabalho Microsoft 365 ou Office 365, consulte [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Se sua organização não tiver adicionado ou configurado um domínio verificado para Microsoft 365 ou Office 365, consulte [Perguntas frequentes sobre domínios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Se sua organização não tiver sincronizado identidades para Azure Active Directory, consulte [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).

- Se a sua organização não tiver o Exchange Online, consulte [Saiba como o Exchange e o Microsoft Teams interagem](Exchange-Teams-interact.md).

- Se a sua organização não tiver o SharePoint Online, consulte [Saiba como o SharePoint Online e o OneDrive for Business interagem com o Microsoft Teams](SharePoint-OneDrive-interact.md).

- Para saber como [Microsoft 365 grupos e Microsoft Teams interagem](Office-365-groups.md).

- Se a sua organização for uma instituição educacional e você usar um Sistema de Informações do Aluno, consulte Bem-vindo ao [Microsoft School Data Sync](/schooldatasync) antes de implantar Microsoft Teams.

- Se a sua organização estiver considerando as opções de chamada PSTN (Rede Telefônica Pública Comugada), consulte Voice - Sistema de Telefonia e [conectividade PSTN](cloud-voice-landing-page.md), [Qual](calling-plan-landing-page.md)Plano de Chamadas é o certo para você e [Sistema de Telefonia Roteamento](direct-routing-landing-page.md)Direto .

- Para garantir que todos os requisitos de rede tenham sido atendidos antes de Teams, consulte Prepare your [organization's network for Microsoft Teams](prepare-network.md).

- Se você estiver usando o Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo Teams PowerShell e atualizar os scripts existentes do PowerShell. Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module for](teams-powershell-move-from-sfbo.md) more information.

Depois de verificar se seu ambiente atende a todos os [](upgrade-plan-journey-evaluate-environment.md)pré-requisitos aplicáveis, avalie seu ambiente atual para Teams .