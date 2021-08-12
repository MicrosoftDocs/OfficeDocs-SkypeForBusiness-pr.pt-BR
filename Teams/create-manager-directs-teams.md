---
title: Criar equipes de gerente de pessoas Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus directs como membros da equipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ce7fb0a34f202481df0062367ec7a905b84848d21e7a2e5e4bce73bea4073eac
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282804"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Criar equipes de gerente de pessoas Microsoft Teams


Ao lançar o Microsoft Teams, em vez de iniciar com uma "lousa em branco" (sem equipes ou canais), é recomendável configurar uma estrutura base de equipes e canais. Isso ajuda a evitar a "expansão de equipe", em que os usuários criam várias equipes quando devem criar canais em equipes existentes. Para ajudá-lo a começar com uma estrutura de equipes e canais bem projetada, criamos um script do PowerShell que cria uma equipe para cada um dos gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe. Esse é um script "point-in-time" (ele não atualiza automaticamente suas equipes ou canais quando as pessoas são adicionadas ou removidas de uma organização). Mas é uma ferramenta valiosa que você pode usar para impor alguma ordem em sua estrutura Teams desde o início. Este script lê o Azure AD, obtém uma lista de gerentes e seus relatórios diretos. Ele usa essa lista para criar uma equipe por gerente de pessoas. 

## <a name="how-to-use-the-powershell-script"></a>Como usar o script do PowerShell 

Comece executando os gerentes de exportação e o script de [directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (o que supõe que você já tenha executado os módulos [Conexão-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Conexão-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell). O *script Exportar gerentes* e seus directs cria um arquivo delimitado por tabulação (ExportedManagerDirects.txt) que lista todos os gerentes com seus relatórios diretos. 

Em seguida, execute o [script Criar novas equipes de gerente de pessoas.](scripts/powershell-script-create-teams-from-managers-new-teams.md) Esse script lê no arquivo ExportedManagerDirects.txt e cria uma equipe para cada gerente, com os relatórios diretos desse gerente como membros. Se qualquer gerente ou direto não estiver habilitado para Teams, o script os ignorará e não criará uma equipe. (Revise o relatório e, em seguida, reprise o script depois que você Teams para qualquer pessoa que precise dele. O script não criará uma segunda equipe para qualquer gerente para o que já tenha criado uma equipe.)

Para cada equipe, o script cria um canal Geral e "Apenas por diversão". 

## <a name="best-practices"></a>Práticas recomendadas

- Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia para o canal Geral de cada equipe. 

- Confira o novo aplicativo de Comunicações de Crise lendo esta postagem de blog de 8 de março de 2020: Coordenar comunicações de crise usando [Microsoft Teams + Plataforma Power](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Tópicos relacionados

[Práticas recomendadas para organizar equipes](best-practices-organizing.md)

[Crie uma equipe englobando toda a organização no Teams](create-an-org-wide-team.md)