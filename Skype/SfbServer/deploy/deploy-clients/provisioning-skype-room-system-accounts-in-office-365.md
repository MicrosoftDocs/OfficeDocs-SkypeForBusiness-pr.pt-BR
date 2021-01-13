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
ms.openlocfilehash: 115dd83751e0da837d9d88351d57a769b7e313da
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820841"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="2a2ee-103">Provisionando contas do Sistema de Sala do Skype no Microsoft 365 e no Office 365</span><span class="sxs-lookup"><span data-stu-id="2a2ee-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="2a2ee-104">Leia este tópico para saber mais sobre como provisionar contas do Sistema de Sala do Skype no Microsoft 365 ou no Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="2a2ee-105">A seção a seguir aborda o provisionamento da conta do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="2a2ee-106">Pré-requisitos do Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="2a2ee-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="2a2ee-107">Seu locatário online deve atender aos seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="2a2ee-108">O plano do Microsoft 365 ou Office 365 deve incluir o Skype for Business Online Plano 2 ou o Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="2a2ee-109">Para obter detalhes sobre os Planos do Skype for Business Online, consulte a [Descrição do Serviço do Skype for Business Online.](https://technet.microsoft.com/library/jj822172.aspx)</span><span class="sxs-lookup"><span data-stu-id="2a2ee-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="2a2ee-110">Seu locatário deve ter a funcionalidade de conferência do Skype for Business habilitada.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="2a2ee-111">Seu locatário deve ter o Exchange Online habilitado.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="2a2ee-112">O administrador remoto do locatário deve ter o seguinte acesso ao PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="2a2ee-113">Acesso ao PowerShell Remoto do Exchange</span><span class="sxs-lookup"><span data-stu-id="2a2ee-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="2a2ee-114">Acesso ao PowerShell Remoto do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2a2ee-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="2a2ee-115">Módulo Do Windows Azure Active Directory para Windows PowerShell para acessar o diretório do Microsoft 365 ou Office 365</span><span class="sxs-lookup"><span data-stu-id="2a2ee-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="2a2ee-116">Para a conta da Sala do Skype, é necessário o seguinte licenciamento:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="2a2ee-117">Uma licença do Skype for Business Online Plano 2 ou Office 365 E1 ou E3 é necessária para habilitar as Reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="2a2ee-118">Para dar direito à sala com a funcionalidade do Enterprise Voice para que a sala possa ser habilitada com um número de telefone, é necessário ter o Skype for Business Online Plano 2 com a licença do Sistema de Telefonia ou o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="2a2ee-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="2a2ee-119">Se precisar de recursos de discagem de uma reunião, você precisará de uma audioconferência e uma licença do Sistema de Telefonia.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="2a2ee-120">Se precisar de recursos de discagem de uma reunião, você precisará de um Plano de Chamada doméstico ou doméstico e internacional.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="2a2ee-121">Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque ela deve ser configurada como uma conta de caixa de correio de recurso.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="2a2ee-122">Visão geral do provisionamento</span><span class="sxs-lookup"><span data-stu-id="2a2ee-122">Provisioning overview</span></span>

