---
title: "Atribuir Skype para licenças de negócios e Teams da Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
- Strat_SB_PSTN
description: "Saiba como atribuir Skype para licenças de negócios para o sistema telefônico, conferência de áudio, chamar planos e créditos de comunicações. "
ms.openlocfilehash: ca3b7a5abef407bb4b8ead2af060a6cfa9b7dd74
ms.sourcegitcommit: 6c59400d2e677c1022f320c91cd7f102b99d292b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/08/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="c075d-103">Atribuir Skype para licenças de negócios e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c075d-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="c075d-104">Este artigo fornece dicas sobre como atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="c075d-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="c075d-105">Oferece também scripts para atribuir licenças em massa.</span><span class="sxs-lookup"><span data-stu-id="c075d-105">It also provides scripts for assigning licenses in bulk.</span></span>
  
 <span data-ttu-id="c075d-106">**Importante**: consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre as licenças que você precisará comprar e **como comprá** -los - dependendo do seu plano do Office 365 - para que os usuários obtenham audioconferências, números para ligações gratuitas, e a capacidade de chamar números de telefone fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="c075d-106">**IMPORTANT**: See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c075d-107">Telefone de sistema e chamar planos: dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="c075d-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="c075d-108">O que você precisa saber antes de atribuir a conferência de áudio, o sistema telefônico e chamar planejar licenças</span><span class="sxs-lookup"><span data-stu-id="c075d-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="c075d-109">**Você está usando conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="c075d-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="c075d-110">Nesse caso, você precisará atribuir uma licença de **Sistema telefônico** .</span><span class="sxs-lookup"><span data-stu-id="c075d-110">If so, you only need to assign a **Phone System** license.</span></span> <span data-ttu-id="c075d-111">Você deve **não** atribuir um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="c075d-111">You should **NOT** assign a Calling Plan.</span></span>
    
- <span data-ttu-id="c075d-112">**Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Skype para Business Online, possivelmente pode demorar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="c075d-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="c075d-113">Se após 24 horas, o usuário não é atribuído um plano de chamar, entre [o suporte de contato para produtos de negócios - ajuda de Admin](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="c075d-113">If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>
    
- <span data-ttu-id="c075d-114">**Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="c075d-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="c075d-115">Se você precisar comprar mais licenças chamar planejar, escolha **comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="c075d-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="c075d-116">**Próximas etapas**: depois de atribuir licenças chamar planejar para seus usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="c075d-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c075d-117">Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c075d-117">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="c075d-118">Como atribuir uma licença de sistema telefônico e planejar a chamada para um usuário</span><span class="sxs-lookup"><span data-stu-id="c075d-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="c075d-p106">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c075d-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="c075d-121">Como atribuir licenças do sistema telefônico e chamar planejar em massa</span><span class="sxs-lookup"><span data-stu-id="c075d-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="c075d-122">Instale o **Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW**.</span><span class="sxs-lookup"><span data-stu-id="c075d-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="c075d-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="c075d-123">Don't have the module installed?</span></span> <span data-ttu-id="c075d-124">Consulte [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.</span><span class="sxs-lookup"><span data-stu-id="c075d-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>
    
