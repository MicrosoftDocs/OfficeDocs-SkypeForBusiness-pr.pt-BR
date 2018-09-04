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
description: 'Saiba como atribuir licenças de Sistema de Telefonia, Audioconferência, Planos de Chamadas e Créditos de Comunicação do Skype for Business. '
ms.openlocfilehash: 8b83286ef854518197d3b04c23f49bc00ceca2ba
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23253442"
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a><span data-ttu-id="591b1-103">Atribuir licenças do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="591b1-103">Assign Skype for Business and Microsoft Teams licenses</span></span>

<span data-ttu-id="591b1-104">Este artigo fornece dicas de como atribuir licenças de recursos como Audioconferência, Sistema de Telefonia e Planos de Chamadas para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="591b1-104">This article gives you tips about assigning licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="591b1-105">Ele também oferece scripts para atribuir licenças em massa.</span><span class="sxs-lookup"><span data-stu-id="591b1-105">It also provides scripts for assigning licenses in bulk.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="591b1-106">Veja [Licenças complementares do Skype for Business e do Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e **como comprá** -las, de acordo com o seu plano do Office 365, para que os usuários tenham acesso a Audioconferência, números para ligações gratuitas e possam ligar para números de telefone de fora da empresa.</span><span class="sxs-lookup"><span data-stu-id="591b1-106">[IMPORTANT](skype-for-business-and-microsoft-teams-add-on-licensing.md): See**Skype for Business add-on licensing** for information about what licenses you need to buy and how to buy them - depending on your Office 365 plan - so users get dial-in conferencing, toll free numbers, and the ability to call phone numbers outside your business.</span></span>


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="591b1-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="591b1-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="591b1-108">O que você precisa saber antes de atribuir licenças de Audioconferência, Sistema de Telefonia e Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="591b1-108">What you need to know before assigning Audio Conferencing, Phone System and Calling Plan licenses</span></span>

- <span data-ttu-id="591b1-109">**Você usa conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="591b1-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="591b1-110">Nesse caso, precisará atribuir uma licença de **Sistema de Telefonia**.</span><span class="sxs-lookup"><span data-stu-id="591b1-110">If so, you only need to assign a Skype for Business Cloud PBX license.</span></span> <span data-ttu-id="591b1-111">Você **NÃO** deve atribuir um Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="591b1-111">You should **NOT** assign a PSTN Calling plan.</span></span>

- <span data-ttu-id="591b1-112">**Latência após a atribuição de licenças**: Devido à latência entre o Office 365 e o Skype for Business Online, pode levar até 24 horas para um usuário ser habilitado para o Plano de Chamadas após a atribuição da licença.</span><span class="sxs-lookup"><span data-stu-id="591b1-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Skype for Business Online, it can possibly take up to 24 hours for a user to be enabled for PSTN Calling after you assign a license.</span></span> <span data-ttu-id="591b1-113">Se após 24 horas o Plano de Chamadas ainda não estiver habilitado para o usuário, [Entre em contato com o suporte para produtos empresariais - Ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="591b1-113">If after 24 hours, the phone number isn't assigned correctly, please [Contact support for business products - Admin Help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="591b1-114">**Mensagens de erro**: Você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="591b1-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="591b1-115">Se precisar comprar mais licenças de Planos de Chamadas, escolha **Comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="591b1-115">If you need to buy more licenses to enable this user for PSTN Calling, choose **Buy more**.</span></span>

- <span data-ttu-id="591b1-116">**Próximas etapas**: Após atribuir licenças do Plano de Chamadas aos seus usuários, você deverá obter os números de telefone para a sua organização e atribuí-los às pessoas.</span><span class="sxs-lookup"><span data-stu-id="591b1-116">**Next steps**: After you assign PSTN Calling plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="591b1-117">Para instruções passo a passo, veja [Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="591b1-117">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="591b1-118">Como atribuir uma licença de Sistema de Telefonia e Plano de Chamadas a um usuário</span><span class="sxs-lookup"><span data-stu-id="591b1-118">How to assign a Cloud PBX and PSTN Calling license to one user</span></span>

<span data-ttu-id="591b1-p106">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="591b1-p106">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="591b1-121">Como atribuir licenças de Sistema de Telefonia e Planos de Chamadas em massa</span><span class="sxs-lookup"><span data-stu-id="591b1-121">How to assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="591b1-122">Instale o **Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW**.</span><span class="sxs-lookup"><span data-stu-id="591b1-122">Install the **Microsoft Online Services Sign-In Assistant for IT Professionals RTW**.</span></span> <span data-ttu-id="591b1-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="591b1-123">Don't have the module installed?</span></span> <span data-ttu-id="591b1-124">Consulte o [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.</span><span class="sxs-lookup"><span data-stu-id="591b1-124">See[Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="591b1-125">Instale o **Módulo do Active Directory do Azure para Windows**.</span><span class="sxs-lookup"><span data-stu-id="591b1-125">Install the **Windows Azure Active Directory Module.**</span></span> <span data-ttu-id="591b1-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="591b1-126">Don't have the module installed?</span></span> <span data-ttu-id="591b1-127">Consulte [Gerenciar o AD do Azure usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para ver as instruções de download e a sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="591b1-127">See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="591b1-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças aos usuários:</span><span class="sxs-lookup"><span data-stu-id="591b1-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

  <span data-ttu-id="591b1-129">E** ste exemplo ** atribui uma licença Enterprise**  E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.**** **</span><span class="sxs-lookup"><span data-stu-id="591b1-129">This example assigns an **Enterprise E3 license** along with a **Phone System** and a **Domestic Calling Plan** license.</span></span>

  <span data-ttu-id="591b1-130">Os nomes das licenças ou dos produtos no script são listados em itálico (veja **Nomes de produtos ou SKUs de Sistema de Telefonia e Plano de Chamada usados para scripts**, depois do exemplo).</span><span class="sxs-lookup"><span data-stu-id="591b1-130">The name of the licenses or product names in the script are listed in italics text (see **Cloud PBX and PSTN Calling product names or SKUs used for scripting**, after the example).</span></span>

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
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="591b1-131">Nomes de produtos ou SKUs de Sistema de Telefonia e Plano de Chamada e usados para scripts</span><span class="sxs-lookup"><span data-stu-id="591b1-131">Cloud PBX and PSTN Calling product names or SKUs used for scripting</span></span>

|<span data-ttu-id="591b1-132">**Nome de produto**</span><span class="sxs-lookup"><span data-stu-id="591b1-132">**Product name**</span></span>|<span data-ttu-id="591b1-133">**Nome de parte SKU**</span><span class="sxs-lookup"><span data-stu-id="591b1-133">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="591b1-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="591b1-134">Enterprise E5 (with Phone System)</span></span>  <br/> |<span data-ttu-id="591b1-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="591b1-135">ENTERPRISEPREMIUM</span></span>  <br/> |
|<span data-ttu-id="591b1-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="591b1-136">Enterprise E3</span></span>  <br/> |<span data-ttu-id="591b1-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="591b1-137">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="591b1-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="591b1-138">Enterprise E1</span></span>  <br/> |<span data-ttu-id="591b1-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="591b1-139">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="591b1-140">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="591b1-140">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="591b1-141">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="591b1-141">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="591b1-142">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="591b1-142">Phone System</span></span>  <br/> |<span data-ttu-id="591b1-143">MCOEV</span><span class="sxs-lookup"><span data-stu-id="591b1-143">MCOEV</span></span>  <br/> |
|<span data-ttu-id="591b1-144">Plano de Chamadas Internacionais</span><span class="sxs-lookup"><span data-stu-id="591b1-144">International and Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="591b1-145">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="591b1-145">MCOPSTN2</span></span>  <br/> |
|<span data-ttu-id="591b1-146">Plano de Chamadas Domésticas</span><span class="sxs-lookup"><span data-stu-id="591b1-146">Domestic Calling Plan</span></span>  <br/> |<span data-ttu-id="591b1-147">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="591b1-147">MCOPSTN1</span></span>  <br/> |
|<span data-ttu-id="591b1-148">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="591b1-148">Communications Credits</span></span>  <br/> |<span data-ttu-id="591b1-149">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="591b1-149">MCOPSTNPP</span></span>  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="591b1-150">Audioconferência: Dicas e scripts para a atribuição de licenças</span><span class="sxs-lookup"><span data-stu-id="591b1-150">PSTN conferencing: Tips and scripts for assigning licenses</span></span>

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a><span data-ttu-id="591b1-151">O que você precisa saber antes de atribuir licenças de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="591b1-151">What you need to know before assigning PSTN conferencing licenses</span></span>

- <span data-ttu-id="591b1-152">**Outros provedores de serviços de Audioconferência**: Se alguém já tiver as configurações definidas para usar um outro provedor de serviços de audioconferência quando você atribuir uma licença de **Audioconferência**, elas serão alteradas para usar a Microsoft como provedor.</span><span class="sxs-lookup"><span data-stu-id="591b1-152">**Third-party conferencing provider**: If someone is already set up to use a third-party dial-in conferencing provider, when you assign them a **Skype for Business PSTN Conferencing** license, they will be changed to use Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="591b1-153">Você pode mudá-las para usar novamente o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="591b1-153">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="591b1-154">Próximas etapas: Depois de atribuir licenças de **Audioconferência**, você precisa atribuir um provedor de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="591b1-154">Next steps: After you assign PSTN conferencing licenses, you need to assign a dial-in conferencing provider.</span></span> <span data-ttu-id="591b1-155">Veja [Atribuir a Microsoft como provedor de audioconferência].</span><span class="sxs-lookup"><span data-stu-id="591b1-155">See [Assign Microsoft as the audio conferencing provider].</span></span>

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="591b1-156">Como atribuir uma licença de Audioconferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="591b1-156">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="591b1-p111">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="591b1-p111">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="591b1-159">Como atribuir licenças de Audioconferência em massa</span><span class="sxs-lookup"><span data-stu-id="591b1-159">How to assign PSTN conferencing licenses in bulk</span></span>

1. <span data-ttu-id="591b1-160">Baixe e instale o [Assistente de Conexão do Microsoft Online Services para Profissionais de TI RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="591b1-160">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="591b1-p112">Baixe e instale o **Módulo do Active Directory do Azure para Microsoft**. Veja as instruções de download e a sintaxe do cmdlet em[Gerenciar o AD do Azure usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).</span><span class="sxs-lookup"><span data-stu-id="591b1-p112">Download and install the **Windows Azure Active Directory Module.** See[Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

    <span data-ttu-id="591b1-163">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças aos usuários:</span><span class="sxs-lookup"><span data-stu-id="591b1-163">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

    <span data-ttu-id="591b1-164">O nome das licenças ou dos produtos no script são indicados em itálico.</span><span class="sxs-lookup"><span data-stu-id="591b1-164">The name of the licenses or product names in the script are listed in italics text.</span></span> <span data-ttu-id="591b1-165">Veja [Nomes de produtos ou SKUs de Audioconferência usados para scripts](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) para obter todos os nomes de produtos.</span><span class="sxs-lookup"><span data-stu-id="591b1-165">See [Dial-in conferencing product names or SKUs used for scripting](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) for all of the product names.</span></span>

    <span data-ttu-id="591b1-166">Este exemplo atribui uma licença Enterprise E3 juntamente com uma licença de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="591b1-166">This example assigns an Enterprise E3 license along with a PSTN Conferencing license.</span></span>

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

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="591b1-167">Nomes de produtos ou SKUs de Audioconferência usados para scripts</span><span class="sxs-lookup"><span data-stu-id="591b1-167">Dial-in conferencing product names or SKUs used for scripting</span></span>
<span data-ttu-id="591b1-168"><a name="sku"> </a></span><span class="sxs-lookup"><span data-stu-id="591b1-168"></span></span>

|<span data-ttu-id="591b1-169">**Nome de produto**</span><span class="sxs-lookup"><span data-stu-id="591b1-169">**Product name**</span></span>|<span data-ttu-id="591b1-170">**Nome de parte SKU**</span><span class="sxs-lookup"><span data-stu-id="591b1-170">**SKU part name**</span></span>|
|:-----|:-----|
|<span data-ttu-id="591b1-171">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="591b1-171">Audio Conferencing</span></span>  <br/> |<span data-ttu-id="591b1-172">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="591b1-172">MCOMEETADV</span></span>  <br/> |
|<span data-ttu-id="591b1-173">Plano 2 Autônomo do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="591b1-173">Skype for Business Online Standalone Plan 2</span></span>  <br/> |<span data-ttu-id="591b1-174">MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="591b1-174">MCOSTANDARD</span></span>  <br/> |
|<span data-ttu-id="591b1-175">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="591b1-175">Enterprise E1</span></span>  <br/> |<span data-ttu-id="591b1-176">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="591b1-176">STANDARDPACK</span></span>  <br/> |
|<span data-ttu-id="591b1-177">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="591b1-177">Enterprise E3</span></span>  <br/> |<span data-ttu-id="591b1-178">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="591b1-178">ENTERPRISEPACK</span></span>  <br/> |
|<span data-ttu-id="591b1-179">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="591b1-179">Enterprise E5 (without Audio Conferencing)</span></span>  <br/> |<span data-ttu-id="591b1-180">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="591b1-180">ENTERPRISEPREMIUM_NOPSTNCONF</span></span>  <br/> |
|<span data-ttu-id="591b1-181">Enterprise E5 (com Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="591b1-181">Enterprise E5 (with dial-in conferencing)</span></span>  <br/> |<span data-ttu-id="591b1-182">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="591b1-182">ENTERPRISEPREMIUM</span></span>  <br/> |

## <a name="communications-credits"></a><span data-ttu-id="591b1-183">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="591b1-183">Communications Credits</span></span>

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a><span data-ttu-id="591b1-184">O que você precisa saber antes de atribuir licenças Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="591b1-184">What you need to know before assigning PSTN Consumption licenses</span></span>

- <span data-ttu-id="591b1-185">**Clientes Enterprise E5**: Mesmo se os seus usuários já tiverem licenças Enterprise E5 atribuídas, recomendamos que você lhes atribua licenças de **Créditos de Comunicação**.</span><span class="sxs-lookup"><span data-stu-id="591b1-185">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them **Skype for Business PSTN Consumption** licenses.</span></span>

- <span data-ttu-id="591b1-186">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="591b1-186">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="591b1-187">Para instruções passo a passo, veja [Configurar Planos de Chamadas](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="591b1-187">For step-by-step setup instructions, see Set up Calling Plans.</span></span>

### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="591b1-188">Como atribuir uma licença de Créditos de Comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="591b1-188">How to assign a PSTN Conferencing license to one user</span></span>

<span data-ttu-id="591b1-p115">As etapas são iguais às da atribuição de uma licença do Office 365. Veja [Atribuir ou remover licenças do Office 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="591b1-p115">The steps are the same as assigning an Office 365 license. See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="591b1-191">Como atribuir licenças de Créditos de Comunicação em massa</span><span class="sxs-lookup"><span data-stu-id="591b1-191">How to assign PSTN conferencing licenses in bulk</span></span>

<span data-ttu-id="591b1-192">Dê uma olhada na amostra de script para atribuição de licenças de **AudioConferência**.</span><span class="sxs-lookup"><span data-stu-id="591b1-192">Take a look at the sample script for assigning PSTN Conferencing licenses.</span></span> <span data-ttu-id="591b1-193">Atualize-o com as informações para atribuição de licenças de **Créditos de Comunicação**.</span><span class="sxs-lookup"><span data-stu-id="591b1-193">Update it with the info for assigning PSTN Consumption licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="591b1-194">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="591b1-194">Related topics</span></span>

[<span data-ttu-id="591b1-195">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="591b1-195">Set up Calling Plans</span></span>](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)

[<span data-ttu-id="591b1-196">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="591b1-196">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)


