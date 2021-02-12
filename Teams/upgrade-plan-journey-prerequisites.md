---
title: Pré-requisitos e dependências ambientais para a atualização para o Teams
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578274"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências ambientais do Teams

![Diagrama de atualização da jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme que você concluiu essas atividades de estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

O Teams combina vários serviços do Microsoft 365 e do Office 365 e, portanto, depende da implementação e operação correta desses serviços. Esses serviços incluem— mas não estão limitados a — o SharePoint Online, o Exchange Online e o OneDrive for Business.

Embora nem todos os serviços sejam necessários, é altamente recomendável que você implemente todos eles. Se você optar por não implementar determinados serviços, isso afetará a funcionalidade que o Teams pode oferecer à sua organização. Por exemplo, embora você não tenha que implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como o compartilhamento de arquivos em conversas em grupo, portanto, não implementar esse serviço reduzirá a funcionalidade oferecida por meio do cliente.

Confira os artigos a seguir para saber mais sobre pré-requisitos e como o Teams interage com outras tecnologias:

- Se sua organização não implantou cargas de trabalho do Microsoft 365 ou do Office 365, consulte [Começar.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)

- Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou o Office 365, consulte [Perguntas frequentes sobre Domínios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)

- Se sua organização não sincronizou identidades com o Azure Active Directory, consulte modelos de identidade e autenticação [no Microsoft Teams.](identify-models-authentication.md)

- Se sua organização não tiver o Exchange Online, veja [como o Exchange e o Microsoft Teams interagem.](Exchange-Teams-interact.md)

- Se sua organização não tiver o SharePoint Online, veja Como o SharePoint Online e o [OneDrive for Business interagem com o Microsoft Teams.](SharePoint-OneDrive-interact.md)

- Para saber como os [grupos do Microsoft 365 e o Microsoft Teams interagem.](Office-365-groups.md)

- Se sua organização for uma instituição de ensino e você usar um Sistema de Informações do Aluno, consulte Bem-vindo ao [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.

- Se a sua organização estiver considerando as opções de chamada PSTN (Rede Telefônica Pública Comutado), consulte Voz – Sistema de Telefonia e conectividade [PSTN,](cloud-voice-landing-page.md)qual plano de chamada é certo para você [e](calling-plan-landing-page.md)Roteamento Direto do Sistema de Telefonia. [](direct-routing-landing-page.md)

- Para garantir que todos os requisitos de rede tenham sido atendidos antes de lançar o Teams, consulte Preparar a [rede da sua organização para o Microsoft Teams.](prepare-network.md)

Depois de verificar se seu ambiente atende a todos os pré-requisitos aplicáveis, avalie seu [ambiente atual para o Teams.](upgrade-plan-journey-evaluate-environment.md)
