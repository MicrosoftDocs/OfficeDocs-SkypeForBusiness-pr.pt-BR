---
title: Adicionar um convidado a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
ms.date: 01/31/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
description: Conheça as ferramentas disponíveis para adicionar novos usuários a uma organização, incluindo clientes desktop e web do Microsoft Teams e o portal de colaboração do Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 27f1f344313111561c9f1c3a5e57dc1bd0ae20cb
ms.sourcegitcommit: 7ca70e8a2108462afd505258b455169ead30f33f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31041898"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="8543b-103">Adicionar um convidado a uma equipe</span><span class="sxs-lookup"><span data-stu-id="8543b-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8543b-104">Qualquer pessoa com uma conta de email de consumidor ou de negócios, como o Outlook, Gmail ou outras pessoas, pode participar como um convidado em equipes.</span><span class="sxs-lookup"><span data-stu-id="8543b-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="8543b-105">Como administrador, você pode adicionar um novo convidado usuário à organização de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="8543b-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="8543b-106">Administradores globais que são proprietários de uma equipe podem adicionar um convidado a uma equipe através do cliente web ou cliente desktop do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8543b-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="8543b-107">Para obter mais detalhes, confira [Adicionar convidados para uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="8543b-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>
- <span data-ttu-id="8543b-108">Adicione convidados à sua organização através da colaboração do Azure Active Directory B2B.</span><span class="sxs-lookup"><span data-stu-id="8543b-108">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="8543b-109">A colaboração do Azure Active Directory B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer upload de um arquivo de valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B.</span><span class="sxs-lookup"><span data-stu-id="8543b-109">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="8543b-110">Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="8543b-110">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="8543b-111">Com a colaboração do Azure Active Directory B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="8543b-111">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="8543b-112">Essas políticas podem ser aplicadas em nível de locatário, aplicativo ou usuário individual, da mesma forma que são habilitadas para funcionários de período integral e membros da organização.</span><span class="sxs-lookup"><span data-stu-id="8543b-112">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="8543b-113">Essas políticas são aplicadas na organização de recursos.</span><span class="sxs-lookup"><span data-stu-id="8543b-113">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="8543b-114">Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="8543b-114">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="8543b-115">Usuários convidados não podem ser bloqueados individualmente.</span><span class="sxs-lookup"><span data-stu-id="8543b-115">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="8543b-116">Usuários convidados que você já tiver adicionado via B2B do Azure Active Directory, grupos do Office 365 ou SharePoint Online estão prontos para ir.</span><span class="sxs-lookup"><span data-stu-id="8543b-116">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="8543b-117">O administrador do Office 365 ou o proprietário da equipe pode adicionar aqueles convidados às respectivas equipes.</span><span class="sxs-lookup"><span data-stu-id="8543b-117">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="8543b-118">Se uma equipe já estiver com um grupos do Office 365 e um convidado for adicionado ao grupo, ele obterá acesso à equipe.</span><span class="sxs-lookup"><span data-stu-id="8543b-118">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="8543b-119">Adicionar um convidado através do grupo do Office 365 não gera um e-mail de convite para o convidado; então, alguém da equipe precisa notificá-lo.</span><span class="sxs-lookup"><span data-stu-id="8543b-119">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="8543b-120">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="8543b-120">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="8543b-121">Você pode acompanhar a adição de convidados no Centro de Segurança &amp; Conformidade do Azure Active Directory ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8543b-121">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="8543b-122">A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”.</span><span class="sxs-lookup"><span data-stu-id="8543b-122">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="8543b-123">Para obter mais detalhes, consulte [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de Segurança &amp; Conformidade do Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="8543b-123">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="8543b-124">Acesso de convidado versus acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="8543b-124">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="8543b-125">Mais informações</span><span class="sxs-lookup"><span data-stu-id="8543b-125">More information</span></span>

[<span data-ttu-id="8543b-126">Autorizar o acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8543b-126">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="8543b-127">Ativar ou desativar o acesso de convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8543b-127">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="8543b-128">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="8543b-128">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
