---
title: Atualizar para o Teams a partir de uma implantação local do Skype for Business – Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
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
ms.openlocfilehash: cf034969c2b6ca030eede72ff358a517fafe501f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533588"
---
# <a name="upgrade-considerations-for-organizations-with-skype-for-business-server-on-premises-mdash-for-it-administrators"></a><span data-ttu-id="0a915-103">Considerações de atualização para organizações com o Skype for Business Server local &mdash; para administradores de IT</span><span class="sxs-lookup"><span data-stu-id="0a915-103">Upgrade considerations for organizations with Skype for Business Server on-premises &mdash; for IT administrators</span></span>

<span data-ttu-id="0a915-104">Este artigo descreve considerações adicionais para organizações com o Skype for Business Server local.</span><span class="sxs-lookup"><span data-stu-id="0a915-104">This article describes additional considerations for organizations with Skype for Business Server on-premises.</span></span> <span data-ttu-id="0a915-105">Este artigo é o quarto de vários que descrevem conceitos de atualização e implementação para administradores de IT.</span><span class="sxs-lookup"><span data-stu-id="0a915-105">This article is the fourth of several that describe upgrade concepts and implementation for IT administrators.</span></span>  

- [<span data-ttu-id="0a915-106">Visão geral</span><span class="sxs-lookup"><span data-stu-id="0a915-106">Overview</span></span>](upgrade-to-teams-on-prem-overview.md)
- [<span data-ttu-id="0a915-107">Métodos de atualização</span><span class="sxs-lookup"><span data-stu-id="0a915-107">Upgrade methods</span></span>](upgrade-to-teams-on-prem-upgrade-methods.md)
- [<span data-ttu-id="0a915-108">Ferramentas para gerenciar sua atualização</span><span class="sxs-lookup"><span data-stu-id="0a915-108">Tools for managing your upgrade</span></span>](upgrade-to-teams-on-prem-tools.md)
- <span data-ttu-id="0a915-109">**Considerações adicionais para organizações com o Skype for Business local** (este artigo)</span><span class="sxs-lookup"><span data-stu-id="0a915-109">**Additional considerations for organizations with Skype for Business on-premises** (this article)</span></span>
- [<span data-ttu-id="0a915-110">Implementando sua atualização</span><span class="sxs-lookup"><span data-stu-id="0a915-110">Implementing your upgrade</span></span>](upgrade-to-teams-on-prem-implement.md)
- [<span data-ttu-id="0a915-111">Considerações sobre A Rede Telefônica Pública Comutado (PSTN)</span><span class="sxs-lookup"><span data-stu-id="0a915-111">Public Switched Telephone Network (PSTN) considerations</span></span>](upgrade-to-teams-on-prem-pstn-considerations.md)

<span data-ttu-id="0a915-112">Além disso, os artigos a seguir descrevem conceitos de atualização importantes e comportamentos de coexistência:</span><span class="sxs-lookup"><span data-stu-id="0a915-112">In addition, the following articles describe important upgrade concepts and coexistence behaviors:</span></span>

- [<span data-ttu-id="0a915-113">Coexistência do Teams e do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0a915-113">Coexistence of Teams and Skype for Business</span></span>](upgrade-to-teams-on-prem-coexistence.md)
- [<span data-ttu-id="0a915-114">Modos de coexistência - Referência</span><span class="sxs-lookup"><span data-stu-id="0a915-114">Coexistence modes - Reference</span></span>](migration-interop-guidance-for-teams-with-skype.md)
- [<span data-ttu-id="0a915-115">Experiência e conformidade do cliente do Teams a modos de coexistência</span><span class="sxs-lookup"><span data-stu-id="0a915-115">Teams client experience and conformance to coexistence modes</span></span>](teams-client-experience-and-conformance-to-coexistence-modes.md)



## <a name="considerations-for-organizations-with-skype-for-business-server-on-premises"></a><span data-ttu-id="0a915-116">Considerações para organizações com o Skype for Business Server local</span><span class="sxs-lookup"><span data-stu-id="0a915-116">Considerations for organizations with Skype for Business Server on-premises</span></span>

- <span data-ttu-id="0a915-117">Configurar o Skype for Business híbrido é um pré-requisito para migrar para o modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="0a915-117">Setting up Skype for Business hybrid is a prerequisite to migrate to TeamsOnly mode.</span></span> <span data-ttu-id="0a915-118">Embora seja possível usar o Teams no modo Ilhas sem híbrido, a transição para o modo TeamsOnly não poderá ser feita até que o usuário seja movido do Skype for Business local para o Skype for Business Online (usando [o Move-CsUser).](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)</span><span class="sxs-lookup"><span data-stu-id="0a915-118">While it is possible to use Teams in Islands mode without hybrid, the transition to TeamsOnly mode cannot be made until the user is moved from Skype for Business on-premises to Skype for Business Online (using [Move-CsUser](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)).</span></span> <span data-ttu-id="0a915-119">Para obter mais informações, consulte [Configurar conectividade híbrida.](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="0a915-119">For more information, see [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/hybrid/configure-hybrid-connectivity).</span></span>

- <span data-ttu-id="0a915-120">Se sua organização tiver o Skype for Business Server e você não tiver configurado a conectividade híbrida, mas ainda quiser usar o Teams, para administrar a funcionalidade do Teams, use uma conta administrativa que tenha um domínio .onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0a915-120">If your organization has Skype for Business Server and you have not configured hybrid connectivity, but you still want to use Teams, to administer Teams functionality, you must use an administrative account that has an .onmicrosoft.com domain.</span></span> 

- <span data-ttu-id="0a915-121">Os usuários do Teams que têm uma conta do Skype for Business local (ou seja, eles ainda não foram movidos para a nuvem usando o Move-CsUser) não podem interoperar com nenhum usuário do Skype for Business, nem podem federar com usuários externos.</span><span class="sxs-lookup"><span data-stu-id="0a915-121">Teams users who have a Skype for Business account on-premises (that is, they have not yet been moved to the cloud by using Move-CsUser) cannot interoperate with any Skype for Business users, nor can they federate with external users.</span></span> <span data-ttu-id="0a915-122">Essa funcionalidade só estará disponível quando os usuários são movidos para a nuvem (no modo Ilhas ou como usuários do TeamsOnly).</span><span class="sxs-lookup"><span data-stu-id="0a915-122">This functionality is only available once the users are moved to the cloud (either in Islands mode, or as TeamsOnly users).</span></span> 

- <span data-ttu-id="0a915-123">Se você tiver usuários com contas do Skype for Business no local, não poderá atribuir o modo TeamsOnly no nível do locatário.</span><span class="sxs-lookup"><span data-stu-id="0a915-123">If you have any users with Skype for Business accounts on-premises, you cannot assign TeamsOnly mode at the tenant level.</span></span> <span data-ttu-id="0a915-124">Primeiro, você deve mover todos os usuários com contas locais do Skype for Business para a nuvem usando e desabilitar a migração híbrida para concluir a migração `Move-CsUser` [para a nuvem.](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)</span><span class="sxs-lookup"><span data-stu-id="0a915-124">You must first move all  users with on-premises Skype for Business accounts to the cloud using `Move-CsUser` and then [disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>  <span data-ttu-id="0a915-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` não funcionará no nível do locatário se um registro DNS de descoberta lyncdiscover for detectado que aponta para um local diferente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0a915-125">`Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams` will not work at the tenant level if a lyncdiscover DNS record is detected that points to a location other than Office 365.</span></span>

- <span data-ttu-id="0a915-126">Você deve garantir que seus usuários sejam sincronizados corretamente no Azure AD com os atributos corretos do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0a915-126">You must ensure your users are properly synchronized into Azure AD with the correct Skype for Business attributes.</span></span> <span data-ttu-id="0a915-127">Esses atributos são todos prefixos com "msRTCSIP-".</span><span class="sxs-lookup"><span data-stu-id="0a915-127">These attributes are all prefixes with “msRTCSIP-”.</span></span> <span data-ttu-id="0a915-128">Se os usuários não estiverem sincronizados corretamente com o Azure AD, as ferramentas de gerenciamento no Teams não poderão gerenciar esses usuários.</span><span class="sxs-lookup"><span data-stu-id="0a915-128">If users are not synchronized properly to Azure AD, the management tools in Teams will not be able to manage these users.</span></span> <span data-ttu-id="0a915-129">(Por exemplo, você não poderá atribuir políticas do Teams a usuários locais, a menos que esteja sincronizando esses atributos corretamente.) Para obter mais informações, consulte [Configurar o Azure AD Connect para Teams e o Skype for Business.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect)</span><span class="sxs-lookup"><span data-stu-id="0a915-129">(For example, you won’t be able to assign Teams policies to on-premises users unless you are properly syncing these attributes.) For more information, see [Configure Azure AD Connect for Teams and Skype for Business](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-azure-ad-connect).</span></span>

- <span data-ttu-id="0a915-130">Para criar um novo usuário do TeamsOnly ou do Skype for Business Online em uma organização híbrida, primeiro você deve habilitar o usuário no *Skype for Business Server* local e, em seguida, mover o usuário local para a nuvem usando o Move-CsUser.</span><span class="sxs-lookup"><span data-stu-id="0a915-130">To create a new TeamsOnly or Skype for Business Online user in a hybrid organization, *you must first enable the user in Skype for Business Server on-premises*, and then move the user from on-premises to the cloud using Move-CsUser.</span></span>  <span data-ttu-id="0a915-131">Criar o usuário local primeiro garante que outros usuários restantes do Skype for Business local sejam capazes de roteá-lo para o usuário recém-criado.</span><span class="sxs-lookup"><span data-stu-id="0a915-131">Creating the user in on-premises first ensures that any other remaining on-premises Skype for Business users will be able route to the newly created user.</span></span> <span data-ttu-id="0a915-132">Depois que todos os usuários são movidos online, não é mais necessário habilitar os usuários no local.</span><span class="sxs-lookup"><span data-stu-id="0a915-132">Once all users have been moved online, it is no longer necessary to first enable users in on-premises.</span></span>

- <span data-ttu-id="0a915-133">Quando um usuário é movido do local para a nuvem, as reuniões organizadas por esse usuário são migradas para o Skype for Business Online ou o Teams, dependendo se a opção -MoveToTeams está especificada ou não.</span><span class="sxs-lookup"><span data-stu-id="0a915-133">When a user is moved from on-premises to the cloud, meetings organized by that user are migrated to either Skype for Business Online or Teams--depending on whether or not the -MoveToTeams switch is specified.</span></span>

- <span data-ttu-id="0a915-134">Se quiser exibir notificações no cliente Skype for Business para usuários locais, use o TeamsUpgradePolicy no toolset local.</span><span class="sxs-lookup"><span data-stu-id="0a915-134">If you would like display notifications in the Skype for Business client for on-premises users, you must use TeamsUpgradePolicy in the on-premises toolset.</span></span> <span data-ttu-id="0a915-135">Somente o parâmetro NotifySfbUsers é relevante para usuários locais.</span><span class="sxs-lookup"><span data-stu-id="0a915-135">Only the NotifySfbUsers parameter is relevant for on-premises users.</span></span>  <span data-ttu-id="0a915-136">Os usuários locais recebem seu modo das instâncias online do TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0a915-136">On-premises users receive their mode from the online instances of TeamsUpgradePolicy.</span></span> <span data-ttu-id="0a915-137">Veja as anotações [em Grant-CsTeamsUpgradePolicy.](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="0a915-137">See the notes in [Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps).</span></span> 

>[!NOTE]
> <span data-ttu-id="0a915-138">Todos os novos locatários criados após 3 de setembro de 2019 são criados como locatários do TeamsOnly, a menos que a organização já tenha uma implantação local do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a915-138">Any new tenants created after Sept 3, 2019 are created as TeamsOnly tenants unless the organization already has an on-premises deployment of Skype for Business Server.</span></span> <span data-ttu-id="0a915-139">A Microsoft usa registros DNS para identificar organizações locais do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a915-139">Microsoft uses DNS records to identify on-premises Skype for Business Server organizations.</span></span> <span data-ttu-id="0a915-140">Se sua organização tiver o Skype for Business Server local sem entradas dns públicas, você precisará ligar para o Suporte da Microsoft para que seu novo locatário seja downgrade.</span><span class="sxs-lookup"><span data-stu-id="0a915-140">If your organization has on-premises Skype for Business Server with no public DNS entries, you will need to call Microsoft Support to have your new tenant downgraded.</span></span> 













## <a name="related-links"></a><span data-ttu-id="0a915-141">Links relacionados</span><span class="sxs-lookup"><span data-stu-id="0a915-141">Related links</span></span>

[<span data-ttu-id="0a915-142">Orientações de migração e interoperabilidade para organizações que usam o Teams em conjunto com o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0a915-142">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md) 

[<span data-ttu-id="0a915-143">Configurar a conectividade híbrida entre o Skype for Business Server e o Microsoft 365 ou o Office 365</span><span class="sxs-lookup"><span data-stu-id="0a915-143">Configure hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[<span data-ttu-id="0a915-144">Mover os usuários entre um ambiente local e a nuvem</span><span class="sxs-lookup"><span data-stu-id="0a915-144">Move users between on-premises and cloud</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[<span data-ttu-id="0a915-145">Definir suas configurações de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="0a915-145">Setting your coexistence and upgrade settings</span></span>](setting-your-coexistence-and-upgrade-settings.md)

[<span data-ttu-id="0a915-146">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0a915-146">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[<span data-ttu-id="0a915-147">Usando o Meeting Migration Service (MMS)</span><span class="sxs-lookup"><span data-stu-id="0a915-147">Using the Meeting Migration Service (MMS)</span></span>](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

