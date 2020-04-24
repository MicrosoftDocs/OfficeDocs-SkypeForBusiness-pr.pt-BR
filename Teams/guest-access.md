---
title: Acesso para convidado no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
audience: admin
search.appverid: MET150
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
localization_priority: Priority
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e7151c7a84ec6273e14f41330eb4fd2afcd8d989
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776936"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="9a646-103">Acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a646-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="9a646-104">O acesso de convidados permite que você adicione usuários individuais de fora da sua organização às suas equipes e canais no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a646-104">Guest access lets you add individual users from outside your organization to your teams and channels in Microsoft Teams.</span></span> 

<span data-ttu-id="9a646-105">Para comparar o acesso externo (federação) com o acesso de convidados (e decidir qual deles usar), leia [Comunicar-se com usuários de outras organizações no Teams](communicate-with-users-from-other-organizations.md).</span><span class="sxs-lookup"><span data-stu-id="9a646-105">To compare external access (federation) with guest access (and decide which one you should use), read [Communicate with users from other organizations in Teams](communicate-with-users-from-other-organizations.md).</span></span>

<span data-ttu-id="9a646-106">Se você estiver pronto para ativar o acesso de convidados em sua organização, comece com a [Lista de verificação de acesso de convidados](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="9a646-106">If you're ready to turn on guest access in your organization, start with the [Guest access checklist](guest-access-checklist.md).</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="9a646-107">Visão geral do acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="9a646-107">Guest access overview</span></span>

<span data-ttu-id="9a646-108">O acesso de convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo-lhes acesso às equipes e canais existentes no Teams.</span><span class="sxs-lookup"><span data-stu-id="9a646-108">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels in Teams.</span></span> <span data-ttu-id="9a646-109">Qualquer pessoa com uma conta de email corporativa ou de consumidor, como do Outlook, Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="9a646-109">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span> <span data-ttu-id="9a646-110">Como administrador do Teams, você controla quais recursos os convidados podem (e não podem) usar no Teams - confira [Gerenciar acesso de convidados](manage-guests.md).</span><span class="sxs-lookup"><span data-stu-id="9a646-110">As the Teams admin, you control which features guests can (and can't) use in Teams - check out [Manage guest access](manage-guests.md).</span></span>

<span data-ttu-id="9a646-111">O acesso de convidados é uma configuração em toda a organização no Teams e está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9a646-111">Guest access is an org-wide setting in Teams and is turned off by default.</span></span> <span data-ttu-id="9a646-112">O acesso de convidados está sujeito aos limites de serviço do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a646-112">Guest access is subject to Azure AD and Office 365 service limits.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="9a646-113">Os usuários convidados seguem as configurações em toda a organização do Teams para o modo de atualização de coexistência.</span><span class="sxs-lookup"><span data-stu-id="9a646-113">Guest users follow Teams Org-wide settings for the coexistence Upgrade mode.</span></span> <span data-ttu-id="9a646-114">Isso não pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="9a646-114">This can't be changed.</span></span>

## <a name="licensing-for-guest-access"></a><span data-ttu-id="9a646-115">Licenciamento para acesso de convidados</span><span class="sxs-lookup"><span data-stu-id="9a646-115">Licensing for guest access</span></span>

<span data-ttu-id="9a646-116">O acesso de convidados está incluído em todas as assinaturas do Microsoft 365 Business Standard, do Office 365 Enterprise e do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="9a646-116">Guest access is included with all Microsoft 365 Business Standard, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="9a646-117">Não é necessária nenhuma licença adicional do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9a646-117">No additional Office 365 license is necessary.</span></span> <span data-ttu-id="9a646-118">O Teams não restringe o número de convidados que você pode adicionar.</span><span class="sxs-lookup"><span data-stu-id="9a646-118">Teams doesn't restrict the number of guests you can add.</span></span> <span data-ttu-id="9a646-119">No entanto, o número total de convidados que podem ser adicionados ao seu locatário é baseado no que o licenciamento do seu Azure AD permite - normalmente, 5 convidados por usuário licenciado.</span><span class="sxs-lookup"><span data-stu-id="9a646-119">However, the total number of guests that can be added to your tenant is based on what your Azure AD licensing allows - usually 5 guests per licensed user.</span></span> <span data-ttu-id="9a646-120">Para obter mais informações, confira [Licenciamento de colaboração B2B do Azure AD](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="9a646-120">For more information, see [Azure AD B2B collaboration licensing](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>


> [!NOTE]
> <span data-ttu-id="9a646-121">Os usuários em sua organização que possuem apenas planos independentes de assinatura do Office 365, como o Plano 2 do Exchange Online, não podem receber convites para acessar a sua organização como convidados, pois o Teams considera esses usuários como pertencentes à mesma organização.</span><span class="sxs-lookup"><span data-stu-id="9a646-121">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="9a646-122">Para esses usuários usarem o Teams, eles devem receber uma assinatura do Microsoft 365 Business Standard, do Office 365 Enterprise ou do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="9a646-122">For these users to use Teams, they must be assigned an Microsoft 365 Business Standard, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="9a646-123">Quem é um convidado?</span><span class="sxs-lookup"><span data-stu-id="9a646-123">Who is a guest?</span></span>

<span data-ttu-id="9a646-124">Convidado é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9a646-124">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="9a646-125">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="9a646-125">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="9a646-126">Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores.</span><span class="sxs-lookup"><span data-stu-id="9a646-126">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="9a646-127">Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="9a646-127">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="9a646-128">Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.</span><span class="sxs-lookup"><span data-stu-id="9a646-128">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span>

<span data-ttu-id="9a646-129">Para saber mais sobre o que um convidado pode ou não fazer, leia [Autorizar o acesso de convidados no Microsoft Teams](teams-dependencies.md).</span><span class="sxs-lookup"><span data-stu-id="9a646-129">To learn more about what a guest can and can't do, read [Authorize guest access in Microsoft Teams](teams-dependencies.md).</span></span> <span data-ttu-id="9a646-130">Ou confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="9a646-130">Or check out the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> 

<span data-ttu-id="9a646-131">Por fim, todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365 e podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9a646-131">Finally, all guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="9a646-132">Por que usar o acesso de convidados?</span><span class="sxs-lookup"><span data-stu-id="9a646-132">Why use guest access?</span></span>

<span data-ttu-id="9a646-133">Com o acesso de convidados, as organizações que usam o Teams podem fornecer acesso externo às equipes, documentos em canais, recursos, chats e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="9a646-133">With guest access, organizations that use Teams can provide access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="9a646-134">Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365, e os convidados podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9a646-134">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

## <a name="understand-the-limitations-for-guests"></a><span data-ttu-id="9a646-135">Compreender as limitações de convidados</span><span class="sxs-lookup"><span data-stu-id="9a646-135">Understand the limitations for guests</span></span>

<span data-ttu-id="9a646-136">A experiência de convidado tem limitações por padrão.</span><span class="sxs-lookup"><span data-stu-id="9a646-136">The guest experience has limitations by design.</span></span> <span data-ttu-id="9a646-137">Compreenda a experiência de convidado para não tentar corrigir algo que não seja um problema.</span><span class="sxs-lookup"><span data-stu-id="9a646-137">Make sure you understand the guest experience so you don't try to fix something that isn't a problem.</span></span> <span data-ttu-id="9a646-138">Por exemplo, aqui está uma lista de algumas das funcionalidades que não estão disponíveis para um convidado no Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="9a646-138">For example, here's a list of some of the functionality that isn't available to a guest in Microsoft Teams:</span></span>

- <span data-ttu-id="9a646-139">OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="9a646-139">OneDrive for Business</span></span>
- <span data-ttu-id="9a646-140">Pesquisa de pessoas de fora do Teams</span><span class="sxs-lookup"><span data-stu-id="9a646-140">People search outside of Teams</span></span>
- <span data-ttu-id="9a646-141">Calendário, Reuniões Agendadas ou Detalhes da Reunião</span><span class="sxs-lookup"><span data-stu-id="9a646-141">Calendar, Scheduled Meetings, or Meeting Details</span></span>
- <span data-ttu-id="9a646-142">PSTN</span><span class="sxs-lookup"><span data-stu-id="9a646-142">PSTN</span></span>
- <span data-ttu-id="9a646-143">Organograma</span><span class="sxs-lookup"><span data-stu-id="9a646-143">Organization chart</span></span>
- <span data-ttu-id="9a646-144">Criar ou revisar uma equipe</span><span class="sxs-lookup"><span data-stu-id="9a646-144">Create or revise a team</span></span>
- <span data-ttu-id="9a646-145">Procurar uma esquipe</span><span class="sxs-lookup"><span data-stu-id="9a646-145">Browse for a team</span></span>
- <span data-ttu-id="9a646-146">Carregar arquivos para um chat de pessoa para pessoa</span><span class="sxs-lookup"><span data-stu-id="9a646-146">Upload files to a person-to-person chat</span></span>
- <span data-ttu-id="9a646-147">Atualmente, o Teams é compatível apenas aos usuários convidados do Estado 1 e Estado 2, [conforme definido pelo Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span><span class="sxs-lookup"><span data-stu-id="9a646-147">Currently, Teams supports only State 1 and State 2 types of guest users [as defined by Azure B2B](https://docs.microsoft.com/azure/active-directory/b2b/user-properties)</span></span>

<span data-ttu-id="9a646-148">Para obter uma lista completa do que um convidado pode ou não fazer no Teams, confira a tabela [comparação de recursos de membros e de convidados da equipe](guest-experience.md#comparison-of-team-member-and-guest-capabilities).</span><span class="sxs-lookup"><span data-stu-id="9a646-148">For a full list of what a guest can and can't do in Teams, see the [comparison of team member and guest capabilities](guest-experience.md#comparison-of-team-member-and-guest-capabilities) table.</span></span> <span data-ttu-id="9a646-149">Para saber mais sobre o acesso de convidados no nível do Office 365, leia [Adicionar convidados aos Grupos do Microsoft 365](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span><span class="sxs-lookup"><span data-stu-id="9a646-149">To learn more about guest access at the Office 365 level, read [Adding guests to Microsoft 365 Groups](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6).</span></span>


## <a name="more-information"></a><span data-ttu-id="9a646-150">Mais informações</span><span class="sxs-lookup"><span data-stu-id="9a646-150">More information</span></span>

[<span data-ttu-id="9a646-151">Entre em contato com o suporte para produtos para empresas - ajuda para administradores</span><span class="sxs-lookup"><span data-stu-id="9a646-151">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
[<span data-ttu-id="9a646-152">Acesso de convidados aos Grupos do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="9a646-152">Guest access in Microsoft 365 Groups</span></span>](https://support.office.com/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
