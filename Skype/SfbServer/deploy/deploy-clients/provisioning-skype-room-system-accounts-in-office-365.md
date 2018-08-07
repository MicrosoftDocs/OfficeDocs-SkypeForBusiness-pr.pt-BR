---
title: Provisionamento das contas do Sistema de Salas do Skype no Office 365
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.
ms.openlocfilehash: b248168870366db8f685db48197badb3bacf935f
ms.sourcegitcommit: 4660539cf0a6f7fde5de0a68bc4866089962ce80
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2018
ms.locfileid: "22102050"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="8a3c8-103">Provisionamento das contas do Sistema de Salas do Skype no Office 365</span><span class="sxs-lookup"><span data-stu-id="8a3c8-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="8a3c8-104">Leia este tópico para aprender sobre provisionamento de contas do Sistema de Salas do Skype no Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="8a3c8-105">A seção a seguir aborda a conta do sistema de sala do Skype provisionamento para um locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="8a3c8-106">Pré-requisitos do Office 365</span><span class="sxs-lookup"><span data-stu-id="8a3c8-106">Office 365 prerequisites</span></span>

<span data-ttu-id="8a3c8-107">Seu locatário online deve cumprir os seguintes requisitos:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="8a3c8-108">O plano do Office 365 deve incluir Skype para negócios Online plano 2, 3 do plano, ou Office 365 E1, E3 ou E5.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-108">The Office 365 plan must include Skype for Business Online Plan 2, Plan 3, or Office 365 E1, E3 or E5.</span></span>
    
- <span data-ttu-id="8a3c8-109">Seu inquilino deve ter a capacidade de conferência do Skype para negócios habilitado.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-109">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="8a3c8-110">Seu locatário deve ter o Exchange Online habilitado.  </span><span class="sxs-lookup"><span data-stu-id="8a3c8-110">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="8a3c8-111">O administrador remoto do seu locatário deve ter o seguinte acesso PowerShell: </span><span class="sxs-lookup"><span data-stu-id="8a3c8-111">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="8a3c8-112">Acesso PowerShell remoto do Exchange</span><span class="sxs-lookup"><span data-stu-id="8a3c8-112">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="8a3c8-113">Skype para acesso de negócios Online Remote PowerShell</span><span class="sxs-lookup"><span data-stu-id="8a3c8-113">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="8a3c8-114">Windows Azure Active Directory módulo para Windows PowerShell para o acesso ao diretório acesso Office 365</span><span class="sxs-lookup"><span data-stu-id="8a3c8-114">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="8a3c8-115">Para a conta da Sala do Skype, o seguinte licenciamento é exigido:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-115">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="8a3c8-116">Um Skype para negócios Online plano 2 ou Office 365 E1 ou E3 licença é necessária para habilitar Skype reuniões.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-116">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="8a3c8-117">Para dão direito a sala com o recurso de Enterprise Voice para que a sala pode ser habilitada com um número de telefone, um Skype para negócios Online plano 2 com a nuvem complemento de PBX ou Office 365 E5 é necessária (1).</span><span class="sxs-lookup"><span data-stu-id="8a3c8-117">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Cloud PBX Add-on or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="8a3c8-118">A disponibilidade da qualificação de Conferência por PSTN em uma determinada reunião é determinada pela licença do organizador da reunião.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-118">The availability of PSTN Conferencing entitlement within any given meeting is determined by the license of the meeting organizer.</span></span>
    
- <span data-ttu-id="8a3c8-119">Uma licença do Exchange Online não é necessária para a conta da Sala do Skype porque a conta deve ser configurada como uma conta de caixa postal de recursos. </span><span class="sxs-lookup"><span data-stu-id="8a3c8-119">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="8a3c8-120">Visão geral do provisionamento</span><span class="sxs-lookup"><span data-stu-id="8a3c8-120">Provisioning overview</span></span>

<span data-ttu-id="8a3c8-121">O diagrama a seguir fornece uma visão geral da conta do sistema de sala do Skype provisionamento fluxo no Office 365.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-121">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Etapas de provisionamento do Sistemas de Sala do Skype para O365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="8a3c8-123">Identificar uma nova sala de conferência </span><span class="sxs-lookup"><span data-stu-id="8a3c8-123">Identify a new conference room</span></span>

