---
title: Atualização básica do PowerShell | Microsoft Teams | Conceder política de interoperabilidade de atualização
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Stopgap para a atualização para o Microsoft Teams se o centro de administração ainda não estiver aceso em seu locatário
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
ms.openlocfilehash: 20864b6b0a4be8cf9a0a88c6f3ce63c18687f2af
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41837231"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizando seus usuários do Skype for Business online para o Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação de [atualização básica](https://aka.ms/UpgradeBasic) .

Os aspectos da migração técnica de sua atualização envolvem a notificação de seus usuários que o Skype for Business será atualizado para o Microsoft Teams e, em seguida, movendo-os para um modo **somente para equipes** . Essas etapas podem ser realizadas por meio de uma sessão remota do Windows PowerShell do Skype for Business ou por meio do centro de administração do Microsoft Teams.

Estamos lançando ativamente a ferramenta de atualização no [centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ele deve estar disponível em breve no seu locatário. Assim que estiver disponível, você poderá encontrar informações sobre como migrar seus usuários para [definir suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence).

Se estiver pronto para atualizar hoje, você pode usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa básica de atualização # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + notifique o usuário do Skype for Business<br>(Use este comando se os usuários estiverem no modo de ilhas no modo de **ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress = ' TestUser@contoso.com ')* |
| [5](upgrade-basic.md#step-5) | Skype para empresas apenas + notifique o usuário do Skype for Business <br>(Use este comando se os usuários estiverem no modo **somente Skype for Business** .) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Somente equipes | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
