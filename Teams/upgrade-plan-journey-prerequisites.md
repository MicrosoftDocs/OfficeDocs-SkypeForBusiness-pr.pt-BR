---
title: Pré-requisitos e dependências ambientais para a atualização para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para a implantação de equipes em sua organização
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
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a>Pré-requisitos e dependências ambientais para equipes

![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")

Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário. Antes de prosseguir, confirme que você concluiu essas atividades dos estágios anteriores:

- [Alistou as partes envolvidas no seu projeto](upgrade-enlist-stakeholders.md)
- [Definiu o escopo do seu projeto](https://aka.ms/SkypetoTeams-Scope)
- [Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams](https://aka.ms/SkypeToTeams-Coexist)
- [Escolheu sua jornada de atualização](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

O Teams combina vários serviços do Microsoft 365 e do Office 365 e, portanto, depende da implementação e operação corretas desses serviços. Esses serviços incluem, entre outros, o SharePoint Online, o Exchange Online e o OneDrive for Business.

Embora nem todos os serviços sejam necessários, é altamente recomendável que você implemente todos eles. Se você optar por não implementar determinados serviços, ele afetará a funcionalidade que as equipes podem oferecer à sua organização. Por exemplo, embora você não precise implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como compartilhamento de arquivos em conversas em grupo, para que a implementação desse serviço reduza a funcionalidade oferecida por meio do cliente.

Consulte os artigos a seguir para saber mais sobre pré-requisitos e como o Microsoft Teams interage com outras tecnologias:

- Se sua organização não tiver implantado nenhuma carga de trabalho do Microsoft 365 ou do Office 365, consulte [introdução](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).

- Se a sua organização ainda não adicionou ou configurou um domínio verificado para o Microsoft 365 ou o Office 365, consulte [perguntas frequentes sobre domínios](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).

- Se sua organização não tiver identidades sincronizadas com o Azure Active Directory, consulte [modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).

- Se a sua organização não tiver o Exchange Online, confira [entender como o Exchange e o Microsoft Teams interagem](Exchange-Teams-interact.md).

- Se sua organização não tiver o SharePoint Online, confira [entender como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](SharePoint-OneDrive-interact.md).

- Para saber como os [grupos do microsoft 365 e do Microsoft Teams interagem](Office-365-groups.md).

- Se sua organização for uma instituição educacional e você usar um sistema de informações do aluno, consulte [Bem-vindo à sincronização de dados do Microsoft School](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.

- Se a sua organização estiver considerando opções de chamadas PSTN (rede telefônica pública comutada), consulte [sistema de telefonia de voz e conectividade PSTN](cloud-voice-landing-page.md), [que é o plano de chamada adequado para você](calling-plan-landing-page.md)e [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).

- Para garantir que todos os requisitos de rede tenham sido atendidos antes de distribuir o Microsoft Teams, consulte [preparar a rede da sua organização para o Microsoft Teams](prepare-network.md).

Depois de verificar se o seu ambiente atende a todos os pré-requisitos aplicáveis, [avalie o ambiente atual do teams](upgrade-plan-journey-evaluate-environment.md).
