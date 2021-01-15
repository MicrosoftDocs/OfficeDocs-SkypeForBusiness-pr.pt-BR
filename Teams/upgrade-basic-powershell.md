---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder Política de Interopção de Atualização
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre uma parada para atualizar para o Microsoft Teams se o Centro de Administração não tiver se iluminado em seu locatário.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: adb9a0854268df25ebb8dc0337db22f792834b36
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809091"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizando seus usuários do Skype for Business Online para o Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação [Upgrade Basic.](https://aka.ms/UpgradeBasic)

Os aspectos de migração técnica de sua atualização envolvem notificar seus usuários de que o Skype for Business será atualizado para o Teams e, em seguida, migrando-os para um modo somente **teams.** Essas etapas podem ser realizadas por meio de uma sessão de Windows PowerShell remota do Skype for Business ou por meio do centro de administração do Microsoft Teams.

Estamos implantando ativamente as ferramentas de atualização no centro de administração do [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ela deve estar disponível em breve em seu locatário. Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários na configuração de sua coexistência e configurações [de atualização.](https://aka.ms/SkypeToTeams-SetCoexistence)

Se você estiver pronto para atualizar hoje, poderá usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa Do Upgrade Basic # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + Notificar o usuário do Skype for Business<br>(Use este comando se os usuários estão atualmente no **modo Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Somente Skype for Business + Notificar o usuário do Skype for Business <br>(Use este comando se os usuários estão atualmente no **modo somente Skype for Business)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Somente teams | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