<span data-ttu-id="8a3c8-124">Talvez você já tenha uma caixa de correio de sala de recurso no Exchange que fornece o recurso de agendamento, ou você pode criar uma caixa de correio de recurso pela primeira vez facilitar a implantação do sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-124">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="8a3c8-125">Em qualquer caso, você deve identificar uma conta de sala a ser usada em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-125">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="8a3c8-126">A provisão on-line do Exchange e Skype seções de provisão de negócios oferecem diretrizes para ambos os tipos de contas.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-126">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="8a3c8-127">Por exemplo, digamos que você tem as seguintes duas salas e você gostaria de implantar o sistema de sala do Skype para ambos deles:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-127">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="8a3c8-128">Conta existente da caixa de correio do recurso: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8a3c8-128">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="8a3c8-129">Nova conta da caixa de correio do recurso: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="8a3c8-129">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="8a3c8-130">Provisionamento do Exchange Online  </span><span class="sxs-lookup"><span data-stu-id="8a3c8-130">Exchange Online provisioning</span></span>

<span data-ttu-id="8a3c8-131">Primeiro, se conecte ao Exchange Online PowerShell, seguindo as instruções no tópico, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="8a3c8-131">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="8a3c8-132">Para definir uma conta de caixa de correio de sala de recurso existente para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-132">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="8a3c8-133">Para criar uma nova conta de caixa de correio de recursos do Exchange para o sistema de sala Skype, execute os seguintes comandos no PowerShell do Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-133">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="8a3c8-134">Os comandos anteriores configurar ou criar uma nova conta de caixa de correio de recurso Exchange para uso do sistema de sala Skype habilitando a conta.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-134">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="8a3c8-135">Depois de criar a caixa de correio, você pode usar o cmdlet Set-CalendarProcessing no PowerShell do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-135">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="8a3c8-136">Consulte as etapas de 3 a 6 sob Implantações locais da floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-136">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="8a3c8-137">Atribuindo uma licença do Skype for Business Online </span><span class="sxs-lookup"><span data-stu-id="8a3c8-137">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="8a3c8-138">Agora você pode atribuir um Skype para Business Online (plano 2) ou Skype licença Business Online (plano 3) usando o portal do Office 365 administrativo conforme descrito em [atribuir ou remover licenças para o Office 365 para empresas](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) ou em [Skype para o complemento de negócios licenciamento](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="8a3c8-138">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="8a3c8-139">Depois de atribuir uma licença para Skype para Business Online, você poderá fazer logon e validar se a conta está ativa usando qualquer Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-139">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="8a3c8-140">Provisionamento do Skype for Business Online  </span><span class="sxs-lookup"><span data-stu-id="8a3c8-140">Skype for Business Online provisioning</span></span>

<span data-ttu-id="8a3c8-141">Depois de uma sala de recurso conta da caixa de correio foi criada e habilitada, conforme mostrado anteriormente, e a conta possui licenciado para Skype para Business Online da conta serão sincronizadas da floresta do Exchange Online com Skype para floresta Business Online usando o Floresta do Active Directory do Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-141">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="8a3c8-142">As etapas a seguir são necessárias para provisionar a conta de sistema do Skype sala no Skype para pool Business Online.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-142">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="8a3c8-143">Estas etapas são as mesmas para uma conta existente de caixa de correio de recurso ou de uma conta recém-criada (confrm1 ou confrm2), porque quando estiverem habilitados no Exchange Online, ambos dessas contas serão sincronizados com o Skype para Business Online da mesma maneira:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-143">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="8a3c8-144">Crie uma sessão do PowerShell remoto.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-144">Create a Remote PowerShell session.</span></span> <span data-ttu-id="8a3c8-145">Observe que você precisará baixar Skype para negócios on-line do módulo do conector e o assistente Microsoft Online Services entrar e certifique-se de que o seu computador está configurado.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-145">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="8a3c8-146">Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8a3c8-146">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="8a3c8-147">Para habilitar uma conta de sistema de sala Skype para Skype for Business, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-147">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="8a3c8-148">Você pode obter o RegistrarPool retorna endereço onde sua Skype para usuários comerciais hospedados de uma de suas contas existentes usando o seguinte comando para essa propriedade:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-148">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="8a3c8-149">Expiração da senha</span><span class="sxs-lookup"><span data-stu-id="8a3c8-149">Password expiration</span></span>

<span data-ttu-id="8a3c8-150">No Office 365, a política de expiração de senha padrão para todas as contas de usuário é de 90 dias, a menos que você configure uma política de expiração de senha diferente.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-150">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="8a3c8-151">Para contas de sistema do Skype sala, você pode selecionar a senha nunca expira configuração com as seguintes etapas.</span><span class="sxs-lookup"><span data-stu-id="8a3c8-151">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="8a3c8-152">Crie uma sessão do Windows Azure Active Directory usando suas credenciais de administrador global do locatário. </span><span class="sxs-lookup"><span data-stu-id="8a3c8-152">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="8a3c8-153">Definir a senha nunca expira configuração para a conta de sala do sistema de sala do Skype criada anteriormente usando o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8a3c8-153">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="8a3c8-154">Para obter mais informações, consulte [Configurar o computador para o Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8a3c8-154">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  

