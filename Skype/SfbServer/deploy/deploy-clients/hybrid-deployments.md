---
title: Implantações híbridas do sistema de salas do Skype
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
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o sistema de salas do Skype em um ambiente híbrido.
ms.openlocfilehash: 5773fac7aa87a6ee8c7c64c68124e48f4be67b66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219671"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="0378c-103">Implantações híbridas do sistema de salas do Skype</span><span class="sxs-lookup"><span data-stu-id="0378c-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="0378c-104">Leia este tópico para saber como implantar o sistema de salas do Skype em um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="0378c-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="0378c-105">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="0378c-105">Hybrid deployments</span></span>

<span data-ttu-id="0378c-106">Siga estas etapas se sua topologia tiver o Skype for Business Server e o Exchange Online e você quiser hospedar a caixa de correio de recurso do sistema de salas do Skype no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0378c-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="0378c-107">Esta seção também aborda um cenário híbrido em que você tem o Exchange Online e o Exchange Server implantados.</span><span class="sxs-lookup"><span data-stu-id="0378c-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="0378c-108">Para fins ilustrativos, usamos o LyncSample.com para o domínio local e o LyncSample.ccstp.net para o domínio online.</span><span class="sxs-lookup"><span data-stu-id="0378c-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="0378c-109">Crie uma caixa de correio de recurso no centro de administração do Exchange (LyncSample.ccsctp.net) conectando-se ao Shell de gerenciamento do Exchange Online, conforme descrito no aprovisionamento do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="0378c-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```powershell
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="0378c-110">Você pode verificar a conectividade do OWA usando o lrstest5@LyncSample.ccsctp.net para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="0378c-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="0378c-111">No centro de administração do Exchange do Microsoft 365 ou do Office 365, adicione um endereço de email lrstest5@LyncSample.com (domínio local) e defina-o como o endereço de resposta.</span><span class="sxs-lookup"><span data-stu-id="0378c-111">In the Microsoft 365 or Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="0378c-112">Criar um lrstest5@LyncSample.com de usuário do Active Directory local, definir o endereço de email como lrstest5@LyncSample.com e definir o endereço de destino como lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="0378c-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="0378c-113">Disparam a sincronização de diretórios e, após a conclusão da sincronização, verifique se os usuários mesclam no AAD e se não é possível alterar as propriedades dos recursos do destinatário no centro de administração do Exchange do Microsoft 365 ou do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0378c-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Microsoft 365 or Office 365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="0378c-114">Verifique a conectividade do OWA usando o lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="0378c-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="0378c-115">(Anteriormente, você verificou a conectividade do OWA usando o domínio online.)</span><span class="sxs-lookup"><span data-stu-id="0378c-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="0378c-116">Após criar a caixa de correio, você pode usar Set-CalendarProcessing no Shell de gerenciamento do Exchange Online para configurar a caixa de correio.</span><span class="sxs-lookup"><span data-stu-id="0378c-116">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox.</span></span> <span data-ttu-id="0378c-117">Consulte as etapas de 3 a 6 sob implantações locais da floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0378c-117">Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="0378c-118">Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de gerenciamento do Exchange e habilite-RemoteMailbox lrstest5@LyncSample.com-RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-Room.</span><span class="sxs-lookup"><span data-stu-id="0378c-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="0378c-119">Em seguida, acione a sincronização de diretório.</span><span class="sxs-lookup"><span data-stu-id="0378c-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="0378c-120">Se você deseja hospedar a caixa de correio do sistema de salas do Skype no Exchange Online, essas etapas do Shell de gerenciamento do Exchange não são necessárias e você pode prosseguir para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="0378c-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="0378c-121">Habilite a conta do sistema de salas do Skype para o Skype for Business executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="0378c-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="0378c-122">Se você tiver o Skype for Business online em vez do Skype for Business Server no cenário acima, depois de provisionar a caixa de correio de recurso do Exchange, Provisione uma conta do Skype for Business conforme descrito em provisionamento do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="0378c-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

