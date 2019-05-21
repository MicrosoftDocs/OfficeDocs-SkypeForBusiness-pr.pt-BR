---
title: Gerenciar opções de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumo: saiba como configurar opções de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: c7353c305125e8e35523c573150471821f53301e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278416"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="b3608-103">Gerenciar opções de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b3608-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="b3608-104">**Resumo:** Saiba como configurar opções de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b3608-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="b3608-105">Inicialmente, você configura o arquivamento no momento da implantação, mas você e pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="b3608-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="b3608-106">As opções de arquivamento determinam:</span><span class="sxs-lookup"><span data-stu-id="b3608-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="b3608-107">Habilitar ou desabilitar arquivamento</span><span class="sxs-lookup"><span data-stu-id="b3608-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="b3608-108">Arquivar sessões de IM</span><span class="sxs-lookup"><span data-stu-id="b3608-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="b3608-109">Arquivar sessões de webconferência</span><span class="sxs-lookup"><span data-stu-id="b3608-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="b3608-110">Bloquear uma atividade quando o arquivamento não estiver disponível</span><span class="sxs-lookup"><span data-stu-id="b3608-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="b3608-111">Usar integração com o Exchange</span><span class="sxs-lookup"><span data-stu-id="b3608-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="b3608-112">Configurar a limpeza e exportação de dados</span><span class="sxs-lookup"><span data-stu-id="b3608-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="b3608-113">Você pode especificar opções de configuração nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="b3608-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="b3608-114">Configuração de nível global que é criada por padrão quando você implanta o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b3608-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="b3608-115">Configurações opcionais em nível de site que especificam como o arquivamento é implementado para um site específico</span><span class="sxs-lookup"><span data-stu-id="b3608-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="b3608-116">Configurações opcionais de nível de pool que especificam como o arquivamento é implementado para um pool específico</span><span class="sxs-lookup"><span data-stu-id="b3608-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="b3608-117">Você pode excluir uma configuração de site ou de pool, mas não pode excluir a configuração global.</span><span class="sxs-lookup"><span data-stu-id="b3608-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="b3608-118">Se você excluir a configuração global, ela automaticamente retorna para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b3608-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="b3608-119">Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia de configurações de arquivamento, consulte [planejar o arquivamento no Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="b3608-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="b3608-120">Configurar opções de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="b3608-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="b3608-121">Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b3608-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="b3608-122">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b3608-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b3608-123">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b3608-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b3608-124">Na barra de navegação esquerda, clique em **Configuração de arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="b3608-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="b3608-125">Configurar opções de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b3608-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="b3608-126">Você também pode configurar opções de arquivamento usando os cmdlets do Windows PowerShell listados na seguinte tabela.</span><span class="sxs-lookup"><span data-stu-id="b3608-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="b3608-127">Para obter detalhes sobre a sintaxe, incluindo todos os parâmetros disponíveis, consulte [Shell de gerenciamento do Skype for Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="b3608-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="b3608-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="b3608-128">**Cmdlet**</span></span>|<span data-ttu-id="b3608-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b3608-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b3608-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3608-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b3608-131">Retorna informações sobre as configurações de arquivamento na sua organização.</span><span class="sxs-lookup"><span data-stu-id="b3608-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="b3608-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3608-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b3608-133">Cria um novo conjunto de configurações do sistema de mensagens instantâneas (IM), que podem ser usadas para habilitar ou desabilitar a gravação automática de sessões de IM, e também para bloquear qualquer mensagem instantânea que não possa ser arquivada.</span><span class="sxs-lookup"><span data-stu-id="b3608-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="b3608-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3608-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b3608-135">Remove a coleção especificada de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvamento automático de sessões de mensagem instantânea (IM) e bloquear opcionalmente qualquer mensagem instantânea que não possa ser arquivada.</span><span class="sxs-lookup"><span data-stu-id="b3608-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="b3608-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b3608-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b3608-137">Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="b3608-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
