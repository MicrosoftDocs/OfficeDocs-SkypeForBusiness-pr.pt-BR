---
title: Criar equipes de gerente de pessoas no Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus diretos como membros da equipe.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: bd880e58b2c6818b8738afd5fb4e5efaf78642d4
ms.sourcegitcommit: ff783fad2fb5d412e864e3af2ceaa8fedcd9da07
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66562580"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Criar equipes de gerente de pessoas no Microsoft Teams


Quando você implanta o Microsoft Teams, em vez de iniciar com um "slate em branco" (sem equipes ou canais), é altamente recomendável que você configure uma estrutura base de equipes e canais. Isso ajuda a evitar a "expansão da equipe", em que os usuários criam várias equipes quando devem criar canais em equipes existentes. Para ajudá-lo a começar a usar uma estrutura de equipes e canais bem projetada, criamos um script do PowerShell que cria uma equipe para cada um dos gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe. Esse é um script "point-in-time" (ele não atualiza suas equipes ou canais automaticamente quando as pessoas são adicionadas ou removidas de uma organização). Mas é uma ferramenta valiosa que você pode usar para impor alguma ordem em sua estrutura do Teams desde o início. Esse script lê seu Azure AD, obtém uma lista de gerentes e seus relatórios diretos. Ele usa essa lista para criar uma equipe por gerente de pessoas. 

## <a name="how-to-use-the-powershell-script"></a>Como usar o script do PowerShell 

Comece executando os gerenciadores de exportação e o [script de directs](scripts/powershell-script-create-teams-from-managers-export-managers.md) (que pressupõe que você já tenha executado os módulos [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) do PowerShell). Os *gerentes de exportação e seus scripts diretos* criam um arquivo delimitado por tabulação (ExportedManagerDirects.txt) que lista todos os gerentes com seus relatórios diretos. 

Em seguida, execute o [script Criar equipes do Gerenciador de Pessoas](scripts/powershell-script-create-teams-from-managers-new-teams.md). Esse script lê o arquivo ExportedManagerDirects.txt e cria uma equipe para cada gerente, com os relatórios diretos desse gerente como membros. Se qualquer gerente ou direto não estiver habilitado para o Teams, o script ignorará e não criará uma equipe. (Examine o relatório e execute novamente o script depois de ter ativado o Teams para qualquer pessoa que precise dele. O script não criará uma segunda equipe para qualquer gerente para o que já tenha criado uma equipe.)

Para cada equipe, o script cria um canal Geral e "Apenas por diversão". 

## <a name="best-practices"></a>Práticas recomendadas

- Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia para o canal Geral de cada equipe. 

- Confira o novo aplicativo Crisis Communications lendo esta postagem no blog de 8 de março de 2020: Coordenar comunicações de crise usando o [Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Tópicos relacionados

[Práticas recomendadas para organizar equipes](best-practices-organizing.md)

[Crie uma equipe englobando toda a organização no Teams](create-an-org-wide-team.md)