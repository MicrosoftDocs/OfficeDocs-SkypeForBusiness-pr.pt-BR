---
title: Adicionar um convidado a uma equipe
author: LaithAlShamri
ms.author: laal
manager: serdars
ms.date: 11/26/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: sbhatta
description: Conheça as ferramentas disponíveis para adicionar novos usuários a uma organização, incluindo clientes desktop e web do Microsoft Teams e o portal de colaboração do Azure Active Directory B2B.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0671774d01ce8b2dfeea78fff36dde117931ff00
ms.sourcegitcommit: fbcd150e724456ea4521d68cf3acb351e3525e2e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2018
ms.locfileid: "26674461"
---
<a name="add-a-guest-to-a-team"></a><span data-ttu-id="14f2a-103">Adicionar um convidado a uma equipe</span><span class="sxs-lookup"><span data-stu-id="14f2a-103">Add a guest to a team</span></span>
=====================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="14f2a-104">Qualquer pessoa com uma conta de email de consumidor ou de negócios, como o Outlook, Gmail ou outras pessoas, pode participar como um convidado em equipes.</span><span class="sxs-lookup"><span data-stu-id="14f2a-104">Anyone with a business or consumer email account, such as Outlook, Gmail, or others, can participate as a guest in Teams.</span></span>


<span data-ttu-id="14f2a-105">Como administrador, você pode adicionar um novo convidado usuário à organização de algumas maneiras:</span><span class="sxs-lookup"><span data-stu-id="14f2a-105">As an admin, you can add a new guest user to the organization in a couple ways:</span></span> 
- <span data-ttu-id="14f2a-106">Administradores globais que são proprietários de uma equipe podem adicionar um convidado a uma equipe através do cliente web ou cliente desktop do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="14f2a-106">Global admins who are owners of a team and owners of a team can add a guest to a team through either the Microsoft Teams desktop or the web clients.</span></span>
- <span data-ttu-id="14f2a-107">Adicione convidados à sua organização através da colaboração do Azure Active Directory B2B.</span><span class="sxs-lookup"><span data-stu-id="14f2a-107">Add guests to your organization through Azure Active Directory B2B collaboration.</span></span> <span data-ttu-id="14f2a-108">A colaboração do Azure Active Directory B2B permite que um administrador global convide e autorize um conjunto de usuários externos ao fazer upload de um arquivo de valores separados por vírgulas (CSV) de, no máximo, 2.000 linhas no portal de colaboração B2B.</span><span class="sxs-lookup"><span data-stu-id="14f2a-108">Azure Active Directory B2B collaboration allows a global admin to invite and authorize a set of external users by uploading a comma-separated values (CSV) file of no more than 2,000 lines to the B2B collaboration portal.</span></span> <span data-ttu-id="14f2a-109">Para obter mais detalhes, confira [colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=826383).</span><span class="sxs-lookup"><span data-stu-id="14f2a-109">For more details, check out [Azure Active Directory B2B collaboration](https://go.microsoft.com/fwlink/p/?linkid=826383).</span></span>



<span data-ttu-id="14f2a-110">Com a colaboração do Azure Active Directory B2B, as organizações podem impor políticas de acesso condicional e autenticação multifator (MFA) para usuários B2B.</span><span class="sxs-lookup"><span data-stu-id="14f2a-110">With Azure Active Directory B2B collaboration, organizations can enforce conditional access and multi-factor authentication (MFA) policies for B2B users.</span></span> <span data-ttu-id="14f2a-111">Essas políticas podem ser aplicadas em nível de locatário, aplicativo ou usuário individual, da mesma forma que são habilitadas para funcionários de período integral e membros da organização.</span><span class="sxs-lookup"><span data-stu-id="14f2a-111">These policies can be enforced at the tenant, app, or individual user level, the same way that they are enabled for full-time employees and members of the organization.</span></span> <span data-ttu-id="14f2a-112">Essas políticas são aplicadas na organização de recursos.</span><span class="sxs-lookup"><span data-stu-id="14f2a-112">Such policies are enforced at the resource organization.</span></span> <span data-ttu-id="14f2a-113">Para obter mais informações, consulte [Acesso condicional para usuários de colaboração B2B](https://go.microsoft.com/fwlink/?linkid=857454).</span><span class="sxs-lookup"><span data-stu-id="14f2a-113">For more information, see  [Conditional access for B2B collaboration users](https://go.microsoft.com/fwlink/?linkid=857454).</span></span> <span data-ttu-id="14f2a-114">Usuários convidados não podem ser bloqueados individualmente.</span><span class="sxs-lookup"><span data-stu-id="14f2a-114">Individual guest users can't be blocked.</span></span>



<span data-ttu-id="14f2a-115">Usuários convidados que você já tiver adicionado via B2B do Azure Active Directory, grupos do Office 365 ou SharePoint Online estão prontos para ir.</span><span class="sxs-lookup"><span data-stu-id="14f2a-115">Guest users you have already added via Azure Active Directory B2B, Office 365 Groups, or SharePoint Online are ready to go.</span></span> <span data-ttu-id="14f2a-116">O administrador do Office 365 ou o proprietário da equipe pode adicionar aqueles convidados às respectivas equipes.</span><span class="sxs-lookup"><span data-stu-id="14f2a-116">The Office 365 admin or a team owner can add those guests to their respective teams.</span></span> <span data-ttu-id="14f2a-117">Se uma equipe já estiver com um grupos do Office 365 e um convidado for adicionado ao grupo, ele obterá acesso à equipe.</span><span class="sxs-lookup"><span data-stu-id="14f2a-117">If a team is already with an Office 365 group, and a guest is added to the group, the guest will get access to the team.</span></span> <span data-ttu-id="14f2a-118">Adicionar um convidado através do grupo do Office 365 não gera um e-mail de convite para o convidado; então, alguém da equipe precisa notificá-lo.</span><span class="sxs-lookup"><span data-stu-id="14f2a-118">Adding a guest via the Office 365 group doesn't generate an invitation email to the guest, so someone on the team should notify the guest.</span></span>

> [!NOTE]
> <span data-ttu-id="14f2a-119">Os convidados estão sujeitos aos limites de serviço do [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) e do [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="14f2a-119">Guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>



<span data-ttu-id="14f2a-120">Você pode acompanhar a adição de convidados no Centro de Segurança &amp; Conformidade do Azure Active Directory ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="14f2a-120">You can track guest additions in Azure Active Directory or the Office 365 Security &amp; Compliance Center.</span></span> <span data-ttu-id="14f2a-121">A adição de um convidado no Microsoft Teams é auditada e registrada como uma atividade de administração de grupo do Azure AD: “Adicionou membro a grupo”.</span><span class="sxs-lookup"><span data-stu-id="14f2a-121">Adding a guest in Microsoft Teams is audited and logged as an Azure AD group administration activity "Added member to group".</span></span> <span data-ttu-id="14f2a-122">Para obter mais detalhes, consulte [Auditar e reportar um usuário de colaboração B2B](https://go.microsoft.com/fwlink/p/?linkid=858884) e [Procurar registro de auditoria no Centro de Segurança &amp; Conformidade do Office 365](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span><span class="sxs-lookup"><span data-stu-id="14f2a-122">For more details, see  [Auditing and reporting a B2B collaboration user](https://go.microsoft.com/fwlink/p/?linkid=858884) and [Search the audit log in the Office 365 Security &amp; Compliance Center](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security--Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).</span></span>

## <a name="more-information"></a><span data-ttu-id="14f2a-123">Mais informações</span><span class="sxs-lookup"><span data-stu-id="14f2a-123">More information</span></span>

<span data-ttu-id="14f2a-124">[Autorizar o acesso de convidado no Microsoft Teams](teams-dependencies.md)
[Ativar ou desativar o acesso de convidado em equipes da Microsoft](set-up-guests.md)
[Usar o PowerShell para controlar o acesso de convidado para uma equipe](guest-access-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="14f2a-124">[Authorize guest access in Microsoft Teams](teams-dependencies.md)
[Turn on or off guest access in Microsoft Teams](set-up-guests.md)
[Use PowerShell to control guest access to a team](guest-access-powershell.md)</span></span>