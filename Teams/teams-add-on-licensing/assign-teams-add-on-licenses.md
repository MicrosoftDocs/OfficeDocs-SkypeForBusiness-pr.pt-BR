---
title: Atribuir Teams licenças de complemento a usuários
author: cichur
ms.author: v-cichur
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
description: Saiba como atribuir Teams licenças de complemento aos usuários para recursos como Audioconferência, Sistema de Telefonia e Planos de Chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: b30df309412d159b878b4b57655787c9b4b292a8
ms.sourcegitcommit: 5c68298474d1782e69bde8c0940be7150cb93f6e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/23/2021
ms.locfileid: "53095575"
---
# <a name="assign-teams-add-on-licenses-to-users"></a><span data-ttu-id="07900-103">Atribuir Teams licenças de complemento a usuários</span><span class="sxs-lookup"><span data-stu-id="07900-103">Assign Teams add-on licenses to users</span></span>

<span data-ttu-id="07900-104">Licenças de complemento são licenças para recursos de Teams específicos, como Audioconferência, Sistema de Telefonia e Planos de Chamada.</span><span class="sxs-lookup"><span data-stu-id="07900-104">Add-on licenses are licenses for specific Teams features such as Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="07900-105">Este artigo descreve como atribuir licenças de complemento a usuários individuais e a grandes conjuntos de usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="07900-105">This article describes how to assign add-on licenses to individual users and to large sets of users in bulk.</span></span>

> [!NOTE]
> <span data-ttu-id="07900-106">Consulte [Teams de complemento](./microsoft-teams-add-on-licensing.md) para Teams recursos disponíveis com licenças de complemento.</span><span class="sxs-lookup"><span data-stu-id="07900-106">See [Teams add-on licensing](./microsoft-teams-add-on-licensing.md) for Teams features that are available with add-on licenses.</span></span> <span data-ttu-id="07900-107">Você também encontrará informações sobre quais licenças você precisa comprar e como comprá-las (dependendo do seu plano), para que os usuários possam obter recursos como Audioconferência, números de chamada gratuita e a capacidade de chamar números de telefone fora da sua organização.</span><span class="sxs-lookup"><span data-stu-id="07900-107">You'll also find information about what licenses you need to buy and how to buy them (depending on your plan), so users can get features such as Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your organization.</span></span> <span data-ttu-id="07900-108">Depois de decidir quais recursos você deseja para seus usuários, atribua as licenças a eles.</span><span class="sxs-lookup"><span data-stu-id="07900-108">After you decide  which features you want for your users, assign the licenses to them.</span></span>

<span data-ttu-id="07900-109">Você pode usar o Centro de administração do Microsoft 365 ou o PowerShell para atribuir licenças aos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="07900-109">You can use the Microsoft 365 admin center or PowerShell to assign licenses to users in your organization.</span></span> <span data-ttu-id="07900-110">Você deve ser um administrador global ou administrador de gerenciamento de usuários para gerenciar licenças.</span><span class="sxs-lookup"><span data-stu-id="07900-110">You must be a Global admin or User management admin to manage licenses.</span></span>

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a><span data-ttu-id="07900-111">O que você precisa saber antes de atribuir Sistema de Telefonia, Plano de Chamada e Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="07900-111">What you need to know before you assign Phone System, Calling Plan, and Communication Credits licenses</span></span>

<span data-ttu-id="07900-112">Antes de começar, revise os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="07900-112">Before you get started, review the following requirements:</span></span>

- <span data-ttu-id="07900-113">Se você estiver usando a conectividade PSTN (Rede Telefônica Pública Comutado) local para usuários híbridos, você só precisará atribuir uma licença Sistema de Telefonia local.</span><span class="sxs-lookup"><span data-stu-id="07900-113">If you're using on-premises Public Switched Telephone Network (PSTN) connectivity for hybrid users, you only need to assign a Phone System license.</span></span> <span data-ttu-id="07900-114">Não atribua uma licença de Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="07900-114">Do NOT assign a Calling Plan license.</span></span>

