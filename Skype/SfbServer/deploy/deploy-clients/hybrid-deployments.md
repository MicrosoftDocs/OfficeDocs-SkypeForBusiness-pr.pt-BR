---
title: Implantações híbridas do Sistema de Sala do Skype
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente híbrido.
ms.openlocfilehash: 47be9204155a1ff6cf6e8d9dfa67723a370fec26
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805891"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="9564f-103">Implantações híbridas do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="9564f-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="9564f-104">Leia este tópico para saber como implantar o Sistema de Sala do Skype em um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="9564f-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="9564f-105">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="9564f-105">Hybrid deployments</span></span>

<span data-ttu-id="9564f-106">Siga estas etapas se sua topologia tiver o Skype for Business Server e o Exchange Online e você quiser hospedar a caixa de correio de recursos do Sistema de Sala do Skype no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9564f-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="9564f-107">Esta seção também aborda um cenário híbrido em que você tem o Exchange Online e o Exchange Server implantados.</span><span class="sxs-lookup"><span data-stu-id="9564f-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="9564f-108">Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.</span><span class="sxs-lookup"><span data-stu-id="9564f-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="9564f-109">Crie uma caixa de correio de recursos no centro de administração do Exchange (LyncSample.ccsctp.net) conectando-se ao shell de Gerenciamento do Exchange Online, conforme descrito no Provisionamento do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9564f-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="9564f-110">Você pode verificar a conectividade OWA usando lrstest5@LyncSample.ccsctp.net para fazer logoff.</span><span class="sxs-lookup"><span data-stu-id="9564f-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="9564f-111">No Centro de administração do Microsoft 365 ou Office 365 Exchange, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e de definida como o endereço de resposta.</span><span class="sxs-lookup"><span data-stu-id="9564f-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="9564f-112">Crie um endereço de usuário local do Active Directory lrstest5@LyncSample.com, de definir o endereço de email como lrstest5@LyncSample.com e de definir o endereço de destino como lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="9564f-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="9564f-113">Acionar a sincronização de diretórios e, após a conclusão da sincronização, verifique se os usuários são mesclados no AAD e se você não consegue alterar as propriedades nos recursos do destinatário no Centro de administração do Microsoft 365 ou Office 365 Exchange.</span><span class="sxs-lookup"><span data-stu-id="9564f-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="9564f-114">Verifique a conectividade do OWA usando lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="9564f-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="9564f-115">(Anteriormente, você verificou a conectividade OWA usando o domínio online.)</span><span class="sxs-lookup"><span data-stu-id="9564f-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="9564f-116">Depois de criar a caixa de correio, você pode Set-CalendarProcessing no Shell de Gerenciamento do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="9564f-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="9564f-117">Consulte as etapas de 3 a 6 em Implantações De floresta única no prem para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9564f-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="9564f-118">Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de Gerenciamento do Exchange e Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span><span class="sxs-lookup"><span data-stu-id="9564f-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="9564f-119">Em seguida, acionar a Sincronização de Diretórios.</span><span class="sxs-lookup"><span data-stu-id="9564f-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="9564f-120">Se você deseja hospedar a caixa de correio do Sistema de Sala do Skype no Exchange Online, essas etapas do Shell de Gerenciamento do Exchange não são necessárias e você pode prosseguir para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="9564f-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="9564f-121">Habilita a conta do Sistema de Sala do Skype for Business executando o seguinte cmdlet no Shell de Gerenciamento do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="9564f-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="9564f-122">Se você tiver o Skype for Business Online em vez do Skype for Business Server no cenário acima, depois de provisionar a caixa de correio de recursos do Exchange, provisione uma conta do Skype for Business conforme descrito no Provisionamento do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9564f-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

