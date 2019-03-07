---
title: Acesso de convidados no Microsoft Teams
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 11/25/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sbhatta
search.appverid: MET150
description: O acesso de convidados no Microsoft Teams permite que as equipes da sua organização colaborem com pessoas de fora da sua organização, lhes concedendo acesso a equipes e a canais.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59cd4e06d3a5a98298d67fcfbb785efb371fe0f0
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30458824"
---
<a name="guest-access-in-microsoft-teams"></a><span data-ttu-id="4a1c5-103">Acesso de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a1c5-103">Guest access in Microsoft Teams</span></span>
======================================

## <a name="guest-access-overview"></a><span data-ttu-id="4a1c5-104">Visão geral sobre o acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="4a1c5-104">Guest access overview</span></span>

<span data-ttu-id="4a1c5-105">Acesso de convidado é um dos recursos que os clientes solicitaram ao máximo.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-105">Guest access is one of the features customers asked for the most.</span></span> <span data-ttu-id="4a1c5-106">Aqui está como você acompanhe o nosso progresso de acesso do convidado e diga-nos seus pensamentos:</span><span class="sxs-lookup"><span data-stu-id="4a1c5-106">Here’s how you can keep up with our progress on guest access and tell us your thoughts:</span></span>

- <span data-ttu-id="4a1c5-107">Se tiver problemas com o acesso de convidados, confira [Problemas conhecidos do Microsoft Teams](Known-issues.md).</span><span class="sxs-lookup"><span data-stu-id="4a1c5-107">If you’re having trouble with Guest Access, check out [Known issues for Microsoft Teams](Known-issues.md).</span></span>
- <span data-ttu-id="4a1c5-108">Conheça recursos novos ou atualizados no [Roteiro do Microsoft Teams](https://aka.ms/teamsroadmap).</span><span class="sxs-lookup"><span data-stu-id="4a1c5-108">Find out about upcoming new or updated features in the [Teams Roadmap](https://aka.ms/teamsroadmap).</span></span>
- <span data-ttu-id="4a1c5-109">Diga como podemos deixar o [Teams UserVoice](https://aka.ms/TeamsUserVoice) ainda melhor.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-109">Tell us what you want in  [Teams UserVoice](https://aka.ms/TeamsUserVoice).</span></span>
- <span data-ttu-id="4a1c5-110">Compartilhe sua experiência na seção Comentários a seguir.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-110">Share your experience in the Comments section below.</span></span>

<span data-ttu-id="4a1c5-111">Acesso de convidado permite que as equipes em sua organização para colaborar com pessoas fora da sua organização, concedendo a eles acesso às equipes existentes e canais em um ou mais dos seus inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-111">Guest access allows teams in your organization to collaborate with people outside your organization by granting them access to existing teams and channels on one or more of your tenants.</span></span> <span data-ttu-id="4a1c5-112">Qualquer pessoa com uma conta de email comercial ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Microsoft Teams, com acesso total a chats, reuniões e arquivos de equipe.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-112">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="4a1c5-113">Acesso de convidado está incluído no Business Premium do Office 365, Office 365 Enterprise e Office 365 educação todas as inscrições com nenhum requisito de licenciamento adicional.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-113">Guest access is included with all Office 365 Business Premium, Office 365 Enterprise, and Office 365 Education subscriptions with no additional licensing requirement.</span></span> <span data-ttu-id="4a1c5-114">Você pode ter até 5 convidados por usuário licenciado no seu locatário.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-114">You can have up to 5 guests per licensed user on your tenant.</span></span> <span data-ttu-id="4a1c5-115">Para obter mais informações sobre licenciamento, consulte as [diretrizes de licenciamento de colaboração do Windows Azure Active Directory B2B](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span><span class="sxs-lookup"><span data-stu-id="4a1c5-115">For more information about licensing, see [Azure Active Directory B2B collaboration licensing guidance](https://docs.microsoft.com/en-us/azure/active-directory/b2b/licensing-guidance).</span></span> 

<span data-ttu-id="4a1c5-116">O acesso de convidados é uma configuração em nível de locatário no Microsoft Teams está desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-116">Guest access is a tenant-level setting in Microsoft Teams and is turned off by default.</span></span> <span data-ttu-id="4a1c5-117">Acesso de convidado está sujeito a Azure AD e limites de serviço do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-117">Guest access is subject to Azure AD and Office 365 service limits.</span></span>

> [!NOTE]
> <span data-ttu-id="4a1c5-118">Usuários em sua organização que têm planos de assinatura do Office 365 autônomo somente, como Exchange Online plano 2, não podem ser convidados como convidados para sua organização porque equipes considera esses usuários para pertencem à mesma organização.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-118">Users in your organization who have standalone Office 365 subscription plans only, such as Exchange Online Plan 2, cannot be invited as guests to your organization because Teams considers these users to belong to the same organization.</span></span> <span data-ttu-id="4a1c5-119">Esses usuários usem equipes, eles devem ser atribuídos a uma assinatura do Office 365 Business Premium, Office 365 Enterprise ou educação do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-119">For these users to use Teams, they must be assigned an Office 365 Business Premium, Office 365 Enterprise, or Office 365 Education subscription.</span></span> 

## <a name="who-is-a-guest"></a><span data-ttu-id="4a1c5-120">Quem é um convidado?</span><span class="sxs-lookup"><span data-stu-id="4a1c5-120">Who is a guest?</span></span>

<span data-ttu-id="4a1c5-121">Convidado é alguém que não é um funcionário, aluno ou membro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-121">A guest is someone who isn't an employee, student, or member of your organization.</span></span> <span data-ttu-id="4a1c5-122">Eles não têm uma conta escolar nem de trabalho com a sua organização.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-122">They don't have a school or work account with your organization.</span></span> <span data-ttu-id="4a1c5-123">Por exemplo, convidados podem incluir parceiros, revendedores, fornecedores ou consultores.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-123">For example, guests may include partners, vendors, suppliers, or consultants.</span></span> <span data-ttu-id="4a1c5-124">Qualquer pessoa que não faz parte da sua organização pode ser adicionada como convidado em equipes.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-124">Anyone who is not part of your organization can be added as guest in Teams.</span></span> <span data-ttu-id="4a1c5-125">Isso significa que qualquer pessoa com uma conta de negócios (ou seja, uma conta do Windows Azure Active Directory) ou a conta de email do consumidor (com Outlook.com, Gmail.com ou outras pessoas) pode participar como um convidado em equipes, com acesso total às equipes e experiências de canal.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-125">This means that anyone with a business account (that is, an Azure Active Directory account) or consumer email account (with Outlook.com, Gmail.com or others) can participate as a guest in Teams, with full access to teams and channel experiences.</span></span> <span data-ttu-id="4a1c5-126">(Você pode ler sobre as restrições de convidado em [autorizar o acesso de convidado em equipes da Microsoft](teams-dependencies.md)). Todos os convidados em equipes são abordados pelo mesma conformidade e proteção de auditoria como o restante do Office 365 e podem ser gerenciados com segurança dentro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-126">(You can read about guest restrictions in [Authorize guest access in Microsoft Teams](teams-dependencies.md).) All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and can be managed securely within Azure AD.</span></span>

## <a name="why-use-guest-access"></a><span data-ttu-id="4a1c5-127">Por que usar o acesso de convidado?</span><span class="sxs-lookup"><span data-stu-id="4a1c5-127">Why use guest access?</span></span>
      
<span data-ttu-id="4a1c5-128">Com acesso de convidado, as organizações que usam equipes podem fornecer acesso externo para equipes, documentos no canais, recursos, bate-papos e aplicativos para seus parceiros, enquanto mantém controle completo sobre seus próprios dados corporativos.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-128">With guest access, organizations that use Teams can provide external access to teams, documents in channels, resources, chats, and applications to their partners, while maintaining complete control over their own corporate data.</span></span> <span data-ttu-id="4a1c5-129">Todos os convidados em equipes são abordados pelo mesma conformidade e proteção de auditoria como o restante do Office 365 e convidados podem ser gerenciados com segurança dentro do Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-129">All guests in Teams are covered by the same compliance and auditing protection as the rest of Office 365, and guests can be managed securely within Azure AD.</span></span>  

<span data-ttu-id="4a1c5-130">As equipes se baseia em grupos do Office 365 e fornece uma nova maneira de acessar ativos compartilhados para um grupo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-130">Teams is built on Office 365 Groups and provides a new way to access shared assets for an Office 365 group.</span></span> <span data-ttu-id="4a1c5-131">O Teams é a melhor solução de bate-papo persistente entre os membros doe grupos/equipes.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-131">Teams is the best solution for persistent chat among group/team members.</span></span> <span data-ttu-id="4a1c5-132">Os grupos do Office 365 são um serviço que oferece assinatura cruzada de aplicativos para um conjunto de ativos compartilhados de equipe, como um site do SharePoint ou um painel de controle do Power BI, para que a equipe possa colaborar de forma eficaz e segura.</span><span class="sxs-lookup"><span data-stu-id="4a1c5-132">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

## <a name="how-does-guest-access-compare-to-external-access-federation"></a><span data-ttu-id="4a1c5-133">Como o acesso de convidado se comparam para acesso externo (federação)?</span><span class="sxs-lookup"><span data-stu-id="4a1c5-133">How does guest access compare to external access (federation)?</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="4a1c5-134">Mais informações</span><span class="sxs-lookup"><span data-stu-id="4a1c5-134">More information</span></span>
    
[<span data-ttu-id="4a1c5-135">Recursos de suporte para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a1c5-135">Support resources for Microsoft Teams</span></span>](support-resources.md)  
[<span data-ttu-id="4a1c5-136">Acesso de convidado em grupos do Office 365</span><span class="sxs-lookup"><span data-stu-id="4a1c5-136">Guest access in Office 365 Groups</span></span>](https://support.office.com/en-us/article/guest-access-in-office-365-groups-bfc7a840-868f-4fd6-a390-f347bf51aff6?ui=en-US&rs=en-US&ad=US#bkmk_usepowershell&PickTab=FAQ) 
  
|  |  |
|---------|---------|
|<span data-ttu-id="4a1c5-137">Introdução ao Access convidado</span><span class="sxs-lookup"><span data-stu-id="4a1c5-137">Introduction to to guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/D8DW2Urv5y8" frameborder="0" allowfullscreen></iframe>   |
|<span data-ttu-id="4a1c5-138">Conheça em acesso de convidado</span><span class="sxs-lookup"><span data-stu-id="4a1c5-138">Deep dive into guest access</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/vaJRRSjBxxY" frameborder="0" allowfullscreen></iframe>   |
| <span data-ttu-id="4a1c5-139">Adição de convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4a1c5-139">Adding guests in Microsoft Teams</span></span>   | <iframe width="350" height="200" src="https://www.youtube.com/embed/1daMBDyBLZc" frameborder="0" allowfullscreen></iframe>   | 
    

