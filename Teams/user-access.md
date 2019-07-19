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
ms.openlocfilehash: 0858373bebabdb9df6c8a00463ac5a3db1834843
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792131"
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="7838a-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7838a-103">Manage user access to Microsoft Teams</span></span>
=====================================
> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="7838a-104">No nível do usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado para cada usuário, atribuindo ou removendo a licença de produto do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-104">At the user level, access to Microsoft Teams can be enabled or disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="7838a-105">Use políticas de mensagens, gerenciadas a partir do centro de administração do Teams, para controlar quais recursos de chat e mensagens de canal estão disponíveis para os usuários do teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-105">Use messaging policies, managed from the Teams Admin Center, to control what chat and channel messaging features are available to users in Teams.</span></span> <span data-ttu-id="7838a-106">Você pode usar a política padrão ou criar uma ou mais políticas de mensagens personalizadas para as pessoas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7838a-106">You can use the default policy or create one or more custom messaging policies for people in your organization.</span></span> <span data-ttu-id="7838a-107">Para saber mais, leia [gerenciar políticas de mensagens no](messaging-policies-in-teams.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-107">To learn more, read [Manage messaging policies in Teams](messaging-policies-in-teams.md).</span></span>

> [!NOTE]
><span data-ttu-id="7838a-108">A Microsoft recomenda que você ative o Teams para todos os usuários de uma empresa para que as equipes possam ser formadas de forma orgânica para projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="7838a-108">Microsoft recommends that you turn on Teams for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="7838a-109">Mesmo que você esteja decidindo para o piloto, talvez ainda seja útil manter o Microsoft Teams habilitado para todos os usuários, mas somente as comunicações são direcionadas para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="7838a-109">Even if you are deciding to pilot, it may still be helpful to keep Teams enabled for all users, but only target communications to the pilot group of users.</span></span>

## <a name="manage-teams-through-the-microsoft-365-admin-center"></a><span data-ttu-id="7838a-110">Gerenciar equipes por meio do centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7838a-110">Manage Teams through the Microsoft 365 admin center</span></span>

<span data-ttu-id="7838a-111">As licenças de nível de usuário do Team são gerenciadas diretamente por meio das interfaces de gerenciamento de usuários do centro de administração do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="7838a-111">Teams user-level licenses are managed directly through the Microsoft 365 admin center user management interfaces.</span></span> <span data-ttu-id="7838a-112">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="7838a-112">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="7838a-113">O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-113">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="7838a-114">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-114">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="7838a-115">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7838a-115">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção licenças de produto no centro de administração.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="7838a-117">Uma licença de usuário do teams pode ser desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="7838a-117">A Teams user license can be disabled at any time.</span></span> <span data-ttu-id="7838a-118">Depois que a licença estiver desabilitada, o acesso dos usuários ao Microsoft Teams será impedido e o usuário não poderá mais ver as equipes no inicializador de aplicativos e na página inicial do Office 365.</span><span class="sxs-lookup"><span data-stu-id="7838a-118">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela mostrando as equipes selecionadas na seção licenças de produto.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

## <a name="manage-via-powershell"></a><span data-ttu-id="7838a-120">Gerenciar via PowerShell</span><span class="sxs-lookup"><span data-stu-id="7838a-120">Manage via PowerShell</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7838a-121">New-MsolLicenseOptions habilitará todos os serviços que foram desabilitados anteriormente, a menos que explictitly identitied em seu script personalizado.</span><span class="sxs-lookup"><span data-stu-id="7838a-121">New-MsolLicenseOptions will enable all services that were previously disabled unless explictitly identitied in your customized script.</span></span> <span data-ttu-id="7838a-122">Como exemplo, se você quisesse deixar o & do Sway desabilitado durante a desativação do Microsoft Teams, você precisará inlcude-lo no script ou no Exchange & o Sway será habilitado para os usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="7838a-122">As an example, if you wanted to leave both Exchange & Sway disabled while additonally disabling Teams, you'd need to inlcude this in the script or both Exchange & Sway will become enabled for those users you've identified.</span></span> <span data-ttu-id="7838a-123">Se você quiser usar uma GUI para gerenciar essa funcionalidade, consulte: [ferramenta de relatório e gerenciamento de licenças do Office 365-atribuir licenças de remoção em massa](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span><span class="sxs-lookup"><span data-stu-id="7838a-123">If you wish to do utilize a GUI to manage this functionality, See: [Office 365 License Reporting and Management Tool -Assign Remove Licenses in Bulk](https://gallery.technet.microsoft.com/Office365-License-cfd9489c)</span></span>

