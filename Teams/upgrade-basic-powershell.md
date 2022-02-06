---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder Política de Interopção de Atualização
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre uma parada para atualizar para Microsoft Teams se o Centro de Administração não tiver acendido em seu locatário.
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
---

# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a>Atualizando seus usuários do Skype for Business Online para Microsoft Teams

> [!Note]
> Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação [Upgrade Basic](./upgrade-start-here.md) .

Os aspectos de migração técnica de sua atualização implicam notificar seus usuários de que Skype for Business serão atualizados para Teams e, em seguida, migrar para um modo **somente Teams usuário**. Essas etapas podem ser realizadas por meio de uma Skype for Business de Windows PowerShell remota ou por meio do Microsoft Teams de administração.

Estamos implantando ferramentas de atualização ativamente no centro de [](manage-teams-skypeforbusiness-admin-center.md)administração Microsoft Teams e ele deve estar disponível em breve em seu locatário. Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários em Configurando suas configurações de [coexistência e atualização](./setting-your-coexistence-and-upgrade-settings.md).

Se você estiver pronto para atualizar hoje, poderá usar os comandos [do PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.

| Etapa Upgrade Basic # | Modo | Comando do PowerShell |
|---|---|---|
| [5](upgrade-basic.md#step-5) | Ilhas + Notificar o Skype for Business Usuário<br>(Use este comando se os usuários estão atualmente no **modo Ilhas** (padrão)) | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br>*(por exemplo, $SipAddress='TestUser@contoso.com')* |
| [5](upgrade-basic.md#step-5) | Skype for Business Somente + Notificar o Skype for Business Usuário <br>(Use este comando se os usuários estão atualmente **no Skype for Business modo somente**) | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [7](upgrade-basic.md#step-7) | Teams Somente | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |