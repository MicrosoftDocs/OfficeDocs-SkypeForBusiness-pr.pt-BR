---
title: Atualizar os comandos do PowerShell básica - Teams da Microsoft
author: dearbeen
ms.author: dearbeen
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Provisórias para atualizar para equipes se o Admin Center ainda não aceso no seu locatário
localization_priority: Priority
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8b65cd7a7b9ef91194b2045193a98672bfd25326
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001715"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="fcb7c-103">Atualizar seus usuários do Skype para Business Online para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fcb7c-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="fcb7c-104">Os comandos descritos neste artigo foram criados para ser usado como parte da lista de verificação [Atualizar básica](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="fcb7c-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="fcb7c-105">Os aspectos da migração técnico da sua atualização implicam notificar os usuários que Skype para negócios será atualizar para equipes e depois movê-los para um modo de **equipes apenas** .</span><span class="sxs-lookup"><span data-stu-id="fcb7c-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="fcb7c-106">Essas etapas podem ser realizadas por meio de um Skype para sessão do Windows PowerShell remoto de negócios ou por meio do Microsoft Teams & Skype para Business Admin Center.</span><span class="sxs-lookup"><span data-stu-id="fcb7c-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams & Skype for Business Admin Center.</span></span> 
 
<span data-ttu-id="fcb7c-107">Podemos ativamente está implantando ferramentas no [Microsoft equipes & Skype para Business Admin Center](manage-teams-skypeforbusiness-admin-center.md)de atualização e ela deverá estar disponível em breve no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="fcb7c-107">We're actively rolling out upgrade tooling in the [Microsoft Teams & Skype for Business Admin Center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="fcb7c-108">Assim que estiver disponível, você pode encontrar informações sobre como migrar os usuários na [sua coexistência de configuração e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="fcb7c-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span> 
 
<span data-ttu-id="fcb7c-109">Se você estiver pronto para atualizar hoje, você pode usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="fcb7c-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span> 
 
 |<span data-ttu-id="fcb7c-110">Etapa de atualização básica #</span><span class="sxs-lookup"><span data-stu-id="fcb7c-110">Upgrade Basic step #</span></span> | <span data-ttu-id="fcb7c-111">Modo</span><span class="sxs-lookup"><span data-stu-id="fcb7c-111">Mode</span></span> | <span data-ttu-id="fcb7c-112">Comando do PowerShell</span><span class="sxs-lookup"><span data-stu-id="fcb7c-112">PowerShell command</span></span> |
|-------|--------|------|
| [<span data-ttu-id="fcb7c-113">5</span><span class="sxs-lookup"><span data-stu-id="fcb7c-113">5</span></span>](upgrade-basic.md#step-5) |<span data-ttu-id="fcb7c-114">Ilhas + notificar o Skype para o usuário de negócios</span><span class="sxs-lookup"><span data-stu-id="fcb7c-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="fcb7c-115">(Use esse comando se os usuários estão atualmente no modo **Ilhas** (padrão))</span><span class="sxs-lookup"><span data-stu-id="fcb7c-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="fcb7c-116">_(por exemplo, $SipAddress = 'TestUser@contoso.com')_</span><span class="sxs-lookup"><span data-stu-id="fcb7c-116">_(for example, $SipAddress='TestUser@contoso.com')_</span></span><br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingDefaultChatDefault -Identity $SipAddress``` |
| [<span data-ttu-id="fcb7c-117">5</span><span class="sxs-lookup"><span data-stu-id="fcb7c-117">5</span></span>](upgrade-basic.md#step-5)  | <span data-ttu-id="fcb7c-118">Skype para negócios apenas + notificar o Skype para o usuário de negócios</span><span class="sxs-lookup"><span data-stu-id="fcb7c-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="fcb7c-119">(Use esse comando se os usuários estão atualmente no modo de **Skype para negócios somente** )</span><span class="sxs-lookup"><span data-stu-id="fcb7c-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingSfBChatSfB -Identity $SipAddress``` |
| [<span data-ttu-id="fcb7c-120">7</span><span class="sxs-lookup"><span data-stu-id="fcb7c-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="fcb7c-121">Somente as equipes</span><span class="sxs-lookup"><span data-stu-id="fcb7c-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress``` <br><br>```Grant-CsTeamsInteropPolicy -PolicyName DisallowOverrideCallingTeamsChatTeams -Identity $SipAddress``` |


