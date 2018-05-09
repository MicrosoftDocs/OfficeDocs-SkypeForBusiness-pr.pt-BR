---
title: Atribuir Skype para licenças de negócios e Teams da Microsoft
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Licensing
description: 'Saiba como atribuir Skype para licenças de negócios para o sistema telefônico, conferência de áudio, chamar planos e créditos de comunicações. '
ms.openlocfilehash: 00c80637e4b94a66f63c43e51f0bc3e562d42bea
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="e6691-103">Atribuir Skype para licenças de negócios e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="e6691-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="e6691-104">Este artigo fornece dicas sobre como atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="e6691-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="e6691-105">Oferece também scripts para atribuir licenças em massa.</span><span class="sxs-lookup"><span data-stu-id="e6691-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="e6691-106">**Importante**: consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre as licenças que você precisará comprar e **como comprá** -los - dependendo do seu plano do Office 365 - para que os usuários obtenham audioconferências, números para ligações gratuitas, e a capacidade de chamar números de telefone fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="e6691-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e6691-107">Telefone de sistema e chamar planos: dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="e6691-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="e6691-108">O que você precisa saber antes de atribuir a conferência de áudio, o sistema telefônico e chamar planejar licenças</span><span class="sxs-lookup"><span data-stu-id="e6691-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="e6691-109">**Você está usando conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="e6691-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="e6691-110">Nesse caso, você precisará atribuir uma licença de **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="e6691-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="e6691-111">Você deve **não** atribuir um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="e6691-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="e6691-112">**Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Skype para Business Online, possivelmente pode demorar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="e6691-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="e6691-113">Se após 24 horas, o usuário não é atribuído um plano de chamar, entre [o suporte de contato para produtos de negócios - ajuda de Admin](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="e6691-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="e6691-114">**Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="e6691-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="e6691-115">Se você precisar comprar mais licenças chamar planejar, escolha **comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="e6691-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="e6691-116">**Próximas etapas**: depois de atribuir licenças chamar planejar para seus usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6691-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e6691-117">Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e6691-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="e6691-118">Como atribuir uma licença de sistema telefônico e planejar a chamada para um usuário</span><span class="sxs-lookup"><span data-stu-id="e6691-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="e6691-p106">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e6691-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="e6691-121">Como atribuir licenças do sistema telefônico e chamar planejar em massa</span><span class="sxs-lookup"><span data-stu-id="e6691-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="e6691-122">Instale o **Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW**.</span><span class="sxs-lookup"><span data-stu-id="e6691-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="e6691-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="e6691-123">Don't have the module installed?</span></span> <span data-ttu-id="e6691-124">Consulte [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.</span><span class="sxs-lookup"><span data-stu-id="e6691-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="e6691-125">Instale o **Módulo do Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="e6691-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="e6691-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="e6691-126">Don't have the module installed?</span></span> <span data-ttu-id="e6691-127">Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e6691-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="e6691-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="e6691-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="e6691-129">Este exemplo atribui uma **licença Enterprise E3** junto com um **Sistema telefônico** e uma licença **Domésticas chamar planejar** .</span><span class="sxs-lookup"><span data-stu-id="e6691-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="e6691-130">O nome das licenças ou nomes de produto no script estão listados no texto itálico (consulte o **sistema telefônico e chamar planejar nomes de produtos ou SKUs usados para execução de scripts**, após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="e6691-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
  
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e6691-131">Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="e6691-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="e6691-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="e6691-132">**Product name**</span></span>|<span data-ttu-id="e6691-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="e6691-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6691-134">Enterprise E5 (com o sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="e6691-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="e6691-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e6691-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="e6691-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e6691-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e6691-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e6691-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e6691-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e6691-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e6691-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e6691-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e6691-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e6691-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e6691-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e6691-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e6691-142">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="e6691-142">Phone System</span></span>  <br/> |<span data-ttu-id="e6691-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="e6691-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="e6691-144">Plano de chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="e6691-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="e6691-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="e6691-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="e6691-146">Plano de Chamadas Domésticas</span><span class="sxs-lookup"><span data-stu-id="e6691-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="e6691-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="e6691-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="e6691-148">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="e6691-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="e6691-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="e6691-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="e6691-150">Conferência de áudio: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="e6691-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="e6691-151">O que você precisa saber antes de atribuir licenças de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="e6691-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="e6691-152">**Provedor de serviços de audioconferência de terceiros**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de **Serviços de audioconferência** , elas serão alteradas para usar o Microsoft como os serviços de audioconferência provedor.</span><span class="sxs-lookup"><span data-stu-id="e6691-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="e6691-153">Você poderá mudá-lo de volta para o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="e6691-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="e6691-154">Próximas etapas: depois de atribuir licenças de **Serviços de audioconferência** , você precisa atribuir a um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="e6691-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="e6691-155">Consulte [atribuir Microsoft como um provedor de serviços de audioconferência].</span><span class="sxs-lookup"><span data-stu-id="e6691-155">See [Assign Microsoft as the audio conferencing provider].</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="e6691-156">Como atribuir uma licença de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="e6691-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="e6691-p111">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e6691-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="e6691-159">Como atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="e6691-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="e6691-160">Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="e6691-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="e6691-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="e6691-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="e6691-163">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="e6691-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="e6691-164">[!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico.</span><span class="sxs-lookup"><span data-stu-id="e6691-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="e6691-165">Consulte [nomes de produto de conferência de áudio ou SKUs usados para o script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) de todos os nomes dos produtos.</span><span class="sxs-lookup"><span data-stu-id="e6691-165">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="e6691-166">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="e6691-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="e6691-167">Nomes de produto de conferência áudio ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="e6691-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="e6691-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="e6691-168"></span></span>

|<span data-ttu-id="e6691-169">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="e6691-169">**Product name**</span></span>|<span data-ttu-id="e6691-170">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="e6691-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e6691-171">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="e6691-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="e6691-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="e6691-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="e6691-173">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e6691-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="e6691-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="e6691-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="e6691-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="e6691-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="e6691-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="e6691-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="e6691-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="e6691-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="e6691-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="e6691-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="e6691-179">E5 da empresa (sem serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="e6691-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="e6691-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="e6691-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="e6691-181">Enterprise E5 (com serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="e6691-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="e6691-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="e6691-182">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="e6691-183">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="e6691-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="e6691-184">O que você precisa saber antes de atribuir licenças créditos de comunicações</span><span class="sxs-lookup"><span data-stu-id="e6691-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="e6691-185">**Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes **Communications créditos** licenças.</span><span class="sxs-lookup"><span data-stu-id="e6691-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="e6691-186">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="e6691-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="e6691-187">Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="e6691-187">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="e6691-188">Como atribuir uma licença créditos de comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="e6691-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="e6691-p115">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="e6691-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="e6691-191">Como atribuir licenças créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="e6691-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="e6691-192">Dê uma olhada o script de exemplo para atribuir licenças de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="e6691-192">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="e6691-193">Atualizá-lo com as informações para atribuir licenças **Créditos de comunicações** .</span><span class="sxs-lookup"><span data-stu-id="e6691-193">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e6691-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e6691-194">Related topics</span></span>
  
[<span data-ttu-id="e6691-195">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="e6691-195">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="e6691-196">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="e6691-196">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  
  
 