---
title: Atribuir licenças de Complementos do teams aos usuários
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Saiba como atribuir licenças de Complementos do teams a usuários para recursos como videoconferência, sistema telefônico e planos de chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5dd09ae11104aa0297a12417d4c267edfc17cf3f
ms.sourcegitcommit: d1e4e1105d86745009cf0fdf42d1fc5ad545a952
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46788735"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="76ba3-103">Atribuir licenças de Complementos do teams aos usuários</span><span class="sxs-lookup"><span data-stu-id="76ba3-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="76ba3-104">As licenças de complemento são licenças para recursos específicos do Teams, como videoconferência, sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="76ba3-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="76ba3-105">Este artigo descreve como atribuir licenças de Complementos a usuários individuais e a grandes conjuntos de usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="76ba3-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="76ba3-106">Consulte [Licenciamento do complemento do teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) para recursos do teams que estão disponíveis com licenças complementares.</span><span class="sxs-lookup"><span data-stu-id="76ba3-106">See [Teams add-on licensing](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="76ba3-107">Você também encontrará informações sobre quais licenças precisa comprar e como comprá-las (dependendo do seu plano), para que os usuários possam obter recursos como videoconferências, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="76ba3-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="76ba3-108">Depois de decidir quais recursos você deseja para seus usuários, atribua as licenças a eles.</span><span class="sxs-lookup"><span data-stu-id="76ba3-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="76ba3-109">Você pode usar o centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="76ba3-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="76ba3-110">Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.</span><span class="sxs-lookup"><span data-stu-id="76ba3-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="76ba3-111">O que você precisa saber antes de atribuir licenças de um sistema telefônico, plano de chamada e créditos de comunicação</span><span class="sxs-lookup"><span data-stu-id="76ba3-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="76ba3-112">Antes de começar, revise o seguinte:</span><span class="sxs-lookup"><span data-stu-id="76ba3-112">Before you get started, review the following:</span></span>

- <span data-ttu-id="76ba3-113">Se você estiver usando a conectividade PSTN (rede telefônica pública comutada) para usuários híbridos, só precisará atribuir uma licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="76ba3-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="76ba3-114">Não atribua uma licença de plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="76ba3-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="76ba3-115">Devido à latência entre o Microsoft 365 e o Microsoft Teams, pode levar até 24 horas para que um usuário receba um plano de chamada após a atribuição de uma licença.</span><span class="sxs-lookup"><span data-stu-id="76ba3-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="76ba3-116">Se o usuário não estiver atribuído a um plano de chamadas depois de 24 horas, [entre em contato com o suporte para produtos empresariais-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="76ba3-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="76ba3-117">Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="76ba3-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="76ba3-118">Se precisar comprar mais licenças do plano de chamadas, escolha a opção de comprar mais.</span><span class="sxs-lookup"><span data-stu-id="76ba3-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="76ba3-119">Mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, você ainda precisa atribuir licenças de [créditos de comunicações](../what-are-communications-credits.md) a eles se quiser fazer ou receber chamadas da PSTN.</span><span class="sxs-lookup"><span data-stu-id="76ba3-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="76ba3-120">Depois de atribuir licenças de plano de chamada ou de crédito de comunicação aos usuários, você precisará obter números de telefone para sua organização e atribuir esses números aos usuários.</span><span class="sxs-lookup"><span data-stu-id="76ba3-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="76ba3-121">Para obter instruções passo a passo, consulte [configurar planos de chamada](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="76ba3-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="76ba3-122">Usar o centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="76ba3-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="76ba3-123">Use o centro de administração do Microsoft 365 para atribuir licenças para usuários individuais ou pequenos conjuntos de usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="76ba3-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="76ba3-124">Você pode atribuir licenças na página **licenças** (para até 20 usuários de uma vez) ou para a página **usuários ativos** .</span><span class="sxs-lookup"><span data-stu-id="76ba3-124">You can assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page.</span></span> <span data-ttu-id="76ba3-125">O método escolhido depende se você deseja gerenciar licenças de produto para usuários específicos ou gerenciar licenças de usuário para produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="76ba3-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="76ba3-126">Para obter instruções passo a passo, consulte [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="76ba3-126">For step-by-step instructions, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="76ba3-127">Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o PowerShell ou o [Licenciamento baseado em grupo no Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="76ba3-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="76ba3-128">Usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ba3-128">Using PowerShell</span></span>

<span data-ttu-id="76ba3-129">Use o PowerShell para atribuir licenças a usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="76ba3-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="76ba3-130">Para saber mais, confira [atribuir licenças a contas de usuário com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="76ba3-130">To learn more, see [Assign licenses to user accounts with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="76ba3-131">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="76ba3-131">Example script</span></span>

<span data-ttu-id="76ba3-132">Veja um exemplo de como usar um script para atribuir licenças aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="76ba3-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="76ba3-133">Instale a versão de 64 bits do [Assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span><span class="sxs-lookup"><span data-stu-id="76ba3-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).</span></span>
2. <span data-ttu-id="76ba3-134">Instale o módulo do Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="76ba3-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="76ba3-135">Abra um prompt de comando do Windows PowerShell elevado (execute o Windows PowerShell como um administrador).</span><span class="sxs-lookup"><span data-stu-id="76ba3-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="76ba3-136">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="76ba3-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="76ba3-137">Se você for solicitado a instalar o provedor de NuGet, digite **Y**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="76ba3-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="76ba3-138">Se for solicitado a instalar o módulo do PSGallery, digite **Y**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="76ba3-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="76ba3-139">No prompt de comando do Windows PowerShell, execute o seguinte script para atribuir licenças aos seus usuários, onde \<CompanyName:License> é o nome da sua organização e o identificador da licença que você deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="76ba3-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="76ba3-140">Por exemplo, litwareinc: MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="76ba3-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="76ba3-141">O identificador é diferente do nome amigável da licença.</span><span class="sxs-lookup"><span data-stu-id="76ba3-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="76ba3-142">Por exemplo, o identificador do áudio videoconferência é MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="76ba3-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="76ba3-143">Para saber mais, consulte [nomes de produtos e identificadores de SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="76ba3-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
    #user1@domain.com
    #user2@domain.com

    #Import Module
    ipmo MSOnline

    #Authenticate to MSOLservice
    Connect-MSOLService
    #File prompt to select the userlist txt file
    [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
      $OFD = New-Object System.Windows.Forms.OpenFileDialog
      $OFD.filter = "text files (*.*)| *.txt"
      $OFD.ShowDialog() | Out-Null
      $OFD.filename

    If ($OFD.filename -eq '')
    {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
    }

    #Create a variable of all users
    $users = Get-Content $OFD.filename

    #License each user in the $users variable
    foreach ($user in $users)
        {
        Write-host "Assigning License: $user"
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    <span data-ttu-id="76ba3-144">Por exemplo, para atribuir licenças do Microsoft 365 Enterprise 1 e do áudio referencing, use a seguinte sintaxe no script:</span><span class="sxs-lookup"><span data-stu-id="76ba3-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="76ba3-145">Para atribuir uma licença do Microsoft Business Voice (sem plano de chamada), use a seguinte sintaxe no script:</span><span class="sxs-lookup"><span data-stu-id="76ba3-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="76ba3-146">Nomes de produtos e identificadores de SKU para licenciamento</span><span class="sxs-lookup"><span data-stu-id="76ba3-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="76ba3-147">Aqui está uma lista parcial de nomes de produto e seus nomes de partes de SKU correspondentes que você pode usar como referência ao usar o PowerShell para gerenciar licenças no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="76ba3-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="76ba3-148">Para saber mais, consulte [Exibir licenças e serviços com o PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [nomes de produto e identificadores de plano de serviço para licenciamento](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)e [referência de SKU educacional](../sku-reference-edu.md).</span><span class="sxs-lookup"><span data-stu-id="76ba3-148">To learn more, see [View licenses and services with PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="76ba3-149">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="76ba3-149">Product name</span></span>| <span data-ttu-id="76ba3-150">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="76ba3-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="76ba3-151">Microsoft Enterprise E5 (com sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="76ba3-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="76ba3-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="76ba3-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="76ba3-153">Microsoft Enterprise E5 (sem conferência de áudio)</span><span class="sxs-lookup"><span data-stu-id="76ba3-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="76ba3-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="76ba3-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="76ba3-155">Microsoft Enterprise E5 (com conferência de áudio)</span><span class="sxs-lookup"><span data-stu-id="76ba3-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="76ba3-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="76ba3-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="76ba3-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="76ba3-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="76ba3-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="76ba3-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="76ba3-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="76ba3-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="76ba3-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="76ba3-160">STANDARDPACK</span></span> |
| <span data-ttu-id="76ba3-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="76ba3-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="76ba3-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="76ba3-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="76ba3-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="76ba3-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="76ba3-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="76ba3-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="76ba3-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="76ba3-165">Microsoft 365 Business</span></span> | <span data-ttu-id="76ba3-166">SP</span><span class="sxs-lookup"><span data-stu-id="76ba3-166">SPB</span></span>|
| <span data-ttu-id="76ba3-167">Microsoft Business Voice (Canadá)</span><span class="sxs-lookup"><span data-stu-id="76ba3-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="76ba3-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="76ba3-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="76ba3-169">Microsoft Business Voice (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="76ba3-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="76ba3-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="76ba3-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="76ba3-171">Microsoft Business Voice (Estados Unidos)</span><span class="sxs-lookup"><span data-stu-id="76ba3-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="76ba3-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="76ba3-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="76ba3-173">Microsoft Business Voice (sem plano de chamada)</span><span class="sxs-lookup"><span data-stu-id="76ba3-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="76ba3-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="76ba3-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="76ba3-175">Microsoft Business Voice (sem plano de chamada) para os Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="76ba3-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="76ba3-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="76ba3-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="76ba3-177">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="76ba3-177">Audio Conferencing</span></span> | <span data-ttu-id="76ba3-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="76ba3-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="76ba3-179">Áudio conferência paga por minuto (pré-pago)</span><span class="sxs-lookup"><span data-stu-id="76ba3-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="76ba3-180">*Requer que os créditos de comunicações sejam configurados e habilitados.*</span><span class="sxs-lookup"><span data-stu-id="76ba3-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="76ba3-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="76ba3-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="76ba3-182">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="76ba3-182">Phone System</span></span> | <span data-ttu-id="76ba3-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="76ba3-183">MCOEV</span></span> |
| <span data-ttu-id="76ba3-184">Plano de chamadas domésticas e internacionais</span><span class="sxs-lookup"><span data-stu-id="76ba3-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="76ba3-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="76ba3-185">MCOPSTN2</span></span> |
| <span data-ttu-id="76ba3-186">Plano de chamadas domésticas (3000 minutos por usuário/mês para EUA/PR/CA, 1200 minutos por usuário/mês para países da UE)</span><span class="sxs-lookup"><span data-stu-id="76ba3-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="76ba3-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="76ba3-187">MCOPSTN1</span></span> |
| <span data-ttu-id="76ba3-188">Plano de chamadas domésticas (120 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="76ba3-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="76ba3-189">*Este plano não está disponível nos Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="76ba3-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="76ba3-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="76ba3-190">MCOPSTN5</span></span> |
| <span data-ttu-id="76ba3-191">Plano de chamadas domésticas (240 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="76ba3-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="76ba3-192">*Este plano não está disponível nos Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="76ba3-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="76ba3-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="76ba3-193">MCOPSTN6</span></span> |
| <span data-ttu-id="76ba3-194">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="76ba3-194">Communications Credits</span></span> | <span data-ttu-id="76ba3-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="76ba3-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="76ba3-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="76ba3-196">Related topics</span></span>

- [<span data-ttu-id="76ba3-197">Licenciamento do complemento do Teams</span><span class="sxs-lookup"><span data-stu-id="76ba3-197">Teams add-on licensing</span></span>](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [<span data-ttu-id="76ba3-198">Gerenciamento do acesso de usuários ao Teams</span><span class="sxs-lookup"><span data-stu-id="76ba3-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="76ba3-199">Exibir licenças e serviços com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="76ba3-199">View licenses and services with PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="76ba3-200">Nomes de produtos e identificadores de plano de serviço para licenciamento</span><span class="sxs-lookup"><span data-stu-id="76ba3-200">Product names and service plan identifiers for licensing</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="76ba3-201">Referência de SKU do Education</span><span class="sxs-lookup"><span data-stu-id="76ba3-201">Education SKU reference</span></span>](../sku-reference-edu.md)