---
title: Adicionar um convidado a uma equipe
author: somakbhattacharyya
ms.author: sbhatta
manager: serdars
audience: ITPro
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
ms.openlocfilehash: 78f495b10e953a8e416c8cadd755a098c8c948a7
ms.sourcegitcommit: 09e719ead5c02b3cfa96828841c4905748d192a3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2019
ms.locfileid: "37753246"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="b4db8-103">Adicionar um convidado a uma equipe</span><span class="sxs-lookup"><span data-stu-id="b4db8-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b4db8-104">Qualquer pessoa com uma conta de email corporativa ou de consumidor, como o Outlook, o Gmail ou outras, pode participar como convidado no Teams.</span><span class="sxs-lookup"><span data-stu-id="b4db8-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>

<span data-ttu-id="b4db8-105">Como administrador, você pode adicionar um novo usuário convidado à organização de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="b4db8-105">As an admin, you can add a new guest user to the organization in a couple of ways:</span></span>
- <span data-ttu-id="b4db8-106">Os administradores globais ou administradores do Teams e os proprietários de equipes adicionam um convidado a uma equipe nos clientes do Teams ou no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="b4db8-106">Global admins or Teams admins and team owners add a guest to a team in the Teams clients or in the Teams admin center.</span></span> <span data-ttu-id="b4db8-107">Para saber mais, leia [Adicionar convidados a uma equipe](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span><span class="sxs-lookup"><span data-stu-id="b4db8-107">To learn more, read [Add guests to a team](https://support.office.com/article/add-guests-to-a-team-fccb4fa6-f864-4508-bdde-256e7384a14f).</span></span> <span data-ttu-id="b4db8-108">Se você ainda não configurou o acesso de convidado, siga as etapas da [Lista de verificação de acesso de convidado](guest-access-checklist.md).</span><span class="sxs-lookup"><span data-stu-id="b4db8-108">If you haven't set up guest access yet, go through the steps in the [Guest access checklist](guest-access-checklist.md).</span></span>

> [!NOTE] 
> <span data-ttu-id="b4db8-109">Isso não se aplica quando o recurso **Administradores e usuários na função de emissor de convites podem convidar** se encontra ativado.</span><span class="sxs-lookup"><span data-stu-id="b4db8-109">This does not apply when **Admins and users in the guest inviter role can invite** is enabled.</span></span> <span data-ttu-id="b4db8-110">Isso ocorre porque a função de emissor de convites não é compatível com o Teams.</span><span class="sxs-lookup"><span data-stu-id="b4db8-110">This is because the guest invitor role isn't supported in Teams.</span></span>

- <span data-ttu-id="b4db8-111">Adicione convidados à sua organização através da colaboração do Azure AD (Azure Active Directory) B2B.</span><span class="sxs-lookup"><span data-stu-id="b4db8-111">Add guests to your organization through Azure Active Directory (Azure AD) B2B collaboration.</span></span> <span data-ttu-id="b4db8-112">A colaboração do Azure AD B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer o upload de um arquivo com valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B.</span><span class="sxs-lookup"><span data-stu-id="b4db8-112">Azure AD B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="b4db8-113">Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="b4db8-113">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>

<span data-ttu-id="b4db8-114">Com a colaboração do Azure AD B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="b4db8-114">With Azure AD B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="b4db8-115">Essas políticas podem ser impostas no nível do locatário, aplicativo ou usuário individual, da mesma maneira que podem ser habilitadas para membros e funcionários em tempo integral da organização.</span><span class="sxs-lookup"><span data-stu-id="b4db8-115">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="b4db8-116">Essas políticas são aplicadas na organização de recursos.</span><span class="sxs-lookup"><span data-stu-id="b4db8-116">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="b4db8-117">Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="b4db8-117">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="b4db8-118">Usuários convidados não podem ser bloqueados individualmente.</span><span class="sxs-lookup"><span data-stu-id="b4db8-118">Individual guest users can't be blocked.</span></span>

<span data-ttu-id="b4db8-119">Os usuários convidados que você já adicionou por meio do Azure AD B2B, dos Grupos do Office 365 ou do SharePoint Online estão prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="b4db8-119">Guest users you have already added via Azure AD B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="b4db8-120">O administrador do Office 365 ou o proprietário da equipe pode adicionar aqueles convidados às respectivas equipes.</span><span class="sxs-lookup"><span data-stu-id="b4db8-120">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="b4db8-121">Se uma equipe já estiver com um grupos do Office 365 e um convidado for adicionado ao grupo, ele obterá acesso à equipe.</span><span class="sxs-lookup"><span data-stu-id="b4db8-121">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="b4db8-122">Adicionar um convidado através do grupo do Office 365 não gera um e-mail de convite para o convidado; então, alguém da equipe precisa notificá-lo.</span><span class="sxs-lookup"><span data-stu-id="b4db8-122">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="b4db8-123">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="b4db8-123">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>

<span data-ttu-id="b4db8-124">Você pode acompanhar a adição de convidados no Centro de Conformidade &amp; Segurança do Azure AD ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b4db8-124">You can track guest additions in Azure AD or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="b4db8-125">A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”.</span><span class="sxs-lookup"><span data-stu-id="b4db8-125">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="b4db8-126">Para obter mais detalhes, consulte [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de Segurança &amp; Conformidade do Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="b4db8-126">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>


## <a name="more-information"></a><span data-ttu-id="b4db8-127">Mais informações</span><span class="sxs-lookup"><span data-stu-id="b4db8-127">More information</span></span>

[<span data-ttu-id="b4db8-128">Autorizar o acesso para convidado no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4db8-128">Authorize guest access in Microsoft Teams</span></span>](teams-dependencies.md)</br>
[<span data-ttu-id="b4db8-129">Ativar ou desativar o acesso a convidados no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b4db8-129">Turn on or off guest access in Microsoft Teams</span></span>](set-up-guests.md)</br>
[<span data-ttu-id="b4db8-130">Usar o PowerShell para controlar o acesso de convidados a uma equipe</span><span class="sxs-lookup"><span data-stu-id="b4db8-130">Use PowerShell to control guest access to a team</span></span>](guest-access-powershell.md)