2. <span data-ttu-id="c075d-125">Instale o **Módulo do Windows Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c075d-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="c075d-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="c075d-126">Don't have the module installed?</span></span> <span data-ttu-id="c075d-127">Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c075d-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
3. <span data-ttu-id="c075d-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="c075d-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
  <span data-ttu-id="c075d-129">Este exemplo atribui uma **licença Enterprise E3** junto com um **Sistema telefônico** e uma licença **Domésticas chamar planejar** .</span><span class="sxs-lookup"><span data-stu-id="c075d-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>
    
  <span data-ttu-id="c075d-130">O nome das licenças ou nomes de produto no script estão listados no texto itálico (consulte o **sistema telefônico e chamar planejar nomes de produtos ou SKUs usados para execução de scripts**, após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="c075d-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>
    
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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c075d-131">Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="c075d-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="c075d-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="c075d-132">**Product name**</span></span>|<span data-ttu-id="c075d-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="c075d-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c075d-134">Enterprise E5 (com o sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="c075d-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="c075d-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c075d-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="c075d-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c075d-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c075d-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c075d-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c075d-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c075d-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c075d-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c075d-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c075d-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c075d-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c075d-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c075d-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c075d-142">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="c075d-142">Phone System</span></span>  <br/> |<span data-ttu-id="c075d-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="c075d-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="c075d-144">Plano de chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="c075d-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="c075d-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="c075d-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="c075d-146">Plano de Chamadas Domésticas</span><span class="sxs-lookup"><span data-stu-id="c075d-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="c075d-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="c075d-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="c075d-148">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="c075d-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="c075d-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="c075d-149">MCOPSTNPP</span></span>  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="c075d-150">Conferência de áudio: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="c075d-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="c075d-151">O que você precisa saber antes de atribuir licenças de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="c075d-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="c075d-152">**Provedor de serviços de audioconferência de terceiros**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de **Serviços de audioconferência** , elas serão alteradas para usar o Microsoft como os serviços de audioconferência provedor.</span><span class="sxs-lookup"><span data-stu-id="c075d-152">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="c075d-153">Você poderá mudá-lo de volta para o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="c075d-153">You can change them back to the third-party provider.</span></span>
    
- <span data-ttu-id="c075d-154">Próximas etapas: depois de atribuir licenças de **Serviços de audioconferência** , você precisa atribuir a um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="c075d-154">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="c075d-155">Use uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c075d-155">Do one of the following:</span></span>
    
  - [<span data-ttu-id="c075d-156">Atribuir a Microsoft como provedor de audioconferência</span><span class="sxs-lookup"><span data-stu-id="c075d-156">Assign Microsoft as the audio conferencing provider</span></span>](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - <span data-ttu-id="c075d-157">Ou, [atribua um terceiro como um provedor de serviços de audioconferência](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span><span class="sxs-lookup"><span data-stu-id="c075d-157">Or, [Assign a third-party as the audio conferencing provider](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)</span></span>
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="c075d-158">Como atribuir uma licença de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="c075d-158">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="c075d-p111">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c075d-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="c075d-161">Como atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="c075d-161">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="c075d-162">Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="c075d-162">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>
    
2. <span data-ttu-id="c075d-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="c075d-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>
    
    <span data-ttu-id="c075d-165">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="c075d-165">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>
    
    <span data-ttu-id="c075d-166">[!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico.</span><span class="sxs-lookup"><span data-stu-id="c075d-166">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="c075d-167">Consulte [nomes de produto de conferência de áudio ou SKUs usados para o script](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) de todos os nomes dos produtos.</span><span class="sxs-lookup"><span data-stu-id="c075d-167">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>
    
    <span data-ttu-id="c075d-168">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="c075d-168">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>
    
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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="c075d-169">Nomes de produto de conferência áudio ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="c075d-169">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="c075d-170"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="c075d-170"></span></span>

|<span data-ttu-id="c075d-171">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="c075d-171">**Product name**</span></span>|<span data-ttu-id="c075d-172">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="c075d-172">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c075d-173">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="c075d-173">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="c075d-174">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="c075d-174">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="c075d-175">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c075d-175">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="c075d-176">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="c075d-176">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="c075d-177">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c075d-177">Enterprise E1</span></span>  <br/> |<span data-ttu-id="c075d-178">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="c075d-178">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="c075d-179">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c075d-179">Enterprise E3</span></span>  <br/> |<span data-ttu-id="c075d-180">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="c075d-180">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="c075d-181">E5 da empresa (sem serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="c075d-181">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c075d-182">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="c075d-182">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="c075d-183">Enterprise E5 (com serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="c075d-183">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="c075d-184">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="c075d-184">ENTERPRISEPREMIUM</span></span>  <br/> |
   
## <a name="communications-credits"></a><span data-ttu-id="c075d-185">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="c075d-185">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="c075d-186">O que você precisa saber antes de atribuir licenças créditos de comunicações</span><span class="sxs-lookup"><span data-stu-id="c075d-186">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="c075d-187">**Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes **Communications créditos** licenças.</span><span class="sxs-lookup"><span data-stu-id="c075d-187">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="c075d-188">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="c075d-188">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="c075d-189">Para obter instruções detalhadas, consulte [Configurar planos de chamada](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="c075d-189">For step-by-step instructions, see [Set up Calling Plans](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="c075d-190">Como atribuir uma licença créditos de comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="c075d-190">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="c075d-p115">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="c075d-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="c075d-193">Como atribuir licenças créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="c075d-193">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="c075d-194">Dê uma olhada o script de exemplo para atribuir licenças de **Conferência de áudio** .</span><span class="sxs-lookup"><span data-stu-id="c075d-194">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="c075d-195">Atualizá-lo com as informações para atribuir licenças **Créditos de comunicações** .</span><span class="sxs-lookup"><span data-stu-id="c075d-195">Update it with the info for assigning **Communications Credits** licenses.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c075d-196">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c075d-196">Related topics</span></span>

[<span data-ttu-id="c075d-197">Configurar conferência de áudio para o Skype for Business e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="c075d-197">Set up Audio Conferencing for Skype for Business and Microsoft Teams</span></span>](../audio-conferencing-in-office-365/set-up-audio-conferencing.md)
  
[<span data-ttu-id="c075d-198">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="c075d-198">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[<span data-ttu-id="c075d-199">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="c075d-199">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
  
## <a name="feedback"></a><span data-ttu-id="c075d-200">Comentários?</span><span class="sxs-lookup"><span data-stu-id="c075d-200">Feedback?</span></span>
<span data-ttu-id="c075d-201">Para fornecer comentários sobre o produto ou para saber como estamos indo, consulte [Skype para comentários de negócios](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="c075d-201">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>