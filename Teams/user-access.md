---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como gerenciar o acesso do usuário às equipes ao atribuir ou remover uma licença do teams para os usuários de sua organização.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d877a4c6534c76b894583401dc5dba0936c3c75
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521378"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="d567b-103">Gerenciamento do acesso de usuários ao Teams</span><span class="sxs-lookup"><span data-stu-id="d567b-103">Manage user access to Teams</span></span>

<span data-ttu-id="d567b-104">Você gerencia o acesso às equipes no nível do usuário, atribuindo ou removendo uma licença de produto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="d567b-105">Cada usuário da sua organização deve ter uma licença do teams para poder usar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-105">Each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="d567b-106">Você pode atribuir uma licença do teams para novos usuários quando novas contas de usuário forem criadas ou para usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="d567b-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="d567b-107">Por padrão, quando um plano de licenciamento (por exemplo, o Microsoft 365 Enterprise E3 ou o Microsoft 365 Business Premium) é atribuído a um usuário, uma licença do Team é automaticamente atribuída e o usuário é habilitado para Teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium)  is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="d567b-108">Você pode desabilitar ou habilitar o Microsoft Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d567b-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="d567b-109">Use políticas de mensagens, gerenciadas a partir do <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">centro de administração do teams</a>, para controlar quais recursos de chat e mensagens de canal estão disponíveis para os usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="d567b-110">Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d567b-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="d567b-111">Para saber mais, leia [gerenciar políticas de mensagens no Microsoft Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d567b-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="d567b-112">Você gerencia as licenças do teams no centro de administração do Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d567b-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="d567b-113">Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.</span><span class="sxs-lookup"><span data-stu-id="d567b-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d567b-114">Recomendamos que você habilite o Teams para todos os usuários para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="d567b-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="d567b-115">Mesmo que você esteja executando um piloto, talvez ainda seja útil manter o Microsoft Teams habilitado para todos os usuários, mas somente as comunicações são direcionadas para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="d567b-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d567b-116">Usar o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d567b-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d567b-117">As licenças de nível de usuário do Team são gerenciadas diretamente por meio das interfaces de gerenciamento de usuários do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d567b-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="d567b-118">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="d567b-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d567b-119">O administrador deve ter privilégios de administrador global ou administrador de gerenciamento de usuários para gerenciar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="d567b-120">Use o centro de administração do Microsoft 365 para gerenciar as licenças do teams para usuários individuais ou pequenos conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="d567b-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="d567b-121">Você pode gerenciar as licenças do teams na página **licenças** (para até 20 usuários no momento) ou página **usuários ativos** .</span><span class="sxs-lookup"><span data-stu-id="d567b-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="d567b-122">O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="d567b-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d567b-123">Se você precisar gerenciar as licenças do Team para um grande número de usuários, como centenas ou milhares de usuários, [use o PowerShell](#using-powershell) ou o [Licenciamento baseado em grupo no Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="d567b-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use Powershell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="d567b-124">Atribuir uma licença do teams</span><span class="sxs-lookup"><span data-stu-id="d567b-124">Assign a Teams license</span></span>

