---
title: Provisionamento das contas do Sistema de Salas do Skype no Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
ms.openlocfilehash: 74512be2d097ca5f43fbd6a22ff17bba8040dd36
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295446"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="a44db-103">Provisionamento das contas do Sistema de Salas do Skype no Office 365</span><span class="sxs-lookup"><span data-stu-id="a44db-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="a44db-104">Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a44db-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="a44db-105">A seção a seguir aborda a conta do sistema de sala do Skype provisionamento para um locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="a44db-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="a44db-106">Pré-requisitos do Office 365</span><span class="sxs-lookup"><span data-stu-id="a44db-106">Office 365 prerequisites</span></span>

<span data-ttu-id="a44db-107">Seu locatário online deve cumprir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="a44db-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="a44db-108">O plano do Office 365 deve incluir Skype para negócios Online 2 do plano, ou Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="a44db-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="a44db-109">Para obter detalhes sobre Skype para negócios Online planos, consulte o [Skype para negócios Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="a44db-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="a44db-110">Seu inquilino deve ter a capacidade de conferência do Skype para negócios habilitado.</span><span class="sxs-lookup"><span data-stu-id="a44db-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="a44db-111">Seu locatário deve ter o Exchange Online habilitado.  </span><span class="sxs-lookup"><span data-stu-id="a44db-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="a44db-112">O administrador remoto do seu locatário deve ter o seguinte acesso PowerShell: </span><span class="sxs-lookup"><span data-stu-id="a44db-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="a44db-113">Acesso PowerShell remoto do Exchange</span><span class="sxs-lookup"><span data-stu-id="a44db-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="a44db-114">Skype para acesso de negócios Online Remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="a44db-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="a44db-115">Windows Azure Active Directory módulo para Windows PowerShell para o acesso ao diretório acesso Office 365</span><span class="sxs-lookup"><span data-stu-id="a44db-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="a44db-116">Para a conta da Sala do Skype, o seguinte licenciamento é exigido:</span><span class="sxs-lookup"><span data-stu-id="a44db-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="a44db-117">Um Skype para negócios Online plano 2 ou Office 365 E1 ou E3 licença é necessária para habilitar Skype reuniões.</span><span class="sxs-lookup"><span data-stu-id="a44db-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="a44db-118">Para dão direito a sala com o recurso de Enterprise Voice para que a sala pode ser habilitada com um número de telefone, um Skype para negócios Online plano 2 com a licença do sistema telefônico ou Office 365 E5 é necessária (1).</span><span class="sxs-lookup"><span data-stu-id="a44db-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="a44db-119">Se você precisar de recursos de dial-in de uma reunião, você precisará uma conferência de áudio e a licença do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="a44db-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="a44db-120">Se você precisar de recursos de discagem de uma reunião, será necessário um locais ou nacionais e internacionais chamar planejar.</span><span class="sxs-lookup"><span data-stu-id="a44db-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="a44db-121">Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa postal de recursos. </span><span class="sxs-lookup"><span data-stu-id="a44db-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="a44db-122">Visão geral do provisionamento</span><span class="sxs-lookup"><span data-stu-id="a44db-122">Provisioning overview</span></span>

<span data-ttu-id="a44db-123">O diagrama a seguir fornece uma visão geral da conta do sistema de sala do Skype provisionamento fluxo no Office 365.</span><span class="sxs-lookup"><span data-stu-id="a44db-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Etapas de provisionamento do Sistemas de Sala do Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="a44db-125">Identificar uma nova sala de conferência </span><span class="sxs-lookup"><span data-stu-id="a44db-125">Identify a new conference room</span></span>

<span data-ttu-id="a44db-126">Talvez você já tenha uma caixa de correio de sala de recurso no Exchange que fornece o recurso de agendamento, ou você pode criar uma caixa de correio de recurso pela primeira vez facilitar a implantação do sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="a44db-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="a44db-127">Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="a44db-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="a44db-128">A provisão on-line do Exchange e Skype seções de provisão de negócios oferecem diretrizes para ambos os tipos de contas.</span><span class="sxs-lookup"><span data-stu-id="a44db-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="a44db-129">Por exemplo, digamos que você tem as seguintes duas salas e você gostaria de implantar o sistema de sala do Skype para ambos deles:</span><span class="sxs-lookup"><span data-stu-id="a44db-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="a44db-130">Conta existente da caixa de correio do recurso: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a44db-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="a44db-131">Nova conta da caixa de correio do recurso: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="a44db-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="a44db-132">Provisionamento do Exchange Online  </span><span class="sxs-lookup"><span data-stu-id="a44db-132">Exchange Online provisioning</span></span>

<span data-ttu-id="a44db-133">Primeiro, se conecte ao Exchange Online PowerShell, seguindo as instruções no tópico, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="a44db-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="a44db-134">Para definir uma conta de caixa de correio de sala de recurso existente para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a44db-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="a44db-135">Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="a44db-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="a44db-136">Os comandos anteriores configurar ou criar uma nova conta de caixa de correio de recurso Exchange para uso do sistema de sala Skype habilitando a conta.</span><span class="sxs-lookup"><span data-stu-id="a44db-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="a44db-137">Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="a44db-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="a44db-138">Consulte as etapas de 3 a 6 sob Implantações locais da floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="a44db-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="a44db-139">Atribuindo uma licença do Skype for Business Online </span><span class="sxs-lookup"><span data-stu-id="a44db-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="a44db-140">Agora você pode atribuir um Skype para Business Online (plano 2) ou Skype licença Business Online (plano 3) usando o portal do Office 365 administrativo conforme descrito em [atribuir ou remover licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou em [Skype para o complemento de negócios licenciamento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="a44db-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="a44db-141">Depois de atribuir uma licença para Skype para Business Online, você poderá fazer logon e validar se a conta está ativa usando qualquer Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="a44db-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="a44db-142">Provisionamento do Skype for Business Online  </span><span class="sxs-lookup"><span data-stu-id="a44db-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="a44db-143">Depois de uma sala de recurso conta da caixa de correio foi criada e habilitada, conforme mostrado anteriormente, e a conta possui licenciado para Skype para Business Online da conta serão sincronizadas da floresta do Exchange Online com Skype para floresta Business Online usando o Floresta do Active Directory do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="a44db-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="a44db-144">As etapas a seguir são necessárias para provisionar a conta de sistema do Skype sala no Skype para pool Business Online.</span><span class="sxs-lookup"><span data-stu-id="a44db-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="a44db-145">Estas etapas são as mesmas para uma conta existente de caixa de correio de recurso ou de uma conta recém-criada (confrm1 ou confrm2), porque quando estiverem habilitados no Exchange Online, ambos dessas contas serão sincronizados com o Skype para Business Online da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="a44db-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="a44db-146">Crie uma sessão do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="a44db-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="a44db-147">Observe que você precisará baixar Skype para negócios on-line do módulo do conector e o assistente Microsoft Online Services entrar e certifique-se de que o seu computador está configurado.</span><span class="sxs-lookup"><span data-stu-id="a44db-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="a44db-148">Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a44db-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="a44db-149">Para habilitar uma conta de sistema de sala Skype para Skype for Business, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a44db-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="a44db-150">Você pode obter o RegistrarPool retorna endereço onde sua Skype para usuários comerciais hospedados de uma de suas contas existentes usando o seguinte comando para essa propriedade:</span><span class="sxs-lookup"><span data-stu-id="a44db-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="a44db-151">Expiração da senha</span><span class="sxs-lookup"><span data-stu-id="a44db-151">Password expiration</span></span>

<span data-ttu-id="a44db-152">No Office 365, a política de expiração de senha padrão para todas as contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente.</span><span class="sxs-lookup"><span data-stu-id="a44db-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="a44db-153">Para contas de sistema do Skype sala, você pode selecionar a senha nunca expira configuração com as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="a44db-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="a44db-154">Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário. </span><span class="sxs-lookup"><span data-stu-id="a44db-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="a44db-155">Definir a senha nunca expira configuração para a conta de sala do sistema de sala do Skype criada anteriormente usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="a44db-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="a44db-156">Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="a44db-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="a44db-157">Validar</span><span class="sxs-lookup"><span data-stu-id="a44db-157">Validate</span></span>

<span data-ttu-id="a44db-158">Para validação, você deve ser capaz de usar qualquer Skype para o cliente de negócios para entrar com a conta que você criou.</span><span class="sxs-lookup"><span data-stu-id="a44db-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

