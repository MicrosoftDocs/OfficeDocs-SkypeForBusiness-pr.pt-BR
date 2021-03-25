---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder Política de Interopção de Atualização
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
ms.openlocfilehash: ef164ee5d93cb5491923ef3b319ae51134924cc2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120532"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizando seus usuários do Skype for Business Online para o Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação [Upgrade Basic.](./upgrade-start-here.md)

Os aspectos de migração técnica de sua atualização implicam notificar os usuários de que o Skype for Business será atualizado para o Teams e, em seguida, migrar para um modo somente **do Teams.** Essas etapas podem ser realizadas por meio de uma sessão Windows PowerShell remota do Skype for Business ou por meio do Centro de administração do Microsoft Teams.

Estamos implantando ferramentas de atualização ativamente no centro de administração do [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ele deve estar disponível em breve no locatário. Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários em Configurando suas configurações de [coexistência e atualização.](./setting-your-coexistence-and-upgrade-settings.md)

Se você estiver pronto para atualizar hoje, poderá usar os comandos [do PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa Upgrade Basic # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + Notificar o usuário do Skype for Business<br>(Use este comando se os usuários estão atualmente no **modo Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Only + Notificar o usuário do Skype for Business <br>(Use este comando se os usuários estão atualmente **no modo somente skype for Business)** | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Somente equipes | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |