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
description: Para que as pessoas em sua organização possam usar a Transmissão de Reunião do Skype, você precisa habilita-la. Para fazer isso, você precisa saber como usar Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um parceiro da Microsoft para fazer esta etapa para você.
ms.openlocfilehash: 1ba8f11913c932d695806ae4fd30db5e8609530f
ms.sourcegitcommit: ab566ddab9d26440bac1716a975f30e075d0c7b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/14/2021
ms.locfileid: "49865135"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="ef725-105">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="ef725-105">Enable Skype Meeting Broadcast</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef725-106">O Skype for Business Online está se retirando em 31 de julho de 2021, quando o acesso ao serviço terminará.</span><span class="sxs-lookup"><span data-stu-id="ef725-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="ef725-107">Incentivamos os clientes a iniciar a atualização para o Microsoft Teams, o cliente principal para comunicações e trabalho em equipe no Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ef725-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="ef725-108">Para que as pessoas em sua organização possam usar a Transmissão de Reunião do Skype, você precisa habilita-la.</span><span class="sxs-lookup"><span data-stu-id="ef725-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="ef725-109">Para fazer isso, você precisa saber como usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef725-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="ef725-110">Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="ef725-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="ef725-111">O centro de administração do Microsoft Teams substituiu o Centro de administração do Skype for Business (portal herdado).</span><span class="sxs-lookup"><span data-stu-id="ef725-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="ef725-112">Todas as configurações para gerenciar o Skype for Business agora estão no Centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="ef725-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="ef725-113">Você deve ter a função de administrador do [Azure AD](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) de administrador global ou administrador do Skype for Business para gerenciar os recursos do Skype for Business no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="ef725-113">You must be assigned the [Azure AD admin role](https://docs.microsoft.com/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="ef725-114">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="ef725-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="ef725-115">Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ef725-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="ef725-116">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="ef725-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="ef725-117">Entre com sua conta de administrador global ou conta de administrador do Skype for Business em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="ef725-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="ef725-118">No centro de administração, vá para Os Centros **de Administração do**  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="ef725-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="ef725-119">No Centro **de administração do Teams,** vá para Reuniões de Transmissão de Reuniões do **Portal** herdado  >  **e** selecione Habilitar Transmissão de Reunião do  >   **Skype.**</span><span class="sxs-lookup"><span data-stu-id="ef725-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="ef725-120">Habilitar a Transmissão de Reunião do Skype usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef725-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="ef725-121">Verifique se você está executando a versão 3.0 ou superior do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef725-121">Verify that you are running version 3.0 or higher of Windows PowerShell.</span></span>
    
2. <span data-ttu-id="ef725-122">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ef725-122">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
3. <span data-ttu-id="ef725-123">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ef725-123">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
4. <span data-ttu-id="ef725-124">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef725-124">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="ef725-125">Consulte [o Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) para baixar e atualizar Windows PowerShell para a versão 4.0.</span><span class="sxs-lookup"><span data-stu-id="ef725-125">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="ef725-126">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="ef725-126">Restart your computer when you are prompted.</span></span>
    
5. <span data-ttu-id="ef725-p106">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="ef725-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
6. <span data-ttu-id="ef725-130">No **Menu Iniciar,** escolha **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="ef725-130">From the **Start Menu**, choose **Windows PowerShell**.</span></span>
    
7. <span data-ttu-id="ef725-131">Na janela **Windows PowerShell,** conecte-se ao Microsoft 365 ou Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="ef725-131">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
   ```PowerShell
   $Credential = get-credential
   $O365Session = New-CsOnlineSession -Credential $credential
   Import-PSSession $O365Session
   ```

8. <span data-ttu-id="ef725-132">Confirme sua configuração do Transmissão de Reunião do Skype atual executando:</span><span class="sxs-lookup"><span data-stu-id="ef725-132">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="ef725-133">Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.</span><span class="sxs-lookup"><span data-stu-id="ef725-133">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="ef725-135">Habilite o Transmissão de Reunião do Skype para sua organização executando:</span><span class="sxs-lookup"><span data-stu-id="ef725-135">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="ef725-136">Você pode confirmar se a configuração está habilitada executando  `Get-CsBroadcastMeetingConfiguration` novamente.</span><span class="sxs-lookup"><span data-stu-id="ef725-136">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="ef725-138">[!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="ef725-138">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="ef725-p107">Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="ef725-p107">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="ef725-141">Configurar a rede para transmitir reuniões com participantes externos</span><span class="sxs-lookup"><span data-stu-id="ef725-141">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="ef725-142">Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="ef725-142">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="ef725-143">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="ef725-143">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="ef725-144">Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="ef725-144">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="ef725-145">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ef725-145">Related topics</span></span>

[<span data-ttu-id="ef725-146">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ef725-146">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
  
[<span data-ttu-id="ef725-147">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ef725-147">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
 
