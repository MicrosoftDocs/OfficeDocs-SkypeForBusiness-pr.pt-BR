---
title: PowerShell básica de atualização | As equipes da Microsoft | Política de interoperabilidade de atualização de Grant
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisórias para atualizar para equipes se o Admin Center ainda não aceso no seu locatário
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f81e796d893ef17138398c8a5739a4284bcfc4a3
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30459736"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizar seus usuários do Skype para Business Online para o Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram criados para ser usado como parte da lista de verificação [Atualizar básica](https://aka.ms/UpgradeBasic) .

Os aspectos da migração técnico da sua atualização implicam notificar os usuários que Skype para negócios será atualizar para equipes e depois movê-los para um modo de **equipes apenas** . Essas etapas podem ser realizadas por meio de um Skype para a sessão do Windows PowerShell remoto de negócios ou por meio do Centro de administração do Microsoft Teams.

Podemos ativamente está implantando ferramentas no [Centro de administração do Microsoft equipes](manage-teams-skypeforbusiness-admin-center.md)de atualização e ela deverá estar disponível em breve no seu locatário. Assim que estiver disponível, você pode encontrar informações sobre como migrar os usuários na [sua coexistência de configuração e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).

Se você estiver pronto para atualizar hoje, você pode usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa de atualização básica # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + notificar o Skype para o usuário de negócios<br>(Use esse comando se os usuários estão atualmente no modo **Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress = 'TestUser@contoso.com')*<br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [5](upgrade-basic.md#step-5) | Skype para negócios apenas + notificar o Skype para o usuário de negócios <br>(Use esse comando se os usuários estão atualmente no modo de **Skype para negócios somente** ) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [7](upgrade-basic.md#step-7) | Somente as equipes | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |