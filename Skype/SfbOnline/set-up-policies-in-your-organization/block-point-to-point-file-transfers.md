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
description: No Skype for Business Online, você tem a capacidade de controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes. No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização. Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.
ms.openlocfilehash: 75e7149d73b8693cf5acdeb08365965956da6ca0
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569097"
---
# <a name="block-point-to-point-file-transfers"></a><span data-ttu-id="ac383-105">Bloquear transferências de arquivos ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="ac383-105">Block Point-to-Point file transfers</span></span>

<span data-ttu-id="ac383-106">No Skype for Business Online, você tem a capacidade de controlar transferências de arquivos ponto a ponto (P2P) como parte das configurações de política de conferência existentes.</span><span class="sxs-lookup"><span data-stu-id="ac383-106">In Skype for Business Online, you have ability to control Point-to-Point (P2P) file transfers as part of existing conferencing policy settings.</span></span> <span data-ttu-id="ac383-107">No entanto, isso permite ou bloqueia transferências de arquivos para os usuários se eles estão ou não transferindo arquivos para um usuário que está dentro da mesma organização ou para um usuário federado de outra organização.</span><span class="sxs-lookup"><span data-stu-id="ac383-107">However, this allows or blocks file transfers for users whether or not they are transferring files to a user who is within the same organization or to a federated user from another organization.</span></span> <span data-ttu-id="ac383-108">Seguindo as etapas abaixo, você pode bloquear transferências de arquivos P2P com organizações federadas ou parceiros.</span><span class="sxs-lookup"><span data-stu-id="ac383-108">Following the steps below, you can block P2P file transfers with federated organizations or partners.</span></span>
  
 <span data-ttu-id="ac383-109">Um cenário muito comum é quando você deseja permitir que os usuários internos usem a transferência de arquivos P2P, mas bloqueiem a transferência de arquivos com parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="ac383-109">A very common scenario is when you want to allow internal users to use P2P file transfer but block file transfer with federated partners.</span></span> <span data-ttu-id="ac383-110">Para esse cenário, você precisaria fazer:</span><span class="sxs-lookup"><span data-stu-id="ac383-110">For this scenario, you would need to do:</span></span>
  
- <span data-ttu-id="ac383-111">Atribua uma política de conferência com transferência de arquivo P2P habilitada (_EnableP2PFileTransfer_ definido como _True_) aos usuários em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac383-111">Assign a conferencing policy with P2P file transfer enabled (_EnableP2PFileTransfer_ set to _True_) to users in your organization.</span></span>
    
- <span data-ttu-id="ac383-112">Crie uma política de comunicação externa do usuário global definida para bloquear transferências de arquivos P2P externos (_EnableP2PFileTransfer_ definido como _False_) e atribuí-la a um usuário em sua organização.</span><span class="sxs-lookup"><span data-stu-id="ac383-112">Create a global external user communication policy set to block external P2P file transfers (_EnableP2PFileTransfer_ set to _False_) and assign it to a user in your organization.</span></span> 
    
