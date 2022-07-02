---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder política de interoperabilidade de atualização
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre um stopgap para atualizar para o Microsoft Teams se o Administração Center não tiver sido iluminado em seu locatário.
ms.localizationpriority: medium
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
ms.openlocfilehash: 02ba32e5b498639e93bc10757c51429871f5683a
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606030"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizando seus usuários do Skype for Business Online para o Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação [Atualizar Básico](./upgrade-start-here.md) .

Os aspectos de migração técnica da atualização envolvem notificar os usuários de que Skype for Business serão atualizados para o Teams e, em seguida, movê-los para um modo somente **teams**. Essas etapas podem ser realizadas por meio de Skype for Business sessão Windows PowerShell remota ou por meio do Centro de administração do Microsoft Teams.

Estamos implantando ativamente as ferramentas de atualização no centro de administração do [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md) e ela deve estar disponível em breve no seu locatário. Assim que ele estiver disponível, você poderá encontrar informações sobre como migrar seus usuários em Definir suas configurações [de coexistência e atualização](./setting-your-coexistence-and-upgrade-settings.md).

Se você estiver pronto para atualizar hoje, poderá usar os comandos do [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa Atualizar Básico # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + Notificar o Skype for Business usuário<br>(Use este comando se os usuários estão atualmente no **modo Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business + Notificar o Skype for Business usuário <br>(Use este comando se os usuários estão atualmente **Skype for Business modo** somente) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Somente Equipes | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |