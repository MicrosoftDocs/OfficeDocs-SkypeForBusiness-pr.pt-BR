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
f1keywords: None
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: 96f2805a031ab122dce0fc354da4a4e60dbded32
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301264"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="661cb-103">Atribuir licenças do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="661cb-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="661cb-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="661cb-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="661cb-106">Consulte [Licenciamento de Complementos do Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e **como comprá** -las-dependendo do seu plano do Office 365-para que os usuários recebam videoconferências, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone fora sua empresa.</span><span class="sxs-lookup"><span data-stu-id="661cb-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="661cb-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="661cb-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="661cb-108">O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="661cb-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="661cb-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="661cb-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="661cb-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="661cb-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="661cb-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="661cb-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="661cb-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="661cb-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="661cb-118">Como atribuir uma licença do sistema telefônico e do plano de chamada a um usuário</span><span class="sxs-lookup"><span data-stu-id="661cb-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="661cb-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="661cb-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="661cb-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="661cb-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="661cb-121">Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa</span><span class="sxs-lookup"><span data-stu-id="661cb-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="661cb-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="661cb-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="661cb-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="661cb-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="661cb-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="661cb-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="661cb-129">Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.</span><span class="sxs-lookup"><span data-stu-id="661cb-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="661cb-130">O nome das licenças ou nomes de produto no script são listados em texto em itálico (consulte o **sistema telefônico e os nomes de produto do plano de chamada ou os SKUs usados para script**, após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="661cb-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="661cb-131">Nomes de produtos ou SKUs dos planos de chamadas e sistema telefônico usados para scripts</span><span class="sxs-lookup"><span data-stu-id="661cb-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="661cb-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="661cb-132">**Product name**</span></span>|<span data-ttu-id="661cb-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="661cb-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="661cb-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="661cb-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="661cb-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="661cb-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="661cb-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="661cb-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="661cb-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="661cb-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="661cb-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="661cb-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="661cb-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="661cb-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="661cb-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="661cb-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="661cb-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="661cb-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="661cb-142">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="661cb-142">Phone System</span></span>  <br/> |<span data-ttu-id="661cb-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="661cb-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="661cb-144">Plano de chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="661cb-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="661cb-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="661cb-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="661cb-146">Plano de Chamadas Domésticas</span><span class="sxs-lookup"><span data-stu-id="661cb-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="661cb-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="661cb-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="661cb-148">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="661cb-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="661cb-149">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="661cb-149">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="661cb-150">Conferência de áudio: dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="661cb-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="661cb-151">O que você precisa saber antes de atribuir licenças de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="661cb-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="661cb-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span><span class="sxs-lookup"><span data-stu-id="661cb-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="661cb-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span><span class="sxs-lookup"><span data-stu-id="661cb-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="661cb-156">Como atribuir uma licença de audioconferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="661cb-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="661cb-157">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="661cb-157">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="661cb-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="661cb-158">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="661cb-159">Como atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="661cb-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="661cb-160">Baixe e instale [o assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="661cb-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="661cb-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="661cb-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="661cb-163">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="661cb-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="661cb-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span><span class="sxs-lookup"><span data-stu-id="661cb-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="661cb-166">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="661cb-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="661cb-167">Nomes de produtos ou SKUs da conferência de áudio usados para scripts</span><span class="sxs-lookup"><span data-stu-id="661cb-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="661cb-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="661cb-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="661cb-169">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="661cb-169">**Product name**</span></span>|<span data-ttu-id="661cb-170">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="661cb-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="661cb-171">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="661cb-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="661cb-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="661cb-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="661cb-173">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="661cb-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="661cb-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="661cb-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="661cb-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="661cb-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="661cb-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="661cb-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="661cb-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="661cb-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="661cb-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="661cb-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="661cb-179">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="661cb-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="661cb-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="661cb-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="661cb-181">Enterprise E5 (com conferência de áudio)</span><span class="sxs-lookup"><span data-stu-id="661cb-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="661cb-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="661cb-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="661cb-183">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="661cb-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="661cb-184">O que você precisa saber antes de atribuir licenças de créditos de comunicações</span><span class="sxs-lookup"><span data-stu-id="661cb-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="661cb-185">**Clientes Enterprise E5**: mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, ainda recomendamos que você atribua licenças de **créditos de comunicações** .</span><span class="sxs-lookup"><span data-stu-id="661cb-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="661cb-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="661cb-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="661cb-188">Como atribuir uma licença de créditos de comunicações a um usuário</span><span class="sxs-lookup"><span data-stu-id="661cb-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="661cb-189">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="661cb-189">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="661cb-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="661cb-190">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="661cb-191">Como atribuir licenças de créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="661cb-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="661cb-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span><span class="sxs-lookup"><span data-stu-id="661cb-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="661cb-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="661cb-194">Related topics</span></span>
  
[<span data-ttu-id="661cb-195">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="661cb-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="661cb-196">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="661cb-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
