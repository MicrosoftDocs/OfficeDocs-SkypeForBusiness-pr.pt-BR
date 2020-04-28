---
title: Atribuir licenças do Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Saiba mais sobre como atribuir licenças para recursos como conferência de áudio, sistema telefônico e planos de chamada.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 55d85aae6540c6b5888be848ad08d686bd0da2b1
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905063"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="0185d-103">Atribuir licenças do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0185d-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="0185d-104">Você pode atribuir licenças aos usuários para obter recursos como conferência de áudio, sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="0185d-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="0185d-105">Este artigo explica como adicionar essas licenças em massa e para um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="0185d-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="0185d-106">Consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obter informações sobre quais licenças você precisa comprar e como comprá-las, dependendo do seu plano do Office 365, para que os usuários recebam conferências de áudio, números de chamada gratuita e a capacidade de fazer chamadas para números de telefone de fora da sua empresa.</span><span class="sxs-lookup"><span data-stu-id="0185d-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="0185d-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="0185d-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="0185d-108">Veja aqui o que você precisa saber antes de atribuir licenças de conferência de áudio, sistema telefônico e plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0185d-108">Here's what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="0185d-109">**Você está usando conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="0185d-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="0185d-110">Em caso afirmativo, você só precisa atribuir uma licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="0185d-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="0185d-111">Você não deve atribuir um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="0185d-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="0185d-112">**Latência após a atribuição de licenças**: devido à latência entre o Office 365 e o Microsoft Teams, pode levar até 24 horas para que um usuário receba um plano de chamada após a atribuição de uma licença.</span><span class="sxs-lookup"><span data-stu-id="0185d-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="0185d-113">Se após 24 horas, o usuário não estiver atribuído a um plano de chamadas, [entre em contato com o suporte para produtos empresariais-ajuda para administradores](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="0185d-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="0185d-114">**Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="0185d-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="0185d-115">Se precisar comprar mais licenças do plano de chamadas, escolha **comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="0185d-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="0185d-116">**Próximas etapas**: após atribuir licenças de plano de chamada aos seus usuários, você precisará obter seus números de telefone para a sua organização e atribuir esses números às pessoas de sua organização.</span><span class="sxs-lookup"><span data-stu-id="0185d-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="0185d-117">Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="0185d-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="0185d-118">Atribuir uma licença do sistema telefônico e do plano de chamada a um usuário</span><span class="sxs-lookup"><span data-stu-id="0185d-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="0185d-119">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0185d-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="0185d-120">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="0185d-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="0185d-121">Atribuir licenças do sistema telefônico e do plano de chamada em massa</span><span class="sxs-lookup"><span data-stu-id="0185d-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="0185d-122">Instale o Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW.</span><span class="sxs-lookup"><span data-stu-id="0185d-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="0185d-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="0185d-123">Don't have the module installed?</span></span> <span data-ttu-id="0185d-124">Consulte [Assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123) para fazer o download.</span><span class="sxs-lookup"><span data-stu-id="0185d-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="0185d-125">Instale o Módulo do Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0185d-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="0185d-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="0185d-126">Don't have the module installed?</span></span> <span data-ttu-id="0185d-127">Consulte [gerenciar o Azure ad usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0185d-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="0185d-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="0185d-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="0185d-129">Este exemplo atribui uma licença Enterprise E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.</span><span class="sxs-lookup"><span data-stu-id="0185d-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="0185d-130">O nome das licenças ou nomes de produto no script são listados em itálico (consulte o [sistema telefônico e os planos de chamada e os nomes de produto ou SKUs usados para script](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="0185d-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

```powershell
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

## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="0185d-131">Nomes de produtos ou SKUs dos planos de chamadas e sistema telefônico usados para scripts</span><span class="sxs-lookup"><span data-stu-id="0185d-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="0185d-132">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="0185d-132">Product name</span></span> | <span data-ttu-id="0185d-133">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="0185d-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="0185d-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="0185d-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="0185d-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="0185d-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="0185d-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="0185d-136">Enterprise E3</span></span> | <span data-ttu-id="0185d-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="0185d-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="0185d-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="0185d-138">Enterprise E1</span></span> | <span data-ttu-id="0185d-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="0185d-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="0185d-140">Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="0185d-140">Phone System</span></span> | <span data-ttu-id="0185d-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="0185d-141">MCOEV</span></span> |
| <span data-ttu-id="0185d-142">Plano de chamadas internacionais & domésticas</span><span class="sxs-lookup"><span data-stu-id="0185d-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="0185d-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="0185d-143">MCOPSTN2</span></span> |
| <span data-ttu-id="0185d-144">Plano de chamadas domésticas (3000 minutos por usuário/mês para EUA/PR/CA, 1200 minutos por usuário/mês para países da UE)</span><span class="sxs-lookup"><span data-stu-id="0185d-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="0185d-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="0185d-145">MCOPSTN1</span></span> |
| <span data-ttu-id="0185d-146">Plano de chamadas domésticas (120 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="0185d-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="0185d-147">*Observação: este plano não está disponível para nós*.</span><span class="sxs-lookup"><span data-stu-id="0185d-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="0185d-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="0185d-148">MCOPSTN5</span></span> |
| <span data-ttu-id="0185d-149">Plano de chamadas domésticas (240 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="0185d-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="0185d-150">*Observação: este plano não está disponível para nós*.</span><span class="sxs-lookup"><span data-stu-id="0185d-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="0185d-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="0185d-151">MCOPSTN6</span></span> |
| <span data-ttu-id="0185d-152">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="0185d-152">Communications Credits</span></span> | <span data-ttu-id="0185d-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="0185d-153">MCOPSTNPP</span></span> | 

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="0185d-154">Atribuir uma licença de audioconferência a um usuário</span><span class="sxs-lookup"><span data-stu-id="0185d-154">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="0185d-155">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0185d-155">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="0185d-156">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="0185d-156">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="0185d-157">Atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="0185d-157">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="0185d-158">Baixe e instale [o assistente de conexão do Microsoft Online Services para profissionais de ti RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="0185d-158">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="0185d-159">Baixe e instale o Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0185d-159">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="0185d-160">Consulte [gerenciar o Azure ad usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe de cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0185d-160">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="0185d-161">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="0185d-161">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="0185d-162">O nome das licenças ou nomes de produtos no script são listados em itálico.</span><span class="sxs-lookup"><span data-stu-id="0185d-162">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="0185d-163">Consulte os [nomes de produtos ou SKUs da conferência de áudio](#audio-conferencing-product-names-or-skus-used-for-scripting) para todos os nomes dos produtos.</span><span class="sxs-lookup"><span data-stu-id="0185d-163">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="0185d-164">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="0185d-164">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

```powershell
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

## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="0185d-165">Nomes de produtos ou SKUS da conferência de áudio usados para scripts</span><span class="sxs-lookup"><span data-stu-id="0185d-165">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="0185d-166">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="0185d-166">Product name</span></span> | <span data-ttu-id="0185d-167">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="0185d-167">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="0185d-168">Conferência de áudio (assinatura)</span><span class="sxs-lookup"><span data-stu-id="0185d-168">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="0185d-169">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="0185d-169">MCOMEETADV</span></span> | 
| <span data-ttu-id="0185d-170">Áudio conferência paga por minuto (pré-pago)</span><span class="sxs-lookup"><span data-stu-id="0185d-170">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="0185d-171">*Observação: exige que os créditos de comunicações sejam configurados e habilitados*.</span><span class="sxs-lookup"><span data-stu-id="0185d-171">*Note: Requires Communications Credits to be set up and enabled*.</span></span> |    <span data-ttu-id="0185d-172">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="0185d-172">MCOMEETACPEA</span></span> |
| <span data-ttu-id="0185d-173">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="0185d-173">Enterprise E1</span></span> | <span data-ttu-id="0185d-174">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="0185d-174">STANDARDPACK</span></span> | 
| <span data-ttu-id="0185d-175">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="0185d-175">Enterprise E3</span></span> | <span data-ttu-id="0185d-176">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="0185d-176">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="0185d-177">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="0185d-177">Enterprise E5 (without Audio Conferencing)</span></span> |     <span data-ttu-id="0185d-178">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="0185d-178">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="0185d-179">Enterprise E5 (com conferência de áudio)</span><span class="sxs-lookup"><span data-stu-id="0185d-179">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="0185d-180">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="0185d-180">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="0185d-181">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="0185d-181">Communications Credits</span></span>

<span data-ttu-id="0185d-182">Veja o que você precisa saber antes de atribuir licenças de créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="0185d-182">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="0185d-183">**Clientes Enterprise E5**: mesmo que seus usuários tenham licenças Enterprise E5 atribuídas, ainda recomendamos que você atribua licenças de créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="0185d-183">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="0185d-184">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="0185d-184">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="0185d-185">Para obter instruções passo a passo, consulte [configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="0185d-185">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="0185d-186">Atribuir uma licença de créditos de comunicações a um usuário</span><span class="sxs-lookup"><span data-stu-id="0185d-186">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="0185d-187">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0185d-187">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="0185d-188">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="0185d-188">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="0185d-189">Atribuir licenças de créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="0185d-189">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="0185d-190">Dê uma olhada no exemplo de script para atribuir licenças de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="0185d-190">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="0185d-191">Atualize-o com as informações para atribuir licenças de créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="0185d-191">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="0185d-192">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0185d-192">Related topics</span></span>

[<span data-ttu-id="0185d-193">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="0185d-193">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="0185d-194">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="0185d-194">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
