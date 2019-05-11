---
title: Implantações híbridas do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eba70d88-13b3-4598-95d5-8a343c9e7d26
description: Leia este tópico para saber como implantar o sistema de sala do Skype em um ambiente híbrido.
ms.openlocfilehash: 2f48707fd4e247a952bc17d26284a8a29eba025a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895170"
---
# <a name="skype-room-system-hybrid-deployments"></a><span data-ttu-id="4e719-103">Implantações híbridas do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="4e719-103">Skype Room System hybrid deployments</span></span>

<span data-ttu-id="4e719-104">Leia este tópico para saber como implantar o sistema de sala do Skype em um ambiente híbrido.</span><span class="sxs-lookup"><span data-stu-id="4e719-104">Read this topic to learn how to deploy Skype Room System in a hybrid environment.</span></span>
  
## <a name="hybrid-deployments"></a><span data-ttu-id="4e719-105">Implantações híbridas</span><span class="sxs-lookup"><span data-stu-id="4e719-105">Hybrid deployments</span></span>

<span data-ttu-id="4e719-106">Siga estas etapas se sua topologia tem Skype para Business Server e o Exchange Online, e você deseja hospedar a caixa de correio de recursos de sistema do Skype sala no Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4e719-106">Follow these steps if your topology has Skype for Business Server and Exchange Online, and you want to host the Skype Room System resource mailbox on Exchange Online.</span></span> <span data-ttu-id="4e719-107">Esta seção também abrange um cenário híbrido onde você tem o Exchange Online e o Exchange Server implantados.</span><span class="sxs-lookup"><span data-stu-id="4e719-107">This section also covers a hybrid scenario where you have both Exchange Online and Exchange Server deployed.</span></span>
  
<span data-ttu-id="4e719-108">Para fins ilustrativos, usamos LyncSample.com para o domínio local e LyncSample.ccstp.net para o domínio online.</span><span class="sxs-lookup"><span data-stu-id="4e719-108">For illustrative purpose, we use LyncSample.com for the on-premises domain and LyncSample.ccstp.net for the online domain.</span></span>
  
1. <span data-ttu-id="4e719-109">Crie uma caixa de correio de recurso no Centro de administração do Exchange (LyncSample.ccsctp.net) estabelecendo conexão com o shell de gerenciamento do Exchange Online, conforme descrito no Exchange Online provisionamento.</span><span class="sxs-lookup"><span data-stu-id="4e719-109">Create a resource mailbox in Exchange admin center (LyncSample.ccsctp.net) by connecting to the Exchange Online Management shell as described in Exchange Online Provisioning.</span></span>
    
   ```
   New-Mailbox -room -name "LRS Test 5" -RoomMailboxPassword (ConvertTo-SecureString <password> -AsPlainText -Force) -EnableRoomMailboxAccount $true 
   ```

    <span data-ttu-id="4e719-110">Você pode verificar a conectividade do OWA usando lrstest5@LyncSample.ccsctp.net para fazer logon.</span><span class="sxs-lookup"><span data-stu-id="4e719-110">You can verify OWA connectivity using lrstest5@LyncSample.ccsctp.net to log in.</span></span>
    
2. <span data-ttu-id="4e719-111">No Centro de administração do Exchange do Office 365, adicione um endereço de email lrstest5@LyncSample.com (domínio em prem) e defini-la como o endereço de resposta.</span><span class="sxs-lookup"><span data-stu-id="4e719-111">In the Office 365 Exchange admin center, add an e-mail address lrstest5@LyncSample.com (on-prem domain) and set it as the reply address.</span></span>
    
3. <span data-ttu-id="4e719-112">Criar no prem Active Directory usuário lrstest5@LyncSample.com, defina o endereço de email como lrstest5@LyncSample.com e definir o endereço de destino para lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="4e719-112">Create an on-prem Active Directory user lrstest5@LyncSample.com, set the e-mail address to lrstest5@LyncSample.com, and set the target address to lrstest5@LyncSample.com.</span></span>
    
