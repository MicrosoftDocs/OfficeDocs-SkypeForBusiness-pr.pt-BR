---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83d2b0710b811431546f0df9931d3a0b867d2b2b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205828"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="7d9ad-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7d9ad-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7d9ad-104">No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário por como atribuir ou remover a licença do produto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="7d9ad-105">Use políticas de mensagens, gerenciadas do Centro de administração de equipes, para controlar quais chat e os recursos de mensagens de canal estão disponíveis aos usuários em equipes.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="7d9ad-106">Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="7d9ad-107">Para saber mais, leia as [políticas de gerenciar mensagens em equipes](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="7d9ad-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="7d9ad-108">A Microsoft recomenda que você ativar equipes para todos os usuários em uma empresa para que as equipes podem ser formadas organicamente para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="7d9ad-109">Mesmo se você decidir para piloto, ainda será útil manter equipes habilitadas para todos os usuários, mas apenas as comunicações para o grupo piloto de usuários de destino.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-office-365-admin-center"></a><span data-ttu-id="7d9ad-110">Gerenciar equipes por meio do Centro de administração do Office 365</span><span class="sxs-lookup"><span data-stu-id="7d9ad-110">Manage Teams through the Office 365 admin center</span></span>

<span data-ttu-id="7d9ad-111">As equipes licenças de nível de usuário são gerenciadas diretamente por meio das interfaces de gerenciamento de usuário do Office 365 admin center.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-111">Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="7d9ad-112">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="7d9ad-113">O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="7d9ad-114">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="7d9ad-115">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="7d9ad-117">Uma licença de usuário de equipes pode estar desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="7d9ad-118">Depois que a licença é desabilitada, não poderá fazer o acesso de usuários a Microsoft Teams e o usuário não terá mais conseguirá ver equipes na home page e iniciador de aplicativo do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="7d9ad-120">Gerenciar via PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d9ad-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7d9ad-121">New-MsolLicenseOptions permitirá que todos os serviços que foram desabilitados anteriormente, a menos que explictitly identitied em seu script personalizada.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="7d9ad-122">Por exemplo, se você quisesse deixar os dois & Exchange Sway desabilitado enquanto Além disso, desabilitando equipes, você precisaria inclua isso no script ou ambos os & Exchange Sway será ficado habilitado para os usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="7d9ad-123">Se quiser utilizar uma interface gráfica do usuário para gerenciar essa funcionalidade, consulte: [ferramenta de gerenciamento e relatório de licença do Office 365-atribuir remover licenças em massa](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="7d9ad-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="7d9ad-124">A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="7d9ad-125">O nome do plano de serviço é TEAMS1 for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="7d9ad-126">Para GCC o nome do plano de serviço é TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="7d9ad-127">Para alta GCC o nome do plano de serviço é TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="7d9ad-128">Para DoD o nome do plano de serviço é TEAMS_DOD (consulte [Desabilitar o acesso a serviços com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="7d9ad-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="7d9ad-129">**Exemplo:** A seguir é apenas uma amostra rápida sobre como você faria desabilitar equipes para todas as pessoas em um tipo de licença específico.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="7d9ad-130">Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="7d9ad-131">Para exibir os tipos de assinatura que você tem na organização, use este comando:</span><span class="sxs-lookup"><span data-stu-id="7d9ad-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="7d9ad-132">Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="7d9ad-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="7d9ad-133">Para desabilitar as equipes de todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7d9ad-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="7d9ad-135">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="7d9ad-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="7d9ad-136">O que é o planejamento da sua organização para inclusão de equipes em toda a organização?</span><span class="sxs-lookup"><span data-stu-id="7d9ad-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="7d9ad-137">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="7d9ad-137">(Pilot or Open)</span></span></li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="7d9ad-139">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="7d9ad-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="7d9ad-140">Se a inclusão por meio de um piloto fechado, decida se você gostaria de fazê-lo por meio de licenciamento ou destinadas a comunicação.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="7d9ad-141">Dependendo de decisão, siga as etapas para certificar-se testar apenas usuários que têm permissão para acessar as equipes (se necessário).</span><span class="sxs-lookup"><span data-stu-id="7d9ad-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="7d9ad-142">Documente as diretrizes para quais usuários que serão (ou não) têm acesso às equipes.</span><span class="sxs-lookup"><span data-stu-id="7d9ad-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="7d9ad-143">Gerenciar equipes a nível de locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="7d9ad-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

