---
title: Gerenciar políticas de arquivamento no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Resumo: Saiba como gerenciar políticas de usuário para arquivamento para Skype para Business Server.'
ms.openlocfilehash: 78c2e9d565ce755c9c23bce97702575a5861a23a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884958"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="83efe-103">Gerenciar políticas de arquivamento no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="83efe-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="83efe-104">**Resumo:** Saiba como gerenciar políticas de usuário para arquivamento para Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="83efe-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="83efe-105">Inicialmente, você configurar políticas de arquivamento quando você implanta o arquivamento, mas você pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="83efe-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="83efe-106">Políticas de arquivamento determinam se deseja arquivar:</span><span class="sxs-lookup"><span data-stu-id="83efe-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="83efe-107">Comunicações internas</span><span class="sxs-lookup"><span data-stu-id="83efe-107">Internal communications</span></span>
    
- <span data-ttu-id="83efe-108">Comunicações externas</span><span class="sxs-lookup"><span data-stu-id="83efe-108">External communications</span></span>
    
<span data-ttu-id="83efe-109">Políticas de arquivamento podem ser definido no nível global, site ou nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="83efe-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="83efe-110">Se você ativou a integração do Microsoft Exchange para sua implantação, o controle de políticas do Exchange se o arquivamento estiver habilitado para os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco.</span><span class="sxs-lookup"><span data-stu-id="83efe-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="83efe-111">Para obter detalhes, consulte [Planejar o arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md) e [Configure integração com Exchange storage para Skype para Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="83efe-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="83efe-112">Gerenciar políticas de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="83efe-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="83efe-113">Você pode gerenciar políticas de arquivamento usando o Painel de Controle da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="83efe-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="83efe-114">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="83efe-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="83efe-115">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="83efe-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="83efe-116">Na barra de navegação esquerda, clique em **Política de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="83efe-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="83efe-117">Gerenciar políticas de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="83efe-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="83efe-118">Você também pode configurar políticas de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="83efe-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="83efe-119">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype do Shell de gerenciamento do servidor de negócios](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="83efe-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="83efe-120">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="83efe-120">**Cmdlet**</span></span>|<span data-ttu-id="83efe-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="83efe-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83efe-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="83efe-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="83efe-123">Retorna informações sobre as políticas de arquivamento de sessões de mensagens instantâneas (IM) da sua organização.</span><span class="sxs-lookup"><span data-stu-id="83efe-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="83efe-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="83efe-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="83efe-125">Atribui a usuários ou grupos de usuários políticas de arquivamento de sessões de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="83efe-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="83efe-126">Essas políticas permitem arquivar sessões de IM entre usuários internos e/ou arquivar sessões de IM entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="83efe-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="83efe-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="83efe-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="83efe-128">Cria novas políticas de arquivamento de sessões de IM.</span><span class="sxs-lookup"><span data-stu-id="83efe-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="83efe-129">Essas políticas permitem arquivar sessões de IM que ocorrerem entre usuários internos e/ou arquivar sessões de IM que ocorrerem entre usuários internos e externos.</span><span class="sxs-lookup"><span data-stu-id="83efe-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="83efe-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="83efe-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="83efe-131">Remove o especificado mensagens instantâneas (IM) que determina se o Skype para Business Server salvará automaticamente todas as sessões IM ocorridas entre usuários internos e/ou todas as sessões de mensagens Instantâneas entre usuários internos e parceiros federados política de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="83efe-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="83efe-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="83efe-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="83efe-133">Modifica uma política existente de arquivamento de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="83efe-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="83efe-134">As políticas de arquivamento permitem arquivar todas as sessões de IM e conferências entre usuários internos; é possível também arquivar sessões que entre usuários internos e parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="83efe-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

