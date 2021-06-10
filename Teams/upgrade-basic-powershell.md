---
title: Atualização básica do PowerShell| Microsoft Teams| Conceder Política de Interopção de Atualização
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre uma parada para atualizar para Microsoft Teams se o Centro de Administração não tiver acendido em seu locatário.
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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="523f2-103">Atualizando seus usuários do Skype for Business Online para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="523f2-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="523f2-104">Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação [Upgrade Basic.](./upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="523f2-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](./upgrade-start-here.md) checklist.</span></span>

<span data-ttu-id="523f2-105">Os aspectos de migração técnica de sua atualização implicam notificar os usuários de que Skype for Business serão atualizados para Teams e, em seguida, migrar para um modo somente **Teams** usuário.</span><span class="sxs-lookup"><span data-stu-id="523f2-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="523f2-106">Essas etapas podem ser realizadas por meio de uma Skype for Business de Windows PowerShell remota ou por meio do Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="523f2-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="523f2-107">Estamos implantando ferramentas de atualização [](manage-teams-skypeforbusiness-admin-center.md)ativamente no centro de administração Microsoft Teams e ele deve estar disponível em breve em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="523f2-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="523f2-108">Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários em Configurando suas configurações de [coexistência e atualização.](./setting-your-coexistence-and-upgrade-settings.md)</span><span class="sxs-lookup"><span data-stu-id="523f2-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md).</span></span>

<span data-ttu-id="523f2-109">Se você estiver pronto para atualizar hoje, poderá usar os comandos [do PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="523f2-109">If you're ready to upgrade today, you can use the [PowerShell](/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="523f2-110">Etapa Upgrade Basic #</span><span class="sxs-lookup"><span data-stu-id="523f2-110">Upgrade Basic step #</span></span> | <span data-ttu-id="523f2-111">Modo</span><span class="sxs-lookup"><span data-stu-id="523f2-111">Mode</span></span> | <span data-ttu-id="523f2-112">Comando do PowerShell</span><span class="sxs-lookup"><span data-stu-id="523f2-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="523f2-113">5</span><span class="sxs-lookup"><span data-stu-id="523f2-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="523f2-114">Ilhas + Notificar o Skype for Business Usuário</span><span class="sxs-lookup"><span data-stu-id="523f2-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="523f2-115">(Use este comando se os usuários estão atualmente no **modo Ilhas** (padrão))</span><span class="sxs-lookup"><span data-stu-id="523f2-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="523f2-116">*(por exemplo, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="523f2-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="523f2-117">5</span><span class="sxs-lookup"><span data-stu-id="523f2-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="523f2-118">Skype for Business Somente + Notificar o Skype for Business Usuário</span><span class="sxs-lookup"><span data-stu-id="523f2-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="523f2-119">(Use este comando se os usuários estão atualmente **no Skype for Business único** modo)</span><span class="sxs-lookup"><span data-stu-id="523f2-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="523f2-120">7</span><span class="sxs-lookup"><span data-stu-id="523f2-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="523f2-121">Teams Somente</span><span class="sxs-lookup"><span data-stu-id="523f2-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |