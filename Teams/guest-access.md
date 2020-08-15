---
title: Acesso para convidado no Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
ms.openlocfilehash: f04fce7f75df32111b2577119c12b14eadf963b9
ms.sourcegitcommit: 20258b691ffc559b1656fd1e57f67f5c3a9e29e1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/15/2020
ms.locfileid: "46761237"
---
# <a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="5afe2-103">Acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5afe2-103">Guest access in Microsoft Teams</span></span>

<span data-ttu-id="5afe2-104">O acesso de convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo-lhes acesso às equipes e canais existentes no Teams.</span><span class="sxs-lookup"><span data-stu-id="5afe2-104">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="5afe2-105">Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Microsoft 365, o Outlook, o Gmail ou outros, pode participar como um convidado no Microsoft Teams com acesso total a chats, reuniões e arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="5afe2-105">Anyone with a business or consumer email account, such as Microsoft 365, Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="5afe2-106">Como administrador do Teams, você controla quais recursos os convidados podem (e não podem) usar no Teams - confira [Gerenciar acesso de convidados](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="5afe2-106">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="5afe2-107">Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="5afe2-107">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="5afe2-108">O acesso de convidados é uma configuração em toda a organização no Teams e está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="5afe2-108">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="5afe2-109">(Você pode controlar o acesso de convidados a equipes individuais usando [Rótulos de sensibilidade](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span><span class="sxs-lookup"><span data-stu-id="5afe2-109">(You can control guest access to individual teams by using [sensitivity labels](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).)</span></span>

<span data-ttu-id="5afe2-110">Se você estiver pronto para começar a convidar convidados para o Microsoft Teams, leia um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="5afe2-110">If you're ready to start inviting guests to teams, read one of the following:</span></span>

- <span data-ttu-id="5afe2-111">Para configurar o acesso de convidado para o Microsoft Teams para uso geral, consulte [colaborar com convidados em uma equipe](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span><span class="sxs-lookup"><span data-stu-id="5afe2-111">To configure guest access for Teams for general use, see [Collaborate with guests in a team](https://docs.microsoft.com/microsoft-365/solutions/collaborate-as-team).</span></span>
- <span data-ttu-id="5afe2-112">Para colaborar com uma organização parceira que usa o Azure Active Directory e permitir que os convidados se registrem automaticamente para acesso à equipe, consulte [criar uma extranet B2B com convidados gerenciados](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span><span class="sxs-lookup"><span data-stu-id="5afe2-112">To collaborate with a partner organization that uses Azure Active Directory and allow guests to self-enroll for team access, see [Create a B2B extranet with managed guests](https://docs.microsoft.com/microsoft-365/solutions/b2b-extranet).</span></span>

<span data-ttu-id="5afe2-113">O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="5afe2-113">Guest access is subject to Azure AD and Microsoft 365 or Office 365 service limits.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5afe2-114">Os usuários convidados seguem as configurações em toda a organização do Teams para o modo de atualização de coexistência.</span><span class="sxs-lookup"><span data-stu-id="5afe2-114">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="5afe2-115">Isso não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="5afe2-115">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="5afe2-116">Licenciamento para acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="5afe2-116">Licensing for guest access</span></span>

<span data-ttu-id="5afe2-117">O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="5afe2-117">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="5afe2-118">Não é necessária nenhuma licença adicional do Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="5afe2-118">No additional Microsoft 365 or Office 365 license is necessary.</span></span> <span data-ttu-id="5afe2-119">O Teams não restringe o número de convidados que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="5afe2-119">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="5afe2-120">No entanto, o número total de convidados que podem ser adicionados ao seu locatário pode ficar restrito pelos recursos pagos do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5afe2-120">However, the total number of guests that can be added to your tenant may be restricted by the paid features of Azure AD.</span></span> <span data-ttu-id="5afe2-121">Para obter mais informações, confira [Licenciamento de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="5afe2-121">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="5afe2-122">Os usuários em sua organização que possuem apenas planos de assinatura autônomos do Microsoft 365 ou Office 365, como o Exchange Online Plano 2, não podem ser convidados para participar da sua organização porque o Teams considera que esses usuários pertencem à mesma organização.</span><span class="sxs-lookup"><span data-stu-id="5afe2-122">Users in your organization who have standalone Microsoft 365 or Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="5afe2-123">Para esses usuários usarem o Teams, eles devem receber uma assinatura do Microsoft 365 Business Standard, do Office 365 Enterprise ou do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="5afe2-123">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="5afe2-124">Quem é um convidado?</span><span class="sxs-lookup"><span data-stu-id="5afe2-124">Who is a guest?</span></span>

<span data-ttu-id="5afe2-125">Convidado é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5afe2-125">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="5afe2-126">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="5afe2-126">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="5afe2-127">Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores.</span><span class="sxs-lookup"><span data-stu-id="5afe2-127">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="5afe2-128">Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="5afe2-128">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="5afe2-129">Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.</span><span class="sxs-lookup"><span data-stu-id="5afe2-129">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="5afe2-130">Para saber mais sobre o que um convidado pode ou não fazer, leia [Autorizar o acesso de convidados no Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="5afe2-130">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="5afe2-131">Ou confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="5afe2-131">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="5afe2-132">Por fim, todos os convidados do teams são cobertos pela mesma proteção de auditoria e conformidade que o restante do Microsoft 365 e podem ser gerenciados no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5afe2-132">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Microsoft 365, and can be managed within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="5afe2-133">Por que usar o acesso de convidados?</span><span class="sxs-lookup"><span data-stu-id="5afe2-133">Why use guest access?</span></span>

<span data-ttu-id="5afe2-134">Com o acesso de convidados, as organizações que usam o Teams podem fornecer acesso externo às equipes, documentos em canais, recursos, chats e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="5afe2-134">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> 

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="5afe2-135">Compreender as limitações de convidados</span><span class="sxs-lookup"><span data-stu-id="5afe2-135">Understand the limitations for guests</span></span>

<span data-ttu-id="5afe2-136">A experiência de convidado tem limitações por padrão.</span><span class="sxs-lookup"><span data-stu-id="5afe2-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="5afe2-137">Compreenda a experiência de convidado para não tentar corrigir algo que não seja um problema.</span><span class="sxs-lookup"><span data-stu-id="5afe2-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="5afe2-138">Aqui está uma lista de algumas das funcionalidades que não estão disponíveis para um convidado no Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="5afe2-138">Here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="5afe2-139">OneDrive</span><span class="sxs-lookup"><span data-stu-id="5afe2-139">OneDrive</span></span>
- <span data-ttu-id="5afe2-140">Pesquisa de pessoas de fora do Teams</span><span class="sxs-lookup"><span data-stu-id="5afe2-140">People search outside of Teams</span></span>
- <span data-ttu-id="5afe2-141">Calendário, Reuniões Agendadas ou Detalhes da Reunião</span><span class="sxs-lookup"><span data-stu-id="5afe2-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="5afe2-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="5afe2-142">PSTN</span></span>
- <span data-ttu-id="5afe2-143">Organograma</span><span class="sxs-lookup"><span data-stu-id="5afe2-143">Organization chart</span></span>
- <span data-ttu-id="5afe2-144">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="5afe2-144">Create or revise a team</span></span>
- <span data-ttu-id="5afe2-145">Procurar uma esquipe</span><span class="sxs-lookup"><span data-stu-id="5afe2-145">Browse for a team</span></span>
- <span data-ttu-id="5afe2-146">Carregar arquivos para um chat de pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="5afe2-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="5afe2-147">Atualmente, o Teams oferece suporte somente para [os tipos de usuários convidados do estado 1 e do estado 2](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="5afe2-147">Currently, Teams supports only [State 1 and State 2 types of guest users](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="5afe2-148">Para obter uma lista completa do que um convidado pode ou não fazer no Teams, confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="5afe2-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="5afe2-149">Para saber mais sobre o acesso de convidados no nível do Microsoft 365, leia [colaborando com pessoas de fora da sua organização](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span><span class="sxs-lookup"><span data-stu-id="5afe2-149">To learn more about guest access at the Microsoft 365 level, read [Collaborating with people outside your organization](https://docs.microsoft.com/microsoft-365/solutions/collaborate-with-people-outside-your-organization).</span></span>


## <a name="related-topics"></a><span data-ttu-id="5afe2-150">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5afe2-150">Related topics</span></span>

[<span data-ttu-id="5afe2-151">Entre em contato com o suporte para produtos para empresas - ajuda para administradores</span><span class="sxs-lookup"><span data-stu-id="5afe2-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)

[<span data-ttu-id="5afe2-152">Configurar o Microsoft Teams com três níveis de proteção</span><span class="sxs-lookup"><span data-stu-id="5afe2-152">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
