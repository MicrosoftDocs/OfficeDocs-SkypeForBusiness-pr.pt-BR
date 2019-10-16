---
title: Adicionar um convidado a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
ms.date: 06/21/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
search.appverid: MET150
ms.reviewer: sbhatta
localization_priority: Priority
description: Conheça as ferramentas disponíveis para adicionar novos usuários a uma organização, incluindo clientes desktop e web do Microsoft Teams e o portal de colaboração do Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b23ee82e90dea1bc302f14f305274d3ba64d471
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2019
ms.locfileid: "37516116"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="b9a87-103">Adicionar um convidado a uma equipe</span><span class="sxs-lookup"><span data-stu-id="b9a87-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b9a87-104">Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="b9a87-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams, with full access to team chats, meetings, and files.</span></span>

<span data-ttu-id="b9a87-105">Como administrador, você pode adicionar um novo usuário convidado à organização de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="b9a87-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span>
- <span data-ttu-id="b9a87-106">Administradores globais que são proprietários de uma equipe podem adicionar um convidado a uma equipe através do cliente web ou cliente desktop do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9a87-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span> <span data-ttu-id="b9a87-107">Para mais detalhes, confira [Adicionar convidados à uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span><span class="sxs-lookup"><span data-stu-id="b9a87-107">For more details, check out [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f)</span></span>

> [!NOTE] 
> <span data-ttu-id="b9a87-108">Isso não se aplica quando o recurso **Administradores e usuários na função de emissor de convites podem convidar** se encontra ativado.</span><span class="sxs-lookup"><span data-stu-id="b9a87-108">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="b9a87-109">Isso ocorre porque a função de emissor de convites não é compatível com o Teams.</span><span class="sxs-lookup"><span data-stu-id="b9a87-109">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="b9a87-110">Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B.</span><span class="sxs-lookup"><span data-stu-id="b9a87-110">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="b9a87-111">A colaboração do Azure AD B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer o upload de um arquivo com valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B.</span><span class="sxs-lookup"><span data-stu-id="b9a87-111">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="b9a87-112">Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="b9a87-112">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="b9a87-113">Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="b9a87-113">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="b9a87-114">Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização.</span><span class="sxs-lookup"><span data-stu-id="b9a87-114">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="b9a87-115">Essas políticas são aplicadas na organização de recursos.</span><span class="sxs-lookup"><span data-stu-id="b9a87-115">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="b9a87-116">Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="b9a87-116">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="b9a87-117">Usuários convidados não podem ser bloqueados individualmente.</span><span class="sxs-lookup"><span data-stu-id="b9a87-117">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="b9a87-118">Os usuários convidados que você já adicionou por meio do Azure AD B2B, dos Grupos do Office 365 ou do SharePoint Online estão prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="b9a87-118">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups or SharePoint Online are ready to go.</span></span> <span data-ttu-id="b9a87-119">O administrador do Office 365 ou o proprietário da equipe pode adicionar aqueles convidados às respectivas equipes.</span><span class="sxs-lookup"><span data-stu-id="b9a87-119">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="b9a87-120">Se uma equipe já estiver com um grupos do Office 365 e um convidado for adicionado ao grupo, ele obterá acesso à equipe.</span><span class="sxs-lookup"><span data-stu-id="b9a87-120">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="b9a87-121">Adicionar um convidado através do grupo do Office 365 não gera um e-mail de convite para o convidado; então, alguém da equipe precisa notificá-lo.</span><span class="sxs-lookup"><span data-stu-id="b9a87-121">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="b9a87-122">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="b9a87-122">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="b9a87-123">Você pode acompanhar a adição de convidados no Centro de Conformidade &amp; Segurança do Azure AD ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9a87-123">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="b9a87-124">A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”.</span><span class="sxs-lookup"><span data-stu-id="b9a87-124">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="b9a87-125">Para obter mais detalhes, consulte [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de Segurança &amp; Conformidade do Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="b9a87-125">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="guest-access-vs-external-access-federation"></a><span data-ttu-id="b9a87-126">Acesso de convidado vs. acesso externo (federação)</span><span class="sxs-lookup"><span data-stu-id="b9a87-126">Guest access vs. external access (federation)</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]

## <a name="more-information"></a><span data-ttu-id="b9a87-127">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b9a87-127">More information</span></span>

[<span data-ttu-id="b9a87-128">Autorizar o acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9a87-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="b9a87-129">Ativar ou desativar o acesso a convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9a87-129">Turn on or turn off guest access in Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="b9a87-130">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="b9a87-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
