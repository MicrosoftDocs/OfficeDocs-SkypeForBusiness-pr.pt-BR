---
title: Gerenciar políticas de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: saiba como gerenciar políticas de usuário para o arquivamento do Skype for Business Server.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278423"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="3f7cd-103">Gerenciar políticas de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3f7cd-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="3f7cd-104">**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="3f7cd-105">Inicialmente, você define as políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="3f7cd-106">As políticas de arquivamento determinam se devem ser arquivadas:</span><span class="sxs-lookup"><span data-stu-id="3f7cd-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="3f7cd-107">Comunicações internas</span><span class="sxs-lookup"><span data-stu-id="3f7cd-107">Internal communications</span></span>
    
- <span data-ttu-id="3f7cd-108">Comunicações externas</span><span class="sxs-lookup"><span data-stu-id="3f7cd-108">External communications</span></span>
    
<span data-ttu-id="3f7cd-109">As políticas de arquivamento podem ser definidas no nível global, do site ou do usuário.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3f7cd-110">Se você ativou a integração do Microsoft Exchange para a sua implantação, as políticas do Exchange controlam se o arquivamento está habilitado para os usuários que são hospedados no Exchange e têm suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="3f7cd-111">Para obter detalhes, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configurar a integração com o armazenamento do Exchange para o Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="3f7cd-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="3f7cd-112">Gerenciar políticas de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="3f7cd-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="3f7cd-113">Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="3f7cd-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="3f7cd-114">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3f7cd-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3f7cd-116">Na barra de navegação esquerda, clique em **Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="3f7cd-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="3f7cd-117">Gerenciar políticas de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3f7cd-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="3f7cd-118">Você também pode configurar políticas de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="3f7cd-119">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="3f7cd-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="3f7cd-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="3f7cd-120">**Cmdlet**</span></span>|<span data-ttu-id="3f7cd-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3f7cd-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f7cd-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f7cd-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3f7cd-123">Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="3f7cd-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f7cd-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3f7cd-125">Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="3f7cd-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="3f7cd-126">Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3f7cd-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f7cd-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3f7cd-128">Cria novas políticas de arquivamento de sessões de IM.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="3f7cd-129">Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="3f7cd-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f7cd-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3f7cd-131">Remove a política de arquivamento de mensagens instantâneas (IM) especificada que determina se o Skype for Business Server salvará automaticamente todas as sessões de mensagens instantâneas que ocorrem entre usuários internos e/ou todas as sessões de mensagens instantâneas entre usuários internos e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="3f7cd-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="3f7cd-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="3f7cd-133">Modifica uma política existente de arquivamento de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="3f7cd-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="3f7cd-134">As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="3f7cd-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

