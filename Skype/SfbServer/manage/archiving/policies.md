---
title: Gerenciar políticas de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: saiba como gerenciar políticas de usuário para arquivamento do Skype for Business Server.'
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828541"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="697d9-103">Gerenciar políticas de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="697d9-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="697d9-104">**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="697d9-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="697d9-105">Inicialmente, você configura políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="697d9-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="697d9-106">As políticas de arquivamento determinam se são arquivadas:</span><span class="sxs-lookup"><span data-stu-id="697d9-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="697d9-107">Comunicações internas</span><span class="sxs-lookup"><span data-stu-id="697d9-107">Internal communications</span></span>
    
- <span data-ttu-id="697d9-108">Comunicações externas</span><span class="sxs-lookup"><span data-stu-id="697d9-108">External communications</span></span>
    
<span data-ttu-id="697d9-109">As políticas de arquivamento podem ser definidas no nível global, de site ou de usuário.</span><span class="sxs-lookup"><span data-stu-id="697d9-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="697d9-110">Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Espera.</span><span class="sxs-lookup"><span data-stu-id="697d9-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="697d9-111">Para obter detalhes, [consulte Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and Configure integration with Exchange storage for Skype for Business [Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="697d9-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="697d9-112">Gerenciar políticas de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="697d9-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="697d9-113">Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="697d9-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="697d9-114">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="697d9-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="697d9-115">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="697d9-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="697d9-116">Na barra de navegação esquerda, clique em **Política de Arquivamento**</span><span class="sxs-lookup"><span data-stu-id="697d9-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="697d9-117">Gerenciar políticas de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="697d9-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="697d9-118">Você também pode configurar políticas de arquivamento usando os cmdlets do Windows PowerShell listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="697d9-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="697d9-119">Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="697d9-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="697d9-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="697d9-120">**Cmdlet**</span></span>|<span data-ttu-id="697d9-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="697d9-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="697d9-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="697d9-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="697d9-123">Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="697d9-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="697d9-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="697d9-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="697d9-125">Atribui políticas de arquivamento de sessões de mensagens instantâneas (IM) a usuários ou conjuntos de usuários.</span><span class="sxs-lookup"><span data-stu-id="697d9-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="697d9-126">Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="697d9-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="697d9-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="697d9-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="697d9-128">Cria novas políticas de arquivamento de sessões de IM.</span><span class="sxs-lookup"><span data-stu-id="697d9-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="697d9-129">Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="697d9-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="697d9-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="697d9-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="697d9-131">Remove a política de arquivamento de mensagens instantâneas (IM) especificada que determina se o Skype for Business Server salvará automaticamente todas as sessões de IM que ocorrerem entre usuários internos e/ou todas as sessões de IM entre usuários internos e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="697d9-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="697d9-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="697d9-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="697d9-133">Modifica uma política existente de arquivamento de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="697d9-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="697d9-134">As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências que ocorrerem entre usuários internos; é possível também arquivar sessões que ocorrerem entre usuários internos e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="697d9-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

