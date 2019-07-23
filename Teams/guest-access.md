---
title: Acesso para convidado no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/25/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
localization_priority: Priority
f1keywords: ms.teamsadmincenter.orgwidesettings.guestaccess.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4af2c6870cb636703ae35a9d3c7c5c19bd2f3105
ms.sourcegitcommit: 8ec1aa8f953206a08a488efdb59691824e26056a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/19/2019
ms.locfileid: "35804680"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="f0978-103">Acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0978-103">Guest access in Microsoft Teams</span></span>
======================================

<span data-ttu-id="f0978-104">O acesso a convidados é um dos recursos mais pedidos pelos clientes.</span><span class="sxs-lookup"><span data-stu-id="f0978-104">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="f0978-105">Veja como você pode acompanhar nosso progresso com o acesso a convidados e nos contar sua opinião:</span><span class="sxs-lookup"><span data-stu-id="f0978-105">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="f0978-106">Se você estiver com problemas com o acesso a convidados, confira [Problemas conhecidos do Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f0978-106">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="f0978-107">Conheça recursos novos ou atualizados no [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="f0978-107">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="f0978-108">Diga como podemos deixar o [Teams UserVoice](https://aka.ms/TeamsUserVoice) ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="f0978-108">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="f0978-109">Compartilhe sua experiência na seção Comentários a seguir.</span><span class="sxs-lookup"><span data-stu-id="f0978-109">Share your experience in the Comments section below.</span></span>

## <a name="guest-access-overview"></a><span data-ttu-id="f0978-110">Visão geral do acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="f0978-110">Guest access overview</span></span>

<span data-ttu-id="f0978-111">O acesso a convidados permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, concedendo a elas acesso a equipes e canais existentes em um ou mais de seus locatários.</span><span class="sxs-lookup"><span data-stu-id="f0978-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="f0978-112">Qualquer pessoa com uma conta de email corporativa ou de consumidor, como do Outlook, Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="f0978-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="f0978-113">O acesso de convidados está incluído em várias assinaturas do Office 365, sem requisitos adicionais de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="f0978-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="f0978-114">Para obter mais informações sobre licenciamento, consulte o [guia de licenciamento de colaboração do Azure Active Directory B2B](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="f0978-114">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/azure/active-directory/b2b/licensing-guidance).</span></span>

<span data-ttu-id="f0978-115">O acesso a convidados é uma configuração a nível de locatário no Microsoft Teams e está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="f0978-115">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="f0978-116">O acesso a convidados está sujeito aos limites de serviço do Azure AD e do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0978-116">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="f0978-117">Os usuários em sua organização que possuem apenas planos independentes de assinatura do Office 365, como o Plano 2 do Exchange Online, não podem receber convites para acessar a sua organização como convidados, pois o Teams considera esses usuários como pertencentes à mesma organização.</span><span class="sxs-lookup"><span data-stu-id="f0978-117">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="f0978-118">Para esses usuários usarem o Teams, eles devem receber uma assinatura do Office 365 Business Premium, do Office 365 Enterprise ou do Office 365 Education.</span><span class="sxs-lookup"><span data-stu-id="f0978-118">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="f0978-119">Quem é um convidado?</span><span class="sxs-lookup"><span data-stu-id="f0978-119">Who is a guest?</span></span>

<span data-ttu-id="f0978-120">Convidado é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0978-120">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="f0978-121">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="f0978-121">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="f0978-122">Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores.</span><span class="sxs-lookup"><span data-stu-id="f0978-122">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="f0978-123">Qualquer pessoa que não faça parte da sua organização pode ser adicionada como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="f0978-123">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="f0978-124">Isso significa que qualquer pessoa com uma conta comercial (ou seja, uma conta do Azure Active Directory) ou uma conta de email de consumidor (com Outlook.com, Gmail.com ou outros) pode participar como convidado no Teams, com acesso total a equipes e experiências de canal.</span><span class="sxs-lookup"><span data-stu-id="f0978-124">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="f0978-125">(Você pode ler sobre restrições de convidados em [Autorizar o acesso a convidados no Microsoft Teams](teams-dependencies.md).) Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365, e podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0978-125">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="f0978-126">Por que usar o acesso de convidado?</span><span class="sxs-lookup"><span data-stu-id="f0978-126">Why use guest access?</span></span>

<span data-ttu-id="f0978-127">Com o acesso a convidados, as organizações que usam o Teams podem fornecer acesso externo a equipes, documentos em canais, recursos, bate-papos e aplicativos para seus parceiros, enquanto mantêm controle total sobre seus próprios dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="f0978-127">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="f0978-128">Todos os convidados no Teams estão cobertos pela mesma proteção de conformidade e auditoria que o restante do Office 365, e os convidados podem ser gerenciados com segurança no Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0978-128">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="f0978-129">O Teams é baseado nos Grupos do Office 365, e fornece uma nova maneira de acessar ativos compartilhados de um grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f0978-129">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="f0978-130">O Teams é a melhor solução de bate-papo persistente entre os membros doe grupos/equipes.</span><span class="sxs-lookup"><span data-stu-id="f0978-130">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="f0978-131">Os grupos do Office 365 são um serviço que oferece assinatura cruzada de aplicativos para um conjunto de ativos compartilhados de equipe, como um site do SharePoint ou um painel de controle do Power BI, para que a equipe possa colaborar de forma eficaz e segura.</span><span class="sxs-lookup"><span data-stu-id="f0978-131">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="f0978-132">Como o acesso de convidado se compara ao acesso externo (federação)?</span><span class="sxs-lookup"><span data-stu-id="f0978-132">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="f0978-133">Mais informações</span><span class="sxs-lookup"><span data-stu-id="f0978-133">More information</span></span>

[<span data-ttu-id="f0978-134">Entre em contato com o suporte para produtos comerciais - Ajuda para Administradores</span><span class="sxs-lookup"><span data-stu-id="f0978-134">Contact support for business products - Admin Help</span></span>](https://docs.microsoft.com/office365/admin/contact-support-for-business-products?toc=/microsoftteams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)  
<span data-ttu-id="f0978-135">
  [Acesso a convidados em Grupos do Office 365](https://support.office.com/pt-BR/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span><span class="sxs-lookup"><span data-stu-id="f0978-135">[Guest access in Office 365 Groups](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ)</span></span> 
  
|  |  |
|---------|---------|
|<span data-ttu-id="f0978-136">Introdução ao acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="f0978-136">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="f0978-137">Visão detalhada do acesso a convidados</span><span class="sxs-lookup"><span data-stu-id="f0978-137">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="f0978-138">Adicionando convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0978-138">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

