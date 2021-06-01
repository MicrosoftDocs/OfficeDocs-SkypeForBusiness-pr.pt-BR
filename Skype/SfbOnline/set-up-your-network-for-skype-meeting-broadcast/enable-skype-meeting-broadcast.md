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
description: Para que as pessoas em sua organização possam usar Reunião do Skype Transmissão, você precisa habilita-la. Para fazer isso, você precisa saber como usar Windows PowerShell. Se você não conhece o Windows PowerShell, considere contratar um Parceiro Microsoft para realizar essa etapa para você.
ms.openlocfilehash: 6cdd7f12483025697b139203907f87f9cd3dc764
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237007"
---
# <a name="enable-skype-meeting-broadcast"></a><span data-ttu-id="d5b5f-105">Habilitar a Transmissão de Reunião do Skype</span><span class="sxs-lookup"><span data-stu-id="d5b5f-105">Enable Skype Meeting Broadcast</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="d5b5f-106">Skype for Business Online está se retirando em 31 de julho de 2021, quando o acesso ao serviço terminará.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-106">Skype for Business Online is retiring on July 31, 2021, at which time access to the service will end.</span></span> <span data-ttu-id="d5b5f-107">Incentivamos os clientes a começar a atualização para Microsoft Teams, o cliente principal para comunicações e trabalho em equipe Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-107">We encourage customers to begin the upgrade to Microsoft Teams, the core client for communications and teamwork in Microsoft 365.</span></span>

<span data-ttu-id="d5b5f-108">Para que as pessoas em sua organização possam usar Reunião do Skype Transmissão, você precisa habilita-la.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-108">Before the people in your organization can use Skype Meeting Broadcast, you need to enable it.</span></span> <span data-ttu-id="d5b5f-109">Para fazer isso, você precisa saber como usar Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-109">To do this, you need to know how to use Windows PowerShell.</span></span> <span data-ttu-id="d5b5f-110">Se você não conhece o Windows PowerShell, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-110">If you don't know Windows PowerShell, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>



> [!NOTE]
> <span data-ttu-id="d5b5f-111">O Microsoft Teams de administração substituiu o Skype for Business de administração (portal herdado).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-111">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="d5b5f-112">Todas as configurações para o Skype for Business agora estão no centro Teams administrador.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-112">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="d5b5f-113">Você deve ter a função de administrador do [Azure AD](/azure/active-directory/roles/permissions-reference) de administrador global ou Skype for Business para gerenciar Skype for Business recursos no centro de administração Teams do Azure.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-113">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="d5b5f-114">Para obter mais informações, confira [Gerenciar as configurações do Skype for Business do centro de Administração do Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-114">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

  
## <a name="enable-skype-meeting-broadcast-using-the-skype-for-business-admin-center"></a><span data-ttu-id="d5b5f-115">Habilitar Transmissão de Reunião do Skype usando o centro de administração do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="d5b5f-115">Enable Skype Meeting Broadcast using the Skype for Business admin center</span></span>

<span data-ttu-id="d5b5f-116">![Um ícone mostrando o logotipo do Skype for Business](../images/sfb-logo-30x30.png) **Usando o centro de administração do Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d5b5f-116">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="d5b5f-117">Entre com sua conta de administrador global ou Skype for Business de administrador em [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home) .</span><span class="sxs-lookup"><span data-stu-id="d5b5f-117">Sign in with your global admin account or Skype for Business admin account at [https://portal.office.com/adminportal/home](https://portal.office.com/adminportal/home).</span></span>
    
2. <span data-ttu-id="d5b5f-118">No centro de administração, vá para **Centros de administração**  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-118">In the admin center, go to **Admin centers** > **Teams**.</span></span>
    
3. <span data-ttu-id="d5b5f-119">No centro **de Teams de** administração, vá para Reuniões de transmissão de transmissão de reuniões do **portal**  >  **herdado** e selecione  >   **Habilitar Reunião do Skype Transmissão**.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-119">In the **Teams admin center**, go to **Legacy portal** > **Online meetings** > **Broadcast meetings**, and then select **Enable Skype Meeting Broadcast**.</span></span>
    
## <a name="enable-skype-meeting-broadcast-using-powershell"></a><span data-ttu-id="d5b5f-120">Habilitar a Transmissão de Reunião do Skype usando o PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5b5f-120">Enable Skype Meeting Broadcast using PowerShell</span></span>

1. <span data-ttu-id="d5b5f-121">Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-121">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d5b5f-122">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="d5b5f-122">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```
3. <span data-ttu-id="d5b5f-123">Confirme sua configuração do Transmissão de Reunião do Skype atual executando:</span><span class="sxs-lookup"><span data-stu-id="d5b5f-123">Confirm your current Skype Meeting Broadcast configuration by running:</span></span>
    
   ```PowerShell
   Get-CsBroadcastMeetingConfiguration
   ```

    <span data-ttu-id="d5b5f-124">Verifique se o parâmetro  _EnableBroadcastMeeting_ está definido como `False`.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-124">Verify that the parameter  _EnableBroadcastMeeting_ is set to `False`.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/44abe30d-d3df-4ca9-9761-603a7ff78723.png)
  
9. <span data-ttu-id="d5b5f-126">Habilite o Transmissão de Reunião do Skype para sua organização executando:</span><span class="sxs-lookup"><span data-stu-id="d5b5f-126">Enable Skype Meeting Broadcast for your organization by running:</span></span>
    
   ```PowerShell
   Set-CsBroadcastMeetingConfiguration -EnableBroadcastMeeting $True
   ```

    <span data-ttu-id="d5b5f-127">Você pode confirmar se a configuração está habilitada executando  `Get-CsBroadcastMeetingConfiguration` novamente.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-127">You can confirm that the setting is enabled by running  `Get-CsBroadcastMeetingConfiguration` again.</span></span>
    
     ![Cmdlet Habilitar Organização para Transmissão de Reunião do Skype.](../images/788515f0-32c9-415a-9235-6bfbe095e6f3.png)
  
    > [!TIP]
    > <span data-ttu-id="d5b5f-129">[!DICA] Depois que você fizer a alteração, ela poderá levar até uma hora para entrar em vigor no portal do Transmissão de Reunião do Skype.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-129">After you make the change, it may take up to an hour to take effect in the Skype Meeting Broadcast portal.</span></span> 
  
10. <span data-ttu-id="d5b5f-p105">Agora os usuários podem realizar reuniões de transmissão com outros usuários na empresa. Para que eles comecem, indique [O que é uma Transmissão de Reunião do Skype?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span><span class="sxs-lookup"><span data-stu-id="d5b5f-p105">Your users can now hold broadcast meetings with other users in your business. To get them started, point them to [What is a Skype Meeting Broadcast?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)</span></span>
    
## <a name="configure-your-network-to-broadcast-meetings-with-external-attendees"></a><span data-ttu-id="d5b5f-132">Configurar a rede para transmitir reuniões com participantes externos</span><span class="sxs-lookup"><span data-stu-id="d5b5f-132">Configure your network to broadcast meetings with external attendees</span></span>

<span data-ttu-id="d5b5f-133">Se tiver um firewall e desejar realizar transmissões com pessoas de fora da empresa (que não fazem parte de uma empresa federada), você precisará configurar a rede usando estas instruções: [Configurar a rede para a Transmissão de Reunião do Skype](set-up-your-network-for-skype-meeting-broadcast.md).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-133">If you have a firewall, and you want to hold broadcasts with people outside of your business (who are not a federated business), you need to configure your network using these instructions: [Set up your network for Skype Meeting Broadcast](set-up-your-network-for-skype-meeting-broadcast.md).</span></span> 
  
<span data-ttu-id="d5b5f-134">Se você não tiver experiência com a configuração do firewall, considere contratar um [Parceiro Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) para realizar essa etapa para você.</span><span class="sxs-lookup"><span data-stu-id="d5b5f-134">If you aren't experienced with configuring your firewall, consider hiring a [Microsoft partner](https://go.microsoft.com/fwlink/?linkid=391089) to do this step for you.</span></span>
  
<span data-ttu-id="d5b5f-135">Para ignorar esta etapa e adicionar outra empresa à federação, veja [Permitir que os usuários entrem em contato com usuários externos do Skype for Business](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span><span class="sxs-lookup"><span data-stu-id="d5b5f-135">To skip this step and instead add another business to your federation, see [Allow users to contact external Skype for Business users](../set-up-skype-for-business-online/allow-users-to-contact-external-skype-for-business-users.md).</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="d5b5f-136">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="d5b5f-136">Related topics</span></span>

[<span data-ttu-id="d5b5f-137">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5b5f-137">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
[<span data-ttu-id="d5b5f-138">Configurar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="d5b5f-138">Set up Skype for Business Online</span></span>](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

  
