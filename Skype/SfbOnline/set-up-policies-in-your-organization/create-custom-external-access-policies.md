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
description: Skype for Business Online permite que você crie políticas de acesso externo adicionais. Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.
ms.openlocfilehash: f9d99789bdb400cee9b7597bfcdc4079c1d3612d
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240140"
---
# <a name="create-custom-external-access-policies"></a><span data-ttu-id="87af2-104">Criar políticas personalizadas de acesso externo</span><span class="sxs-lookup"><span data-stu-id="87af2-104">Create custom external access policies</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="87af2-105">Skype for Business Online permite que você crie políticas de acesso externo adicionais.</span><span class="sxs-lookup"><span data-stu-id="87af2-105">Skype for Business Online allows you to create additional external access policies.</span></span> <span data-ttu-id="87af2-106">Ao contrário das políticas de cliente ou conferência, onde você pode ter várias combinações, há três políticas de acesso externo predefinidas que podem abranger a maioria dos cenários.</span><span class="sxs-lookup"><span data-stu-id="87af2-106">Unlike client or conferencing policies, where you can have multiple combinations, there are three predefined external access policies that can cover most of the scenarios.</span></span> <span data-ttu-id="87af2-107">São elas:</span><span class="sxs-lookup"><span data-stu-id="87af2-107">These are:</span></span>
  
- <span data-ttu-id="87af2-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span><span class="sxs-lookup"><span data-stu-id="87af2-108">No Federated or Skype Consumer Access (_Tag:NoFederationAndPIC_ )</span></span>
    
- <span data-ttu-id="87af2-109">Somente acesso federado (_Tag:FederationOnly_ )</span><span class="sxs-lookup"><span data-stu-id="87af2-109">Federated Access Only (_Tag:FederationOnly_ )</span></span>
    
- <span data-ttu-id="87af2-110">Acesso federado e de consumidor (_FederationAndPICDefault_)</span><span class="sxs-lookup"><span data-stu-id="87af2-110">Federated and Consumer Access (_FederationAndPICDefault_)</span></span>
    
<span data-ttu-id="87af2-111">Políticas externas personalizadas permitem que você crie políticas adicionais que não são cobertas pelas configurações acima.</span><span class="sxs-lookup"><span data-stu-id="87af2-111">Custom external policies allow you to create additional polices that aren't covered by the settings above.</span></span> <span data-ttu-id="87af2-112">Quando a política foi criada, você seria obrigado a definir todos os parâmetros necessários e não poderia alterá-los posteriormente.</span><span class="sxs-lookup"><span data-stu-id="87af2-112">When the policy was created, you would be required to set all required parameters and you couldn't alter them later.</span></span> <span data-ttu-id="87af2-113">A criação de novas políticas personalizadas permite que você controle recursos como o acesso ao consumidor Skype ou uma política para desabilitar o áudio/vídeo em nuvem pública, que é algo que não foi abordado com configurações predefinidas.</span><span class="sxs-lookup"><span data-stu-id="87af2-113">Creating new custom policies allow you to control features such as Skype consumer access or a policy to disable public cloud audio/video, which is something that wasn't covered with predefined settings.</span></span> <span data-ttu-id="87af2-114">Políticas de acesso externo personalizadas seguem a mesma sintaxe que as políticas de cliente, mobilidade e conferência.</span><span class="sxs-lookup"><span data-stu-id="87af2-114">Custom external access policies follow the same syntax as client, mobility, and conferencing policies.</span></span> <span data-ttu-id="87af2-115">Você pode saber mais sobre essas configurações [aqui](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="87af2-115">You can find out more about those settings [here](/previous-versions//mt228132(v=technet.10)).</span></span>
  
<span data-ttu-id="87af2-116">Para que isso funcione, o usuário deve estar usando uma versão com suporte do aplicativo clique para executar Skype for Business 2016 que a suporta.</span><span class="sxs-lookup"><span data-stu-id="87af2-116">To make this work, the user must be using a supported version of 2016 Click-to-Run Skype for Business app that supports it.</span></span> <span data-ttu-id="87af2-117">A seguinte versão mínima do Skype for Business 2016 Click-to-Run client é necessária:</span><span class="sxs-lookup"><span data-stu-id="87af2-117">The following minimum version of Skype for Business 2016 Click-to-Run client is required:</span></span>
  
|<span data-ttu-id="87af2-118">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="87af2-118">**Type**</span></span>|<span data-ttu-id="87af2-119">**Data de lançamento**</span><span class="sxs-lookup"><span data-stu-id="87af2-119">**Release date**</span></span>|<span data-ttu-id="87af2-120">**Versão**</span><span class="sxs-lookup"><span data-stu-id="87af2-120">**Version**</span></span>|<span data-ttu-id="87af2-121">**Compilação**</span><span class="sxs-lookup"><span data-stu-id="87af2-121">**Build**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="87af2-122">Primeira versão do Canal Atual</span><span class="sxs-lookup"><span data-stu-id="87af2-122">First Release for Current Channel</span></span>  <br/> |<span data-ttu-id="87af2-123">11/17/2016</span><span class="sxs-lookup"><span data-stu-id="87af2-123">11/17/2016</span></span>  <br/> |<span data-ttu-id="87af2-124">16.0.7571.2006</span><span class="sxs-lookup"><span data-stu-id="87af2-124">16.0.7571.2006</span></span>  <br/> |<span data-ttu-id="87af2-125">Versão 1611 (build 7571.2006)</span><span class="sxs-lookup"><span data-stu-id="87af2-125">Version 1611 (Build 7571.2006)</span></span>  <br/> |
|<span data-ttu-id="87af2-126">Canal Atual</span><span class="sxs-lookup"><span data-stu-id="87af2-126">Current Channel</span></span>  <br/> |<span data-ttu-id="87af2-127">12/6/2016</span><span class="sxs-lookup"><span data-stu-id="87af2-127">12/6/2016</span></span>  <br/> |<span data-ttu-id="87af2-128">16.0.7571.2072</span><span class="sxs-lookup"><span data-stu-id="87af2-128">16.0.7571.2072</span></span>  <br/> |<span data-ttu-id="87af2-129">Versão 1611 (build 7571.2072)</span><span class="sxs-lookup"><span data-stu-id="87af2-129">Version 1611 (Build 7571.2072)</span></span>  <br/> |
|<span data-ttu-id="87af2-130">Canal Adiado</span><span class="sxs-lookup"><span data-stu-id="87af2-130">Deferred Channel</span></span>  <br/> |<span data-ttu-id="87af2-131">2/22/2017</span><span class="sxs-lookup"><span data-stu-id="87af2-131">2/22/2017</span></span>  <br/> |<span data-ttu-id="87af2-132">16.0.7369.2118</span><span class="sxs-lookup"><span data-stu-id="87af2-132">16.0.7369.2118</span></span>  <br/> |<span data-ttu-id="87af2-133">Versão 1609 (build 7369.2118)</span><span class="sxs-lookup"><span data-stu-id="87af2-133">Version 1609 (Build 7369.2118)</span></span>  <br/> |
   
> [!CAUTION]
> <span data-ttu-id="87af2-134">Os usuários que estão usando versões mais antigas Skype for Business Windows aplicativos ou clientes Mac ainda poderão transferir arquivos.</span><span class="sxs-lookup"><span data-stu-id="87af2-134">Users who are using older versions of Skype for Business Windows apps or Mac clients will still be able to transfer files.</span></span> 
  
## <a name="start-windows-powershell"></a><span data-ttu-id="87af2-135">Iniciar Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="87af2-135">Start Windows PowerShell</span></span>

> [!NOTE]
> <span data-ttu-id="87af2-136">O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="87af2-136">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span> <span data-ttu-id="87af2-137">Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="87af2-137">If you're using the latest Teams PowerShell public release, you don't need to install the Skype for Business Online Connector.</span></span>
1. <span data-ttu-id="87af2-138">Instale o [módulo Teams PowerShell](/microsoftteams/teams-powershell-install).</span><span class="sxs-lookup"><span data-stu-id="87af2-138">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="87af2-139">Abra um prompt Windows PowerShell de comando e execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="87af2-139">Open a Windows PowerShell command prompt and run the following commands:</span></span> 
 ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   
   <span data-ttu-id="87af2-140">Se você quiser mais informações sobre como iniciar Windows PowerShell, consulte Conexão para todos os serviços Microsoft 365 ou [Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) em uma única janela de Windows PowerShell ou Configurar seu computador para Windows PowerShell [.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="87af2-140">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
   
## <a name="create-a-custom-external-access-policy-for-a-user"></a><span data-ttu-id="87af2-141">Criar uma política de acesso externo personalizada para um usuário</span><span class="sxs-lookup"><span data-stu-id="87af2-141">Create a custom external access policy for a user</span></span>

<span data-ttu-id="87af2-142">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="87af2-142">To do this, run:</span></span>
  
 
```powershell
New-CsExternalAccessPolicy -Identity BlockSkypeVideo -EnablePublicCloudAccess $True -EnablePublicCloudAudioVideoAccess $False -EnableFederationAccess $True -EnableOutsideAccess $True
```


```powershell
Grant-CsExternalAccessPolicy -PolicyName BlockSkypeVideo -Identity amosm@contoso.com
```

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="87af2-143">Deseja saber mais sobre o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="87af2-143">Want to know more about Windows PowerShell?</span></span>

- <span data-ttu-id="87af2-144">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="87af2-144">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="87af2-145">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou Office 365 e Skype for Business Online usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="87af2-145">With Windows PowerShell, you can manage Microsoft 365 or Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="87af2-146">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="87af2-146">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="87af2-147">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87af2-147">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="87af2-148">Por que você precisa usar Microsoft 365 ou Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="87af2-148">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- <span data-ttu-id="87af2-149">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="87af2-149">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="87af2-150">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="87af2-150">Learn about these advantages in the following topics:</span></span>
    
  - <span data-ttu-id="87af2-151">[Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="87af2-151">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
  - [<span data-ttu-id="87af2-152">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87af2-152">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="87af2-153">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="87af2-153">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a><span data-ttu-id="87af2-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="87af2-154">Related topics</span></span>
[<span data-ttu-id="87af2-155">Bloquear transferências de arquivo ponto a ponto</span><span class="sxs-lookup"><span data-stu-id="87af2-155">Block point-to-point file transfers</span></span>](block-point-to-point-file-transfers.md)

[<span data-ttu-id="87af2-156">Configurar políticas de clientes para sua organização</span><span class="sxs-lookup"><span data-stu-id="87af2-156">Set up client policies for your organization</span></span>](set-up-client-policies-for-your-organization.md)

[<span data-ttu-id="87af2-157">Configurar políticas de conferência em sua organização</span><span class="sxs-lookup"><span data-stu-id="87af2-157">Set up conferencing policies in your organization</span></span>](set-up-conferencing-policies-for-your-organization.md)

  
