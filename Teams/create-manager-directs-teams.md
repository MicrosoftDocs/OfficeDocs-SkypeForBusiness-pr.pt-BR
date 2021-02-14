---
title: Criar equipes de gerente de pessoas no Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus diretos como membros da equipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583670"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Criar equipes de gerente de pessoas no Microsoft Teams


Ao lançar o Microsoft Teams, em vez de iniciar com um "slate em branco" (sem equipes ou canais), é recomendável configurar uma estrutura base de equipes e canais. Isso ajuda a evitar o "swlwl da equipe", em que os usuários criam várias equipes quando devem criar canais em equipes existentes. Para ajudá-lo a começar com uma estrutura de canais e equipes bem projetada, criamos um script do PowerShell que cria uma equipe para cada um dos seus gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe. Este é um script "point-in-time" (ele não atualiza automaticamente suas equipes ou canais quando as pessoas são adicionadas ou removidas de uma organização). Mas é uma ferramenta valiosa que você pode usar para impor alguma ordem na estrutura do Teams desde o início. Este script lê seu Azure AD, obtém uma lista de gerentes e seus relatórios diretos. Ela usa essa lista para criar uma equipe por gerente de pessoas. 

## <a name="how-to-use-the-powershell-script"></a>Como usar o script do PowerShell 

Comece executando os gerentes de exportação e seus [scripts diretos](scripts/powershell-script-create-teams-from-managers-export-managers.md) (o que pressuporá que você já tenha executado os módulos [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). Os gerentes de exportação e seus *scripts diretos* criam um arquivo separado por tabulação (ExportedManagerDirects.txt) que lista todos os gerentes com seus relatórios diretos. 

Em seguida, execute [o script Criar novas equipes de gerente de pessoas.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Esse script é lido no arquivo ExportedManagerDirects.txt e cria uma equipe para cada gerente, com os relatórios diretos desse gerente como membros. Se algum gerente ou direto não estiver habilitado para o Teams, o script os ignorará e não criará uma equipe. (Revise o relatório e, em seguida, reprise o script depois de ter ligado o Teams para qualquer pessoa que precise dele. O script não criará uma segunda equipe para qualquer gerente para o que já tenha criado uma equipe.)

Para cada equipe, o script cria um canal Geral e "Apenas por diversão". 

## <a name="best-practices"></a>Práticas recomendadas

- Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia para o canal Geral de cada equipe. 

- Confira o novo aplicativo De comunicações de crise lendo esta postagem de blog de 8 de março de 2020: Coordenar comunicações de crise usando [o Microsoft Teams + Power Platform.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)

## <a name="related-topics"></a>Tópicos relacionados

[Práticas recomendadas para organizar equipes](best-practices-organizing.md)

[Crie uma equipe englobando toda a organização no Teams](create-an-org-wide-team.md)
