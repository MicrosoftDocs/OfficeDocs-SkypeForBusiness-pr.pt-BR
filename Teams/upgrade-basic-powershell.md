---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder a Política Interop de Atualização
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre uma parada para atualizar para o Microsoft Teams se o Centro de Administração não tiver acendido em seu locatário.
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
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação do [Upgrade Basic.](https://aka.ms/UpgradeBasic)

Os aspectos da migração técnica de sua atualização exigem a notificação aos usuários de que o Skype for Business será atualizado para o Teams e, em seguida, migrando-os para um modo somente **do Teams.** Essas etapas podem ser realizadas por meio de uma sessão remota do Windows PowerShell do Skype for Business ou por meio do Centro de administração do Microsoft Teams.

Estamos implantando ativamente as ferramentas de atualização no Centro de administração do [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ela deverá estar disponível em breve no seu locatário. Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários em Definir sua coexistência e configurações [de atualização.](https://aka.ms/SkypeToTeams-SetCoexistence)

Se você estiver pronto para atualizar hoje, poderá usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa básica de atualização # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Islands+Notifique o Usuário do Skype for Business<br>(Use esse comando se os usuários estão no modo **Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Somente Skype for Business + Notificar o Usuário do Skype for Business <br>(Use este comando se os usuários estão atualmente no **modo somente skype for Business)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Somente equipes | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
