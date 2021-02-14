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
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="8a8f7-103">Atualizando seus usuários do Skype for Business Online para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8a8f7-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="8a8f7-104">Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação do [Upgrade Basic.](https://aka.ms/UpgradeBasic)</span><span class="sxs-lookup"><span data-stu-id="8a8f7-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="8a8f7-105">Os aspectos da migração técnica de sua atualização exigem a notificação aos usuários de que o Skype for Business será atualizado para o Teams e, em seguida, migrando-os para um modo somente **do Teams.**</span><span class="sxs-lookup"><span data-stu-id="8a8f7-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="8a8f7-106">Essas etapas podem ser realizadas por meio de uma sessão remota do Windows PowerShell do Skype for Business ou por meio do Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8a8f7-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="8a8f7-107">Estamos implantando ativamente as ferramentas de atualização no Centro de administração do [Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ela deverá estar disponível em breve no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8a8f7-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="8a8f7-108">Assim que ele está disponível, você pode encontrar informações sobre como migrar seus usuários em Definir sua coexistência e configurações [de atualização.](https://aka.ms/SkypeToTeams-SetCoexistence)</span><span class="sxs-lookup"><span data-stu-id="8a8f7-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="8a8f7-109">Se você estiver pronto para atualizar hoje, poderá usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="8a8f7-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="8a8f7-110">Etapa básica de atualização #</span><span class="sxs-lookup"><span data-stu-id="8a8f7-110">Upgrade Basic step #</span></span> | <span data-ttu-id="8a8f7-111">Modo</span><span class="sxs-lookup"><span data-stu-id="8a8f7-111">Mode</span></span> | <span data-ttu-id="8a8f7-112">Comando do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a8f7-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="8a8f7-113">5</span><span class="sxs-lookup"><span data-stu-id="8a8f7-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8a8f7-114">Islands+Notifique o Usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8a8f7-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="8a8f7-115">(Use esse comando se os usuários estão no modo **Ilhas** (padrão))</span><span class="sxs-lookup"><span data-stu-id="8a8f7-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="8a8f7-116">*(por exemplo, $SipAddress='TestUser@contoso.com')*</span><span class="sxs-lookup"><span data-stu-id="8a8f7-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="8a8f7-117">5</span><span class="sxs-lookup"><span data-stu-id="8a8f7-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="8a8f7-118">Somente Skype for Business + Notificar o Usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8a8f7-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="8a8f7-119">(Use este comando se os usuários estão atualmente no **modo somente skype for Business)**</span><span class="sxs-lookup"><span data-stu-id="8a8f7-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="8a8f7-120">7</span><span class="sxs-lookup"><span data-stu-id="8a8f7-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="8a8f7-121">Somente equipes</span><span class="sxs-lookup"><span data-stu-id="8a8f7-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
