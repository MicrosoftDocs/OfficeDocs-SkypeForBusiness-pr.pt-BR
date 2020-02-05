---
title: Provisionamento das contas do Sistema de Salas do Skype no Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
ms.openlocfilehash: 33c3acf2f0fffc69da55468e8c16902ec7fa4f88
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768744"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="2d807-103">Provisionamento das contas do Sistema de Salas do Skype no Office 365</span><span class="sxs-lookup"><span data-stu-id="2d807-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="2d807-104">Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d807-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="2d807-105">A seção a seguir aborda o provisionamento da conta do sistema de sala do Skype para um locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d807-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="2d807-106">Pré-requisitos do Office 365</span><span class="sxs-lookup"><span data-stu-id="2d807-106">Office 365 prerequisites</span></span>

<span data-ttu-id="2d807-107">Seu locatário online deve cumprir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="2d807-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="2d807-108">O plano do Office 365 deve incluir o Skype for Business online plano 2 ou o Office 365 E1, E3 ou e5.</span><span class="sxs-lookup"><span data-stu-id="2d807-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="2d807-109">Para obter detalhes sobre os planos do Skype for Business Online, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="2d807-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="2d807-110">Seu locatário deve ter a funcionalidade de conferência do Skype for Business habilitada.</span><span class="sxs-lookup"><span data-stu-id="2d807-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="2d807-111">Seu locatário deve ter o Exchange Online habilitado.  </span><span class="sxs-lookup"><span data-stu-id="2d807-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="2d807-112">O administrador remoto do seu locatário deve ter o seguinte acesso PowerShell: </span><span class="sxs-lookup"><span data-stu-id="2d807-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="2d807-113">Acesso PowerShell remoto do Exchange</span><span class="sxs-lookup"><span data-stu-id="2d807-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="2d807-114">Acesso do PowerShell remoto do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2d807-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="2d807-115">Módulo do Windows Azure Active Directory para Windows PowerShell para acessar o acesso a diretório do Office 365</span><span class="sxs-lookup"><span data-stu-id="2d807-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="2d807-116">Para a conta da Sala do Skype, o seguinte licenciamento é exigido:</span><span class="sxs-lookup"><span data-stu-id="2d807-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="2d807-117">É necessária uma licença do Skype for Business online plano 2 ou Office 365 E1 ou E3 para habilitar reuniões do Skype.</span><span class="sxs-lookup"><span data-stu-id="2d807-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="2d807-118">Para entitle a sala com a funcionalidade do Enterprise Voice para que a sala possa ser habilitada com um número de telefone, é necessário um plano 2 do Skype for Business online com a licença do sistema de telefone ou o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="2d807-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="2d807-119">Se precisar de recursos de discagem de uma reunião, você precisará de uma conferência de áudio e uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="2d807-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="2d807-120">Se precisar de recursos de discagem de uma reunião, você precisará de um plano de chamada internacional ou doméstico e internacional.</span><span class="sxs-lookup"><span data-stu-id="2d807-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="2d807-121">Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa postal de recursos. </span><span class="sxs-lookup"><span data-stu-id="2d807-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="2d807-122">Visão geral do provisionamento</span><span class="sxs-lookup"><span data-stu-id="2d807-122">Provisioning overview</span></span>

<span data-ttu-id="2d807-123">O diagrama a seguir fornece uma visão geral do fluxo de provisionamento da conta do sistema de sala do Skype no Office 365.</span><span class="sxs-lookup"><span data-stu-id="2d807-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Etapas do provisionamento do sistema de sala Skype para o O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="2d807-125">Identificar uma nova sala de conferência </span><span class="sxs-lookup"><span data-stu-id="2d807-125">Identify a new conference room</span></span>

<span data-ttu-id="2d807-126">Você pode já ter uma caixa de correio de sala de recursos no Exchange que fornece o recurso de agendamento ou pode estar criando uma caixa de correio de recurso pela primeira vez para facilitar a implantação do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2d807-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="2d807-127">Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="2d807-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="2d807-128">As seções de provisionamento do Exchange Online e do Skype for Business fornecem orientação para os dois tipos de conta.</span><span class="sxs-lookup"><span data-stu-id="2d807-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="2d807-129">Por exemplo, digamos que você tenha as duas salas a seguir e queira implantar o sistema de salas da Skype para ambos:</span><span class="sxs-lookup"><span data-stu-id="2d807-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="2d807-130">Conta existente da caixa de correio do recurso: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2d807-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="2d807-131">Nova conta da caixa de correio do recurso: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="2d807-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="2d807-132">Provisionamento do Exchange Online  </span><span class="sxs-lookup"><span data-stu-id="2d807-132">Exchange Online provisioning</span></span>

