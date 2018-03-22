---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: ritikag
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: a612420808af06a773d206573f02d805aac06b15
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="0147e-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0147e-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="0147e-104">No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário por como atribuir ou remover a licença do produto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0147e-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="0147e-105">Atualmente, não existem opções para equipes ou um subconjunto dos recursos de equipes, ativando ou desativando em um nível de usuário individual fora do licenciamento por política.</span><span class="sxs-lookup"><span data-stu-id="0147e-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="0147e-106">A Microsoft recomenda que você ativar equipes para todos os usuários em uma empresa para que as equipes podem ser formadas organicamente para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="0147e-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="0147e-107">Mesmo se você decidir para piloto, ainda será útil manter equipes habilitadas para todos os usuários, mas apenas as comunicações para o grupo piloto de usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="0147e-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-directly-through-the-office-365-admin-center"></a><span data-ttu-id="0147e-108">Gerenciar diretamente por meio do Centro de administração do Office 365</span><span class="sxs-lookup"><span data-stu-id="0147e-108">Manage directly through the Office 365 admin center</span></span>

<span data-ttu-id="0147e-109">As equipes licenças de nível de usuário são gerenciadas diretamente por meio das interfaces de gerenciamento de usuário do Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="0147e-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="0147e-110">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="0147e-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="0147e-111">O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0147e-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="0147e-112">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0147e-112">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="0147e-113">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="0147e-113">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="0147e-115">Uma licença de usuário de equipes pode estar desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="0147e-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="0147e-116">Depois que a licença é desabilitada, não poderá fazer o acesso de usuários a Microsoft Teams e o usuário não terá mais conseguirá ver equipes na home page e iniciador de aplicativo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0147e-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="0147e-118">Gerenciar via PowerShell</span><span class="sxs-lookup"><span data-stu-id="0147e-118">Manage via PowerShell</span></span>

<span data-ttu-id="0147e-119">A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="0147e-119">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="0147e-120">O nome do plano de serviço é TEAMS1 for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0147e-120">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="0147e-121">(Consulte mais informações em [Desabilitar o acesso aos serviços com o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="0147e-121">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="0147e-122">**Exemplo:** Abaixo é apenas um exemplo rápido sobre como você faria desabilitar equipes para todas as pessoas em um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="0147e-122">**Sample:** Below is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="0147e-123">Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.</span><span class="sxs-lookup"><span data-stu-id="0147e-123">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="0147e-124">Para exibir os tipos de assinatura que você tem na organização, use este comando:</span><span class="sxs-lookup"><span data-stu-id="0147e-124">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="0147e-125">Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="0147e-125">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="0147e-126">Para desabilitar as equipes de todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0147e-126">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="0147e-128">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="0147e-128">Decision Point</span></span>         |<ul><li><span data-ttu-id="0147e-129">O que é o planejamento da sua organização para inclusão de equipes em toda a organização?</span><span class="sxs-lookup"><span data-stu-id="0147e-129">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="0147e-130">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="0147e-130">(Pilot or Open)</span></span></li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="0147e-132">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="0147e-132">Next Steps</span></span>         |<ul><li><span data-ttu-id="0147e-133">Se for iniciar via piloto fechado, decida se deseja fazê-lo através de licenciamento ou comunicação direcionada.</span><span class="sxs-lookup"><span data-stu-id="0147e-133">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="0147e-134">Dependendo de decisão, siga as etapas para certificar-se testar apenas usuários que têm permissão para acessar as equipes (se necessário).</span><span class="sxs-lookup"><span data-stu-id="0147e-134">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="0147e-135">Documente as diretrizes para quais usuários que serão (ou não) têm acesso às equipes.</span><span class="sxs-lookup"><span data-stu-id="0147e-135">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-via-office-sku-level-switch"></a><span data-ttu-id="0147e-136">Gerenciar por meio de switch de nível de Sku do Office</span><span class="sxs-lookup"><span data-stu-id="0147e-136">Manage via Office Sku level switch</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

1.  <span data-ttu-id="0147e-137">Entre no [Centro de Administração do Office 365](https://go.microsoft.com/fwlink/?linkid=854614) com uma conta que tenha privilégios de administrador global.</span><span class="sxs-lookup"><span data-stu-id="0147e-137">Sign in to the [Office 365 Admin center](https://go.microsoft.com/fwlink/?linkid=854614) with an account that has Global Administrator privileges.</span></span>

2.  <span data-ttu-id="0147e-138">Vá até **Configurações** > **Serviços e suplementos**.</span><span class="sxs-lookup"><span data-stu-id="0147e-138">Go to **Settings** > **Services & add-ins**.</span></span>

    ![<span data-ttu-id="0147e-139">Captura de tela da seção de Configurações do centro de administração do Office 365 com Serviços e complementos selecionado.</span><span class="sxs-lookup"><span data-stu-id="0147e-139">Screenshot of the Settings section in the Office 365 admin center with Services & add-ins selected.</span></span> ](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image1.png)

3.  <span data-ttu-id="0147e-140">Na página se Serviços e complementos, clique em **Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="0147e-140">On the Services & add-ins page, click **Microsoft Teams**.</span></span>

    ![Captura de tela da página de Serviços e complementos com o Microsoft Teams selecionado.](media/Set_up_Microsoft_Teams_in_your_Office_365_organization_image2.png)

4.  <span data-ttu-id="0147e-142">Para ativar o Microsoft Teams para a organização, use o seletor de licenças e escolha cada licença. Depois definina a opção como **Ativado** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0147e-142">To turn on Teams for the organization use the license picker and select each license then set the toggle to **On** and then click **Save**.</span></span>

    ![Captura de tela da página de configurações do Microsoft Teams mostrando o botão de alternância como Habilitado para habilitar o Microsoft Teams.](media/Services-and-addins-control-Microsoft-Teams.PNG)
