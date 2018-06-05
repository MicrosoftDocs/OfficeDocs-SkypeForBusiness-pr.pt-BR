---
title: Criar políticas de acesso externo personalizadas
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 89cbd278-5480-473c-8cd9-04e07e5f9e0b
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Setup
description: Skype para Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários.
ms.openlocfilehash: e166aa9af162fd6432c8932d5842ea0fd00a36b3
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568308"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="edbe5-104">Criar políticas de acesso externo personalizadas</span><span class="sxs-lookup"><span data-stu-id="edbe5-104">Create custom external access policies</span></span>

<span data-ttu-id="edbe5-105">Skype para Business Online permite que você crie políticas de acesso externo adicionais.</span><span class="sxs-lookup"><span data-stu-id="edbe5-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="edbe5-106">Ao contrário de políticas de cliente ou de conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinido que podem abranger a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="edbe5-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="edbe5-107">São elas:</span><span class="sxs-lookup"><span data-stu-id="edbe5-107">These are:</span></span>
  
- <span data-ttu-id="edbe5-108">Não federado ou acesso de consumidor do Skype (_Marca: NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="edbe5-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="edbe5-109">Somente acesso federado (_Marca: FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="edbe5-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="edbe5-110">Federados e consumidor acessar (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="edbe5-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="edbe5-111">Políticas externas personalizadas permitem que você criar adicionais políticas que não estão cobertos pelas configurações acima.</span><span class="sxs-lookup"><span data-stu-id="edbe5-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="edbe5-112">Quando a diretiva tiver sido criada, você poderia ser necessário para configurar todos os parâmetros necessários e não pôde alterá-los mais tarde.</span><span class="sxs-lookup"><span data-stu-id="edbe5-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="edbe5-113">Criando novas políticas personalizadas permitem que você os recursos de controle, como acesso de consumidor do Skype ou uma diretiva para desabilitar público na nuvem áudio/vídeo, que é algo que não foi coberto com configurações predefinidas.</span><span class="sxs-lookup"><span data-stu-id="edbe5-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="edbe5-114">Políticas de acesso externo personalizadas siga a mesma sintaxe de políticas de cliente, mobilidade e conferência.</span><span class="sxs-lookup"><span data-stu-id="edbe5-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="edbe5-115">Você pode encontrar mais informações sobre essas configurações [aqui](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span><span class="sxs-lookup"><span data-stu-id="edbe5-115">You can find out more about those settings [here](https://technet.microsoft.com/en-us/library/mt228132.aspx).</span></span>
  
<span data-ttu-id="edbe5-116">Para que isso funcione, o usuário deve estar usando uma versão compatível do 2016 Skype Click-to-Run para o aplicativo de negócios que lhe fornecer apoio.</span><span class="sxs-lookup"><span data-stu-id="edbe5-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="edbe5-117">A seguinte versão mínima do Skype para negócios 2016 Click-to-Run cliente é necessária:</span><span class="sxs-lookup"><span data-stu-id="edbe5-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="edbe5-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="edbe5-118">**Type**</span></span>|<span data-ttu-id="edbe5-119">**Data de lançamento**</span><span class="sxs-lookup"><span data-stu-id="edbe5-119">**Release date**</span></span>|<span data-ttu-id="edbe5-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="edbe5-120">**Version**</span></span>|<span data-ttu-id="edbe5-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="edbe5-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="edbe5-122">Primeira versão do canal atual</span><span class="sxs-lookup"><span data-stu-id="edbe5-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="edbe5-123">17/11/2016</span><span class="sxs-lookup"><span data-stu-id="edbe5-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="edbe5-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="edbe5-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="edbe5-125">Versão 1611 (compilação 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="edbe5-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="edbe5-126">Canal atual</span><span class="sxs-lookup"><span data-stu-id="edbe5-126">Current Channel</span></span>  <br/> |<span data-ttu-id="edbe5-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="edbe5-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="edbe5-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="edbe5-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="edbe5-129">Versão 1611 (compilação 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="edbe5-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="edbe5-130">Canal adiada</span><span class="sxs-lookup"><span data-stu-id="edbe5-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="edbe5-131">22/2/2017</span><span class="sxs-lookup"><span data-stu-id="edbe5-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="edbe5-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="edbe5-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="edbe5-133">Versão 1609 (compilação 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="edbe5-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="edbe5-134">Usuários que estiverem usando versões mais antigas do Skype para aplicativos do Windows de negócios ou clientes Mac ainda poderá transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="edbe5-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="verify-and-start-windows-powershell"></a><span data-ttu-id="edbe5-135">Verificar e iniciar o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="edbe5-135">Verify and start Windows PowerShell</span></span>

- <span data-ttu-id="edbe5-136">**Verifique se está executando o Windows PowerShell 3.0 ou versão superior**</span><span class="sxs-lookup"><span data-stu-id="edbe5-136">**Check that you are running Windows PowerShell version 3.0 or higher**</span></span>
    
1. <span data-ttu-id="edbe5-137">Para verificar se você está executando a versão 3.0 ou superior: **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="edbe5-137">To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="edbe5-138">Verifique a versão digitando  _Get-Host_ na janela do **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="edbe5-138">Check the version by typing  _Get-Host_ in the **Windows PowerShell** window.</span></span>
    
3. <span data-ttu-id="edbe5-p105">Se você não tiver a versão 3.0 ou superior, deverá baixar e instalar as atualizações do Windows PowerShell. Confira [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) para baixar e atualizar o Windows PowerShell para a versão 4.0. Reinicie o computador quando for solicitado.</span><span class="sxs-lookup"><span data-stu-id="edbe5-p105">If you don't have version 3.0 or higher, you need to download and install updates to Windows PowerShell. See [Windows Management Framework 4.0 ](https://www.microsoft.com/en-us/download/details.aspx?id=40855) to download and update Windows PowerShell to version 4.0. Restart your computer when you are prompted.</span></span>
    
4. <span data-ttu-id="edbe5-p106">Você também precisará instalar o módulo do Windows PowerShell para Skype for Business Online, que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo do Windows PowerShell para o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Se for solicitado, reinicie o seu computador.</span><span class="sxs-lookup"><span data-stu-id="edbe5-p106">You will also need to install the Windows PowerShell module for Skype for Business Online that enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688). Restart your computer if you are prompted.</span></span>
    
    <span data-ttu-id="edbe5-145">Se precisar saber mais, confira [Conectar-se a todos os serviços do Office 365 usando uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span><span class="sxs-lookup"><span data-stu-id="edbe5-145">If you need to know more, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx).</span></span>
    
- <span data-ttu-id="edbe5-146">**Iniciar uma sessão do Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="edbe5-146">**Start a Windows PowerShell session**</span></span>
    
1. <span data-ttu-id="edbe5-147">No **Menu Iniciar** > **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="edbe5-147">From the **Start Menu** > **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="edbe5-148">Na janela do **Windows PowerShell**, conecte-se à organização do Office 365 executando:</span><span class="sxs-lookup"><span data-stu-id="edbe5-148">In the **Windows PowerShell** window, connect to your Office 365 organization by running:</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="edbe5-149">[!OBSERVAçãO] Execute o comando **Import-Module** apenas quando usar o módulo do Windows PowerShell do Skype for Business Online pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="edbe5-149">You only have to run the **Import-Module** command the first time you use the Skype for Business Online Windows PowerShell module.</span></span>

  ```      
    Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

  <span data-ttu-id="edbe5-150">Se você quiser obter mais informações sobre como iniciar o Windows PowerShell, consulte [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) ou [Conectando-se ao Skype para negócios Online usando o Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="edbe5-150">If you want more information about starting Windows PowerShell, see [Connect to all Office 365 services in a single Windows PowerShell window](https://technet.microsoft.com/EN-US/library/dn568015.aspx) or [Connecting to Skype for Business Online by using Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).</span></span>
    
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="edbe5-151">Criar uma política de acesso externo personalizadas para um usuário</span><span class="sxs-lookup"><span data-stu-id="edbe5-151">Create a custom external access policy for a user</span></span>

<span data-ttu-id="edbe5-152">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="edbe5-152">To do this, run:</span></span>
  
> 
  ```
  New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
  ```

> 
  ```
  Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
  ```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="edbe5-153">Quer saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="edbe5-153">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="edbe5-154">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="edbe5-154">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="edbe5-155">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="edbe5-155">With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="edbe5-156">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="edbe5-156">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="edbe5-157">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="edbe5-157">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="edbe5-158">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="edbe5-158">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="edbe5-p108">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="edbe5-p108">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="edbe5-161">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="edbe5-161">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="edbe5-162">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="edbe5-162">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="edbe5-163">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="edbe5-163">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="edbe5-164">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="edbe5-164">Related topics</span></span>
[<span data-ttu-id="edbe5-165">Transferências de arquivos ponto a ponto de bloqueio</span><span class="sxs-lookup"><span data-stu-id="edbe5-165">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="edbe5-166">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="edbe5-166">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="edbe5-167">Configurar políticas de conferência na sua organização</span><span class="sxs-lookup"><span data-stu-id="edbe5-167">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
 