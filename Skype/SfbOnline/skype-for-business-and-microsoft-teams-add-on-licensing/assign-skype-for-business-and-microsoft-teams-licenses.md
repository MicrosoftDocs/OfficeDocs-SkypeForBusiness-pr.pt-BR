---
title: Atribuir licenças do Skype for Business
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: 41f1788e4c562f3b4cc1f43d7875b64805b19ed8
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237487"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="01993-103">Atribuir licenças do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="01993-103">Assign Skype for Business licenses</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="01993-104">Este artigo fornece dicas de como atribuir licenças de recursos como Audioconferência, Sistema de Telefonia e Planos de Chamadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="01993-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="01993-105">Oferece também scripts para atribuir licenças em massa.</span><span class="sxs-lookup"><span data-stu-id="01993-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="01993-106">Consulte [Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md) licenciamento de complementos para obter informações sobre quais  licenças você precisa comprar e como comprá-las - dependendo do seu plano de Microsoft 365 ou Office 365 - para que os usuários recebam Audioconferência, números de chamada gratuita e a capacidade de chamar números de telefone fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="01993-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Microsoft 365 or Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="01993-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="01993-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="01993-108">O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="01993-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="01993-109">**Você está usando conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="01993-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="01993-110">Em caso afirmado, você só precisa atribuir uma **Sistema de Telefonia** de usuário.</span><span class="sxs-lookup"><span data-stu-id="01993-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="01993-111">Você NÃO **deve atribuir** um Plano de Chamada.</span><span class="sxs-lookup"><span data-stu-id="01993-111">You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="01993-112">**Latência** após a atribuição de licenças : devido à latência entre o Microsoft 365 ou o Office 365 e o Skype for Business Online, pode levar até 24 horas para que um usuário seja atribuído a um Plano de Chamada depois de atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="01993-112">**Latency after assigning licenses**: Because of the latency between Microsoft 365 or Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="01993-113">Se após 24 horas o usuário não tiver um Plano de Chamada, entre em contato com o suporte para produtos comerciais [- Ajuda do administrador](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="01993-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="01993-114">**Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="01993-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="01993-115">Se precisar comprar mais licenças do Plano de Chamada, escolha **Comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="01993-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="01993-116">**Próximas** etapas: depois de atribuir licenças do Plano de Chamadas aos usuários, você precisará obter seus números de telefone para sua organização e atribuir esses números às pessoas da sua organização.</span><span class="sxs-lookup"><span data-stu-id="01993-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="01993-117">Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="01993-117">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="01993-118">Como atribuir uma licença Sistema de Telefonia e Plano de Chamada a um usuário</span><span class="sxs-lookup"><span data-stu-id="01993-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="01993-119">As etapas são as mesmas que atribuir uma licença de Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="01993-119">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="01993-120">Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="01993-120">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="01993-121">Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa</span><span class="sxs-lookup"><span data-stu-id="01993-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="01993-122">Instale o **Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW**.</span><span class="sxs-lookup"><span data-stu-id="01993-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="01993-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="01993-123">Don't have the module installed?</span></span> <span data-ttu-id="01993-124">Consulte [Microsoft Online Services Sign-In assistente para profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.</span><span class="sxs-lookup"><span data-stu-id="01993-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="01993-125">Instale o **Módulo do Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="01993-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="01993-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="01993-126">Don't have the module installed?</span></span> <span data-ttu-id="01993-127">Consulte [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet sintaxe.</span><span class="sxs-lookup"><span data-stu-id="01993-127">See [Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="01993-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="01993-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="01993-129">Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.</span><span class="sxs-lookup"><span data-stu-id="01993-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="01993-130">O nome das licenças ou nomes de produtos no script estão listados no texto itálico (consulte Sistema de Telefonia nomes de produtos ou **SKUs** do Plano de Chamada usados para scripts , após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="01993-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

   #Example of text file:
   #user1@domain.com
   #user2@domain.com

   #Import Module
   ipmo MSOnline
   #Authenticate to MSOLservice.
   Connect-MSOLService
   #File prompt to select the userlist txt file.
   [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
   $OFD = New-Object System.Windows.Forms.OpenFileDialog
   $OFD.filter = "text files (*.*)| *.txt"
   $OFD.ShowDialog() | Out-Null
   $OFD.filename
   If ($OFD.filename -eq '')
   {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
   }
   #Create a variable of all users.
   $users = Get-Content $OFD.filename
   #License each user in the $users variable.
   #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
   International Calling.
   for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    }
   ```
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="01993-131">Sistema de Telefonia nomes de produtos ou SKUs de planos de chamada e planos de chamada usados para scripts</span><span class="sxs-lookup"><span data-stu-id="01993-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="01993-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="01993-132">**Product name**</span></span>|<span data-ttu-id="01993-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="01993-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01993-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="01993-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="01993-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="01993-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="01993-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="01993-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="01993-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="01993-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="01993-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="01993-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="01993-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="01993-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="01993-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="01993-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="01993-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="01993-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="01993-142">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="01993-142">Phone System</span></span>  <br/> |<span data-ttu-id="01993-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="01993-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="01993-144">Plano de Chamadas Internacionais</span><span class="sxs-lookup"><span data-stu-id="01993-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="01993-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="01993-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="01993-146">Plano de Chamada Doméstica (3.000 min us / 1200 min planos da UE)</span><span class="sxs-lookup"><span data-stu-id="01993-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="01993-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="01993-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="01993-148">Plano de Chamada Doméstica (plano de chamada de 120 minutos)</span><span class="sxs-lookup"><span data-stu-id="01993-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="01993-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="01993-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="01993-150">Plano de Chamada Doméstica (plano de chamada de 240 minutos)</span><span class="sxs-lookup"><span data-stu-id="01993-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="01993-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="01993-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="01993-152">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="01993-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="01993-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="01993-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="01993-154">Audioconferência: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="01993-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="01993-155">O que você precisa saber antes de atribuir licenças de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="01993-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="01993-156">Provedor de audioconferência de terceiros : se alguém já estiver definido para usar um provedor de audioconferência de terceiros, quando você atribuir uma licença de **Audioconferência,** ele será alterado para usar a Microsoft como provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="01993-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="01993-157">Você poderá mudá-lo de volta para o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="01993-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="01993-158">Próximas etapas: depois de atribuir **licenças** de Audioconferência, você precisará atribuir um provedor de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="01993-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="01993-159">Veja [Atribuir a Microsoft como provedor de audioconferência].</span><span class="sxs-lookup"><span data-stu-id="01993-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="01993-160">Como atribuir uma licença de Audioconferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="01993-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="01993-161">As etapas são as mesmas que atribuir uma licença de Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="01993-161">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="01993-162">Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="01993-162">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="01993-163">Como atribuir licenças de Audioconferência em massa</span><span class="sxs-lookup"><span data-stu-id="01993-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="01993-164">Baixe e instale [Microsoft Online Services Sign-In Assistente para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="01993-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="01993-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em [Gerenciar o Azure AD usando o Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="01993-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="01993-167">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="01993-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="01993-168">[!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico.</span><span class="sxs-lookup"><span data-stu-id="01993-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="01993-169">Consulte [Nomes de produtos de audioconferência ou SKUs usados para scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos os nomes de produtos.</span><span class="sxs-lookup"><span data-stu-id="01993-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="01993-170">Este exemplo atribui uma licença Enterprise E3 juntamente com uma licença de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="01993-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
    #Example of text file:
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
        }
    ```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="01993-171">Nomes de produtos de audioconferência ou SKUs usados para scripts</span><span class="sxs-lookup"><span data-stu-id="01993-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="01993-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="01993-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="01993-173">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="01993-173">**Product name**</span></span>|<span data-ttu-id="01993-174">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="01993-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="01993-175">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="01993-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="01993-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="01993-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="01993-177">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="01993-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="01993-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="01993-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="01993-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="01993-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="01993-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="01993-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="01993-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="01993-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="01993-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="01993-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="01993-183">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="01993-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="01993-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="01993-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="01993-185">Enterprise E5 (com Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="01993-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="01993-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="01993-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="01993-187">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="01993-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="01993-188">O que você precisa saber antes de atribuir licenças de Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="01993-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="01993-189">**Enterprise clientes do E5**: Mesmo que seus usuários sejam atribuídos Enterprise licenças do E5, ainda recomendamos que você atribua a eles licenças de **Créditos de** Comunicação.</span><span class="sxs-lookup"><span data-stu-id="01993-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="01993-190">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="01993-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="01993-191">Para obter instruções passo a passo, consulte [Configurar Planos de Chamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="01993-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="01993-192">Como atribuir uma licença de Créditos de Comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="01993-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="01993-193">As etapas são as mesmas que atribuir uma licença de Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="01993-193">The steps are the same as assigning a Microsoft 365 or Office 365 license.</span></span> <span data-ttu-id="01993-194">Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="01993-194">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="01993-195">Como atribuir licenças de Créditos de Comunicação em massa</span><span class="sxs-lookup"><span data-stu-id="01993-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="01993-196">Dê uma olhada no script de exemplo para atribuir licenças de **Audioconferência.**</span><span class="sxs-lookup"><span data-stu-id="01993-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="01993-197">Atualize-o com as informações para atribuir **licenças de Créditos de** Comunicações.</span><span class="sxs-lookup"><span data-stu-id="01993-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="01993-198">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="01993-198">Related topics</span></span>
  
[<span data-ttu-id="01993-199">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="01993-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="01993-200">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="01993-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