<span data-ttu-id="2a2ee-123">O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Etapas de provisionamento do Sistema de Sala do Skype](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="2a2ee-125">Identificar uma nova sala de conferência</span><span class="sxs-lookup"><span data-stu-id="2a2ee-125">Identify a new conference room</span></span>

<span data-ttu-id="2a2ee-126">Você pode já ter uma caixa de correio de sala de recursos no Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="2a2ee-127">De qualquer forma, você deve identificar uma conta de sala a ser usada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="2a2ee-128">As seções Provisão do Exchange Online e Provisão do Skype for Business fornecem orientações para ambos os tipos de contas.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="2a2ee-129">Por exemplo, digamos que você tenha as duas salas a seguir e gostaria de implantar o Sistema de Salas do Skype para ambas:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="2a2ee-130">Conta de Caixa de Correio de Recurso existente: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a2ee-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="2a2ee-131">Nova Conta de Caixa de Correio de Recurso: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2a2ee-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="2a2ee-132">Provisionamento do Exchange Online</span><span class="sxs-lookup"><span data-stu-id="2a2ee-132">Exchange Online provisioning</span></span>

<span data-ttu-id="2a2ee-133">Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico, [Conectar-se ao PowerShell do Exchange Online.](https://go.microsoft.com/fwlink/p/?LinkId=396554)</span><span class="sxs-lookup"><span data-stu-id="2a2ee-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="2a2ee-134">Para definir uma conta de caixa de correio de sala de recursos existente para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="2a2ee-135">Para criar uma nova conta de caixa de correio de recursos do Exchange para o Sistema de Sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="2a2ee-136">Os comandos anteriores configuram ou criam uma nova conta de caixa de correio de recursos do Exchange para uso do Sistema de Sala do Skype habilitando a conta.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="2a2ee-137">Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="2a2ee-138">Consulte as etapas 3 a 6 em Implantações locais de floresta única para obter mais detalhes</span><span class="sxs-lookup"><span data-stu-id="2a2ee-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="2a2ee-139">Atribuindo uma licença do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2a2ee-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="2a2ee-140">Agora você pode atribuir uma licença do Skype for Business Online (Plano 2) ou do Skype for Business Online (Plano 3) usando o portal administrativo do Microsoft 365 conforme descrito em Atribuir ou remover licenças do [Microsoft 365 para](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) empresas ou no licenciamento de complementos do Skype for [Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)</span><span class="sxs-lookup"><span data-stu-id="2a2ee-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="2a2ee-141">Depois de atribuir uma licença para o Skype for Business Online, você poderá entrar e validar se a conta está ativa usando qualquer cliente do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="2a2ee-142">Provisionamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2a2ee-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="2a2ee-143">Depois que uma conta de caixa de correio de sala de recursos tiver sido criada e habilitada como mostrado anteriormente, e você tiver licenciado a conta para o Skype for Business Online, a conta será sincronizada da floresta do Exchange Online para a floresta do Skype for Business Online usando a floresta do Active Directory do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="2a2ee-144">As etapas a seguir são necessárias para provisionar a conta do Sistema de Sala do Skype no pool do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="2a2ee-145">Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou uma conta recém-criada (confrm1 ou confrm2), pois depois de habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business Online da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="2a2ee-146">Crie uma sessão do PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="2a2ee-147">Observe que você precisará baixar o Módulo conector do Skype for Business Online e o Assistente de Sign-In microsoft Online Services e certificar-se de que seu computador está configurado.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="2a2ee-148">Para obter mais informações, [consulte Configurar seu computador para o Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2a2ee-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="2a2ee-149">Para habilitar uma conta do Sistema de Sala do Skype for Business, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="2a2ee-150">Você pode obter o endereço RegistrarPool onde seus usuários do Skype for Business estão a partir de uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="2a2ee-151">A MFA (Autenticação Multifatória) não é suportada para contas do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="2a2ee-152">Expiração da senha</span><span class="sxs-lookup"><span data-stu-id="2a2ee-152">Password expiration</span></span>

<span data-ttu-id="2a2ee-153">No Microsoft 365 ou Office 365, a política de expiração de senha padrão para todas as suas contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-153">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="2a2ee-154">Para contas do Sistema de Sala do Skype, você pode selecionar a configuração Senha nunca expira com as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="2a2ee-155">Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="2a2ee-156">Definir a configuração Senha nunca expira para a conta de sala do Sistema de Sala do Skype criada anteriormente usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a2ee-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="2a2ee-157">Para obter mais informações, [consulte Configurar seu computador para o Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="2a2ee-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="2a2ee-158">Validar</span><span class="sxs-lookup"><span data-stu-id="2a2ee-158">Validate</span></span>

<span data-ttu-id="2a2ee-159">Para validação, você deve ser capaz de usar qualquer cliente do Skype for Business para entrar na conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="2a2ee-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

