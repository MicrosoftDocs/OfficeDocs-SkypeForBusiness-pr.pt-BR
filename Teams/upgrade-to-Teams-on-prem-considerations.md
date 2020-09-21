---
title: Atualize para o Teams a partir de uma implantação local do Skype for Business-Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/20
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Atualização do Skype for Business para o Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e16e651004148645789f5e8e55df6fbbfa1dea9c
ms.sourcegitcommit: b37632ffa22e3a6045b476c95d46889e9193a15b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/17/2020
ms.locfileid: "47955908"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="43d81-103">Considerações de atualização para organizações com o Skype for Business Server local &mdash; para administradores de ti</span><span class="sxs-lookup"><span data-stu-id="43d81-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="43d81-104">Este artigo descreve outras considerações sobre organizações com o Skype for Business Server no local.</span><span class="sxs-lookup"><span data-stu-id="43d81-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="43d81-105">Este artigo é o quarto de vários que descrevem os conceitos de atualização e a implementação para administradores de ti.</span><span class="sxs-lookup"><span data-stu-id="43d81-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="43d81-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="43d81-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="43d81-107">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="43d81-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="43d81-108">Ferramentas para gerenciar a atualização</span><span class="sxs-lookup"><span data-stu-id="43d81-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="43d81-109">**Considerações adicionais sobre organizações com o Skype for Business local** (este artigo)</span><span class="sxs-lookup"><span data-stu-id="43d81-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="43d81-110">Implementando a atualização</span><span class="sxs-lookup"><span data-stu-id="43d81-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="43d81-111">Considerações sobre PSTN (rede telefônica pública comutada)</span><span class="sxs-lookup"><span data-stu-id="43d81-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="43d81-112">Além disso, os seguintes artigos descrevem conceitos importantes de atualização e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="43d81-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="43d81-113">Coexistência de Teams e Skype for Business</span><span class="sxs-lookup"><span data-stu-id="43d81-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="43d81-114">Modos de coexistência-referência</span><span class="sxs-lookup"><span data-stu-id="43d81-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="43d81-115">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="43d81-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="43d81-116">Considerações sobre organizações com o Skype for Business Server no local</span><span class="sxs-lookup"><span data-stu-id="43d81-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="43d81-117">Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="43d81-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="43d81-118">Embora seja possível usar o Teams no modo de ilhas sem híbrido, a transição para o modo TeamsOnly não pode ser feita até que o usuário seja movido do Skype for Business local para o Skype for Business online (usando [move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span><span class="sxs-lookup"><span data-stu-id="43d81-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="43d81-119">Para obter mais informações, consulte [configurar conectividade híbrida](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="43d81-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="43d81-120">Se sua organização tiver o Skype for Business Server e você ainda não configurou a conectividade híbrida, mas ainda deseja usar o Teams, para administrar a funcionalidade do Teams, você deve usar uma conta administrativa que tenha um domínio. onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="43d81-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="43d81-121">Os usuários do teams que têm uma conta local do Skype for Business (ou seja, eles ainda não foram movidos para a nuvem usando move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar usuários externos.</span><span class="sxs-lookup"><span data-stu-id="43d81-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="43d81-122">Essa funcionalidade só estará disponível quando os usuários forem movidos para a nuvem (no modo de ilhas ou como usuários do TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="43d81-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="43d81-123">Se você tiver usuários com contas do Skype for Business no local, não deverá atribuir o modo TeamsOnly no nível do locatário, a menos que você explicitamente atribua um outro modo para todos os usuários com contas do Skype for Business locais.</span><span class="sxs-lookup"><span data-stu-id="43d81-123">If you have any users with Skype for Business accounts on-premises, you must not assign TeamsOnly mode at the tenant level, unless you explicitly assign some other mode to all users with on-premises Skype for Business accounts.</span></span> 

- <span data-ttu-id="43d81-124">Você deve garantir que seus usuários sejam sincronizados corretamente com o Azure AD com os atributos corretos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="43d81-124">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="43d81-125">Esses atributos são todos os prefixos com "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="43d81-125">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="43d81-126">Se os usuários não forem sincronizados corretamente para o Azure AD, as ferramentas de gerenciamento do Teams não poderão gerenciar esses usuários.</span><span class="sxs-lookup"><span data-stu-id="43d81-126">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="43d81-127">(Por exemplo, você não poderá atribuir políticas de equipe aos usuários locais, a menos que você esteja sincronizando corretamente esses atributos.) Para obter mais informações, consulte [Configurar o Azure ad Connect para Teams e o Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span><span class="sxs-lookup"><span data-stu-id="43d81-127">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="43d81-128">Para criar um novo usuário do TeamsOnly ou do Skype for Business online em uma organização híbrida, *primeiro você deve habilitar o usuário no Skype for Business Server no local*e, em seguida, mover o usuário do local para a nuvem usando mover-CsUser.</span><span class="sxs-lookup"><span data-stu-id="43d81-128">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="43d81-129">A criação do usuário no local primeiro garante que qualquer outro usuário do Skype for Business restante seja direcionado para o usuário recém criado.</span><span class="sxs-lookup"><span data-stu-id="43d81-129">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="43d81-130">Depois que todos os usuários tiverem sido movidos online, não será mais necessário primeiro habilitar os usuários no local.</span><span class="sxs-lookup"><span data-stu-id="43d81-130">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="43d81-131">Quando um usuário é movido do local para a nuvem, as reuniões organizadas por esse usuário são migradas para o Skype for Business online ou para o Teams, dependendo se a opção-MoveToTeams está ou não especificada.</span><span class="sxs-lookup"><span data-stu-id="43d81-131">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="43d81-132">Se quiser exibir notificações no cliente Skype for Business para usuários locais, você deve usar o TeamsUpgradePolicy no conjunto de ferramentas local.</span><span class="sxs-lookup"><span data-stu-id="43d81-132">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="43d81-133">Somente o parâmetro NotifySfbUsers é relevante para usuários locais.</span><span class="sxs-lookup"><span data-stu-id="43d81-133">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="43d81-134">Os usuários locais recebem o modo das instâncias online do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="43d81-134">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="43d81-135">Consulte as anotações em [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="43d81-135">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="43d81-136">Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43d81-136">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="43d81-137">A Microsoft usa registros de DNS para identificar as organizações do Skype for Business Server locais.</span><span class="sxs-lookup"><span data-stu-id="43d81-137">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="43d81-138">Se sua organização tiver o Skype for Business Server local sem entradas DNS públicas, você precisará ligar para o suporte da Microsoft para que seu novo locatário seja rebaixado.</span><span class="sxs-lookup"><span data-stu-id="43d81-138">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 



















## <a name="related-links"></a><span data-ttu-id="43d81-139">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="43d81-139">Related links</span></span>

[<span data-ttu-id="43d81-140">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="43d81-140">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="43d81-141">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="43d81-141">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="43d81-142">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="43d81-142">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="43d81-143">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="43d81-143">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="43d81-144">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="43d81-144">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="43d81-145">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="43d81-145">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