<span data-ttu-id="d567b-125">As etapas são diferentes dependendo se você usa a página **licenças** ou a página **usuários ativos** .</span><span class="sxs-lookup"><span data-stu-id="d567b-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="d567b-126">Para obter instruções passo a passo, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="d567b-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Captura de tela da licença do teams habilitada para um usuário](media/assign-teams-licenses-1.png)    | ![Captura de tela da licença do teams habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="d567b-129">Remover uma licença do teams</span><span class="sxs-lookup"><span data-stu-id="d567b-129">Remove a Teams license</span></span>

<span data-ttu-id="d567b-130">Quando você remove uma licença do teams de um usuário, o Microsoft Teams é desabilitado para esse usuário, e ele não vê mais as equipes no inicializador de aplicativos ou na Home Page.</span><span class="sxs-lookup"><span data-stu-id="d567b-130">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="d567b-131">Para obter etapas detalhadas, consulte [cancelar a atribuição de licenças dos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="d567b-131">For detailed steps, see [Unassign licenses from users](https://docs.microsoft.com/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Captura de tela da licença do teams desabilitada para um usuário](media/remove-teams-licenses-1.png)    | ![Captura de tela da licença do teams desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="d567b-134">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d567b-134">Using PowerShell</span></span>

<span data-ttu-id="d567b-135">Use o PowerShell para gerenciar as licenças do teams para usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="d567b-135">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="d567b-136">Você pode habilitar e desabilitar o Microsoft Teams pelo PowerShell da mesma forma que faria para qualquer outra licença de plano de serviço.</span><span class="sxs-lookup"><span data-stu-id="d567b-136">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="d567b-137">Você precisará dos identificadores para os planos de serviço do Teams, que são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="d567b-137">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="d567b-138">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="d567b-138">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="d567b-139">Microsoft Teams para GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="d567b-139">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="d567b-140">Microsoft Teams para DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="d567b-140">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="d567b-141">Atribuir licenças de equipe em massa</span><span class="sxs-lookup"><span data-stu-id="d567b-141">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="d567b-142">Para obter etapas detalhadas, consulte [atribuir licenças a contas de usuário com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d567b-142">For detailed steps, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="d567b-143">Remover licenças do Team em massa</span><span class="sxs-lookup"><span data-stu-id="d567b-143">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="d567b-144">Para obter etapas detalhadas, confira [desabilitar o acesso a serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) e [desabilitar o acesso aos serviços ao atribuir licenças de usuário](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="d567b-144">For detailed steps, see [Disable access to services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="d567b-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d567b-145">Example</span></span> 

<span data-ttu-id="d567b-146">Veja a seguir um exemplo de como usar os cmdlets [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) e [set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="d567b-146">The following is an example of how to use the [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](https://docs.microsoft.com/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="d567b-147">Por exemplo, siga estas etapas para desabilitar primeiro o Teams para todos os usuários que tenham um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="d567b-147">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="d567b-148">Em seguida, habilite o Teams para cada usuário individual que deve ter acesso ao Teams.</span><span class="sxs-lookup"><span data-stu-id="d567b-148">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d567b-149">O cmdlet [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) habilitará todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificados em seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="d567b-149">The [New-MsolLicenseOptions](https://docs.microsoft.com/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="d567b-150">Por exemplo, se você quiser deixar o Exchange e o Sway desabilitado e também desabilitar o Teams, será necessário incluir isso no script ou o Exchange e o Sway serão habilitados para os usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="d567b-150">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="d567b-151">Execute o comando a seguir para exibir todos os planos de licenciamento disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d567b-151">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="d567b-152">Para saber mais, consulte [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d567b-152">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>

      Get-MsolAccountSku

<span data-ttu-id="d567b-153">Execute os seguintes comandos, onde \<CompanyName:License> é o nome da sua organização e o identificador para o plano de licenciamento que você recuperou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d567b-153">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="d567b-154">Por exemplo, ContosoSchool: ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="d567b-154">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

      $acctSKU="<CompanyName:License>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"

<span data-ttu-id="d567b-155">Execute o comando a seguir para desabilitar o Microsoft Teams para todos os usuários que têm uma licença ativa para o plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="d567b-155">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

## <a name="manage-teams-at-the-organization-level"></a><span data-ttu-id="d567b-156">Gerenciar equipes no nível da organização</span><span class="sxs-lookup"><span data-stu-id="d567b-156">Manage teams at the organization level</span></span>

[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

## <a name="related-topics"></a><span data-ttu-id="d567b-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d567b-157">Related topics</span></span>

- [<span data-ttu-id="d567b-158">Licenças de Complementos do teams</span><span class="sxs-lookup"><span data-stu-id="d567b-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d567b-159">Atribuir licenças de Complementos do teams</span><span class="sxs-lookup"><span data-stu-id="d567b-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="d567b-160">Exibir licenças e serviços com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d567b-160">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d567b-161">Nomes de produtos e identificadores de plano de serviço para licenciamento</span><span class="sxs-lookup"><span data-stu-id="d567b-161">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d567b-162">Referência de SKU do Education</span><span class="sxs-lookup"><span data-stu-id="d567b-162">Education SKU reference</span></span>](sku-reference-edu.md)