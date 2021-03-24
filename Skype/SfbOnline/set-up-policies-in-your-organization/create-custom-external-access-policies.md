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
description: O Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.
ms.openlocfilehash: 3e5e8cf1c464b1011a49b06b2d1958246d332c91
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100607"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="de808-104">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="de808-104">Create custom external access policies</span></span>

<span data-ttu-id="de808-105">O Skype for Business Online permite que você crie políticas de acesso externo adicionais.</span><span class="sxs-lookup"><span data-stu-id="de808-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="de808-106">Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="de808-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="de808-107">São elas:</span><span class="sxs-lookup"><span data-stu-id="de808-107">These are:</span></span>
  
- <span data-ttu-id="de808-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="de808-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="de808-109">Somente acesso federado (_Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="de808-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="de808-110">Acesso federado e de consumidor (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="de808-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="de808-111">Políticas externas personalizadas permitem que você crie políticas adicionais que não são cobertas pelas configurações acima.</span><span class="sxs-lookup"><span data-stu-id="de808-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="de808-112">Quando a política foi criada, você seria obrigado a definir todos os parâmetros necessários e não poderia alterá-los posteriormente.</span><span class="sxs-lookup"><span data-stu-id="de808-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="de808-113">A criação de novas políticas personalizadas permite controlar recursos como o acesso ao consumidor do Skype ou uma política para desabilitar o áudio/vídeo em nuvem pública, que é algo que não foi abordado com configurações predefinidas.</span><span class="sxs-lookup"><span data-stu-id="de808-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="de808-114">Políticas de acesso externo personalizadas seguem a mesma sintaxe que as políticas de cliente, mobilidade e conferência.</span><span class="sxs-lookup"><span data-stu-id="de808-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="de808-115">Você pode saber mais sobre essas configurações [aqui](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="de808-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="de808-116">Para que isso funcione, o usuário deve estar usando uma versão com suporte do aplicativo Clique para Executar do Skype for Business de 2016 que a suporte.</span><span class="sxs-lookup"><span data-stu-id="de808-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="de808-117">A seguinte versão mínima do cliente Clique para Executar do Skype for Business 2016 é necessária:</span><span class="sxs-lookup"><span data-stu-id="de808-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="de808-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="de808-118">**Type**</span></span>|<span data-ttu-id="de808-119">**Data de lançamento**</span><span class="sxs-lookup"><span data-stu-id="de808-119">**Release date**</span></span>|<span data-ttu-id="de808-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="de808-120">**Version**</span></span>|<span data-ttu-id="de808-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="de808-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de808-122">Primeira versão do Canal Atual</span><span class="sxs-lookup"><span data-stu-id="de808-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="de808-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="de808-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="de808-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="de808-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="de808-125">Versão 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="de808-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="de808-126">Canal Atual</span><span class="sxs-lookup"><span data-stu-id="de808-126">Current Channel</span></span>  <br/> |<span data-ttu-id="de808-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="de808-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="de808-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="de808-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="de808-129">Versão 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="de808-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="de808-130">Canal Adiado</span><span class="sxs-lookup"><span data-stu-id="de808-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="de808-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="de808-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="de808-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="de808-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="de808-133">Versão 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="de808-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="de808-134">Os usuários que estão usando versões mais antigas de aplicativos do Skype for Business ou clientes Mac ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="de808-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="de808-135">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="de808-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="de808-136">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="de808-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="de808-137">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="de808-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="de808-138">Instale o [módulo do Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="de808-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="de808-139">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="de808-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="de808-140">Se você quiser mais informações sobre como iniciar o Windows PowerShell, consulte Conectar-se a todos os serviços do [Microsoft 365 ou do Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="de808-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="de808-141">Criar uma política de acesso externo personalizada para um usuário</span><span class="sxs-lookup"><span data-stu-id="de808-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="de808-142">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="de808-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="de808-143">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="de808-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="de808-144">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="de808-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="de808-145">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 e o Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="de808-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="de808-146">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="de808-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="de808-147">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="de808-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="de808-148">Por que você precisa usar o Microsoft 365 ou o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="de808-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="de808-149">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="de808-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="de808-150">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="de808-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="de808-151">[Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="de808-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="de808-152">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="de808-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="de808-153">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="de808-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="de808-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="de808-154">Related topics</span></span>
[<span data-ttu-id="de808-155">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="de808-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="de808-156">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="de808-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="de808-157">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="de808-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
