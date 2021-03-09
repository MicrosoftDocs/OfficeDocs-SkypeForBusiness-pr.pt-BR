---
title: Restrições de caracteres especiais nas políticas do Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policies.naming.error
- seo-marvel-mar2020
description: Veja quais são os problemas com caracteres especiais nos nomes das políticas e o que você pode fazer para corrigi-lo.
ms.openlocfilehash: bc5a2fbb28e37602b21e6c519ea3b3b7cb9a0325
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569403"
---
# <a name="what-are-the-special-character-restrictions-in-teams-policies"></a><span data-ttu-id="9b493-103">Quais são as restrições de caracteres especiais nas políticas do Teams?</span><span class="sxs-lookup"><span data-stu-id="9b493-103">What are the special character restrictions in Teams policies?</span></span>

<span data-ttu-id="9b493-104">Não é possível criar ou editar políticas **(para mensagens, reuniões etc.)** que tenham um caractere especial no nome no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b493-104">**You can't create or edit policies (for messaging, meetings, etc.) that have a special character in the name in the Microsoft Teams admin center**.</span></span> 

<span data-ttu-id="9b493-105">Se um nome de política contiver caracteres especiais, você será limitado no gerenciamento dessas políticas no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b493-105">If a policy name contains special characters, you will be limited in managing these policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9b493-106">**Como tal, recomendamos que os nomes de política não incluam caracteres especiais.**</span><span class="sxs-lookup"><span data-stu-id="9b493-106">**As such, we strongly recommend that policy names don't include special characters**.</span></span> 

<span data-ttu-id="9b493-107">Os nomes de política criados usando o PowerShell para reuniões e mensagens no Teams podem ter caracteres especiais como @,#,$.</span><span class="sxs-lookup"><span data-stu-id="9b493-107">Policy names that have been created using PowerShell for meetings and messaging in Teams can have special characters such as @,#,$.</span></span> <span data-ttu-id="9b493-108">No entanto, se você quiser fazer alterações na política no centro de administração do Microsoft Teams, não será possível.</span><span class="sxs-lookup"><span data-stu-id="9b493-108">However, if you are wanting to make changes to the policy in the Microsoft Teams admin center,you won't be able to.</span></span> 

<span data-ttu-id="9b493-109">Se você tiver uma política com caracteres especiais, precisará editar a política usando o Windows PowerShell (para sempre) ou criar uma nova política no centro de administração do Microsoft Teams com as mesmas configurações da política antiga e atribuí-la ao mesmo grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="9b493-109">If you have a policy with special characters, you will need to either edit the policy using Windows PowerShell (forever) or create a new policy in the Microsoft Teams admin center with the same settings as the old policy and assign it to the same group of users.</span></span>

## <a name="to-remove-special-characters"></a><span data-ttu-id="9b493-110">Para remover caracteres especiais</span><span class="sxs-lookup"><span data-stu-id="9b493-110">To remove special characters</span></span>

