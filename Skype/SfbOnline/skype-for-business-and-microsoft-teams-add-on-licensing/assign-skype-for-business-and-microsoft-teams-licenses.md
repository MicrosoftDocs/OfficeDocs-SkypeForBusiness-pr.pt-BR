---
title: Atribuir licenças do Skype for Business e do Microsoft Teams
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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Licensing
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: e14ca00d7afa2045248b2a6f18e42a51f3d77b71
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25372792"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="5226a-103">Atribuir licenças do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5226a-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="5226a-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="5226a-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5226a-106">Ver o [Licenciamento do Skype para complemento de negócios e equipes da Microsoft](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisará comprar e **como comprá** -los - dependendo do seu Office 365 planejar - portanto, os usuários têm a capacidade de chamar, números para ligações gratuitas e conferência de áudio números de telefone fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="5226a-106">See [Skype for Business and Microsoft Teams add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5226a-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="5226a-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="5226a-108">O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5226a-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="5226a-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="5226a-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="5226a-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="5226a-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="5226a-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="5226a-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="5226a-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="5226a-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="5226a-118">Como atribuir uma licença de sistema telefônico e planejar a chamada para um usuário</span><span class="sxs-lookup"><span data-stu-id="5226a-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="5226a-p106">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5226a-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="5226a-121">Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa</span><span class="sxs-lookup"><span data-stu-id="5226a-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="5226a-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="5226a-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="5226a-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="5226a-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="5226a-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="5226a-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="5226a-129">Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.</span><span class="sxs-lookup"><span data-stu-id="5226a-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="5226a-130">O nome das licenças ou nomes de produto no script estão listados no texto itálico (consulte o **sistema telefônico e chamar planejar nomes de produtos ou SKUs usados para execução de scripts**, após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="5226a-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5226a-131">Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="5226a-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="5226a-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="5226a-132">**Product name**</span></span>|<span data-ttu-id="5226a-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="5226a-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5226a-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="5226a-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="5226a-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5226a-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="5226a-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5226a-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="5226a-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5226a-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="5226a-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5226a-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="5226a-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5226a-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="5226a-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5226a-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="5226a-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="5226a-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="5226a-142">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="5226a-142">Phone System</span></span>  <br/> |<span data-ttu-id="5226a-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="5226a-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="5226a-144">Plano de chamadas internacionais</span><span class="sxs-lookup"><span data-stu-id="5226a-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="5226a-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="5226a-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="5226a-146">Plano de Chamadas Domésticas</span><span class="sxs-lookup"><span data-stu-id="5226a-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="5226a-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="5226a-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="5226a-148">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="5226a-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="5226a-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="5226a-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="5226a-150">Conferência de áudio: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="5226a-150">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="5226a-151">O que você precisa saber antes de atribuir licenças de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="5226a-151">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="5226a-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span><span class="sxs-lookup"><span data-stu-id="5226a-p109">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider. You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="5226a-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span><span class="sxs-lookup"><span data-stu-id="5226a-p110">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider. See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="5226a-156">Como atribuir uma licença de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="5226a-156">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="5226a-p111">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5226a-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="5226a-159">Como atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="5226a-159">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="5226a-160">Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="5226a-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="5226a-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="5226a-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="5226a-163">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="5226a-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="5226a-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span><span class="sxs-lookup"><span data-stu-id="5226a-p113">The name of the licenses or product names in the script are listed in italics text. See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="5226a-166">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="5226a-166">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="5226a-167">Nomes de produto de conferência áudio ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="5226a-167">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="5226a-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="5226a-168"><a name="sku"> </a></span></span>

|<span data-ttu-id="5226a-169">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="5226a-169">**Product name**</span></span>|<span data-ttu-id="5226a-170">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="5226a-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5226a-171">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="5226a-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="5226a-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="5226a-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="5226a-173">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5226a-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="5226a-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="5226a-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="5226a-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="5226a-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="5226a-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="5226a-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="5226a-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="5226a-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="5226a-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="5226a-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="5226a-179">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="5226a-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="5226a-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="5226a-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="5226a-181">Enterprise E5 (com serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="5226a-181">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="5226a-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="5226a-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="5226a-183">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="5226a-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="5226a-184">O que você precisa saber antes de atribuir licenças créditos de comunicações</span><span class="sxs-lookup"><span data-stu-id="5226a-184">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="5226a-185">**Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes **Communications créditos** licenças.</span><span class="sxs-lookup"><span data-stu-id="5226a-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="5226a-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="5226a-p114">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="5226a-188">Como atribuir uma licença créditos de comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="5226a-188">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="5226a-p115">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="5226a-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="5226a-191">Como atribuir licenças créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="5226a-191">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="5226a-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span><span class="sxs-lookup"><span data-stu-id="5226a-p116">Take a look at the sample script for assigning **Audio Conferencing** licenses. Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5226a-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5226a-194">Related topics</span></span>
  
[<span data-ttu-id="5226a-195">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="5226a-195">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="5226a-196">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="5226a-196">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
