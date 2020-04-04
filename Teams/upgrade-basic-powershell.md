---
title: Atualização básica do PowerShell | Microsoft Teams | Conceder política de interoperabilidade de atualização
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Stopgap para a atualização do Microsoft Teams se o centro de administração ainda não estiver aceso em seu locatário.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 84ecfb8b9286b749e5b1bf6d34cdf0c8c8fd4113
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139670"
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
