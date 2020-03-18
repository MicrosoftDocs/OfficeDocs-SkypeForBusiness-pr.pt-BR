---
title: Criar equipes do Gerenciador de pessoas no Microsoft Teams
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: Saiba como usar um script do PowerShell para criar uma equipe para cada gerente com seus direcionamentos como membros da equipe.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796180"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a>Criar equipes do Gerenciador de pessoas no Microsoft Teams


Ao implantar o Microsoft Teams, em vez de iniciar com uma "ardósia em branco" (sem equipes ou canais), recomendamos enfaticamente que você configure uma estrutura base de equipes e canais. Isso ajuda a evitar a "proliferação de equipe", em que os usuários criam várias equipes quando devem criar canais em equipes existentes. Para ajudá-lo a começar com uma estrutura bem projetada de equipes e canais, criamos um script do PowerShell que cria uma equipe para cada um dos gerentes de pessoas de primeira e segunda linha, com os relatórios diretos de cada gerente como membros da equipe. Esse é um script "point-in-time" (não atualiza suas equipes ou canais automaticamente quando as pessoas são adicionadas ou removidas de uma organização). Mas é uma ferramenta valiosa que você pode usar para impor algum pedido na estrutura de suas equipes desde o início. Esse script lê seu Azure AD, obtém uma lista de gerentes e seus subordinados diretos. Ele usa essa lista para criar uma equipe por gerentes de pessoas. 

## <a name="how-to-use-the-powershell-script"></a>Como usar o script do PowerShell 

Comece executando os [gerentes de exportação e o script de direcionadores](scripts/powershell-script-create-teams-from-managers-export-managers.md) (que pressupõe que você já tenha executado os módulos do PowerShell [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) e [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) ). Os *gerentes de exportação e seus scripts do directs* criam um arquivo delimitado por tabulação (ExportedManagerDirects. txt) que lista todos os gerentes com seus subordinados diretos. 

Em seguida, execute o [script criar novas equipes de gerentes de pessoas](scripts/powershell-script-create-teams-from-managers-new-teams.md). Esse script lê no arquivo ExportedManagerDirects. txt e cria uma equipe para cada gerente, com os relatórios diretos do gerente como membros. Se algum gerente ou direto não estiver habilitado para o Teams, o script os ignorará e não criará uma equipe. (Revise o relatório e execute o script novamente depois de ativar o Teams para qualquer pessoa que precisar. O script não criará uma segunda equipe para qualquer gerente que já tenha criado uma equipe.)

Para cada equipe, o script cria um canal geral e "apenas para diversão". 

## <a name="best-practices"></a>Práticas recomendadas

- Peça a cada gerente de pessoas para adicionar o site de comunicações de crise da sua organização como uma guia ao canal geral para cada equipe. 

- Confira o novo aplicativo de comunicações de crise lendo esta postagem de blog de 8 de março de 2020: [coordene comunicações de crise usando a plataforma de energia do Microsoft Teams +](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).

## <a name="related-topics"></a>Tópicos relacionados

[Práticas recomendadas para organizar equipes](best-practices-organizing.md)

[Criar uma equipe englobando toda a organização no Teams](create-an-org-wide-team.md)
