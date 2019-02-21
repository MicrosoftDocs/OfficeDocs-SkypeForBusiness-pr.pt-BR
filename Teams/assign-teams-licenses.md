---
title: Atribuir licenças de equipes
author: lolaj
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection: Teams_ITAdmin_Help
search.appverid: MET150
ms.reviewer: mikedav
description: Saiba como atribuir licenças para recursos como audioconferências, o sistema telefônico, e planos de chamada.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 078db13179f0e33cb950c00ea58e76f11c8eb405
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2019
ms.locfileid: "30127626"
---
# <a name="assign-microsoft-teams-licenses"></a><span data-ttu-id="d735b-103">Atribuir licenças Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="d735b-103">Assign Microsoft Teams licenses</span></span>

<span data-ttu-id="d735b-104">Você pode atribuir licenças aos usuários recursos como conferência de áudio, sistema telefônico e planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="d735b-104">You can assign licenses to your users for features like Audio Conferencing, Phone System, and Calling Plans.</span></span> <span data-ttu-id="d735b-105">Este artigo explica como adicionar essas licenças em massa e para um usuário individual.</span><span class="sxs-lookup"><span data-stu-id="d735b-105">This article explains how to add these licenses in bulk and for an individual user.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="d735b-106">Consulte [Licenciamento de complemento de equipes da Microsoft](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para obter informações sobre o que você precisará comprar de licenças e como comprá-los, dependendo do seu Office 365 planejar, portanto, os usuários têm a capacidade de chamar números de telefone fora da sua empresa, números para ligações gratuitas e conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d735b-106">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) for information about what licenses you need to buy and how to buy them, depending on your Office 365 plan, so users get Audio Conferencing, toll-free numbers, and the ability to call phone numbers outside your business.</span></span>

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d735b-107">Sistema de Telefonia e Planos de Chamadas: Dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="d735b-107">Phone System and Calling Plans: Tips and scripts for assigning licenses</span></span>

<span data-ttu-id="d735b-108">Aqui está o que você precisa saber antes de atribuir licenças de conferência de áudio, sistema telefônico e planejar a chamada.</span><span class="sxs-lookup"><span data-stu-id="d735b-108">Here’s what you need to know before assigning Audio Conferencing, Phone System, and Calling Plan licenses.</span></span>

- <span data-ttu-id="d735b-109">**Você está usando conectividade PSTN local para usuários híbridos?**</span><span class="sxs-lookup"><span data-stu-id="d735b-109">**Using on-premises PSTN connectivity for hybrid users?**</span></span> <span data-ttu-id="d735b-110">Nesse caso, você precisará atribuir uma licença de sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="d735b-110">If so, you only need to assign a Phone System license.</span></span> <span data-ttu-id="d735b-111">Você não deve atribuir um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="d735b-111">You should NOT assign a Calling Plan.</span></span>

- <span data-ttu-id="d735b-112">**Latência após a atribuição de licenças**: devido a latência entre o Office 365 e Teams da Microsoft, pode demorar até 24 horas para um usuário a ser atribuído um plano de chamar depois que você atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="d735b-112">**Latency after assigning licenses**: Because of the latency between Office 365 and Microsoft Teams, it can take up to 24 hours for a user to be assigned a Calling Plan after you assign a license.</span></span> <span data-ttu-id="d735b-113">Se após 24 horas, o usuário não for atribuído um plano de chamada, entre [em contato no suporte para produtos de negócios - ajuda de admin](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span><span class="sxs-lookup"><span data-stu-id="d735b-113">If after 24 hours the user isn't assigned a Calling Plan, please [contact support for business products - admin help](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).</span></span>

- <span data-ttu-id="d735b-114">**Mensagens de erro**: você receberá uma mensagem de erro se não tiver adquirido o número correto de licenças.</span><span class="sxs-lookup"><span data-stu-id="d735b-114">**Error messages**: You will get an error message if you haven't purchased the correct number of licenses.</span></span> <span data-ttu-id="d735b-115">Se você precisar comprar mais licenças chamar planejar, escolha **comprar mais**.</span><span class="sxs-lookup"><span data-stu-id="d735b-115">If you need to buy more Calling Plan licenses, choose **Buy more**.</span></span>

- <span data-ttu-id="d735b-116">**Próximas etapas**: depois de atribuir licenças chamar planejar para seus usuários, você precisará obter seus números de telefone para sua organização e, em seguida, atribuir esses números para as pessoas na sua organização.</span><span class="sxs-lookup"><span data-stu-id="d735b-116">**Next steps**: After you assign Calling Plan licenses to your users, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d735b-117">Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d735b-117">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a><span data-ttu-id="d735b-118">Atribuir uma licença de sistema telefônico e chamar planejar a um usuário</span><span class="sxs-lookup"><span data-stu-id="d735b-118">Assign a Phone System and Calling Plan license to one user</span></span>

<span data-ttu-id="d735b-119">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d735b-119">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d735b-120">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d735b-120">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a><span data-ttu-id="d735b-121">Atribuir licenças do sistema telefônico e chamar planejar em massa</span><span class="sxs-lookup"><span data-stu-id="d735b-121">Assign Phone System and Calling Plan licenses in bulk</span></span>

1. <span data-ttu-id="d735b-122">Instale o Assistente de Logon do Microsoft Online Services para Profissionais de TI RTW.</span><span class="sxs-lookup"><span data-stu-id="d735b-122">Install the Microsoft Online Services Sign-In Assistant for IT Professionals RTW.</span></span> <span data-ttu-id="d735b-123">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="d735b-123">Don't have the module installed?</span></span> <span data-ttu-id="d735b-124">Consulte [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123) para baixá-lo.</span><span class="sxs-lookup"><span data-stu-id="d735b-124">See [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123) to download it.</span></span>

2. <span data-ttu-id="d735b-125">Instale o Módulo do Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d735b-125">Install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="d735b-126">Não tem o módulo instalado?</span><span class="sxs-lookup"><span data-stu-id="d735b-126">Don't have the module installed?</span></span> <span data-ttu-id="d735b-127">Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d735b-127">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

3. <span data-ttu-id="d735b-128">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="d735b-128">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="d735b-129">Este exemplo atribui uma licença Enterprise E3 junto com um Sistema de Telefonia e uma licença de Plano de Chamadas Domésticas.</span><span class="sxs-lookup"><span data-stu-id="d735b-129">This example assigns an Enterprise E3 license along with a Phone System and a Domestic Calling Plan license.</span></span>

<span data-ttu-id="d735b-130">O nome das licenças ou nomes de produto no script são listados em itálico (consulte o [sistema telefônico e planos de chamar os nomes dos produtos ou SKUs usados para execução de scripts](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), após o exemplo).</span><span class="sxs-lookup"><span data-stu-id="d735b-130">The name of the licenses or product names in the script are listed in italics (see [Phone System and Calling Plans product names or SKUs used for scripting](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), after the example).</span></span>

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d735b-131">Nomes de produto do sistema telefônico e planos de chamar ou SKUs usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="d735b-131">Phone System and Calling Plans product names or SKUs used for scripting</span></span>

| <span data-ttu-id="d735b-132">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="d735b-132">Product name</span></span> | <span data-ttu-id="d735b-133">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="d735b-133">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d735b-134">Enterprise E5 (com Sistema de Telefonia)</span><span class="sxs-lookup"><span data-stu-id="d735b-134">Enterprise E5 (with Phone System)</span></span> | <span data-ttu-id="d735b-135">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d735b-135">ENTERPRISEPREMIUM</span></span> |
| <span data-ttu-id="d735b-136">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d735b-136">Enterprise E3</span></span> | <span data-ttu-id="d735b-137">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d735b-137">ENTERPRISEPACK</span></span> | 
| <span data-ttu-id="d735b-138">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d735b-138">Enterprise E1</span></span> | <span data-ttu-id="d735b-139">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d735b-139">STANDARDPACK</span></span> | 
| <span data-ttu-id="d735b-140">Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="d735b-140">Phone System</span></span> | <span data-ttu-id="d735b-141">MCOEV</span><span class="sxs-lookup"><span data-stu-id="d735b-141">MCOEV</span></span> |
| <span data-ttu-id="d735b-142">Plano de chamadas internacionais do & domésticas</span><span class="sxs-lookup"><span data-stu-id="d735b-142">Domestic & International Calling Plan</span></span> | <span data-ttu-id="d735b-143">MCOPSTN2</span><span class="sxs-lookup"><span data-stu-id="d735b-143">MCOPSTN2</span></span> |
| <span data-ttu-id="d735b-144">Planejar chamar domésticas (3000 minutos por usuário/mês para PR/US/CA, 1200 minutos por usuário/mês para países da UE)</span><span class="sxs-lookup"><span data-stu-id="d735b-144">Domestic Calling Plan (3000 minutes per user/month for US/PR/CA, 1200 minutes per user/month for EU countries)</span></span> | <span data-ttu-id="d735b-145">MCOPSTN1</span><span class="sxs-lookup"><span data-stu-id="d735b-145">MCOPSTN1</span></span> |
| <span data-ttu-id="d735b-146">Planejar chamar domésticas (120 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="d735b-146">Domestic Calling Plan (120 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d735b-147">*Observação: este plano não está disponível nos EUA*.</span><span class="sxs-lookup"><span data-stu-id="d735b-147">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="d735b-148">MCOPSTN5</span><span class="sxs-lookup"><span data-stu-id="d735b-148">MCOPSTN5</span></span> |
| <span data-ttu-id="d735b-149">Planejar chamar domésticas (240 minutos por usuário/mês para cada país)</span><span class="sxs-lookup"><span data-stu-id="d735b-149">Domestic Calling Plan (240 minutes per user/month for each country)</span></span> </br><span data-ttu-id="d735b-150">*Observação: este plano não está disponível nos EUA*.</span><span class="sxs-lookup"><span data-stu-id="d735b-150">*Note: This plan is not available in US*.</span></span> | <span data-ttu-id="d735b-151">MCOPSTN6</span><span class="sxs-lookup"><span data-stu-id="d735b-151">MCOPSTN6</span></span> |
| <span data-ttu-id="d735b-152">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="d735b-152">Communications Credits</span></span> | <span data-ttu-id="d735b-153">MCOPSTNPP</span><span class="sxs-lookup"><span data-stu-id="d735b-153">MCOPSTNPP</span></span> | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a><span data-ttu-id="d735b-154">Conferência de áudio: dicas e scripts para atribuir licenças</span><span class="sxs-lookup"><span data-stu-id="d735b-154">Audio Conferencing: tips and scripts for assigning licenses</span></span>

<span data-ttu-id="d735b-155">Aqui está o que você precisa saber antes de atribuir licenças de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d735b-155">Here's what you need to know before assigning Audio Conferencing licenses.</span></span>

- <span data-ttu-id="d735b-156">**Provedor de serviços de audioconferência de terceiros**: se alguém já estiver configurado para usar um provedor de serviços de audioconferência de terceiros, quando você atribuir uma licença de serviços de audioconferência, eles serão alterados para usar o Microsoft como um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d735b-156">**Third-party audio conferencing provider**: If someone is already set up to use a third-party audio conferencing provider, when you assign them an Audio Conferencing license, they will be changed to use Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="d735b-157">Você poderá mudá-lo de volta para o provedor terceirizado.</span><span class="sxs-lookup"><span data-stu-id="d735b-157">You can change them back to the third-party provider.</span></span>

- <span data-ttu-id="d735b-158">**Próximas etapas**: depois de atribuir licenças de serviços de audioconferência, você precisa atribuir a um provedor de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="d735b-158">**Next steps**: After you assign Audio Conferencing licenses, you need to assign an audio conferencing provider.</span></span> <span data-ttu-id="d735b-159">Consulte [Atribuir Microsoft como um provedor de serviços de audioconferência](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span><span class="sxs-lookup"><span data-stu-id="d735b-159">See [Assign Microsoft as the audio conferencing provider](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

## <a name="assign-an-audio-conferencing-license-to-one-user"></a><span data-ttu-id="d735b-160">Atribuir uma licença de conferência de áudio a um usuário</span><span class="sxs-lookup"><span data-stu-id="d735b-160">Assign an Audio Conferencing license to one user</span></span>

<span data-ttu-id="d735b-161">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d735b-161">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d735b-162">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d735b-162">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-audio-conferencing-licenses-in-bulk"></a><span data-ttu-id="d735b-163">Atribuir licenças de conferência de áudio em massa</span><span class="sxs-lookup"><span data-stu-id="d735b-163">Assign Audio Conferencing licenses in bulk</span></span>

1. <span data-ttu-id="d735b-164">Baixe e instale o [Assistente Microsoft Online Services entrar para RTW de profissionais de TI](https://go.microsoft.com/fwlink/?LinkId=625123).</span><span class="sxs-lookup"><span data-stu-id="d735b-164">Download and install [Microsoft Online Services Sign-In Assistant for IT Professionals RTW](https://go.microsoft.com/fwlink/?LinkId=625123).</span></span>

2. <span data-ttu-id="d735b-165">Baixe e instale o Módulo Microsoft Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d735b-165">Download and install the Windows Azure Active Directory Module.</span></span> <span data-ttu-id="d735b-166">Consulte [Gerenciar o Azure AD usando o Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) para obter instruções de download e sintaxe do cmdlet.</span><span class="sxs-lookup"><span data-stu-id="d735b-166">See [Manage Azure AD using Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) for download instructions and cmdlet syntax.</span></span>

<span data-ttu-id="d735b-167">Depois de instalar os módulos, use o prompt de comando do Windows PowerShell e a seguinte sintaxe para atribuir as licenças a seus usuários:</span><span class="sxs-lookup"><span data-stu-id="d735b-167">Once you get the modules installed, use the Windows PowerShell command prompt and the following syntax to assign the licenses to your users:</span></span>

<span data-ttu-id="d735b-168">O nome das licenças ou nomes de produto no script são listados em itálico.</span><span class="sxs-lookup"><span data-stu-id="d735b-168">The name of the licenses or product names in the script are listed in italics.</span></span> <span data-ttu-id="d735b-169">Consulte [nomes de produto de conferência de áudio ou SKUS usados para o script](#audio-conferencing-product-names-or-skus-used-for-scripting) de todos os nomes dos produtos.</span><span class="sxs-lookup"><span data-stu-id="d735b-169">See [Audio Conferencing product names or SKUS used for scripting](#audio-conferencing-product-names-or-skus-used-for-scripting) for all of the product names.</span></span>

<span data-ttu-id="d735b-170">Este exemplo atribui uma licença Enterprise E3, juntamente com uma licença de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d735b-170">This example assigns an Enterprise E3 license along with an Audio Conferencing license.</span></span>

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a><span data-ttu-id="d735b-171">Nomes de produto de conferência áudio ou SKUS usados para execução de scripts</span><span class="sxs-lookup"><span data-stu-id="d735b-171">Audio Conferencing product names or SKUS used for scripting</span></span>

| <span data-ttu-id="d735b-172">Nome do produto</span><span class="sxs-lookup"><span data-stu-id="d735b-172">Product name</span></span> | <span data-ttu-id="d735b-173">Nome de parte da SKU</span><span class="sxs-lookup"><span data-stu-id="d735b-173">SKU part name</span></span> |
|--------------|---------------|
| <span data-ttu-id="d735b-174">Serviços de audioconferência (assinatura)</span><span class="sxs-lookup"><span data-stu-id="d735b-174">Audio Conferencing (subscription)</span></span> | <span data-ttu-id="d735b-175">MCOMEETADV</span><span class="sxs-lookup"><span data-stu-id="d735b-175">MCOMEETADV</span></span> | 
| <span data-ttu-id="d735b-176">Áudio conferência pagar por minuto (pré-pago)</span><span class="sxs-lookup"><span data-stu-id="d735b-176">Audio Conferencing Pay Per Minute (pay as you go)</span></span></br><span data-ttu-id="d735b-177">*Observação: requer créditos de comunicações para ser configurado e ativado*.</span><span class="sxs-lookup"><span data-stu-id="d735b-177">*Note: Requires Communications Credits to be set up and enabled*.</span></span> | <span data-ttu-id="d735b-178">MCOMEETACPEA</span><span class="sxs-lookup"><span data-stu-id="d735b-178">MCOMEETACPEA</span></span> |
| <span data-ttu-id="d735b-179">Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="d735b-179">Enterprise E1</span></span> | <span data-ttu-id="d735b-180">STANDARDPACK</span><span class="sxs-lookup"><span data-stu-id="d735b-180">STANDARDPACK</span></span> | 
| <span data-ttu-id="d735b-181">Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="d735b-181">Enterprise E3</span></span> | <span data-ttu-id="d735b-182">ENTERPRISEPACK</span><span class="sxs-lookup"><span data-stu-id="d735b-182">ENTERPRISEPACK</span></span> |
| <span data-ttu-id="d735b-183">Enterprise E5 (sem Audioconferência)</span><span class="sxs-lookup"><span data-stu-id="d735b-183">Enterprise E5 (without Audio Conferencing)</span></span> |  <span data-ttu-id="d735b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span><span class="sxs-lookup"><span data-stu-id="d735b-184">ENTERPRISEPREMIUM_NOPSTNCONF</span></span> |
| <span data-ttu-id="d735b-185">Enterprise E5 (com serviços de audioconferência)</span><span class="sxs-lookup"><span data-stu-id="d735b-185">Enterprise E5 (with Audio Conferencing)</span></span> | <span data-ttu-id="d735b-186">ENTERPRISEPREMIUM</span><span class="sxs-lookup"><span data-stu-id="d735b-186">ENTERPRISEPREMIUM</span></span> |

##  <a name="communications-credits"></a><span data-ttu-id="d735b-187">Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="d735b-187">Communications Credits</span></span>

<span data-ttu-id="d735b-188">Aqui está o que você precisa saber antes de atribuir licenças créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="d735b-188">Here's what you need to know before assigning Communications Credits licenses.</span></span>

- <span data-ttu-id="d735b-189">**Os clientes corporativos E5**: mesmo se os usuários recebem licenças E5 da empresa, ainda recomendamos que você atribuir-lhes Communications créditos licenças.</span><span class="sxs-lookup"><span data-stu-id="d735b-189">**Enterprise E5 customers**: Even if your users are assigned Enterprise E5 licenses, we still recommend that you assign them Communications Credits licenses.</span></span>

- <span data-ttu-id="d735b-190">**Próximas etapas**: após atribuir essas licenças, você precisará obter os números de telefone para a sua organização e atribuí-los aos usuários.</span><span class="sxs-lookup"><span data-stu-id="d735b-190">**Next steps**: After you assign these licenses, you will need to get your phone numbers for your organization, and then assign those numbers to the people in your organization.</span></span> <span data-ttu-id="d735b-191">Para obter instruções detalhadas, consulte [Configurar planos de chamada](set-up-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="d735b-191">For step-by-step instructions, see [Set up Calling Plans](set-up-calling-plans.md).</span></span>

## <a name="assign-a-communications-credits-license-to-one-user"></a><span data-ttu-id="d735b-192">Atribuir uma licença de créditos de comunicação a um usuário</span><span class="sxs-lookup"><span data-stu-id="d735b-192">Assign a Communications Credits license to one user</span></span>

<span data-ttu-id="d735b-193">As etapas são iguais às da atribuição de uma licença do Office 365.</span><span class="sxs-lookup"><span data-stu-id="d735b-193">The steps are the same as assigning an Office 365 license.</span></span> <span data-ttu-id="d735b-194">Veja [Atribuir ou remover licenças de assinatura no Office 365](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="d735b-194">See [Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

## <a name="assign-communications-credits-licenses-in-bulk"></a><span data-ttu-id="d735b-195">Atribuir licenças créditos de comunicações em massa</span><span class="sxs-lookup"><span data-stu-id="d735b-195">Assign Communications Credits licenses in bulk</span></span>

<span data-ttu-id="d735b-196">Dê uma olhada o script de exemplo para atribuir licenças de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="d735b-196">Take a look at the sample script for assigning Audio Conferencing licenses.</span></span> <span data-ttu-id="d735b-197">Atualizá-lo com as informações para atribuir licenças créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="d735b-197">Update it with the info for assigning Communications Credits licenses.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d735b-198">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d735b-198">Related topics</span></span>

[<span data-ttu-id="d735b-199">Configurar Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="d735b-199">Set up Calling Plans</span></span>](set-up-calling-plans.md)
</br>
[<span data-ttu-id="d735b-200">Adicionar fundos e gerenciar Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="d735b-200">Add funds and manage Communications Credits</span></span>](add-funds-and-manage-communications-credits.md)
