---
title: Habilitar a Transmissão de Reunião do Skype
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: micchan
ms.topic: article
ms.assetid: 5299cce0-850e-42dc-b6ae-2d0ee775c4a9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- SMB
description: Antes que as pessoas em sua organização possam usar a transmissão de reunião do Skype, você precisa habilitá-la. Para fazer isso, você precisa saber como usar o Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um parceiro da Microsoft para fazer esta etapa para você.
ms.openlocfilehash: 20d3671beb608413c5d0d61f599f65a47b55732d
ms.sourcegitcommit: a5bc64abb02201cb5c2ff6696f6ef99064e1cae7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753426"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="eff09-105">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="eff09-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eff09-106">O centro de administração do Microsoft Teams substituiu o centro de administração do Skype for Business (Portal herdado).</span><span class="sxs-lookup"><span data-stu-id="eff09-106">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="eff09-107">Todas as configurações para gerenciar o Skype for Business agora estão no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="eff09-107">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="eff09-108">Você deve receber a função de administrador global do [Azure ad](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do teams.</span><span class="sxs-lookup"><span data-stu-id="eff09-108">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="eff09-109">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="eff09-109">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="eff09-110">Antes que as pessoas em sua organização possam usar a transmissão de reunião do Skype, você precisa habilitá-la.</span><span class="sxs-lookup"><span data-stu-id="eff09-110">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="eff09-111">Para fazer isso, você precisa saber como usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eff09-111">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="eff09-112">Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="eff09-112">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="eff09-113">Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="eff09-113">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="eff09-114">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="eff09-114">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="eff09-115">Entre com sua conta de administrador global ou uma conta de administrador do Skype for Business em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="eff09-115">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="eff09-116">No centro de administração, vá para equipes de **centros de administração**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="eff09-116">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="eff09-117">No **centro de administração do teams**, vá para reuniões online do **portal herdado**  >  **Online meetings**  >  **reuniões de transmissão**e selecione **habilitar transmissão de reunião do Skype**.</span><span class="sxs-lookup"><span data-stu-id="eff09-117">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="eff09-118">Habilitar a Transmissão de Reunião do Skype usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="eff09-118">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="eff09-119">Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eff09-119">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="eff09-120">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eff09-120">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="eff09-121">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eff09-121">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="eff09-122">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eff09-122">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="eff09-123">Consulte [Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="eff09-123">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="eff09-124">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="eff09-124">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="eff09-p105">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="eff09-p105">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="eff09-128">No **menu iniciar**, escolha **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="eff09-128">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="eff09-129">Na janela do **Windows PowerShell** , conecte-se ao seu Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="eff09-129">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="eff09-130">Confirme sua configuração do Transmissão de Reunião do Skype atual executando:</span><span class="sxs-lookup"><span data-stu-id="eff09-130">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="eff09-131">Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.</span><span class="sxs-lookup"><span data-stu-id="eff09-131">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="eff09-133">Habilite o Transmissão de Reunião do Skype para sua organização executando:</span><span class="sxs-lookup"><span data-stu-id="eff09-133">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="eff09-134">Você pode confirmar se a configuração está habilitada executando-se  `Get-CsBroadcastMeetingConfiguration` novamente.</span><span class="sxs-lookup"><span data-stu-id="eff09-134">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="eff09-136">[!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="eff09-136">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="eff09-p106">Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="eff09-p106">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="eff09-139">Configurar a rede para transmitir reuniões com participantes externos</span><span class="sxs-lookup"><span data-stu-id="eff09-139">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="eff09-140">Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="eff09-140">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="eff09-141">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="eff09-141">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="eff09-142">Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="eff09-142">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="eff09-143">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="eff09-143">Related topics</span></span>

[<span data-ttu-id="eff09-144">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eff09-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="eff09-145">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eff09-145">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
