---
title: Acesso para convidado no Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
localization_priority: Normal
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ae1f3149ca915e2fd5a9ddf59fdb0bfad2be2ca2
ms.sourcegitcommit: a8f6b70fce1b5073f4743f7f413f7ce9fad8ead1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/10/2019
ms.locfileid: "31765145"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="9d9e3-103">Acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d9e3-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="9d9e3-104">Visão geral do acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="9d9e3-104">Guest access overview</span></span>

<span data-ttu-id="9d9e3-105">O acesso a convidados é um dos recursos mais pedidos pelos clientes.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-105">It’s one of the features customers asked for the most.</span></span> <span data-ttu-id="9d9e3-106">Veja como você pode acompanhar nosso progresso com o acesso a convidados e nos contar sua opinião:</span><span class="sxs-lookup"><span data-stu-id="9d9e3-106">Here’s how you can keep up with our progress on Guest Access and tell us your thoughts:</span></span>

- <span data-ttu-id="9d9e3-107">Se tiver problemas com o acesso de convidados, confira [Problemas conhecidos do Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="9d9e3-108">Conheça recursos novos ou atualizados no [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="9d9e3-109">Diga como podemos deixar o [Teams UserVoice](https://aka.ms/TeamsUserVoice) ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="9d9e3-110">Compartilhe sua experiência na seção Comentários a seguir.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="9d9e3-111">O acesso a convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo a elas acesso a equipes e canais existentes em um ou mais de seus locatários.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-111">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels.</span></span> <span data-ttu-id="9d9e3-112">Qualquer pessoa com uma conta de email corporativa ou de consumidor, como do Outlook, Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-112">Guest access in Microsoft Teams allows teams in your organization to collaborate with people outside your organization by granting them access to teams and channels. Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files. For more information, see Guest access in Microsoft Teams.</span></span>

<span data-ttu-id="9d9e3-113">O acesso a convidados está incluído em todas as assinaturas do Office 365 Business Premium, do Office 365 Enterprise e do Office 365 Education sem nenhum requisito de licenciamento adicional.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions.</span></span> <span data-ttu-id="9d9e3-114">Você pode ter até cinco convidados por usuário licenciado no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="9d9e3-115">Para obter mais informações sobre licenciamento, consulte o [guia de licenciamento de colaboração do Azure Active Directory B2B](https://docs.microsoft.com/pt-BR/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="9d9e3-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/pt-BR/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="9d9e3-116">O acesso a convidados é uma configuração a nível de locatário no Microsoft Teams e está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="9d9e3-117">O acesso a convidados está sujeito aos limites de serviço do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="9d9e3-118">Os usuários em sua organização que possuem apenas planos independentes de assinatura do Office 365, como o Plano 2 do Exchange Online, não podem receber convites para acessar a sua organização como convidados, pois o Teams considera esses usuários como pertencentes à mesma organização.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="9d9e3-119">Para esses usuários usarem o Teams, eles devem receber uma assinatura do Office 365 Business Premium, do Office 365 Enterprise ou do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="9d9e3-120">Quem é um convidado?</span><span class="sxs-lookup"><span data-stu-id="9d9e3-120">Who is a guest?</span></span>

<span data-ttu-id="9d9e3-121">Convidado é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="9d9e3-122">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="9d9e3-123">Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="9d9e3-124">Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="9d9e3-125">Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="9d9e3-126">(Você pode ler sobre restrições de convidados em [Autorizar o acesso a convidados no Microsoft Teams](teams-dependencies.md).) Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365, e podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="9d9e3-127">Por que usar o acesso de convidado?</span><span class="sxs-lookup"><span data-stu-id="9d9e3-127">Why use guest access?</span></span>
      
<span data-ttu-id="9d9e3-128">Com o acesso a convidados, as organizações que usam o Teams podem fornecer acesso externo a equipes, documentos em canais, recursos, bate-papos e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-128">Organizations using Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="9d9e3-129">Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365, e os convidados podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="9d9e3-130">O Teams é baseado nos Grupos do Office 365, e fornece uma nova maneira de acessar ativos compartilhados de um grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-130">Teams is built upon Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="9d9e3-131">O Teams é a melhor solução de bate-papo persistente entre os membros doe grupos/equipes.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="9d9e3-132">Os grupos do Office 365 são um serviço que oferece assinatura cruzada de aplicativos para um conjunto de ativos compartilhados de equipe, como um site do SharePoint ou um painel de controle do Power BI, para que a equipe possa colaborar de forma eficaz e segura.</span><span class="sxs-lookup"><span data-stu-id="9d9e3-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="9d9e3-133">Como o acesso de convidado se compara ao acesso externo (federação)?</span><span class="sxs-lookup"><span data-stu-id="9d9e3-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="9d9e3-134">Mais informações</span><span class="sxs-lookup"><span data-stu-id="9d9e3-134">More information</span></span>
    
[<span data-ttu-id="9d9e3-135">Entre em contato com o suporte para produtos comerciais - Ajuda para Administradores</span><span class="sxs-lookup"><span data-stu-id="9d9e3-135">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
<span data-ttu-id="9d9e3-136">
  [Acesso a convidados em Grupos do Office 365](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="9d9e3-136">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="9d9e3-137">Introdução ao acesso a convidados</span><span class="sxs-lookup"><span data-stu-id="9d9e3-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="9d9e3-138">Visão detalhada do acesso a convidados</span><span class="sxs-lookup"><span data-stu-id="9d9e3-138">Deep dive into Guest Access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="9d9e3-139">Adicionando convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d9e3-139">Adding Guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