- <span data-ttu-id="07900-115">Devido à latência entre Microsoft 365 e Microsoft Teams, pode levar até 24 horas para que um usuário seja atribuído um Plano de Chamada depois de atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="07900-115">Because of the latency between Microsoft 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="07900-116">Se o usuário não tiver um Plano de Chamada após 24 horas, contate o suporte para produtos comerciais [- ajuda do administrador.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)</span><span class="sxs-lookup"><span data-stu-id="07900-116">If the user isn't assigned a Calling Plan after 24 hours, [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="07900-117">Você receberá uma mensagem de erro se não tiver comprado o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="07900-117">You'll get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="07900-118">Se você precisar comprar mais licenças do Plano de Chamada, escolha a opção para comprar mais.</span><span class="sxs-lookup"><span data-stu-id="07900-118">If you need to buy more Calling Plan licenses, choose the option to buy more.</span></span>

- <span data-ttu-id="07900-119">Mesmo que seus usuários sejam atribuídos Enterprise licenças do E5, você ainda precisará atribuir licenças de [Créditos](../what-are-communications-credits.md) de Comunicação a eles se eles quiserem fazer ou receber chamadas da PSTN.</span><span class="sxs-lookup"><span data-stu-id="07900-119">Even if your users are assigned Enterprise E5 licenses, you still need to assign [Communications Credits](../what-are-communications-credits.md) licenses to them if they want to make or receive calls from the PSTN.</span></span>

- <span data-ttu-id="07900-120">Depois de atribuir licenças de Plano de Chamadas ou Créditos de Comunicação aos usuários, você precisará obter números de telefone para sua organização e atribuir esses números aos usuários.</span><span class="sxs-lookup"><span data-stu-id="07900-120">After you assign Calling Plan or Communication Credits licenses to your users, you'll need to get phone numbers for your organization, and then assign those numbers to users.</span></span> <span data-ttu-id="07900-121">Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](../set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="07900-121">For step-by-step instructions, see [Set up Calling Plans](../set-up-calling-plans.md).</span></span>

## <a name="using-the-microsoft-365-admin-center"></a><span data-ttu-id="07900-122">Usando o Centro de administração do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="07900-122">Using the Microsoft 365 admin center</span></span>

<span data-ttu-id="07900-123">Use o Centro de administração do Microsoft 365 para atribuir licenças a usuários individuais ou pequenos conjuntos de usuários por vez.</span><span class="sxs-lookup"><span data-stu-id="07900-123">Use the Microsoft 365 admin center to assign licenses to individual users or small sets of users at a time.</span></span> <span data-ttu-id="07900-124">Você atribui licenças na página **Licenças** (para até 20  usuários por vez) ou na página Usuários ativos (para até 40 usuários por vez).</span><span class="sxs-lookup"><span data-stu-id="07900-124">You assign licenses on the **Licenses** page (for up to 20 users at a time) or the **Active users** page (for up to 40 users at a time).</span></span> <span data-ttu-id="07900-125">O método escolhido depende se você deseja gerenciar licenças de produtos para usuários específicos ou gerenciar licenças de usuário para produtos específicos.</span><span class="sxs-lookup"><span data-stu-id="07900-125">The method you choose depends on whether you want to manage product licenses for specific users or manage user licenses for specific products.</span></span>

