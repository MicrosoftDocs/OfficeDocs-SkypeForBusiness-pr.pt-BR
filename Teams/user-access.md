---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: be2e95d7be359856d5aef4f67664ef27ee62fa74
ms.sourcegitcommit: c0679cbaf7df38769f722afd65c4232311d25515
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/26/2019
ms.locfileid: "29562609"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="be1f6-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="be1f6-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="be1f6-104">No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário por como atribuir ou remover a licença do produto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="be1f6-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="be1f6-105">Atualmente, não existem opções para equipes ou um subconjunto dos recursos de equipes, ativando ou desativando em um nível de usuário individual fora do licenciamento por política.</span><span class="sxs-lookup"><span data-stu-id="be1f6-105">Currently, there are no policy options for turning Teams, or a subset of Teams features, on or off at an individual user level outside of licensing.</span></span>

> [!NOTE]
><span data-ttu-id="be1f6-106">A Microsoft recomenda que você ativar equipes para todos os usuários em uma empresa para que as equipes podem ser formadas organicamente para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="be1f6-106">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="be1f6-107">Mesmo se você decidir para piloto, ainda será útil manter equipes habilitadas para todos os usuários, mas apenas as comunicações para o grupo piloto de usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="be1f6-107">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="be1f6-108">Gerenciar equipes por meio do Centro de administração do Office 365</span><span class="sxs-lookup"><span data-stu-id="be1f6-108">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="be1f6-109">As equipes licenças de nível de usuário são gerenciadas diretamente por meio das interfaces de gerenciamento de usuário do Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="be1f6-109">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="be1f6-110">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="be1f6-110">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="be1f6-111">O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="be1f6-111">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="be1f6-112">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="be1f6-112">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="be1f6-113">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="be1f6-113">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="be1f6-115">Uma licença de usuário de equipes pode estar desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="be1f6-115">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="be1f6-116">Depois que a licença é desabilitada, não poderá fazer o acesso de usuários a Microsoft Teams e o usuário não terá mais conseguirá ver equipes na home page e iniciador de aplicativo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="be1f6-116">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="be1f6-118">Gerenciar via PowerShell</span><span class="sxs-lookup"><span data-stu-id="be1f6-118">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="be1f6-119">New-MsolLicenseOptions permitirá que todos os serviços que foram desabilitados anteriormente, a menos que explictitly identitied em seu script personalizada.</span><span class="sxs-lookup"><span data-stu-id="be1f6-119">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="be1f6-120">Por exemplo, se você quisesse deixar os dois & Exchange Sway desabilitado enquanto Além disso, desabilitando equipes, você precisaria inclua isso no script ou ambos os & Exchange Sway será ficado habilitado para os usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="be1f6-120">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="be1f6-121">Se quiser utilizar uma interface gráfica do usuário para gerenciar essa funcionalidade, consulte: [ferramenta de gerenciamento e relatório de licença do Office 365-atribuir remover licenças em massa](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="be1f6-121">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="be1f6-122">A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="be1f6-122">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="be1f6-123">O nome do plano de serviço é TEAMS1 for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="be1f6-123">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="be1f6-124">Para o governo, o nome do plano de serviço é TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="be1f6-124">For Government the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="be1f6-125">(Consulte mais informações em [Desabilitar o acesso aos serviços com o PowerShell do Office 365](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell).)</span><span class="sxs-lookup"><span data-stu-id="be1f6-125">(See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="be1f6-126">**Exemplo:** A seguir é apenas uma amostra rápida sobre como você faria desabilitar equipes para todas as pessoas em um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="be1f6-126">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="be1f6-127">Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.</span><span class="sxs-lookup"><span data-stu-id="be1f6-127">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="be1f6-128">Para exibir os tipos de assinatura que você tem na organização, use este comando:</span><span class="sxs-lookup"><span data-stu-id="be1f6-128">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="be1f6-129">Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="be1f6-129">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="be1f6-130">Para desabilitar as equipes de todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="be1f6-130">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="be1f6-132">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="be1f6-132">Decision Point</span></span>         |<ul><li><span data-ttu-id="be1f6-133">O que é o planejamento da sua organização para inclusão de equipes em toda a organização?</span><span class="sxs-lookup"><span data-stu-id="be1f6-133">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="be1f6-134">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="be1f6-134">(Pilot or Open)</span></span></li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="be1f6-136">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="be1f6-136">Next Steps</span></span>         |<ul><li><span data-ttu-id="be1f6-137">Se a inclusão por meio de um piloto fechado, decida se você gostaria de fazê-lo por meio de licenciamento ou destinadas a comunicação.</span><span class="sxs-lookup"><span data-stu-id="be1f6-137">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="be1f6-138">Dependendo de decisão, siga as etapas para certificar-se testar apenas usuários que têm permissão para acessar as equipes (se necessário).</span><span class="sxs-lookup"><span data-stu-id="be1f6-138">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="be1f6-139">Documente as diretrizes para quais usuários que serão (ou não) têm acesso às equipes.</span><span class="sxs-lookup"><span data-stu-id="be1f6-139">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="be1f6-140">Gerenciar equipes a nível de locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="be1f6-140">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