4. <span data-ttu-id="4e719-113">Acionar a sincronização de diretórios e, depois de sincronização estiver concluída, verifique se os usuários mesclagem em AAD e que não é possível alterar as propriedades em recursos do destinatário Office365 Exchange admin center.</span><span class="sxs-lookup"><span data-stu-id="4e719-113">Trigger directory synchronization, and, after synchronization is complete, verify that users merge in AAD and that you are not able to change properties in recipient's resources in the Office365 Exchange admin center.</span></span>
    
5. <span data-ttu-id="4e719-114">Verifique a conectividade do OWA usando lrstest5@LyncSample.com.</span><span class="sxs-lookup"><span data-stu-id="4e719-114">Verify OWA connectivity using lrstest5@LyncSample.com.</span></span> <span data-ttu-id="4e719-115">(Anteriormente, você verificou a conectividade OWA utilizando o domínio online.)</span><span class="sxs-lookup"><span data-stu-id="4e719-115">(Earlier, you verified OWA connectivity using the online domain.)</span></span>
    
    <span data-ttu-id="4e719-p103">Depois de criar a caixa de correio, você pode utilizar o Set-CalendarProcessing no Shell de Gerenciamento do Exchange Online para configurar a caixa de correio do. Consulte as etapas de 3 a 6 sob Implantações Locais da Floresta única para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="4e719-p103">After creating the mailbox, you can use Set-CalendarProcessing on the Exchange Online Management Shell to configure the mailbox. Refer to steps 3 through 6 under Single Forest On-prem Deployments for more details.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="4e719-118">Se você tiver um ambiente híbrido com o Exchange Server e o Exchange Online, vá para o Shell de gerenciamento do Exchange e Enable-RemoteMailbox lrstest5@LyncSample.com - RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net-sala.</span><span class="sxs-lookup"><span data-stu-id="4e719-118">If you have a hybrid environment with Exchange Server and Exchange Online, go to the Exchange Management Shell and Enable-RemoteMailbox lrstest5@LyncSample.com -RemoteRoutingAddress lrstest5@LyncSample.mail.ccsctp.net -Room.</span></span> <span data-ttu-id="4e719-119">Em seguida, ative a Sincronização de Diretório.</span><span class="sxs-lookup"><span data-stu-id="4e719-119">Then trigger Directory Synchronization.</span></span> 
  
    <span data-ttu-id="4e719-120">Se você quiser hospedar a caixa de correio do sistema do Skype sala no Exchange Online, estas etapas do Shell de gerenciamento do Exchange não são necessárias e prossiga para a etapa 6.</span><span class="sxs-lookup"><span data-stu-id="4e719-120">If you want to host the Skype Room System mailbox in Exchange Online, these Exchange Management Shell steps are not required and you can proceed to step 6.</span></span>
    
6. <span data-ttu-id="4e719-121">Habilite a conta do sistema do Skype sala para Skype para negócios executando o seguinte cmdlet em Skype do Shell de gerenciamento de negócios:</span><span class="sxs-lookup"><span data-stu-id="4e719-121">Enable the Skype Room System account for Skype for Business by running the following cmdlet on Skype for Business Management Shell:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress 'sip: lrstest5@LyncSample.com' -RegistrarPool pool1.child.corp.LyncSample.com -Identity lrstest5@LyncSample.com
   Set-CsMeetingRoom -Identity lrstest5@LyncSample.com -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="4e719-122">Se você tiver Skype para negócios Online em vez do Skype para Business Server na situação acima, em seguida, após a provisionamento a caixa de correio de recursos do Exchange, provisione um Skype para conta comercial, conforme descrito em Skype para provisionamento Online de negócios.</span><span class="sxs-lookup"><span data-stu-id="4e719-122">If you have Skype for Business Online instead of Skype for Business Server in the above scenario, then after provisioning the Exchange resource mailbox, provision a Skype for Business account as described in Skype for Business Online Provisioning.</span></span> 
  

