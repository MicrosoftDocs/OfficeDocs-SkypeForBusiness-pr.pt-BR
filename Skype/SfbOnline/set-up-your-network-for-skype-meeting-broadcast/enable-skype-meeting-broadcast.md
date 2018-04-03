---
title: Habilitar a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- SMB
description: Antes das pessoas na sua organização podem usar a transmissão do Skype reunião, é necessário habilitá-lo. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um Parceiro Microsoft para realizar essa etapa para você.
ms.openlocfilehash: 6dc6e52d9a91e9ba3ceb32c2be5a8c0b4564902d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="21706-105">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="21706-105">Enable Skype Meeting Broadcast</span></span>

<span data-ttu-id="21706-106">Antes das pessoas na sua organização podem usar a transmissão do Skype reunião, é necessário habilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="21706-106">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="21706-107">Para fazer isso, você precisa saber como usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21706-107">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="21706-108">Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="21706-108">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="21706-p103">Transmissão do Skype reunião está desativado por padrão, porque a distribuição do conteúdo de uma reunião de transmissão mídia usa a rede de entrega de conteúdo (CDN) do Microsoft Azure para atingir escala muito alta para dar suporte a milhares de pessoas assistindo a uma transmissão. O conteúdo de mídia fragmentada passem pela CDN é criptografado e o cache CDN tem uma vida útil limitada. Além disso, o componente do Windows Azure CDN pode não atender ainda elementos todas as cláusulas de modelo da UE lematização da diretiva de proteção de dados da UE. Ao habilitar esse recurso, você reconhece este aviso.</span><span class="sxs-lookup"><span data-stu-id="21706-p103">Skype Meeting Broadcast is turned off by default because distribution of the media content of a broadcast meeting uses Microsoft Azure's Content Delivery Network (CDN) to achieve very high scale to support thousands of people watching a broadcast. The chunked media content passing through the CDN is encrypted, and the CDN cache has a limited lifetime. Also, the Azure CDN component may not yet meet all elements of the EU Model Clauses stemming from the EU Data Protection Directive. By enabling this feature, you acknowledge this notice.</span></span> 
  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="21706-113">Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="21706-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

1. <span data-ttu-id="21706-114">Entre usando sua conta de administrador global do Office 365 em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span><span class="sxs-lookup"><span data-stu-id="21706-114">Sign in with your Office 365 global admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="21706-115">No Centro de Administração do Office 365 vá para **Centros de Administração** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="21706-115">In the Office 365 Admin center go to **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="21706-116">No **Skype para centro de administração de negócios**, vá para **reuniões Online** > **reuniões de difusão**e selecione **Habilitar transmissão de reunião do Skype**.</span><span class="sxs-lookup"><span data-stu-id="21706-116">In the **Skype for Business admin center**, go to **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="21706-117">Habilitar a Transmissão de Reunião do Skype usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="21706-117">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="21706-118">Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="21706-118">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
1. <span data-ttu-id="21706-119">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="21706-119">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="21706-120">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="21706-120">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="21706-p104">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="21706-p104">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="21706-p105">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="21706-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
2. <span data-ttu-id="21706-127">No **Menu Iniciar**, escolha o **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="21706-127">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="21706-128">Na janela do **Windows PowerShell**, conecte-se à sua organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="21706-128">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
  ```
  $Credential = get-credential
  $O365Session = New-CsOnlineSession -Credential $credential
  Import-PSSession $O365Session
  ```

4. <span data-ttu-id="21706-129">Confirme sua configuração do Transmissão de Reunião do Skype atual executando:</span><span class="sxs-lookup"><span data-stu-id="21706-129">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
  ```
  Get-CsBroadcastMeetingConfiguration
  ```

    <span data-ttu-id="21706-130">Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.</span><span class="sxs-lookup"><span data-stu-id="21706-130">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
5. <span data-ttu-id="21706-132">Habilite o Transmissão de Reunião do Skype para sua organização executando:</span><span class="sxs-lookup"><span data-stu-id="21706-132">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
  ```
  Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
  ```

    <span data-ttu-id="21706-133">Você pode confirmar que a configuração é habilitada executando `Get-CsBroadcastMeetingConfiguration` novamente.</span><span class="sxs-lookup"><span data-stu-id="21706-133">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="21706-135">[!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="21706-135">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
6. <span data-ttu-id="21706-p106">Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="21706-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/en-us/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="21706-138">Configurar a rede para transmitir reuniões com participantes externos</span><span class="sxs-lookup"><span data-stu-id="21706-138">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="21706-139">Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="21706-139">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="21706-140">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="21706-140">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="21706-141">Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="21706-141">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="21706-142">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="21706-142">Related topics</span></span>

[<span data-ttu-id="21706-143">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="21706-143">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="21706-144">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="21706-144">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 