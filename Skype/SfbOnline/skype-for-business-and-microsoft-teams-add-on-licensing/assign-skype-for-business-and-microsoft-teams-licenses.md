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
ms.openlocfilehash: 9aa423683160c064b13be140c4226b2327dd9b69
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692516"
---
# <a name="assign-skype-for-business-licenses"></a><span data-ttu-id="88a4e-103">Atribuir licenças do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="88a4e-103">Assign Skype for Business licenses</span></span>

<span data-ttu-id="88a4e-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span><span class="sxs-lookup"><span data-stu-id="88a4e-p101">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans. It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88a4e-106">Consulte [Licenciamento de complemento do Skype for Business](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e **como comprá** -las, dependendo do seu plano do Office 365, para que os usuários recebam conferências de áudio, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="88a4e-106">See [Skype for Business add-on licensing](skype-for-business-and-microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and **how to buy** them - depending on your Office 365 plan - so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="88a4e-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="88a4e-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="88a4e-108">O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="88a4e-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="88a4e-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span><span class="sxs-lookup"><span data-stu-id="88a4e-p102">**Using on-premises PSTN connectivity for hybrid users?** If so, you only need to assign a **Phone System** license. You should **NOT** assign a Calling Plan.</span></span>

- <span data-ttu-id="88a4e-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="88a4e-p103">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be assigned a Calling Plan after you assign a license. If after 24 hours the user isn't assigned a Calling Plan, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="88a4e-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span><span class="sxs-lookup"><span data-stu-id="88a4e-p104">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses. If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>
    
- <span data-ttu-id="88a4e-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="88a4e-p105">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization. For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="88a4e-118">Como atribuir uma licença do sistema telefônico e do plano de chamada a um usuário</span><span class="sxs-lookup"><span data-stu-id="88a4e-118">How to assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="88a4e-119">The steps are the same as assigning an Office 365 license.</span><span class="sxs-lookup"><span data-stu-id="88a4e-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="88a4e-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="88a4e-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="88a4e-121">Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa</span><span class="sxs-lookup"><span data-stu-id="88a4e-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="88a4e-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span><span class="sxs-lookup"><span data-stu-id="88a4e-p107">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**. Don't have the module installed? See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="88a4e-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span><span class="sxs-lookup"><span data-stu-id="88a4e-p108">Install the **Windows Azure Active Directory Module.** Don't have the module installed? See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="88a4e-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="88a4e-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

   <span data-ttu-id="88a4e-129">Este exemplo atribui uma licença **Enterprise E3** junto com um **Sistema de Telefonia** e uma licença de **Plano de Chamadas Domésticas**.</span><span class="sxs-lookup"><span data-stu-id="88a4e-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

   <span data-ttu-id="88a4e-130">O nome das licenças ou nomes de produto no script são listados em texto em itálico (consulte o **sistema telefônico e os nomes de produto do plano de chamada ou os SKUs usados para script**, após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="88a4e-130">The name of the licenses or product names in the script are listed in italics text (see **Phone System and Calling Plan product names or SKUs used for scripting**, after the example).</span></span>

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
   ### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="88a4e-131">Nomes de produtos ou SKUs dos planos de chamadas e sistema telefônico usados para scripts</span><span class="sxs-lookup"><span data-stu-id="88a4e-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

|<span data-ttu-id="88a4e-132">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="88a4e-132">**Product name**</span></span>|<span data-ttu-id="88a4e-133">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="88a4e-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88a4e-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="88a4e-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="88a4e-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="88a4e-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="88a4e-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="88a4e-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="88a4e-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="88a4e-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="88a4e-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="88a4e-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="88a4e-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="88a4e-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="88a4e-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="88a4e-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="88a4e-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="88a4e-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="88a4e-142">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="88a4e-142">Phone System</span></span>  <br/> |<span data-ttu-id="88a4e-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="88a4e-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="88a4e-144">Plano de Chamadas Internacionais</span><span class="sxs-lookup"><span data-stu-id="88a4e-144">International Calling Plan</span></span>  <br/> |<span data-ttu-id="88a4e-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="88a4e-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="88a4e-146">Plano de chamadas domésticas (3000 min-US/1200 min) planos da UE)</span><span class="sxs-lookup"><span data-stu-id="88a4e-146">Domestic Calling Plan (3000 min US / 1200 min EU plans)</span></span>  <br/> |<span data-ttu-id="88a4e-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="88a4e-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="88a4e-148">Plano de chamadas domésticas (120 min-plano de chamadas)</span><span class="sxs-lookup"><span data-stu-id="88a4e-148">Domestic Calling Plan (120 min calling plan)</span></span>  <br/> |<span data-ttu-id="88a4e-149">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="88a4e-149">MCOPSTN5</span></span>  <br/> |
|<span data-ttu-id="88a4e-150">Plano de chamadas domésticas (240 min-plano de chamadas)</span><span class="sxs-lookup"><span data-stu-id="88a4e-150">Domestic Calling Plan (240 min calling plan)</span></span>  <br/> |<span data-ttu-id="88a4e-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="88a4e-151">MCOPSTN6</span></span>  <br/> |
|<span data-ttu-id="88a4e-152">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="88a4e-152">Communications Credits</span></span>  <br/> |<span data-ttu-id="88a4e-153">MCOPSTNC</span><span class="sxs-lookup"><span data-stu-id="88a4e-153">MCOPSTNC</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="88a4e-154">Conferência de áudio: dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="88a4e-154">Audio Conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="88a4e-155">O que você precisa saber antes de atribuir licenças de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="88a4e-155">What you need to know before assigning Audio Conferencing licenses</span></span>

- <span data-ttu-id="88a4e-156">**Provedor de serviços de audioconferência terceirizado**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, ao atribuir uma licença de **audioconferência** , ele será alterado para usar a Microsoft como provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="88a4e-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an **Audio Conferencing** license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="88a4e-157">Você poderá mudá-lo de volta para o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="88a4e-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="88a4e-158">Próximas etapas: depois de atribuir licenças de **audioconferência** , você precisa atribuir um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="88a4e-158">Next steps: After you assign **Audio Conferencing** licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="88a4e-159">Veja [Atribuir a Microsoft como provedor de audioconferência].</span><span class="sxs-lookup"><span data-stu-id="88a4e-159">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="88a4e-160">Como atribuir uma licença de audioconferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="88a4e-160">How to assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="88a4e-161">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="88a4e-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="88a4e-162">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="88a4e-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="88a4e-163">Como atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="88a4e-163">How to assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="88a4e-164">Baixe e instale [o assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="88a4e-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="88a4e-p112">Baixe e instale o **Módulo Microsoft Azure Active Directory**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="88a4e-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="88a4e-167">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="88a4e-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="88a4e-168">[!OBSERVAçãO] O nome das licenças ou dos produtos no script são indicados em itálico.</span><span class="sxs-lookup"><span data-stu-id="88a4e-168">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="88a4e-169">Consulte os [nomes de produtos ou SKUs da conferência de áudio](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para todos os nomes dos produtos.</span><span class="sxs-lookup"><span data-stu-id="88a4e-169">See [Audio Conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="88a4e-170">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="88a4e-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="88a4e-171">Nomes de produtos ou SKUs da conferência de áudio usados para scripts</span><span class="sxs-lookup"><span data-stu-id="88a4e-171">Audio Conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="88a4e-172"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="88a4e-172"><a name="sku"> </a></span></span>

|<span data-ttu-id="88a4e-173">**Nome do produto**</span><span class="sxs-lookup"><span data-stu-id="88a4e-173">**Product name**</span></span>|<span data-ttu-id="88a4e-174">**Nome de parte da SKU**</span><span class="sxs-lookup"><span data-stu-id="88a4e-174">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="88a4e-175">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="88a4e-175">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="88a4e-176">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="88a4e-176">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="88a4e-177">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="88a4e-177">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="88a4e-178">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="88a4e-178">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="88a4e-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="88a4e-179">Enterprise E1</span></span>  <br/> |<span data-ttu-id="88a4e-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="88a4e-180">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="88a4e-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="88a4e-181">Enterprise E3</span></span>  <br/> |<span data-ttu-id="88a4e-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="88a4e-182">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="88a4e-183">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="88a4e-183">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="88a4e-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="88a4e-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="88a4e-185">Enterprise E5 (com conferência de áudio)</span><span class="sxs-lookup"><span data-stu-id="88a4e-185">Enterprise E5 (with Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="88a4e-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="88a4e-186">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="88a4e-187">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="88a4e-187">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="88a4e-188">O que você precisa saber antes de atribuir licenças de créditos de comunicações</span><span class="sxs-lookup"><span data-stu-id="88a4e-188">What you need to know before assigning Communications Credits licenses</span></span>

- <span data-ttu-id="88a4e-189">**Clientes Enterprise E5**: mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, ainda recomendamos que você atribua licenças de **créditos de comunicações** .</span><span class="sxs-lookup"><span data-stu-id="88a4e-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Communications Credits** licenses.</span></span>
    
- <span data-ttu-id="88a4e-190">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="88a4e-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="88a4e-191">Para obter instruções passo a passo, consulte [configurar planos de chamada](/microsoftteams/set-up-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="88a4e-191">For step-by-step instructions, see [Set up Calling Plans](/microsoftteams/set-up-calling-plans).</span></span>
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="88a4e-192">Como atribuir uma licença de créditos de comunicações a um usuário</span><span class="sxs-lookup"><span data-stu-id="88a4e-192">How to assign a Communications Credits license to one user</span></span>

<span data-ttu-id="88a4e-193">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="88a4e-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="88a4e-194">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="88a4e-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="88a4e-195">Como atribuir licenças de créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="88a4e-195">How to assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="88a4e-196">Dê uma olhada no exemplo de script para atribuir licenças de **audioconferência** .</span><span class="sxs-lookup"><span data-stu-id="88a4e-196">Take a look at the sample script for assigning **Audio Conferencing** licenses.</span></span> <span data-ttu-id="88a4e-197">Atualize-o com as informações para atribuir licenças de **créditos de comunicações** .</span><span class="sxs-lookup"><span data-stu-id="88a4e-197">Update it with the info for assigning **Communications Credits** licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="88a4e-198">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="88a4e-198">Related topics</span></span>
  
[<span data-ttu-id="88a4e-199">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="88a4e-199">Set up Calling Plans</span></span>](/microsoftteams/set-up-calling-plans)
  
[<span data-ttu-id="88a4e-200">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="88a4e-200">Add funds and manage Communications Credits</span></span>](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
 