<span data-ttu-id="ac383-113">Você pode saber mais sobre essas configurações [aqui](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="ac383-113">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="ac383-114">Se um usuário federado fora da sua organização tentar enviar um arquivo para um usuário no qual a política foi aplicada, ele receberá um erro **de** Falha na Transferência.</span><span class="sxs-lookup"><span data-stu-id="ac383-114">If a federated user outside your organization tries to send a file to a user where the policy has been applied, they will receive a **Transfer Failed** error.</span></span> <span data-ttu-id="ac383-115">E se um usuário tentar enviar um arquivo, ele receberá um **erro de** transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="ac383-115">And if a user tries to send a file, they will receive a **File transfer is turned off** error.</span></span>
  
<span data-ttu-id="ac383-116">Para que isso funcione, o usuário deve estar usando uma versão com suporte de um aplicativo do Skype for Business de 2016 que oferece suporte a ela.</span><span class="sxs-lookup"><span data-stu-id="ac383-116">To make this work, the user must be using a supported version of a 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="ac383-117">A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:</span><span class="sxs-lookup"><span data-stu-id="ac383-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="ac383-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ac383-118">**Type**</span></span>|<span data-ttu-id="ac383-119">**Data de lançamento**</span><span class="sxs-lookup"><span data-stu-id="ac383-119">**Release date**</span></span>|<span data-ttu-id="ac383-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="ac383-120">**Version**</span></span>|<span data-ttu-id="ac383-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="ac383-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ac383-122">Primeira versão do Canal Atual</span><span class="sxs-lookup"><span data-stu-id="ac383-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="ac383-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="ac383-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="ac383-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="ac383-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="ac383-125">Versão 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="ac383-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="ac383-126">Canal Atual</span><span class="sxs-lookup"><span data-stu-id="ac383-126">Current Channel</span></span>  <br/> |<span data-ttu-id="ac383-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="ac383-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="ac383-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="ac383-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="ac383-129">Versão 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="ac383-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="ac383-130">Canal Adiado</span><span class="sxs-lookup"><span data-stu-id="ac383-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="ac383-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="ac383-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="ac383-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="ac383-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="ac383-133">Versão 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="ac383-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="ac383-134">Os usuários que estão usando versões mais antigas de aplicativos do Skype for Business ou clientes Mac ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="ac383-134">Users that are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="ac383-135">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac383-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="ac383-136">O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ac383-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="ac383-137">Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="ac383-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="ac383-138">Instale o [módulo do Teams PowerShell](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="ac383-138">Install the [Teams PowerShell module](https://docs.microsoft.com/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="ac383-139">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="ac383-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

    ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="ac383-140">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="ac383-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="disable-p2p-file-transfers-for-your-organization"></a><span data-ttu-id="ac383-141">Desabilitar transferências de arquivos P2P para sua organização</span><span class="sxs-lookup"><span data-stu-id="ac383-141">Disable P2P file transfers for your organization</span></span>

<span data-ttu-id="ac383-142">Por padrão, _EnableP2PFileTransfer_ está habilitado na política global da organização.</span><span class="sxs-lookup"><span data-stu-id="ac383-142">By default, _EnableP2PFileTransfer_ is enabled on the organization's global policy.</span></span> <span data-ttu-id="ac383-143">Quando ele foi criado, seus usuários foram atribuídos à _política BposSAllModality._</span><span class="sxs-lookup"><span data-stu-id="ac383-143">When it was created, your users were assigned the _BposSAllModality_ policy.</span></span>
  
<span data-ttu-id="ac383-144">Para permitir transferências P2P para dentro da sua organização, mas bloquear transferências de arquivos externos para outra organização, você só precisa alterá-la em nível global.</span><span class="sxs-lookup"><span data-stu-id="ac383-144">To allow P2P transfers for inside your organization but block external file transfers to another organization, you just need to change it at a global level.</span></span> <span data-ttu-id="ac383-145">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="ac383-145">To do that, run:</span></span>
    
  ```PowerShell
  Set-CsExternalUserCommunicationPolicy -EnableP2PFileTransfer $False
  ```

## <a name="disable-p2p-file-transfers-for-a-user"></a><span data-ttu-id="ac383-146">Desabilitar transferências de arquivos P2P para um usuário</span><span class="sxs-lookup"><span data-stu-id="ac383-146">Disable P2P file transfers for a user</span></span>

<span data-ttu-id="ac383-147">Você pode aplicar isso a um usuário criando uma nova política e concedendo-a a esse usuário.</span><span class="sxs-lookup"><span data-stu-id="ac383-147">You can apply this to a user by creating a new policy and granting it to that user.</span></span> <span data-ttu-id="ac383-148">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="ac383-148">To do that, run:</span></span> 

```powershell
New-CsExternalUserCommunicationPolicy -Identity BlockExternalFT -EnableP2PFileTransfer $False
```

```powershell
Grant-CsExternalUserCommunicationPolicy -PolicyName BlockExternalFT -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="ac383-149">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="ac383-149">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="ac383-150">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="ac383-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="ac383-151">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="ac383-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="ac383-152">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ac383-152">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="ac383-153">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac383-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="ac383-154">Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac383-154">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="ac383-155">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="ac383-155">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="ac383-156">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ac383-156">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="ac383-157">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ac383-157">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="ac383-158">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac383-158">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="ac383-159">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="ac383-159">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="ac383-160">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ac383-160">Related topics</span></span>
[<span data-ttu-id="ac383-161">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="ac383-161">Create custom external access policies</span></span>](create-custom-external-access-policies.md)

[<span data-ttu-id="ac383-162">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="ac383-162">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="ac383-163">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="ac383-163">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