<span data-ttu-id="2d807-133">Primeiro, conecte-se ao PowerShell do Exchange Online seguindo as instruções no tópico [conectar-se ao PowerShell do Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="2d807-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="2d807-134">Para definir uma conta de caixa de correio de sala de recursos existente para o sistema de sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2d807-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="2d807-135">Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de sala do Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="2d807-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="2d807-136">Os comandos anteriores configurados ou criar uma nova conta de caixa de correio de recursos do Exchange para o uso do sistema de sala do Skype habilitando a conta.</span><span class="sxs-lookup"><span data-stu-id="2d807-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="2d807-137">Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="2d807-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="2d807-138">Consulte as etapas de 3 a 6 sob Implantações locais da floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="2d807-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="2d807-139">Atribuindo uma licença do Skype for Business Online </span><span class="sxs-lookup"><span data-stu-id="2d807-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="2d807-140">Agora você pode atribuir uma licença do Skype for Business online (plano 2) ou do Skype for Business online (plano 3) usando o portal administrativo do Office 365 conforme descrito em [atribuir ou remover licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou no [Licenciamento do complemento do Skype for Business](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="2d807-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="2d807-141">Depois de atribuir uma licença do Skype for Business Online, você poderá se conectar e validar que a conta está ativa usando qualquer cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="2d807-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="2d807-142">Provisionamento do Skype for Business Online  </span><span class="sxs-lookup"><span data-stu-id="2d807-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="2d807-143">Após a criação e a habilitação da conta de caixa de correio da sala de recursos, conforme mostrado anteriormente, e você tiver licenciado a conta do Skype for Business Online, a conta será sincronizada da floresta do Exchange Online para a floresta do Skype for Business online usando o botão Floresta do Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2d807-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="2d807-144">As etapas a seguir são necessárias para configurar a conta do sistema de sala do Skype no pool do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2d807-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="2d807-145">Essas etapas são as mesmas para uma conta de caixa de correio de recurso existente ou com uma conta recém-criada (confrm1 ou confrm2), como quando elas são habilitadas no Exchange Online, ambas as contas serão sincronizadas com o Skype for Business online da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="2d807-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="2d807-146">Crie uma sessão do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="2d807-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="2d807-147">Observe que você precisará baixar o módulo do conector Skype for Business Online e o assistente de conexão do Microsoft Online Services e verificar se o seu computador está configurado.</span><span class="sxs-lookup"><span data-stu-id="2d807-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="2d807-148">Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d807-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```powershell
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="2d807-149">Para habilitar uma conta do sistema de sala do Skype para o Skype for Business, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2d807-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="2d807-150">Você pode obter o endereço do RegistrarPool em que seus usuários do Skype for Business são hospedados em uma de suas contas existentes usando o seguinte comando para retornar essa propriedade:</span><span class="sxs-lookup"><span data-stu-id="2d807-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="2d807-151">A autenticação multifator (MFA) não tem suporte para contas do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="2d807-151">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="2d807-152">Expiração da senha</span><span class="sxs-lookup"><span data-stu-id="2d807-152">Password expiration</span></span>

<span data-ttu-id="2d807-153">No Office 365, a política de expiração de senha padrão para todas as contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente.</span><span class="sxs-lookup"><span data-stu-id="2d807-153">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="2d807-154">Para contas do sistema de sala do Skype, você pode selecionar a configuração senha nunca expira com as etapas a seguir.</span><span class="sxs-lookup"><span data-stu-id="2d807-154">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="2d807-155">Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário. </span><span class="sxs-lookup"><span data-stu-id="2d807-155">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="2d807-156">Defina a configuração a senha nunca expira para a conta da sala do sistema de sala do Skype criada anteriormente usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2d807-156">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="2d807-157">Para obter mais informações, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="2d807-157">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="2d807-158">Válida</span><span class="sxs-lookup"><span data-stu-id="2d807-158">Validate</span></span>

<span data-ttu-id="2d807-159">Para a validação, você deve ser capaz de usar qualquer cliente Skype for Business para entrar na conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="2d807-159">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

