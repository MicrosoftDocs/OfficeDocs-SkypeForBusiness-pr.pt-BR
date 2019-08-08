---
title: Pré-requisitos do Microsoft Teams | Atualização de adoção de dependências
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para implantar equipes em sua organização
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0da49178a55cc14b98946beb7212a1627829c13e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236065"
---
![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica] (media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")

Este artigo faz parte do estágio de preparação técnica da sua jornada de atualização, uma atividade que você conclui em paralelo com o estágio de preparação do usuário. Antes de prosseguir, confirme que você concluiu essas atividades dos estágios anteriores:

- [Listamos os participantes do projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolhido a jornada da atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências ambientais para equipes

O Teams combina vários serviços do Office 365 e, portanto, depende da implementação e operação corretas desses serviços. Esses serviços incluem, entre outros, o SharePoint Online, o Exchange Online e o OneDrive for Business.

Embora nem todos os serviços sejam necessários, é altamente recomendável que você implemente todos eles. Se você optar por não implementar determinados serviços, ele afetará a funcionalidade que as equipes podem oferecer à sua organização. Por exemplo, embora você não precise implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como compartilhamento de arquivos em conversas em grupo, para que a implementação desse serviço reduza a funcionalidade oferecida por meio da guia clientes.

Consulte os artigos a seguir para saber mais sobre pré-requisitos e como o Microsoft Teams interage com outras tecnologias:

- Se sua organização ainda não implantou nenhuma carga de trabalho do Office 365, consulte [introdução ao office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Se a sua organização ainda não adicionou ou configurou um domínio verificado para o Office 365, consulte [verificar seu domínio do office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Se sua organização não tiver identidades sincronizadas com o Azure Active Directory, consulte [modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

- Se a sua organização não ¹ tiver o Exchange Online, confira [entender como o Exchange e o Microsoft Teams interagem](Exchange-Teams-interact.md).

- Se sua organização não tiver o SharePoint Online, confira [entender como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](SharePoint-OneDrive-interact.md).

- Saiba como os [grupos do Office 365 e do Microsoft Teams interagem](Office-365-groups.md).

- Se sua organização for uma instituição educacional e você usar um sistema de informações do aluno, [implante a sincronização de dados da escola](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.

Depois de verificar se o seu ambiente atende a todos os pré-requisitos aplicáveis, [avalie o ambiente atual do teams](upgrade-plan-journey-evaluate-environment.md).
