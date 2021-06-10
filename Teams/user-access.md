---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como gerenciar o acesso do usuário ao Teams atribuindo ou removendo uma licença Teams aos usuários em sua organização.
f1.keywords:
- CSH
- ms.teamsadmincenter.signin.domainerror.nolicensedusers
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 770dcea62d6f3dc65f576a3d64a520dd4de2ecad
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637723"
---
# <a name="manage-user-access-to-teams"></a><span data-ttu-id="d67ef-103">Gerenciamento do acesso de usuários ao Teams</span><span class="sxs-lookup"><span data-stu-id="d67ef-103">Manage user access to Teams</span></span>

<span data-ttu-id="d67ef-104">Você gerencia o acesso Teams no nível do usuário atribuindo ou removendo uma licença Microsoft Teams produto.</span><span class="sxs-lookup"><span data-stu-id="d67ef-104">You manage access to Teams at the user level by assigning or removing a Microsoft Teams product license.</span></span> <span data-ttu-id="d67ef-105">Com exceção de Teams reuniões anônimas, cada usuário em sua organização deve ter uma licença Teams para poder usar Teams.</span><span class="sxs-lookup"><span data-stu-id="d67ef-105">Except for joining Teams meetings anonymously, each user in your organization must have a Teams license before they can use Teams.</span></span> <span data-ttu-id="d67ef-106">Você pode atribuir uma Teams para novos usuários quando novas contas de usuário são criadas ou para usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="d67ef-106">You can assign a Teams license for new users when new user accounts are created or to users with existing accounts.</span></span>

<span data-ttu-id="d67ef-107">Por padrão, quando um plano de licenciamento (por exemplo, Microsoft 365 Enterprise E3 ou Microsoft 365 Business Premium) é atribuído a um usuário, uma licença Teams é atribuída automaticamente e o usuário está habilitado para Teams.</span><span class="sxs-lookup"><span data-stu-id="d67ef-107">By default, when a licensing plan (for example, Microsoft 365 Enterprise E3 or Microsoft 365 Business Premium) is assigned to a user, a Teams license is automatically assigned, and the user is enabled for Teams.</span></span> <span data-ttu-id="d67ef-108">Você pode desabilitar ou habilitar Teams para um usuário removendo ou atribuindo uma licença a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="d67ef-108">You can disable or enable Teams for a user by removing or assigning a license at any time.</span></span>

<span data-ttu-id="d67ef-109">Use políticas de mensagens, gerenciadas <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Centro</a>de Administração, para controlar quais recursos de mensagens de chat e canal estão disponíveis para os usuários no Teams.</span><span class="sxs-lookup"><span data-stu-id="d67ef-109">Use messaging policies, managed from the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Teams Admin Center</a>, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="d67ef-110">Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d67ef-110">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="d67ef-111">Para saber mais, leia [Gerenciar políticas de mensagens em Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="d67ef-111">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>
<span data-ttu-id="d67ef-112">Você gerencia Teams licenças no centro de administração Microsoft 365 ou usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d67ef-112">You manage Teams licenses in the Microsoft 365 admin center or by using PowerShell.</span></span> <span data-ttu-id="d67ef-113">Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.</span><span class="sxs-lookup"><span data-stu-id="d67ef-113">You must be a Global admin or User management admin to manage licenses.</span></span>