<span data-ttu-id="07900-126">Para obter instruções passo a passo, consulte [Atribuir licenças aos usuários](/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="07900-126">For step-by-step instructions, see [Assign licenses to users](/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>

<span data-ttu-id="07900-127">Se você precisar atribuir licenças para um grande número de usuários, como centenas ou milhares de usuários, use o Powershell ou licenciamento baseado em grupo no [Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="07900-127">If you need to assign licenses for a large number of users, such as hundreds or thousands of users, use Powershell or [group-based licensing in Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span></span>  

## <a name="using-powershell"></a><span data-ttu-id="07900-128">Usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="07900-128">Using PowerShell</span></span>

<span data-ttu-id="07900-129">Use o PowerShell para atribuir licenças a usuários em massa.</span><span class="sxs-lookup"><span data-stu-id="07900-129">Use PowerShell to assign licenses to users in bulk.</span></span>  <span data-ttu-id="07900-130">Para saber mais, confira [Atribuir licenças a contas de usuário com o PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span><span class="sxs-lookup"><span data-stu-id="07900-130">To learn more, see [Assign licenses to user accounts with PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).</span></span>

### <a name="example-script"></a><span data-ttu-id="07900-131">Script de exemplo</span><span class="sxs-lookup"><span data-stu-id="07900-131">Example script</span></span>

<span data-ttu-id="07900-132">Veja um exemplo de como usar um script para atribuir licenças aos usuários.</span><span class="sxs-lookup"><span data-stu-id="07900-132">Here's an example of how to use a script to assign licenses to your users.</span></span>

1. <span data-ttu-id="07900-133">Instale a versão de 64 bits do assistente de entrada [Microsoft Online Services para profissionais de TI RTW](/collaborate/connect-redirect?DownloadID=59185).</span><span class="sxs-lookup"><span data-stu-id="07900-133">Install the 64-bit version of the [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](/collaborate/connect-redirect?DownloadID=59185).</span></span>
2. <span data-ttu-id="07900-134">Instale o módulo Microsoft Azure Active Directory para Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="07900-134">Install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    1. <span data-ttu-id="07900-135">Abra um prompt de Windows PowerShell de comando com privilégios elevados (execute Windows PowerShell como administrador).</span><span class="sxs-lookup"><span data-stu-id="07900-135">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an admin).</span></span>
    2. <span data-ttu-id="07900-136">Execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="07900-136">Run the following command:</span></span>
        ```powershell
        Install-Module MSOnline
        ```
    3. <span data-ttu-id="07900-137">Se você for solicitado a instalar o provedor NuGet, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="07900-137">If you're prompted to install the NuGet provider, type **Y**, and then press Enter.</span></span>
    4. <span data-ttu-id="07900-138">Se você for solicitado a instalar o módulo do PSGallery, digite **Y** e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="07900-138">If you're prompted to install the module from PSGallery, type **Y**, and then press Enter.</span></span>
3. <span data-ttu-id="07900-139">No prompt Windows PowerShell de comando, execute o seguinte script para atribuir licenças aos usuários, onde está o nome da sua organização e o identificador da licença que você \<CompanyName:License> deseja atribuir.</span><span class="sxs-lookup"><span data-stu-id="07900-139">At the Windows PowerShell command prompt, run the following script to assign licenses to your users, where \<CompanyName:License> is your organization name and the identifier for the license that you want to assign.</span></span> <span data-ttu-id="07900-140">Por exemplo, litwareinc:MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="07900-140">For example, litwareinc:MCOMEETADV.</span></span>

    <span data-ttu-id="07900-141">O identificador é diferente do nome amigável da licença.</span><span class="sxs-lookup"><span data-stu-id="07900-141">The identifier is different than the friendly name of the license.</span></span> <span data-ttu-id="07900-142">Por exemplo, o identificador para Audioconferência é MCOMEETADV.</span><span class="sxs-lookup"><span data-stu-id="07900-142">For example, the identifier for Audio Conferencing is MCOMEETADV.</span></span> <span data-ttu-id="07900-143">Para saber mais, confira [Nomes de produto e identificadores SKU para licenciamento](#product-names-and-sku-identifiers-for-licensing).</span><span class="sxs-lookup"><span data-stu-id="07900-143">To learn more, see [Product names and SKU identifiers for licensing](#product-names-and-sku-identifiers-for-licensing).</span></span>

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

    <span data-ttu-id="07900-144">Por exemplo, para atribuir Microsoft 365 Enterprise 1 e licenças de Audioconferência, use a seguinte sintaxe no script:</span><span class="sxs-lookup"><span data-stu-id="07900-144">For example, to assign Microsoft 365 Enterprise 1 and Audio Conferencing licenses, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    <span data-ttu-id="07900-145">Para atribuir uma licença do Microsoft Business Voice (sem Plano de Chamadas), use a seguinte sintaxe no script:</span><span class="sxs-lookup"><span data-stu-id="07900-145">To assign a Microsoft Business Voice (without Calling Plan) license, use the following syntax in the script:</span></span>

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a><span data-ttu-id="07900-146">Nomes de produtos e identificadores SKU para licenciamento</span><span class="sxs-lookup"><span data-stu-id="07900-146">Product names and SKU identifiers for licensing</span></span>

<span data-ttu-id="07900-147">Aqui está uma lista parcial de nomes de produtos e seus nomes de partes SKU correspondentes que você pode usar como referência ao usar o PowerShell para gerenciar licenças em Teams.</span><span class="sxs-lookup"><span data-stu-id="07900-147">Here's a partial list of product names and their corresponding SKU part names that you can use as a reference when you use PowerShell to manage licenses in Teams.</span></span>

<span data-ttu-id="07900-148">Para saber mais, confira Exibir licenças e serviços com [o PowerShell,](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)nomes de produtos e [identificadores](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)de plano de serviço para licenciamento e referência [de SKU do Education.](../sku-reference-edu.md)</span><span class="sxs-lookup"><span data-stu-id="07900-148">To learn more, see [View licenses and services with PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [Product names and service plan identifiers for licensing](/azure/active-directory/users-groups-roles/licensing-service-plan-reference), and [Education SKU reference](../sku-reference-edu.md).</span></span>

| <span data-ttu-id="07900-149">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="07900-149">Product name</span></span>| <span data-ttu-id="07900-150">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="07900-150">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="07900-151">Microsoft Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="07900-151">Microsoft Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="07900-152">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="07900-152">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="07900-153">Microsoft Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="07900-153">Microsoft Enterprise E5 (without Audio Conferencing)</span></span> | <span data-ttu-id="07900-154">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="07900-154">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="07900-155">Microsoft Enterprise E5 (com Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="07900-155">Microsoft Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="07900-156">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="07900-156">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="07900-157">Microsoft Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="07900-157">Microsoft Enterprise E3</span></span> | <span data-ttu-id="07900-158">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="07900-158">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="07900-159">Microsoft Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="07900-159">Microsoft Enterprise E1</span></span> | <span data-ttu-id="07900-160">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="07900-160">STANDARDPACK</span></span> |
| <span data-ttu-id="07900-161">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="07900-161">Microsoft 365 Business Basic</span></span> | <span data-ttu-id="07900-162">O365_BUSINESS_ESSENTIALS</span><span class="sxs-lookup"><span data-stu-id="07900-162">O365_BUSINESS_ESSENTIALS</span></span>|
| <span data-ttu-id="07900-163">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="07900-163">Microsoft 365 Business Standard</span></span> | <span data-ttu-id="07900-164">O365_BUSINESS_PREMIUM</span><span class="sxs-lookup"><span data-stu-id="07900-164">O365_BUSINESS_PREMIUM</span></span>|
| <span data-ttu-id="07900-165">Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="07900-165">Microsoft 365 Business</span></span> | <span data-ttu-id="07900-166">SPB</span><span class="sxs-lookup"><span data-stu-id="07900-166">SPB</span></span>|
| <span data-ttu-id="07900-167">Microsoft Business Voice (Canadá)</span><span class="sxs-lookup"><span data-stu-id="07900-167">Microsoft Business Voice (Canada)</span></span>| <span data-ttu-id="07900-168">BUSINESS_VOICE_MED</span><span class="sxs-lookup"><span data-stu-id="07900-168">BUSINESS_VOICE_MED</span></span>  |
| <span data-ttu-id="07900-169">Microsoft Business Voice (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="07900-169">Microsoft Business Voice (United Kingdom)</span></span> | <span data-ttu-id="07900-170">BUSINESS_VOICE</span><span class="sxs-lookup"><span data-stu-id="07900-170">BUSINESS_VOICE</span></span>  |
| <span data-ttu-id="07900-171">Microsoft Business Voice (Estados Unidos)</span><span class="sxs-lookup"><span data-stu-id="07900-171">Microsoft Business Voice (United States)</span></span> | <span data-ttu-id="07900-172">BUSINESS_VOICE_MED2</span><span class="sxs-lookup"><span data-stu-id="07900-172">BUSINESS_VOICE_MED2</span></span>  |
| <span data-ttu-id="07900-173">Microsoft Business Voice (sem Plano de Chamadas)</span><span class="sxs-lookup"><span data-stu-id="07900-173">Microsoft Business Voice (without Calling Plan)</span></span> | <span data-ttu-id="07900-174">BUSINESS_VOICE_DIRECTROUTING</span><span class="sxs-lookup"><span data-stu-id="07900-174">BUSINESS_VOICE_DIRECTROUTING</span></span>  |
| <span data-ttu-id="07900-175">Microsoft Business Voice (sem Plano de Chamadas) para os Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="07900-175">Microsoft Business Voice (without Calling Plan) for the United States</span></span>| <span data-ttu-id="07900-176">BUSINESS_VOICE_DIRECTROUTING _MED</span><span class="sxs-lookup"><span data-stu-id="07900-176">BUSINESS_VOICE_DIRECTROUTING _MED</span></span> |
| <span data-ttu-id="07900-177">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="07900-177">Audio Conferencing</span></span> | <span data-ttu-id="07900-178">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="07900-178">MCOMEETADV</span></span> | 
| <span data-ttu-id="07900-179">Pagamento de audioconferência por minuto (pagar conforme você vai)</span><span class="sxs-lookup"><span data-stu-id="07900-179">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="07900-180">*Exige que os Créditos de Comunicações sejam definidos e habilitados.*</span><span class="sxs-lookup"><span data-stu-id="07900-180">*Requires Communications Credits to be set up and enabled.*</span></span> | <span data-ttu-id="07900-181">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="07900-181">MCOMEETACPEA</span></span> |
| <span data-ttu-id="07900-182">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="07900-182">Phone System</span></span> | <span data-ttu-id="07900-183">MCOEV</span><span class="sxs-lookup"><span data-stu-id="07900-183">MCOEV</span></span> |
| <span data-ttu-id="07900-184">Plano de Chamada Doméstica e Internacional</span><span class="sxs-lookup"><span data-stu-id="07900-184">Domestic and International Calling Plan</span></span> | <span data-ttu-id="07900-185">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="07900-185">MCOPSTN2</span></span> |
| <span data-ttu-id="07900-186">Plano de Chamada Doméstica (3000 minutos por usuário/mês para US/PR/CA, 1200 minutos por usuário/mês para países da UE)</span><span class="sxs-lookup"><span data-stu-id="07900-186">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="07900-187">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="07900-187">MCOPSTN1</span></span> |
| <span data-ttu-id="07900-188">Plano de Chamada Doméstica (120 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="07900-188">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="07900-189">*Este plano não está disponível nos Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="07900-189">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="07900-190">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="07900-190">MCOPSTN5</span></span> |
| <span data-ttu-id="07900-191">Plano de Chamada Doméstica (240 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="07900-191">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="07900-192">*Este plano não está disponível nos Estados Unidos.*</span><span class="sxs-lookup"><span data-stu-id="07900-192">*This plan isn't available in the United States.*</span></span> | <span data-ttu-id="07900-193">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="07900-193">MCOPSTN6</span></span> |
| <span data-ttu-id="07900-194">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="07900-194">Communications Credits</span></span> | <span data-ttu-id="07900-195">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="07900-195">MCOPSTNPP</span></span> |

## <a name="related-topics"></a><span data-ttu-id="07900-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="07900-196">Related topics</span></span>

- [<span data-ttu-id="07900-197">Licenciamento do complemento do Teams</span><span class="sxs-lookup"><span data-stu-id="07900-197">Teams add-on licensing</span></span>](./microsoft-teams-add-on-licensing.md)
- [<span data-ttu-id="07900-198">Gerenciamento do acesso de usuários ao Teams</span><span class="sxs-lookup"><span data-stu-id="07900-198">Manage user access to Teams</span></span>](../user-access.md)
- [<span data-ttu-id="07900-199">Exibir licenças e serviços com o PowerShell</span><span class="sxs-lookup"><span data-stu-id="07900-199">View licenses and services with PowerShell</span></span>](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [<span data-ttu-id="07900-200">Nomes de produtos e identificadores de plano de serviço para licenciamento</span><span class="sxs-lookup"><span data-stu-id="07900-200">Product names and service plan identifiers for licensing</span></span>](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [<span data-ttu-id="07900-201">Referência de SKU do Education</span><span class="sxs-lookup"><span data-stu-id="07900-201">Education SKU reference</span></span>](../sku-reference-edu.md)
