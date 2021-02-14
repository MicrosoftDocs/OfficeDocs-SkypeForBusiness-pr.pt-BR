---
title: Gerenciar opções de arquivamento no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Resumo: saiba como configurar opções de arquivamento para o Skype for Business Server.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817531"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="b52e3-103">Gerenciar opções de arquivamento no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b52e3-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="b52e3-104">**Resumo:** Saiba como configurar opções de arquivamento para o Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b52e3-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="b52e3-105">Inicialmente, você configura o arquivamento na implantação, mas pode alterar, adicionar e excluir configurações após a implantação.</span><span class="sxs-lookup"><span data-stu-id="b52e3-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="b52e3-106">As opções de arquivamento determinam se:</span><span class="sxs-lookup"><span data-stu-id="b52e3-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="b52e3-107">Habilitar ou desabilitar o arquivamento</span><span class="sxs-lookup"><span data-stu-id="b52e3-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="b52e3-108">Arquivar sessões de IM</span><span class="sxs-lookup"><span data-stu-id="b52e3-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="b52e3-109">Arquivar sessões de webconferência</span><span class="sxs-lookup"><span data-stu-id="b52e3-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="b52e3-110">Bloquear atividade quando o arquivamento não estiver disponível</span><span class="sxs-lookup"><span data-stu-id="b52e3-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="b52e3-111">Usar a integração com o Exchange</span><span class="sxs-lookup"><span data-stu-id="b52e3-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="b52e3-112">Configurar a purgação e a exportação de dados</span><span class="sxs-lookup"><span data-stu-id="b52e3-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="b52e3-113">Você pode especificar opções de configuração nos seguintes níveis:</span><span class="sxs-lookup"><span data-stu-id="b52e3-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="b52e3-114">Configuração de nível global criada por padrão ao implantar o Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b52e3-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="b52e3-115">Configurações opcionais no nível do site que especificam como o arquivamento é implementado para um site específico</span><span class="sxs-lookup"><span data-stu-id="b52e3-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="b52e3-116">Configurações opcionais no nível do pool que especificam como o arquivamento é implementado para um pool específico</span><span class="sxs-lookup"><span data-stu-id="b52e3-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="b52e3-117">Você pode excluir uma configuração de site ou configuração de pool, mas não pode excluir a configuração global.</span><span class="sxs-lookup"><span data-stu-id="b52e3-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="b52e3-118">Se você excluir a configuração global, ela será automaticamente redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="b52e3-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="b52e3-119">Para obter detalhes sobre como as configurações de arquivamento são implementadas e a hierarquia das configurações de arquivamento, consulte Plano para arquivamento no [Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="b52e3-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="b52e3-120">Configurar opções de arquivamento usando o Painel de Controle</span><span class="sxs-lookup"><span data-stu-id="b52e3-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="b52e3-121">Você pode configurar opções de arquivamento usando o Painel de Controle da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="b52e3-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="b52e3-122">A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="b52e3-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b52e3-123">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b52e3-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b52e3-124">Na barra de navegação esquerda, clique em **Configuração de Arquivamento.**</span><span class="sxs-lookup"><span data-stu-id="b52e3-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="b52e3-125">Configurar opções de arquivamento usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b52e3-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="b52e3-126">Você também pode configurar opções de arquivamento usando os cmdlets do Windows PowerShell listados na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="b52e3-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="b52e3-127">Para obter detalhes sobre sintaxe, incluindo todos os parâmetros disponíveis, consulte [Skype for Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="b52e3-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="b52e3-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="b52e3-128">**Cmdlet**</span></span>|<span data-ttu-id="b52e3-129">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b52e3-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b52e3-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b52e3-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b52e3-131">Retorna informações sobre as definições de configuração de arquivamento em sua organização.</span><span class="sxs-lookup"><span data-stu-id="b52e3-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="b52e3-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b52e3-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b52e3-133">Cria um novo conjunto de configurações de mensagens instantâneas (IM), que pode ser usado para habilitar ou desabilitar o salvar automático de sessões de IM e para bloquear qualquer mensagem instantânea que não possa ser arquivada.</span><span class="sxs-lookup"><span data-stu-id="b52e3-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="b52e3-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b52e3-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b52e3-135">Remove o conjunto especificado de configurações de arquivamento que são usadas para habilitar ou desabilitar o salvar automático de sessões de mensagens instantâneas (IM) e, opcionalmente, bloquear qualquer mensagem instantânea que não possa ser arquivada.</span><span class="sxs-lookup"><span data-stu-id="b52e3-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="b52e3-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="b52e3-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="b52e3-137">Modifica uma coleção existente de opções de configuração de arquivamento de mensagens instantâneas (IM).</span><span class="sxs-lookup"><span data-stu-id="b52e3-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