> [!NOTE]
> <span data-ttu-id="d67ef-114">Recomendamos que você habilita Teams para todos os usuários para que as equipes possam ser formadas organicamente para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="d67ef-114">We recommend that you enable Teams for all users so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="d67ef-115">Mesmo que você esteja executando um piloto, ainda pode ser útil manter a Teams habilitada para todos os usuários, mas apenas direcionar as comunicações para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="d67ef-115">Even if you're running a pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="d67ef-116">Usando o Microsoft 365 de administração</span><span class="sxs-lookup"><span data-stu-id="d67ef-116">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="d67ef-117">Teams licenças no nível do usuário são gerenciadas diretamente por meio das interfaces de gerenciamento do Microsoft 365 do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="d67ef-117">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="d67ef-118">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="d67ef-118">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d67ef-119">O administrador deve ter privilégios de Administrador Global ou Administrador de Gerenciamento de Usuários para gerenciar Microsoft Teams licenças.</span><span class="sxs-lookup"><span data-stu-id="d67ef-119">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>
<span data-ttu-id="d67ef-120">Use o Microsoft 365 de administração para gerenciar Teams licenças para usuários individuais ou pequenos conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="d67ef-120">Use the Microsoft 365 admin center to manage Teams licenses for individual users or small sets of users at a time.</span></span> <span data-ttu-id="d67ef-121">Você pode gerenciar Teams licenças na página **Licenças** (para até 20 usuários no momento) ou **página Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="d67ef-121">You can manage Teams licenses on the **Licenses** page (for up to 20 users at at time) or **Active users** page.</span></span> <span data-ttu-id="d67ef-122">O método escolhido depende se você deseja gerenciar licenças de produtos para usuários específicos ou gerenciar licenças de usuário para produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="d67ef-122">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="d67ef-123">Se você precisar gerenciar Teams licenças para um grande número de usuários, como centenas ou milhares de usuários, use o [PowerShell](#using-powershell) ou o licenciamento baseado em grupo no [Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="d67ef-123">If you need to manage Teams licenses for a large number of users, such as hundreds or thousands of users, [use PowerShell](#using-powershell) or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span> 

### <a name="assign-a-teams-license"></a><span data-ttu-id="d67ef-124">Atribuir uma Teams de usuário</span><span class="sxs-lookup"><span data-stu-id="d67ef-124">Assign a Teams license</span></span>

<span data-ttu-id="d67ef-125">As etapas são diferentes, dependendo de você usar a página **Licenças** ou **a página Usuários ativos.**</span><span class="sxs-lookup"><span data-stu-id="d67ef-125">The steps are different depending on whether you use the **Licenses** page or **Active users** page.</span></span>  <span data-ttu-id="d67ef-126">Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="d67ef-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

|||
|---------|---------|
|![Captura de tela Teams licença habilitada para um usuário](media/assign-teams-licenses-1.png)    | ![Captura de tela Teams licença habilitada para um usuário](media/assign-teams-licenses-2.png)        |

### <a name="remove-a-teams-license"></a><span data-ttu-id="d67ef-129">Remover uma Teams de Teams</span><span class="sxs-lookup"><span data-stu-id="d67ef-129">Remove a Teams license</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d67ef-130">Leva cerca de 24 horas para desabilitar uma Teams SKU para fazer efeito.</span><span class="sxs-lookup"><span data-stu-id="d67ef-130">It takes about 24 hours for disabling a Teams SKU to take effect.</span></span>

<span data-ttu-id="d67ef-131">Quando você remove uma Teams de um usuário, o Teams está desabilitado para esse usuário, e ele não verá mais Teams no launcher de aplicativos ou na homepage.</span><span class="sxs-lookup"><span data-stu-id="d67ef-131">When you remove a Teams license from a user, Teams is disabled for that user, and they will no longer see Teams in the app launcher or homepage.</span></span> <span data-ttu-id="d67ef-132">Para etapas detalhadas, consulte [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span><span class="sxs-lookup"><span data-stu-id="d67ef-132">For detailed steps, see [Unassign licenses from users](/microsoft-365/admin/manage/remove-licenses-from-users).</span></span>

|||
|---------|---------|
|![Captura de tela Teams licença desabilitada para um usuário](media/remove-teams-licenses-1.png)    | ![Captura de tela Teams licença desabilitada para um usuário](media/remove-teams-licenses-2.png)        |

## <a name="using-powershell"></a><span data-ttu-id="d67ef-135">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d67ef-135">Using PowerShell</span></span>

<span data-ttu-id="d67ef-136">Use o PowerShell para gerenciar Teams para usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="d67ef-136">Use PowerShell to manage Teams licenses for users in bulk.</span></span> <span data-ttu-id="d67ef-137">Você habilita e desabilita Teams através do PowerShell da mesma forma que faria para qualquer outra licença de plano de serviço.</span><span class="sxs-lookup"><span data-stu-id="d67ef-137">You enable and disable Teams through PowerShell in the same way that you would for any other service plan license.</span></span> <span data-ttu-id="d67ef-138">Você precisará dos identificadores para os planos de serviço para Teams, que são os seguinte:</span><span class="sxs-lookup"><span data-stu-id="d67ef-138">You'll need the identifiers for the service plans for Teams, which are as follows:</span></span>

- <span data-ttu-id="d67ef-139">Microsoft Teams: TEAMS1</span><span class="sxs-lookup"><span data-stu-id="d67ef-139">Microsoft Teams: TEAMS1</span></span>
- <span data-ttu-id="d67ef-140">Microsoft Teams para GCC: TEAMS_GOV</span><span class="sxs-lookup"><span data-stu-id="d67ef-140">Microsoft Teams for GCC: TEAMS_GOV</span></span>
- <span data-ttu-id="d67ef-141">Microsoft Teams para DoD: TEAMS_DOD</span><span class="sxs-lookup"><span data-stu-id="d67ef-141">Microsoft Teams for DoD: TEAMS_DOD</span></span>

### <a name="assign-teams-licenses-in-bulk"></a><span data-ttu-id="d67ef-142">Atribuir Teams licenças em massa</span><span class="sxs-lookup"><span data-stu-id="d67ef-142">Assign Teams licenses in bulk</span></span>

<span data-ttu-id="d67ef-143">Para etapas detalhadas, consulte [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d67ef-143">For detailed steps, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="remove-teams-licenses-in-bulk"></a><span data-ttu-id="d67ef-144">Remover Teams licenças em massa</span><span class="sxs-lookup"><span data-stu-id="d67ef-144">Remove Teams licenses in bulk</span></span>

<span data-ttu-id="d67ef-145">Para etapas detalhadas, consulte [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and Disable access to services while [assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span><span class="sxs-lookup"><span data-stu-id="d67ef-145">For detailed steps, see [Disable access to services with PowerShell](/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) and [Disable access to services while assigning user licenses](/office365/enterprise/powershell/disable-access-to-services-while-assigning-user-licenses).</span></span>

#### <a name="example"></a><span data-ttu-id="d67ef-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d67ef-146">Example</span></span> 

<span data-ttu-id="d67ef-147">Veja a seguir um exemplo de como usar os [cmdlets New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) e [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) para desabilitar o Teams para usuários que têm um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="d67ef-147">The following is an example of how to use the [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) and [Set-MsolUserLicense](/powershell/module/msonline/set-msoluserlicense) cmdlets to disable Teams for users who have a specific licensing plan.</span></span> <span data-ttu-id="d67ef-148">Por exemplo, siga estas etapas para primeiro desabilitar Teams para todos os usuários que têm um plano de licenciamento específico.</span><span class="sxs-lookup"><span data-stu-id="d67ef-148">For example, follow these steps to first disable Teams for all users who have a particular licensing plan.</span></span> <span data-ttu-id="d67ef-149">Em seguida, Teams para cada usuário individual que deve ter acesso a Teams.</span><span class="sxs-lookup"><span data-stu-id="d67ef-149">Then enable Teams for each individual user who should have access to Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d67ef-150">O cmdlet [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) habilita todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificado em seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="d67ef-150">The [New-MsolLicenseOptions](/powershell/module/msonline/new-msollicenseoptions) cmdlet will enable all services that were previously disabled unless explicitly identified in your custom script.</span></span> <span data-ttu-id="d67ef-151">Por exemplo, se você quiser deixar o Exchange e o Sway desabilitados enquanto também desabilita o Teams, você precisará incluir isso no script ou o Exchange e o Sway estarão habilitados para os usuários identificados.</span><span class="sxs-lookup"><span data-stu-id="d67ef-151">For example, if you want to leave both Exchange and Sway disabled while also disabling Teams, you'll need to include this in the script or both Exchange and Sway will be enabled for those users you identified.</span></span>

<span data-ttu-id="d67ef-152">Execute o seguinte comando para exibir todos os planos de licenciamento disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="d67ef-152">Run the following command to display all available licensing plans in your organization.</span></span> <span data-ttu-id="d67ef-153">Para saber mais, confira [Exibir licenças e serviços com o PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="d67ef-153">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell).</span></span>


```powershell
Get-MsolAccountSku
```

<span data-ttu-id="d67ef-154">Execute os comandos a seguir, onde está o nome da sua organização e o identificador do plano de licenciamento que \<CompanyName:License> você recuperou na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d67ef-154">Run the following commands, where \<CompanyName:License> is your organization name and the identifier for the licensing plan that you retrieved in the earlier step.</span></span> <span data-ttu-id="d67ef-155">Por exemplo, ContosoSchool:ENTERPRISEPACK_STUDENT.</span><span class="sxs-lookup"><span data-stu-id="d67ef-155">For example, ContosoSchool:ENTERPRISEPACK_STUDENT.</span></span>

```powershell
$acctSKU="<CompanyName:License>
$x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
```

<span data-ttu-id="d67ef-156">Execute o seguinte comando para desabilitar Teams para todos os usuários que têm uma licença ativa para o plano de licenciamento.</span><span class="sxs-lookup"><span data-stu-id="d67ef-156">Run the following command to disable Teams for all users who have an active license for the licensing plan.</span></span>

```powershell
Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x
```

## <a name="related-topics"></a><span data-ttu-id="d67ef-157">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d67ef-157">Related topics</span></span>

- [<span data-ttu-id="d67ef-158">Teams licenças de complemento</span><span class="sxs-lookup"><span data-stu-id="d67ef-158">Teams add-on licenses</span></span>](teams-add-on-licensing/microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="d67ef-159">Atribuir Teams licenças de complemento</span><span class="sxs-lookup"><span data-stu-id="d67ef-159">Assign Teams add-on licenses</span></span>](teams-add-on-licensing/assign-teams-add-on-licenses.md)
- [<span data-ttu-id="d67ef-160">Exibir licenças e serviços com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d67ef-160">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="d67ef-161">Nomes de produtos e identificadores de plano de serviço para licenciamento</span><span class="sxs-lookup"><span data-stu-id="d67ef-161">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="d67ef-162">Referência de SKU do Education</span><span class="sxs-lookup"><span data-stu-id="d67ef-162">Education SKU reference</span></span>](sku-reference-edu.md)
