---
title: "Gerenciamento do acesso de usuários ao Microsoft Teams | Suporte da Microsoft"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Saiba como habilitar ou desabilitar o acesso em nível de usuário na base por usuário."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 252dfa4c739fddd152c54a38dff71255706bb1ef
ms.sourcegitcommit: 9756856140ea56a94e986c134c5c04e53e5c0fa6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2017
---
<a name="manage-user-access-to-microsoft-teams"></a><span data-ttu-id="056f5-103">Gerenciamento do acesso de usuários ao Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="056f5-103">Manage user access to Microsoft Teams</span></span>
=====================================

<span data-ttu-id="056f5-104">Em nível de usuário, o acesso ao Microsoft Teams pode ser habilitado ou desabilitado em uma base por usuário, com a atribuição ou remoção da licença do produto Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="056f5-104">At the user-level, access to Microsoft Teams can be enabled of disabled on a per-user basis by assigning or removing the Microsoft Teams product license.</span></span>

<span data-ttu-id="056f5-105">No momento, não há opções de políticas, além da licença, para tornar o Microsoft Teams, ou um subconjunto de recursos do Microsoft Teams, habilitado ou desabilitado para usuários individualmente.</span><span class="sxs-lookup"><span data-stu-id="056f5-105">Currently, there are no policy options for turning Microsoft Teams, or a subset of Microsoft Teams features on or off at an individual user level outside of licensing.</span></span>

| | |
|---------|---------|
|![Ícone de nota.](media/Manage_user_access_to_Microsoft_Teams_image1.png)<br></br><span data-ttu-id="056f5-107">Nota</span><span class="sxs-lookup"><span data-stu-id="056f5-107">Note</span></span> |<span data-ttu-id="056f5-108">A Microsoft recomenda que o Microsoft Teams seja habilitado para todos os usuários da empresa, para que as equipes possam ser formadas naturalmente para os projetos e outras iniciativas dinâmicas.</span><span class="sxs-lookup"><span data-stu-id="056f5-108">Microsoft recommends that Microsoft Teams is enabled for all users in a company so that teams can be formed organically for projects and other dynamic initiatives.</span></span> <span data-ttu-id="056f5-109">Mesmo que você esteja decidindo por um piloto, ainda pode ser útil manter o Microsoft Teams habilitado para todos os usuários, mas direcionar as comunicações apenas para o grupo piloto de usuários.</span><span class="sxs-lookup"><span data-stu-id="056f5-109">Even if you are deciding to pilot, it may still be helpful to keep Microsoft Teams enabled for all users, but only target communications to the pilot group of users.</span></span> |

<span data-ttu-id="056f5-110">As licenças em nível de usuário do Microsoft Teams são gerenciadas diretamente das interfaces de gerenciamento de usuários do Centro de Administração do Office 365.</span><span class="sxs-lookup"><span data-stu-id="056f5-110">Microsoft Teams user-level licenses are managed directly through the Office 365 admin center user management interfaces.</span></span> <span data-ttu-id="056f5-111">Um administrador pode atribuir licenças a novos usuários quando novas contas de usuário forem criadas ou a usuários com contas existentes.</span><span class="sxs-lookup"><span data-stu-id="056f5-111">An administrator can assign licenses to new users when new user accounts are created, or to users with existing accounts.</span></span> <span data-ttu-id="056f5-112">O administrador precisa ter privilégios do Administrador Global do Office 365 ou Administrador de Gerenciamento de Usuários para administrar as licenças do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="056f5-112">The administrator must have Office 365 Global Administrator or User Management Administrator privileges to manage Microsoft Teams licenses.</span></span>

<span data-ttu-id="056f5-113">Quando o SKU de uma licença, como E3 ou E5, for atribuído a um usuário, a licença do Microsoft Teams é atribuída automaticamente e o usuário fica habilitado para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="056f5-113">When a license SKU like E3 or E5 is assigned to a user, a Microsoft Teams license is automatically assigned, and the user is enabled for Microsoft Teams.</span></span> <span data-ttu-id="056f5-114">Os administradores podem ter um controle mais detalhado sobre todos os serviços e licenças do Office 365, e a licença do Microsoft Teams para um usuário específico ou um grupo de usuários pode ser habilitada ou desabilitada.</span><span class="sxs-lookup"><span data-stu-id="056f5-114">Administrators can have a granular control over all the Office 365 services and licenses, and the Microsoft Teams license for a specific user or a group of users can be enabled or disabled.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365.](media/Manage_user_access_to_Microsoft_Teams_image2.png) 

<span data-ttu-id="056f5-116">A licença do Microsoft Teams de um usuário pode ser desabilitada a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="056f5-116">A Microsoft Teams user license can be disabled at any time.</span></span> <span data-ttu-id="056f5-117">Após a licença ser desabilitada, o acesso do usuário ao Microsoft Teams será impedido e ele não poderá mais visualizar o Microsoft Teams na página inicial nem no inicializador do aplicativo Office 365.</span><span class="sxs-lookup"><span data-stu-id="056f5-117">Once the license is disabled, the users access to Microsoft Teams will be prevented and the user will no longer be able to see Microsoft Teams in the Office 365 app launcher and homepage.</span></span>

