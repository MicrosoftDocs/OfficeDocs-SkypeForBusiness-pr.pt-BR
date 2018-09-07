---
title: Pré-requisitos e dependências ambientais for Microsoft Teams - Teams da Microsoft
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Use estas diretrizes para aprender sobre os pré-requisitos e as dependências de ambientais para implantar as equipes em sua organização
localization_priority: Priority
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9db3bcc8e9171670288d0e5b14e120a9dd3692f0
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851051"
---
![Estágios da atualização jornada, com ênfase na etapa de preparação técnica] (media/upgrade-banner-tech-readiness.png "Estágios da atualização jornada, com ênfase na etapa de preparação técnica")

Este artigo faz parte do estágio de prontidão técnica de sua atualização jornada, uma atividade que você concluir em paralelo com o estágio de preparação do usuário. Antes de continuar, confirme que você tiver concluído essas atividades desde estágios anteriores:

-   [Inscrito seus participantes do projeto](upgrade-enlist-stakeholders.md)
-   [Definido o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
-   [Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios](https://aka.ms/SkypeToTeams-Coexist)
-   [Escolhido sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências de ambientais para equipes

As equipes combina vários serviços do Office 365 e, portanto, a implementação correta e a operação desses serviços dependentes. Esses serviços incluem —, mas não está limitado a — Exchange Online, SharePoint Online e OneDrive for Business.

Embora nem todos os serviços forem necessários, é altamente recomendável que você implemente todos eles. Se você optar por não implementar determinados serviços, ele afetará a funcionalidade que equipes podem oferecer a sua organização. Por exemplo, embora você não precisa implementar o SharePoint Online, equipes baseiam-se no SharePoint Online para alguns recursos, como compartilhamento de arquivo no conversas do grupo, portanto, não implementar esse serviço reduzirá a funcionalidade oferecida por meio do cliente.

Consulte os seguintes artigos para saber mais sobre os pré-requisitos e como equipes interage com outras tecnologias:

-   Se sua organização não tiver implantado nenhum cargas de trabalho do Office 365, consulte [Getting Started with Office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

-   Se sua organização não tiver adicionado ou configurado um domínio verificado para o Office 365, consulte [Verify seu domínio do Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

-   Se sua organização não tiver sincronizado identidades para o Windows Azure Active Directory, consulte [modelos de identidade e autenticação no equipes da Microsoft](identify-models-authentication.md).

-   Se doesn¹t sua organização tiver o Exchange Online, consulte [Noções básicas sobre como o Exchange e equipes da Microsoft interagem](Exchange-Teams-interact.md).

-   Se sua organização não tiver o SharePoint Online, consulte [Noções básicas sobre como o SharePoint Online e o OneDrive for Business interagem com as equipes da Microsoft](SharePoint-OneDrive-interact.md).

-   Saiba como [interagem grupos do Office 365 e equipes da Microsoft](Office-365-groups.md).

-   Se sua organização é uma instituição educacional e usar um sistema de informações de Student, [Implante a sincronização de dados da escola](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.
                                                                           

Depois que você tiver verificado que seu ambiente atende aos pré-requisitos aplicáveis todos, [avaliar o ambiente atual para equipes](upgrade-plan-journey-evaluate-environment.md).