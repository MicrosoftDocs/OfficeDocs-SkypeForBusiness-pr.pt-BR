---
title: Gerenciamento do acesso de usuários ao Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/12/2018
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.reviewer: ritikag
search.appverid: MET150
description: Saiba como habilitar ou desabilitar o acesso em nível de usuário para cada usuário, atribuindo ou removendo a licença de produto do Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 823038671ac03669808e8a3dec5d065a60682b19
ms.sourcegitcommit: 929c050c038a64216e38b0a67569a8f18ad4baf2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43940608"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="b2a5b-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2a5b-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="b2a5b-104">No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado para cada usuário, atribuindo ou removendo a licença de produto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="b2a5b-105">Use políticas de mensagens, gerenciadas a partir do centro de administração do Teams, para controlar quais recursos de chat e mensagens de canal estão disponíveis para os usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="b2a5b-106">Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="b2a5b-107">Para saber mais, leia [gerenciar políticas de mensagens no Microsoft Teams](messaging-policies-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="b2a5b-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="b2a5b-108">A Microsoft recomenda que você ative o Teams para todos os usuários de uma empresa para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="b2a5b-109">Mesmo que você esteja decidindo para o piloto, talvez ainda seja útil manter o Microsoft Teams habilitado para todos os usuários, mas somente as comunicações são direcionadas para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="b2a5b-110">Gerenciar equipes por meio do centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="b2a5b-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="b2a5b-111">As licenças de nível de usuário do Team são gerenciadas diretamente por meio das interfaces de gerenciamento de usuários do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="b2a5b-112">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="b2a5b-113">O administrador deve ter privilégios de administrador global ou administrador de gerenciamento de usuários para gerenciar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-113">The administrator must have Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="b2a5b-114">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="b2a5b-115">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção licenças de produto no centro de administração.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="b2a5b-117">Uma licença de usuário do teams pode ser desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="b2a5b-118">Depois que a licença estiver desabilitada, o acesso dos usuários ao Microsoft Teams será impedido e o usuário não poderá mais ver as equipes no inicializador de aplicativos e na página inicial do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela mostrando as equipes selecionadas na seção licenças de produto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="b2a5b-120">Gerenciar via PowerShell</span><span class="sxs-lookup"><span data-stu-id="b2a5b-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2a5b-121">New-MsolLicenseOptions habilitará todos os serviços que foram desabilitados anteriormente, a menos que explicitamente identificados em seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explicitly identified in your customized script.</span></span> <span data-ttu-id="b2a5b-122">Como exemplo, se você quisesse deixar o Sway do Exchange & desabilitado, além de desabilitar o Microsoft Teams, você precisará incluí-lo no script ou ambos & o Sway será habilitado para os usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-122">As an example, if you wanted to leave both Exchange & Sway disabled while additionally disabling Teams, you'd need to include this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span>

<span data-ttu-id="b2a5b-123">A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-123">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="b2a5b-124">O nome do plano de serviço é TEAMS1 for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-124">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="b2a5b-125">Para o GCC, o nome do plano de serviço é TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-125">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="b2a5b-126">Para GCC alto, o nome do plano de serviço é TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-126">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="b2a5b-127">Para DoD, o nome do plano de serviço é TEAMS_DOD (consulte [desabilitar o acesso aos serviços com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="b2a5b-127">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="b2a5b-128">**Exemplo:** Veja a seguir um exemplo rápido sobre como você desabilitaria o Teams para todos em um determinado tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-128">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="b2a5b-129">Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-129">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="b2a5b-130">Para exibir os tipos de assinatura que você tem na organização, use este comando:</span><span class="sxs-lookup"><span data-stu-id="b2a5b-130">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="b2a5b-131">Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="b2a5b-131">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="b2a5b-132">Para desabilitar o Microsoft Teams para todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b2a5b-132">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="b2a5b-134">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="b2a5b-134">Decision Point</span></span>         |<ul><li><span data-ttu-id="b2a5b-135">Qual é o plano da sua organização para o enquadro de equipes em toda a organização?</span><span class="sxs-lookup"><span data-stu-id="b2a5b-135">What is your organization's plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="b2a5b-136">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="b2a5b-136">(Pilot or Open)</span></span></li></ul>         |
|![Um ícone que representa as próximas etapas](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="b2a5b-138">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="b2a5b-138">Next Steps</span></span>         |<ul><li><span data-ttu-id="b2a5b-139">Se estiver integração por meio de um piloto fechado, decida se deseja fazer isso por meio de licenciamento ou comunicação direcionada.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-139">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="b2a5b-140">Dependendo da decisão, siga as etapas para garantir que somente os usuários pilotos que têm permissão para acessar o Microsoft Teams (se necessário).</span><span class="sxs-lookup"><span data-stu-id="b2a5b-140">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="b2a5b-141">Documentar as diretrizes para as quais os usuários que (ou não terão) terão acesso ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2a5b-141">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-organization-level"></a><span data-ttu-id="b2a5b-142">Gerenciar equipes no nível da organização do Office 365</span><span class="sxs-lookup"><span data-stu-id="b2a5b-142">Manage Teams at the Office 365 organization level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