![Captura de tela da seção de licenças de produto no centro de administração do Office 365, mostrando o Microsoft Teams selecionado.](media/Manage_user_access_to_Microsoft_Teams_image4.png)

<span data-ttu-id="056f5-119">Além de usar o Centro de Administração do Office 365, os administradores do Office 365 também podem usar o Office 365 PowerShell para atribuir e remover licenças.</span><span class="sxs-lookup"><span data-stu-id="056f5-119">In addition to using the Office 365 admin center, Office 365 admins can also use Office 365 PowerShell to assign and remove licenses.</span></span> <span data-ttu-id="056f5-120">Para atribuir uma licença a um usuário, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="056f5-120">To assign a license to a user, use the following syntax:</span></span>

<span data-ttu-id="056f5-121">Set-MsolUserLicense -UserPrincipalName “\<Account\>” -AddLicenses “\<AccountSkuId\>”</span><span class="sxs-lookup"><span data-stu-id="056f5-121">Set-MsolUserLicense -UserPrincipalName "\<Account\>" -AddLicenses "\<AccountSkuId\>"</span></span>

<span data-ttu-id="056f5-122">O exemplo a seguir atribui uma licença a partir do plano de licença litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) para o usuário não licenciado belindan@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="056f5-122">The following example assigns a license from the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan to the unlicensed user belindan@litwareinc.com.</span></span>

<span data-ttu-id="056f5-123">Set-MsolUserLicense -UserPrincipalName “belindan@litwareinc.com” -AddLicenses “litwareinc:ENTERPRISEPACK”</span><span class="sxs-lookup"><span data-stu-id="056f5-123">Set-MsolUserLicense -UserPrincipalName "belindan@litwareinc.com" -AddLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="056f5-124">Para obter mais exemplos e detalhes, veja [*Atribuir licenças a contas de usuários do Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span><span class="sxs-lookup"><span data-stu-id="056f5-124">For more details and examples, see [*Assign licenses to user accounts with Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855755).</span></span>

<span data-ttu-id="056f5-125">Para remover a licença de uma conta de usuário existente, use a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="056f5-125">To remove licenses from an existing user account, use the following syntax:</span></span>

<span data-ttu-id="056f5-126">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses “\<AccountSkuId1\>”, “\<AccountSkuId2\>”</span><span class="sxs-lookup"><span data-stu-id="056f5-126">Set-MsolUserLicense -UserPrincipalName \<Account\> -RemoveLicenses "\<AccountSkuId1\>", "\<AccountSkuId2\>"</span></span>

<span data-ttu-id="056f5-127">O exemplo a seguir remove a licença a partir do plano de licença litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) da conta de usuário BelindaN@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="056f5-127">The following example removes the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) license from the user account BelindaN@litwareinc.com.</span></span>

<span data-ttu-id="056f5-128">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses “litwareinc:ENTERPRISEPACK”</span><span class="sxs-lookup"><span data-stu-id="056f5-128">Set-MsolUserLicense -UserPrincipalName belindan@litwareinc.com -RemoveLicenses "litwareinc:ENTERPRISEPACK"</span></span>

<span data-ttu-id="056f5-129">Para obter mais exemplos e detalhes, veja [*Remover licenças de contas de usuários do Office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span><span class="sxs-lookup"><span data-stu-id="056f5-129">For more details and examples, see [*Remove licenses from user accounts with office 365 PowerShell*](https://go.microsoft.com/fwlink/?linkid=855756).</span></span>

| | | |
|---------|---------|---------|
|![Ícone de ponto de decisão.](media/Manage_user_access_to_Microsoft_Teams_image5.png)     |<span data-ttu-id="056f5-131">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="056f5-131">Decision Point</span></span>         |<ul><li><span data-ttu-id="056f5-132">Qual é o plano de integração do Microsoft Teams na sua empresa?</span><span class="sxs-lookup"><span data-stu-id="056f5-132">What is your organization’s plan for Microsoft Teams onboarding across the organization?</span></span>  <span data-ttu-id="056f5-133">(Piloto ou Aberto)</span><span class="sxs-lookup"><span data-stu-id="056f5-133">(Pilot or Open)</span></span></li></ul>         |
|![Ícone de próximos passos.](media/Manage_user_access_to_Microsoft_Teams_image6.png)     |<span data-ttu-id="056f5-135">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="056f5-135">Next Steps</span></span>         |<ul><li><span data-ttu-id="056f5-136">Se for iniciar via piloto fechado, decida se deseja fazê-lo através de licenciamento ou comunicação direcionada.</span><span class="sxs-lookup"><span data-stu-id="056f5-136">If onboarding via a closed Pilot, decide if you would like to do so via licensing, or targetted communication.</span></span></li><li><span data-ttu-id="056f5-137">Dependendo da decisão, tome medidas para se certificar de que apenas os usuários do Piloto tenham permissão para acessar o Microsoft Teams (se necessário).</span><span class="sxs-lookup"><span data-stu-id="056f5-137">Depending on decision, take steps to make sure only Pilot users who are allowed to access Microsoft Teams (if needed).</span></span></li><li><span data-ttu-id="056f5-138">Documente abaixo as diretrizes de acordo com as quais os usuários terão (ou não) acesso ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="056f5-138">Document the guidelines for which users who will (or will not) have access to Microsoft Teams below.</span></span></li></ul>         |