<span data-ttu-id="9b493-111">**Etapa 1 : Fazer uma conexão remota com o PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="9b493-111">**Step 1 - Make a remote connection with PowerShell.**</span></span>
> [!NOTE]
> <span data-ttu-id="9b493-112">O Conector do Skype for Business Online atualmente faz parte do módulo mais recente do Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b493-112">Skype for Business Online Connector is currently part of the latest Teams PowerShell Module.</span></span>
>
> <span data-ttu-id="9b493-113">Se você estiver usando a versão pública mais recente do [Teams PowerShell,](https://www.powershellgallery.com/packages/MicrosoftTeams/)não será necessário instalar o Conector do Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="9b493-113">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```


<span data-ttu-id="9b493-114">**Etapa 2 : Obter as configurações da política antiga e capturar a saída.**</span><span class="sxs-lookup"><span data-stu-id="9b493-114">**Step 2 - Get the settings for the old policy and capture the output.**</span></span>

> [!NOTE]
> <span data-ttu-id="9b493-115">Este exemplo é para uma [política de](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) Mensagens.</span><span class="sxs-lookup"><span data-stu-id="9b493-115">This example is for a [Messaging](https://docs.microsoft.com/powershell/module/skype/get-csteamsmessagingpolicy?view=skype-ps) policy.</span></span>  <span data-ttu-id="9b493-116">As etapas seriam as mesmas para outros tipos de política, mas você deve usar o cmdlet correto.</span><span class="sxs-lookup"><span data-stu-id="9b493-116">The steps would be the same for other policy types but you must use the correct cmdlet.</span></span> 

  ```PowerShell
  Get-CsTeamsMessagingPolicy -id <old_policy_name>
  ```


<span data-ttu-id="9b493-117">**Etapa 3 - Criar uma nova política.**</span><span class="sxs-lookup"><span data-stu-id="9b493-117">**Step 3 - Create a new policy.**</span></span>

<span data-ttu-id="9b493-118">Você pode criar a nova política com a mesma configuração usando o Centro de administração do Microsoft Teams ou o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9b493-118">You can either create the new policy with the same setting by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="9b493-119">Executar isso criará uma nova política para você, mas você precisará adicionar as configurações corretas, vendo [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) e executando-a:</span><span class="sxs-lookup"><span data-stu-id="9b493-119">Running this will create a new policy for you but you will need to add the correct settings by seeing [Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) and then running it:</span></span>

  ```PowerShell
  Set-CsTeamsMessagingPolicy -id <new_policy_name>
 ```
<span data-ttu-id="9b493-120">**Etapa 4 - Atribuir a política.**</span><span class="sxs-lookup"><span data-stu-id="9b493-120">**Step 4 - Assign the policy.**</span></span>
 ```PowerShell
Grant-CsTeamsMessagingPolicy -Policy <new_policy_name>
 ```
<span data-ttu-id="9b493-121">Consulte [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b493-121">See, [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="9b493-122">**Etapa 5 - Excluir a política antiga.**</span><span class="sxs-lookup"><span data-stu-id="9b493-122">**Step 5 - Delete the old policy.**</span></span>

<span data-ttu-id="9b493-123">Isso excluirá a política antiga com os caracteres especiais.</span><span class="sxs-lookup"><span data-stu-id="9b493-123">This will delete the old policy with the special characters.</span></span>
  ```PowerShell
  Remove-CsTeamsMessagingPolicy -identity <old_policy_name>
  ```
<span data-ttu-id="9b493-124">Consulte [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) para obter mais informações sobre este cmdlet.</span><span class="sxs-lookup"><span data-stu-id="9b493-124">See, [Remove-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csteamsmessagingpolicy?view=skype-ps) for more information on this cmdlet.</span></span>

<span data-ttu-id="9b493-125">Se esse comando for bem-sucedido, você terminará.</span><span class="sxs-lookup"><span data-stu-id="9b493-125">If this command succeeds, you're done.</span></span> <span data-ttu-id="9b493-126">Se o comando acima retornar um erro, é porque a política antiga é atribuída aos usuários, portanto, você precisa executar para remover todos os usuários atribuídos da política:</span><span class="sxs-lookup"><span data-stu-id="9b493-126">If the above command returns an error, it is because the old policy is assigned to users so you need to run to remove all assigned users from the policy:</span></span>

```PowerShell
Grant-CsMessagingPolicy -Policy <old_policy_name> $null
```
### <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="9b493-127">Quer saber como gerenciar com o Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9b493-127">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="9b493-128">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="9b493-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="9b493-129">Com Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer.</span><span class="sxs-lookup"><span data-stu-id="9b493-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="9b493-130">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9b493-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="9b493-131">Por que você precisa usar o Office 365 PowerShell?</span><span class="sxs-lookup"><span data-stu-id="9b493-131">Why you need to use Office 365 PowerShell?</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="9b493-132">Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9b493-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="9b493-133">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="9b493-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="9b493-134">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="9b493-134">Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="9b493-135">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b493-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="9b493-136">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b493-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="9b493-137">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b493-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="9b493-138">O Windows PowerShell módulo do Skype for Business Online permite que você crie uma sessão de Windows PowerShell remota que se conecta ao Skype for Business Online e ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9b493-138">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online and Microsoft Teams.</span></span> <span data-ttu-id="9b493-139">Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).</span><span class="sxs-lookup"><span data-stu-id="9b493-139">This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  

