---
title: Bloquear transferências de arquivos ponto a ponto
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9adf9859-de5b-461e-92ea-b6ce4dd2f7c1
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
- Setup
description: No Skype for Business Online, você pode controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações ou parceiros federados.
ms.openlocfilehash: 150fb02daa1dcd7486a5bb495c7fd74f8d4736a1
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814630"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="12f2c-105">Bloquear transferências de arquivos ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="12f2c-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="12f2c-106">No Skype for Business Online, você pode controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes.</span><span class="sxs-lookup"><span data-stu-id="12f2c-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="12f2c-107">No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização.</span><span class="sxs-lookup"><span data-stu-id="12f2c-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="12f2c-108">Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações ou parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="12f2c-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="12f2c-109">Um cenário muito comum é quando você deseja permitir que os usuários internos usem a transferência de arquivos P2P, mas bloqueiem a transferência de arquivos com parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="12f2c-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="12f2c-110">Para esse cenário, você precisa fazer:</span><span class="sxs-lookup"><span data-stu-id="12f2c-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="12f2c-111">Atribua uma política de conferência com a transferência de arquivo P2P habilitada _(EnableP2PFileTransfer_ definida como _True)_ aos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="12f2c-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="12f2c-112">Crie uma política de comunicação de usuário externo global definida para bloquear transferências de arquivo P2P externas (_EnableP2PFileTransfer_ definida como _False)_ e atribua-a a um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="12f2c-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="12f2c-113">Saiba mais sobre essas configurações [aqui.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="12f2c-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="12f2c-114">Se um usuário federado fora da sua organização tentar enviar um arquivo para um usuário no qual a política foi aplicada, ele receberá um erro de Falha **na** Transferência.</span><span class="sxs-lookup"><span data-stu-id="12f2c-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="12f2c-115">E se um usuário tentar enviar um arquivo, ele receberá um erro de transferência de **arquivo.**</span><span class="sxs-lookup"><span data-stu-id="12f2c-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="12f2c-116">Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte de um aplicativo Do Skype for Business 2016 com suporte.</span><span class="sxs-lookup"><span data-stu-id="12f2c-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="12f2c-117">A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:</span><span class="sxs-lookup"><span data-stu-id="12f2c-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="12f2c-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="12f2c-118">**Type**</span></span>|<span data-ttu-id="12f2c-119">**Data do lançamento**</span><span class="sxs-lookup"><span data-stu-id="12f2c-119">**Release date**</span></span>|<span data-ttu-id="12f2c-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="12f2c-120">**Version**</span></span>|<span data-ttu-id="12f2c-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="12f2c-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="12f2c-122">Primeiro Lançamento do Canal Atual</span><span class="sxs-lookup"><span data-stu-id="12f2c-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="12f2c-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="12f2c-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="12f2c-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="12f2c-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="12f2c-125">Versão 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="12f2c-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="12f2c-126">Canal Atual</span><span class="sxs-lookup"><span data-stu-id="12f2c-126">Current Channel</span></span>  <br/> |<span data-ttu-id="12f2c-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="12f2c-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="12f2c-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="12f2c-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="12f2c-129">Versão 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="12f2c-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="12f2c-130">Canal Adiado</span><span class="sxs-lookup"><span data-stu-id="12f2c-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="12f2c-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="12f2c-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="12f2c-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="12f2c-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="12f2c-133">Versão 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="12f2c-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="12f2c-134">Os usuários que estão usando versões mais antigas dos aplicativos do Skype for Business para Windows ou clientes Mac ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="12f2c-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="12f2c-135">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12f2c-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="12f2c-136">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="12f2c-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
    1. <span data-ttu-id="12f2c-137">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="12f2c-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="12f2c-138">Verifique a versão digitando _Get-Host_ na **janela do Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="12f2c-138">Check the version by typing _Get-Host_ in the **Windows PowerShell** window.</span></span>
        
    3. <span data-ttu-id="12f2c-139">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12f2c-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="12f2c-140">Confira [o Windows Management Framework 4.0 para](https://go.microsoft.com/fwlink/?LinkId=716845) baixar e atualizar o Windows PowerShell para a versão 4.0.</span><span class="sxs-lookup"><span data-stu-id="12f2c-140">See [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="12f2c-141">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="12f2c-141">Restart your computer when you are prompted.</span></span>
        
    4. <span data-ttu-id="12f2c-142">Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="12f2c-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> 
    
    <span data-ttu-id="12f2c-143">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12f2c-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="12f2c-144">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="12f2c-144">**Start a Windows PowerShell session**</span></span>
    
    1. <span data-ttu-id="12f2c-145">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="12f2c-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
        
    2. <span data-ttu-id="12f2c-146">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="12f2c-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
        > [!NOTE]
        > <span data-ttu-id="12f2c-147">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="12f2c-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
        >
        > <span data-ttu-id="12f2c-148">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="12f2c-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

       ```PowerShell      
        Import-Module -Name MicrosoftTeams
        $credential = Get-Credential
        $session = New-CsOnlineSession -Credential $credential
        Import-PSSession $session
       ```

   <span data-ttu-id="12f2c-149">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="12f2c-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="12f2c-150">Desabilitar transferências de arquivos P2P para sua organização</span><span class="sxs-lookup"><span data-stu-id="12f2c-150">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="12f2c-151">Por padrão, _EnableP2PFileTransfer_ está habilitado na política global da organização.</span><span class="sxs-lookup"><span data-stu-id="12f2c-151">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="12f2c-152">Quando ele foi criado, seus usuários foram atribuídos a _política BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="12f2c-152">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="12f2c-153">Para permitir transferências P2P para dentro de sua organização, mas bloquear transferências de arquivos externos para outra organização, basta alterá-la em um nível global.</span><span class="sxs-lookup"><span data-stu-id="12f2c-153">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="12f2c-154">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="12f2c-154">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="12f2c-155">Desabilitar transferências de arquivos P2P para um usuário</span><span class="sxs-lookup"><span data-stu-id="12f2c-155">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="12f2c-156">Você pode aplicá-la a um usuário criando uma nova política e concedendo-a a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="12f2c-156">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="12f2c-157">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="12f2c-157">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="12f2c-158">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="12f2c-158">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="12f2c-159">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="12f2c-159">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="12f2c-160">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="12f2c-160">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="12f2c-161">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="12f2c-161">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12f2c-162">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12f2c-162">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="12f2c-163">Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="12f2c-163">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="12f2c-164">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="12f2c-164">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="12f2c-165">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="12f2c-165">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="12f2c-166">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12f2c-166">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="12f2c-167">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12f2c-167">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="12f2c-168">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12f2c-168">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="12f2c-169">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="12f2c-169">Related topics</span></span>
[<span data-ttu-id="12f2c-170">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="12f2c-170">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="12f2c-171">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="12f2c-171">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="12f2c-172">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="12f2c-172">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
