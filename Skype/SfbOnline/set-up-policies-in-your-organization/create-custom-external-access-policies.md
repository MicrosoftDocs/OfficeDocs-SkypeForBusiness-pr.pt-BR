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
description: O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou de conferência, em que você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.
ms.openlocfilehash: 19b022bac8a43c595b07085db921da6a404d9ac7
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41887910"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="1ccf4-104">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="1ccf4-104">Create custom external access policies</span></span>

<span data-ttu-id="1ccf4-105">O Skype for Business Online permite que você crie políticas de acesso externo adicionais.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="1ccf4-106">Ao contrário das políticas de cliente ou de conferência, em que você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="1ccf4-107">São elas:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-107">These are:</span></span>
  
- <span data-ttu-id="1ccf4-108">Sem acesso ao consumidor federado ou Skype (_marca: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="1ccf4-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="1ccf4-109">Somente acesso federado (_marca: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="1ccf4-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="1ccf4-110">Acesso federado e de consumidor (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="1ccf4-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="1ccf4-111">Políticas externas personalizadas permitem que você crie políticas adicionais que não estão incluídas nas configurações acima.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="1ccf4-112">Após a criação da política, você será solicitado a definir todos os parâmetros obrigatórios e não poderá alterá-los mais tarde.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="1ccf4-113">A criação de novas políticas personalizadas permite que você controle recursos como o acesso do consumidor do Skype ou uma política para desabilitar o áudio/vídeo de nuvem pública, que é algo que não está coberto por configurações predefinidas.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="1ccf4-114">As políticas personalizadas de acesso externo seguem a mesma sintaxe das políticas de cliente, mobilidade e conferência.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="1ccf4-115">Você pode saber mais sobre essas configurações [aqui](https://technet.microsoft.com/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ccf4-115">You can find out more about those settings [here](https://technet.microsoft.com/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="1ccf4-116">Para fazer isso funcionar, o usuário deve estar usando uma versão com suporte do 2016 clique para executar o aplicativo Skype for Business compatível com ele.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="1ccf4-117">A seguinte versão mínima do Skype for Business 2016 clique para executar cliente é necessária:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="1ccf4-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-118">**Type**</span></span>|<span data-ttu-id="1ccf4-119">**Data do lançamento**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-119">**Release date**</span></span>|<span data-ttu-id="1ccf4-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-120">**Version**</span></span>|<span data-ttu-id="1ccf4-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ccf4-122">Primeiro lançamento do canal atual</span><span class="sxs-lookup"><span data-stu-id="1ccf4-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="1ccf4-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="1ccf4-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="1ccf4-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="1ccf4-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="1ccf4-125">Versão 1611 (Build 7571,2006)</span><span class="sxs-lookup"><span data-stu-id="1ccf4-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="1ccf4-126">Canal atual</span><span class="sxs-lookup"><span data-stu-id="1ccf4-126">Current Channel</span></span>  <br/> |<span data-ttu-id="1ccf4-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="1ccf4-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="1ccf4-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="1ccf4-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="1ccf4-129">Versão 1611 (Build 7571,2072)</span><span class="sxs-lookup"><span data-stu-id="1ccf4-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="1ccf4-130">Canal adiado</span><span class="sxs-lookup"><span data-stu-id="1ccf4-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="1ccf4-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="1ccf4-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="1ccf4-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="1ccf4-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="1ccf4-133">Versão 1609 (Build 7369,2118)</span><span class="sxs-lookup"><span data-stu-id="1ccf4-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="1ccf4-134">Os usuários que usam versões mais antigas dos aplicativos do Windows ou clientes Mac do Skype for Business ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="1ccf4-135">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ccf4-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="1ccf4-136">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="1ccf4-137">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1ccf4-138">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="1ccf4-139">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-139">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell.</span></span> <span data-ttu-id="1ccf4-140">Consulte [Windows Management Framework 4,0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para baixar e atualizar o Windows PowerShell para a versão 4,0.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-140">See [Windows Management Framework 4.0](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0.</span></span> <span data-ttu-id="1ccf4-141">Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-141">Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="1ccf4-p106">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="1ccf4-145">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="1ccf4-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="1ccf4-146">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="1ccf4-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="1ccf4-147">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1ccf4-148">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1ccf4-149">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

   ```PowerShell      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

   <span data-ttu-id="1ccf4-150">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) ou [configurar seu computador para Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="1ccf4-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/library/dn568015.aspx) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="1ccf4-151">Criar uma política de acesso externo personalizada para um usuário</span><span class="sxs-lookup"><span data-stu-id="1ccf4-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="1ccf4-152">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-152">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="1ccf4-153">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="1ccf4-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="1ccf4-154">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1ccf4-155">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1ccf4-156">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="1ccf4-157">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ccf4-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="1ccf4-158">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="1ccf4-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="1ccf4-159">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft 365, como quando você está usando alterações de configuração para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="1ccf4-159">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1ccf4-160">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1ccf4-160">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="1ccf4-161">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ccf4-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="1ccf4-162">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ccf4-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="1ccf4-163">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1ccf4-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="1ccf4-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1ccf4-164">Related topics</span></span>
[<span data-ttu-id="1ccf4-165">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="1ccf4-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="1ccf4-166">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="1ccf4-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="1ccf4-167">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="1ccf4-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 
