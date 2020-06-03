---
title: Atualização básica do PowerShell | Microsoft Teams | Conceder política de interoperabilidade de atualização
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre um stopgap para atualizar para o Microsoft Teams se o centro de administração ainda não estiver aceso em seu locatário.
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
ms.openlocfilehash: d51ff3304aae82f49023bdf461e76e4585cda296
ms.sourcegitcommit: 6acede580649588334aeb48130ab2a5d73245723
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2020
ms.locfileid: "44522474"
---
# <a name="upgrading-your-users-from-skype-for-business-online-to-microsoft-teams"></a><span data-ttu-id="3840e-103">Atualizando seus usuários do Skype for Business online para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3840e-103">Upgrading your users from Skype for Business Online to Microsoft Teams</span></span>

> [!Note]
> <span data-ttu-id="3840e-104">Os comandos descritos neste artigo foram projetados para serem usados como parte da lista de verificação de [atualização básica](https://aka.ms/UpgradeBasic) .</span><span class="sxs-lookup"><span data-stu-id="3840e-104">The commands described in this article are designed to be used as part of the [Upgrade Basic](https://aka.ms/UpgradeBasic) checklist.</span></span>

<span data-ttu-id="3840e-105">Os aspectos da migração técnica de sua atualização envolvem a notificação de seus usuários que o Skype for Business será atualizado para o Microsoft Teams e, em seguida, movendo-os para um modo **somente para equipes** .</span><span class="sxs-lookup"><span data-stu-id="3840e-105">The technical migration aspects of your upgrade entail notifying your users that Skype for Business will be upgrading to Teams and then moving them to a **Teams only** mode.</span></span> <span data-ttu-id="3840e-106">Essas etapas podem ser realizadas por meio de uma sessão remota do Windows PowerShell do Skype for Business ou por meio do centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3840e-106">These steps can be accomplished via a Skype for Business remote Windows PowerShell session or through the Microsoft Teams admin center.</span></span>

<span data-ttu-id="3840e-107">Estamos lançando ativamente a ferramenta de atualização no [centro de administração do Microsoft Teams](manage-teams-skypeforbusiness-admin-center.md)e ele deve estar disponível em breve no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="3840e-107">We're actively rolling out upgrade tooling in the [Microsoft Teams admin center](manage-teams-skypeforbusiness-admin-center.md), and it should be available soon on your tenant.</span></span> <span data-ttu-id="3840e-108">Assim que estiver disponível, você poderá encontrar informações sobre como migrar seus usuários para [definir suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence).</span><span class="sxs-lookup"><span data-stu-id="3840e-108">As soon as it's available, you can find information about migrating your users in [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>

<span data-ttu-id="3840e-109">Se estiver pronto para atualizar hoje, você pode usar os comandos do [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="3840e-109">If you're ready to upgrade today, you can use the [PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell) commands listed in the following table.</span></span>

| <span data-ttu-id="3840e-110">Etapa básica de atualização #</span><span class="sxs-lookup"><span data-stu-id="3840e-110">Upgrade Basic step #</span></span> | <span data-ttu-id="3840e-111">Modo</span><span class="sxs-lookup"><span data-stu-id="3840e-111">Mode</span></span> | <span data-ttu-id="3840e-112">Comando do PowerShell</span><span class="sxs-lookup"><span data-stu-id="3840e-112">PowerShell command</span></span> |
|---|---|---|
| [<span data-ttu-id="3840e-113">5</span><span class="sxs-lookup"><span data-stu-id="3840e-113">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3840e-114">Ilhas + notifique o usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3840e-114">Islands + Notify the Skype for Business User</span></span><br><span data-ttu-id="3840e-115">(Use este comando se os usuários estiverem no modo de ilhas no modo de **ilhas** (padrão))</span><span class="sxs-lookup"><span data-stu-id="3840e-115">(Use this command if users are currently in **Islands** mode (default))</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName IslandsWithNotify -Identity $SipAddress```<br><span data-ttu-id="3840e-116">*(por exemplo, $SipAddress = ' TestUser@contoso.com ')*</span><span class="sxs-lookup"><span data-stu-id="3840e-116">*(for example, $SipAddress='TestUser@contoso.com')*</span></span> |
| [<span data-ttu-id="3840e-117">5</span><span class="sxs-lookup"><span data-stu-id="3840e-117">5</span></span>](upgrade-basic.md#step-5) | <span data-ttu-id="3840e-118">Skype para empresas apenas + notifique o usuário do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="3840e-118">Skype for Business Only + Notify the Skype for Business User</span></span> <br><span data-ttu-id="3840e-119">(Use este comando se os usuários estiverem no modo **somente Skype for Business** .)</span><span class="sxs-lookup"><span data-stu-id="3840e-119">(Use this command if users are currently in **Skype for Business only** mode)</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName SfBOnlyWithNotify -Identity $SipAddress```  |
| [<span data-ttu-id="3840e-120">7</span><span class="sxs-lookup"><span data-stu-id="3840e-120">7</span></span>](upgrade-basic.md#step-7) | <span data-ttu-id="3840e-121">Somente equipes</span><span class="sxs-lookup"><span data-stu-id="3840e-121">Teams Only</span></span> | ```Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Identity $SipAddress```  |
