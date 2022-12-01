---
title: Criar equipes de gerentes de pessoas no Microsoft Teams
ms.reviewer: pbethi
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus directs como membros da equipe.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.custom: chat-teams-channels-revamp
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 89a820a1b828621df2a129b7a972408e7280b3da
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198923"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Criar equipes de gerentes de pessoas no Microsoft Teams


Quando você lança Microsoft Teams, em vez de iniciar com uma "lousa em branco" (sem equipes ou canais), recomendamos fortemente que você configure uma estrutura base de equipes e canais. Isso ajuda a evitar a "expansão da equipe", onde os usuários criam várias equipes quando devem criar canais em equipes existentes. Para ajudá-lo a começar com uma estrutura de canais e equipes bem projetadas, criamos um script do PowerShell que cria uma equipe para cada um de seus gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe. Este é um script "ponto em tempo" (ele não atualiza suas equipes ou canais automaticamente quando as pessoas são adicionadas ou removidas de uma organização). Mas é uma ferramenta valiosa que você pode usar para impor alguma ordem à sua estrutura do Teams desde o início. Este script lê seu Azure AD, obtém uma lista de gerentes e seus relatórios diretos. Ele usa essa lista para criar uma equipe por gerente de pessoas. 

## <a name="how-to-use-the-powershell-script"></a>Como usar o script do PowerShell 

Comece executando os [gerenciador de exportação e o script de direção](scripts/powershell-script-create-teams-from-managers-export-managers.md) (o que pressupõe que você já tenha executado os módulos [Connect-AzureAd](/powershell/module/azuread/connect-azuread) e [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams) PowerShell). Os *gerentes de exportação e seu script de directs* criam um arquivo delimitado por guia (ExportedManagerDirects.txt) que lista todos os gerentes com seus relatórios diretos. 

Em seguida, execute o [script Criar novas equipes do gerenciador de pessoas](scripts/powershell-script-create-teams-from-managers-new-teams.md). Este script lê no arquivo ExportedManagerDirects.txt e cria uma equipe para cada gerente, com os relatórios diretos desse gerente como membros. Se qualquer gerente ou direto não estiver habilitado para o Teams, o script os ignorará e não criará uma equipe. (Examine o relatório e execute novamente o script depois de ativar o Teams para quem precisar. O script não criará uma segunda equipe para qualquer gerente para o qual já criou uma equipe.

Para cada equipe, o script cria um canal geral e "Just for fun". 

## <a name="best-practices"></a>Práticas recomendadas

- Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia ao canal geral de cada equipe. 

- Confira o novo aplicativo de Comunicações de Crise lendo esta postagem de blog de 8 de março de 2020: [Coordene as comunicações de crise usando Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Tópicos relacionados

[Melhores práticas para organizar equipes](best-practices-organizing.md)

[Crie uma equipe englobando toda a organização no Teams](create-an-org-wide-team.md)