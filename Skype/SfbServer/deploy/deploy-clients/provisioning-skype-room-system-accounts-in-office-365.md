---
title: Provisionando contas do Sistema de Sala do Skype no Microsoft 365 e no Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para saber mais sobre como provisionar contas do Sistema de Sala do Skype no Microsoft 365 ou no Office 365.
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093515"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="0cca6-103">Provisionando contas do Sistema de Sala do Skype no Microsoft 365 e no Office 365</span><span class="sxs-lookup"><span data-stu-id="0cca6-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="0cca6-104">Leia este tópico para saber mais sobre como provisionar contas do Sistema de Sala do Skype no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="0cca6-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="0cca6-105">A seção a seguir aborda o provisionamento da conta do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="0cca6-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="0cca6-106">Pré-requisitos do Microsoft 365 e office 365</span><span class="sxs-lookup"><span data-stu-id="0cca6-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="0cca6-107">Seu locatário online deve atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="0cca6-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="0cca6-108">O plano do Microsoft 365 ou office 365 deve incluir o Plano 2 do Skype for Business Online ou o Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="0cca6-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="0cca6-109">Para obter detalhes sobre planos do Skype for Business Online, consulte [a Descrição do serviço do Skype for Business Online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="0cca6-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>
    
- <span data-ttu-id="0cca6-110">Seu locatário deve ter o recurso de conferência do Skype for Business habilitado.</span><span class="sxs-lookup"><span data-stu-id="0cca6-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="0cca6-111">Seu locatário deve ter o Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="0cca6-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="0cca6-112">O administrador remoto do locatário deve ter o seguinte acesso ao PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0cca6-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="0cca6-113">Acesso remoto do PowerShell do Exchange</span><span class="sxs-lookup"><span data-stu-id="0cca6-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="0cca6-114">Acesso remoto do PowerShell do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0cca6-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="0cca6-115">Windows Azure Módulo do Active Directory para Windows PowerShell acessar o acesso ao diretório do Microsoft 365 ou office 365</span><span class="sxs-lookup"><span data-stu-id="0cca6-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="0cca6-116">Para a conta da Sala do Skype, o licenciamento a seguir é necessário:</span><span class="sxs-lookup"><span data-stu-id="0cca6-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="0cca6-117">Uma licença do Skype for Business Online Plan 2 ou Office 365 E1 ou E3 é necessária para habilitar reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="0cca6-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="0cca6-118">Para dar direito à sala com o recurso Enterprise Voice para que a sala possa ser habilitada com um número de telefone, é necessário um Plano 2 do Skype for Business Online com a licença do Sistema de Telefonia ou o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="0cca6-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="0cca6-119">Se você precisar de recursos de discagem de uma reunião, precisará de uma audioconferência e uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="0cca6-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="0cca6-120">Se você precisar de recursos de discagem de uma reunião, precisará de um Plano de Chamada doméstico ou doméstico e internacional.</span><span class="sxs-lookup"><span data-stu-id="0cca6-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="0cca6-121">Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="0cca6-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="0cca6-122">Visão geral do provisionamento</span><span class="sxs-lookup"><span data-stu-id="0cca6-122">Provisioning overview</span></span>

<span data-ttu-id="0cca6-123">O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="0cca6-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Etapas de Provisionamento do Sistema de Sala do Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="0cca6-125">Identificar uma nova sala de conferência</span><span class="sxs-lookup"><span data-stu-id="0cca6-125">Identify a new conference room</span></span>

<span data-ttu-id="0cca6-126">Você pode já ter uma caixa de correio de sala de recursos no Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="0cca6-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="0cca6-127">Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="0cca6-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="0cca6-128">As seções Provisionamento do Exchange Online e Skype for Business Provision fornecem orientações para ambos os tipos de contas.</span><span class="sxs-lookup"><span data-stu-id="0cca6-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="0cca6-129">Por exemplo, digamos que você tenha as duas salas a seguir e gostaria de implantar o Sistema de Salas do Skype para ambas:</span><span class="sxs-lookup"><span data-stu-id="0cca6-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="0cca6-130">Conta de Caixa de Correio de Recurso existente: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0cca6-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="0cca6-131">Nova Conta de Caixa de Correio de Recurso: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="0cca6-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="0cca6-132">Provisionamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="0cca6-132">Exchange Online provisioning</span></span>

<span data-ttu-id="0cca6-133">Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico, [Conectar-se ao PowerShell do Exchange Online.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0cca6-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
<span data-ttu-id="0cca6-134">Para definir uma conta de caixa de correio de sala de recursos existente para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0cca6-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="0cca6-135">Para criar uma nova conta de caixa de correio de recurso do Exchange para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="0cca6-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="0cca6-136">Os comandos anteriores configuram ou criam uma nova conta de caixa de correio de recurso do Exchange para uso do Sistema de Sala do Skype habilitando a conta.</span><span class="sxs-lookup"><span data-stu-id="0cca6-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="0cca6-137">Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0cca6-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="0cca6-138">Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes</span><span class="sxs-lookup"><span data-stu-id="0cca6-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="0cca6-139">Atribuindo uma licença do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0cca6-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="0cca6-140">Agora você pode atribuir uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3) usando o portal administrativo do Microsoft 365 conforme descrito em Atribuir ou remover licenças do [Microsoft 365](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) para empresas ou no licenciamento de complementos do [Skype for Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)</span><span class="sxs-lookup"><span data-stu-id="0cca6-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="0cca6-141">Depois de atribuir uma licença para o Skype for Business Online, você poderá fazer logoff e validar se a conta está ativa usando qualquer cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="0cca6-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="0cca6-142">Provisionamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="0cca6-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="0cca6-143">Depois que uma conta de caixa de correio de sala de recursos tiver sido criada e habilitada como mostrado anteriormente, e você tiver licenciado a conta do Skype For Business Online, a conta será sincronizada da floresta do Exchange Online para a floresta do Skype for Business Online usando a floresta Windows Azure Do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0cca6-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="0cca6-144">As etapas a seguir são necessárias para provisionar a conta do Sistema de Sala do Skype no pool do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="0cca6-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="0cca6-145">Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou para uma conta recém-criada (confrm1 ou confrm2), pois depois de habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business Online da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="0cca6-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="0cca6-146">Criar uma sessão do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="0cca6-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="0cca6-147">Observe que você precisará baixar o módulo [do Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="0cca6-147">Note that you will need to download [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. <span data-ttu-id="0cca6-148">Para habilitar uma conta do Skype Room System para Skype for Business, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0cca6-148">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="0cca6-149">Você pode obter o endereço RegistrarPool onde os usuários do Skype for Business estão em casa de uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:</span><span class="sxs-lookup"><span data-stu-id="0cca6-149">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="0cca6-150">A autenticação multifafação (MFA) não é suportada para contas do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="0cca6-150">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="0cca6-151">Expiração da senha</span><span class="sxs-lookup"><span data-stu-id="0cca6-151">Password expiration</span></span>

<span data-ttu-id="0cca6-152">No Microsoft 365 ou No Office 365, a política de expiração de senha padrão para todas as suas contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente.</span><span class="sxs-lookup"><span data-stu-id="0cca6-152">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="0cca6-153">Para contas do Sistema de Sala do Skype, você pode selecionar a configuração Senha nunca expira com as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="0cca6-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="0cca6-154">Crie uma Windows Azure do Active Directory usando as credenciais de administrador global do locatário.</span><span class="sxs-lookup"><span data-stu-id="0cca6-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="0cca6-155">Definir a configuração Senha nunca expira para a conta de sala do Sistema de Sala do Skype criada anteriormente usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="0cca6-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="0cca6-156">Para obter mais informações, [consulte Configurar seu computador para Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0cca6-156">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="validate"></a><span data-ttu-id="0cca6-157">Validar</span><span class="sxs-lookup"><span data-stu-id="0cca6-157">Validate</span></span>

<span data-ttu-id="0cca6-158">Para validação, você deve poder usar qualquer cliente do Skype for Business para entrar na conta criada.</span><span class="sxs-lookup"><span data-stu-id="0cca6-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>