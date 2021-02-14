---
title: Criar políticas personalizadas de acesso externo
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
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
description: O Skype for Business Online permite criar políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas predefinidas de acesso externo que podem abranger a maioria dos cenários.
ms.openlocfilehash: 9ec8fbe2e2d1a0d0882a0115bb201021fbbc1a35
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814190"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="6bc7d-104">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="6bc7d-104">Create custom external access policies</span></span>

<span data-ttu-id="6bc7d-105">O Skype for Business Online permite criar políticas de acesso externo adicionais.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="6bc7d-106">Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas predefinidas de acesso externo que podem abranger a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="6bc7d-107">São elas:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-107">These are:</span></span>
  
- <span data-ttu-id="6bc7d-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="6bc7d-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="6bc7d-109">Acesso Federado Somente (_Tag:FederationOnly)_</span><span class="sxs-lookup"><span data-stu-id="6bc7d-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="6bc7d-110">Acesso federado e ao consumidor (_FederationAndPICDefault)_</span><span class="sxs-lookup"><span data-stu-id="6bc7d-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="6bc7d-111">As políticas externas personalizadas permitem criar políticas adicionais que não são cobertas pelas configurações acima.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="6bc7d-112">Quando a política foi criada, você seria obrigado a definir todos os parâmetros necessários e não poderia alterá-los mais tarde.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="6bc7d-113">A criação de novas políticas personalizadas permite controlar recursos como o acesso ao consumidor do Skype ou uma política para desabilitar o áudio/vídeo na nuvem pública, que é algo que não foi abordado com configurações predefinidas.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="6bc7d-114">As políticas de acesso externo personalizado seguem a mesma sintaxe que as políticas de cliente, mobilidade e conferência.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="6bc7d-115">Saiba mais sobre essas configurações [aqui.](https://technet.microsoft.com/library/mt228132.aspx)</span><span class="sxs-lookup"><span data-stu-id="6bc7d-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="6bc7d-116">Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte do aplicativo Clique para Executar do Skype for Business 2016 que oferece suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="6bc7d-117">A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="6bc7d-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-118">**Type**</span></span>|<span data-ttu-id="6bc7d-119">**Data do lançamento**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-119">**Release date**</span></span>|<span data-ttu-id="6bc7d-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-120">**Version**</span></span>|<span data-ttu-id="6bc7d-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bc7d-122">Primeiro Lançamento do Canal Atual</span><span class="sxs-lookup"><span data-stu-id="6bc7d-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="6bc7d-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="6bc7d-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="6bc7d-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="6bc7d-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="6bc7d-125">Versão 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="6bc7d-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="6bc7d-126">Canal Atual</span><span class="sxs-lookup"><span data-stu-id="6bc7d-126">Current Channel</span></span>  <br/> |<span data-ttu-id="6bc7d-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="6bc7d-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="6bc7d-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="6bc7d-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="6bc7d-129">Versão 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="6bc7d-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="6bc7d-130">Canal Adiado</span><span class="sxs-lookup"><span data-stu-id="6bc7d-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="6bc7d-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="6bc7d-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="6bc7d-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="6bc7d-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="6bc7d-133">Versão 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="6bc7d-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="6bc7d-134">Os usuários que estão usando versões mais antigas de aplicativos do Skype for Business windows ou clientes Mac ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="6bc7d-135">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bc7d-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="6bc7d-136">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="6bc7d-137">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6bc7d-138">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="6bc7d-139">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="6bc7d-140">Confira [o Windows Management Framework 4.0 para](https://www.microsoft.com/download/details.aspx?id=40855) baixar e atualizar o Windows PowerShell para a versão 4.0.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-140">See [Windows Management Framework 4.0](https://www.microsoft.com/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="6bc7d-141">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="6bc7d-142">Você também precisará instalar o módulo do Windows PowerShell para Teams que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-142">You will also need to install the Windows PowerShell module for Teams that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span>
    
    <span data-ttu-id="6bc7d-143">Se precisar saber mais, confira Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx)em uma única janela do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-143">If you need to know more, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="6bc7d-144">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="6bc7d-144">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="6bc7d-145">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-145">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="6bc7d-146">Na janela **do Windows PowerShell,** conecte-se ao Microsoft 365 ou ao Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-146">In the **Windows PowerShell** window, connect to your Microsoft 365 or Office 365 by running:</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="6bc7d-147">No momento, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-147">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
  >
  > <span data-ttu-id="6bc7d-148">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Skype for Business Online Connector.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-148">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business  Online Connector.</span></span>

   ```PowerShell      
    Import-Module -Name MicrosoftTeams
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="6bc7d-149">Se quiser saber mais sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](https://technet.microsoft.com/library/dn568015.aspx) em uma única janela do Windows PowerShell ou Configurar seu computador para [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="6bc7d-149">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="6bc7d-150">Criar uma política de acesso externo personalizado para um usuário</span><span class="sxs-lookup"><span data-stu-id="6bc7d-150">Create a custom external access policy for a user</span></span>

<span data-ttu-id="6bc7d-151">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-151">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="6bc7d-152">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="6bc7d-152">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="6bc7d-153">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-153">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="6bc7d-154">Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-154">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="6bc7d-155">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-155">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="6bc7d-156">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bc7d-156">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="6bc7d-157">Por que você precisa usar o Microsoft 365 ou o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="6bc7d-157">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="6bc7d-158">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="6bc7d-158">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="6bc7d-159">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="6bc7d-159">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="6bc7d-160">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6bc7d-160">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="6bc7d-161">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bc7d-161">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="6bc7d-162">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="6bc7d-162">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="6bc7d-163">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="6bc7d-163">Related topics</span></span>
[<span data-ttu-id="6bc7d-164">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="6bc7d-164">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="6bc7d-165">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="6bc7d-165">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="6bc7d-166">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="6bc7d-166">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