<span data-ttu-id="7838a-124">A habilitação e desabilitação do Microsoft Teams como uma licença de carga de trabalho pelo PowerShell é realizada da mesma forma que com qualquer outra carga de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7838a-124">Enabling and disabling Teams as a workload license through PowerShell is done just as any other workload.</span></span> <span data-ttu-id="7838a-125">O nome do plano de serviço é TEAMS1 for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-125">The service plan name is TEAMS1 for Microsoft Teams.</span></span> <span data-ttu-id="7838a-126">Para o GCC, o nome do plano do serviço é TEAMS_GOV.</span><span class="sxs-lookup"><span data-stu-id="7838a-126">For GCC the service plan name is TEAMS_GOV.</span></span> <span data-ttu-id="7838a-127">Para GCC alto, o nome do plano de serviço é TEAMS_GCCHIGH.</span><span class="sxs-lookup"><span data-stu-id="7838a-127">For GCC High the service plan name is TEAMS_GCCHIGH.</span></span> <span data-ttu-id="7838a-128">Para DoD, o nome do plano de serviço é TEAMS_DOD (consulte [desabilitar o acesso aos serviços com o Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) para obter mais informações.)</span><span class="sxs-lookup"><span data-stu-id="7838a-128">For DoD the service plan name is TEAMS_DOD (See [Disable access to services with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/disable-access-to-services-with-office-365-powershell) for more information.)</span></span>

<span data-ttu-id="7838a-129">**Exemplo:** Veja a seguir um exemplo rápido sobre como você desabilitaria o Teams para todos em um determinado tipo de licença.</span><span class="sxs-lookup"><span data-stu-id="7838a-129">**Sample:** The following is just a quick sample on how you would disable Teams for everyone in a particular license type.</span></span> <span data-ttu-id="7838a-130">Você precisa fazer isso primeiro e depois habilitá-lo individualmente para os usuários que devem ter acesso para fins de piloto.</span><span class="sxs-lookup"><span data-stu-id="7838a-130">You'll need to do this first, then individually enable it for the users who should have access for piloting purposes.</span></span>

<span data-ttu-id="7838a-131">Para exibir os tipos de assinatura que você tem na organização, use este comando:</span><span class="sxs-lookup"><span data-stu-id="7838a-131">To display the subscription types you have within your organization, use the following command:</span></span>

      Get-MsolAccountSku

<span data-ttu-id="7838a-132">Preencha o nome do seu plano, quen inclui o nome da organização e o plano da escola (como ContosoSchool:ENTERPRISEPACK_STUDENT) e execute estes comandos:</span><span class="sxs-lookup"><span data-stu-id="7838a-132">Fill in the name of your plan that includes your organization name and the plan for your school (such as ContosoSchool:ENTERPRISEPACK_STUDENT), and then run the following commands:</span></span>

      $acctSKU="<plan name>
      $x = New-MsolLicenseOptions -AccountSkuId $acctSKU -DisabledPlans "TEAMS1"
<span data-ttu-id="7838a-133">Para desabilitar o Microsoft Teams para todos os usuários com uma licença ativa para o seu plano nomeado, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="7838a-133">To disable Teams for all users with an active license for your named plan, run the following command:</span></span>

      Get-MsolUser | Where-Object {$_.licenses[0].AccountSku.SkuPartNumber -eq  ($acctSKU).Substring($acctSKU.IndexOf(":")+1,  $acctSKU.Length-$acctSKU.IndexOf(":")-1) -and $_.IsLicensed -eq $True} |  Set-MsolUserLicense -LicenseOptions $x

| | | |
|---------|---------|---------|
|![Um ícone representando um ponto de decisão](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="7838a-135">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="7838a-135">Decision Point</span></span>         |<ul><li><span data-ttu-id="7838a-136">Qual é o plano da sua organização para o enquadro de equipes em toda a organização?</span><span class="sxs-lookup"><span data-stu-id="7838a-136">What is your organization’s plan for Teams onboarding across the organization?</span></span>  <span data-ttu-id="7838a-137">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="7838a-137">(Pilot or Open)</span></span></li></ul>         |
|![Um ícone que representa as próximas etapas](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="7838a-139">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="7838a-139">Next Steps</span></span>         |<ul><li><span data-ttu-id="7838a-140">Se estiver integração por meio de um piloto fechado, decida se deseja fazer isso por meio de licenciamento ou comunicação direcionada.</span><span class="sxs-lookup"><span data-stu-id="7838a-140">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targeted communication.</span></span></li><li><span data-ttu-id="7838a-141">Dependendo da decisão, siga as etapas para garantir que somente os usuários pilotos que têm permissão para acessar o Microsoft Teams (se necessário).</span><span class="sxs-lookup"><span data-stu-id="7838a-141">Depending on decision, take steps to make sure only Pilot users who are allowed to access Teams (if needed).</span></span></li><li><span data-ttu-id="7838a-142">Documentar as diretrizes para as quais os usuários que (ou não terão) terão acesso ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7838a-142">Document the guidelines for which users who will (or will not) have access to Teams.</span></span></li></ul>         |

## <a name="manage-teams-at-the-office-365-tenant-level"></a><span data-ttu-id="7838a-143">Gerenciar equipes no nível do locatário do Office 365</span><span class="sxs-lookup"><span data-stu-id="7838a-143">Manage Teams at the Office 365 tenant level</span></span>
[!INCLUDE [global-switch-expiry-note](includes/global-switch-expiry-note.md)]

