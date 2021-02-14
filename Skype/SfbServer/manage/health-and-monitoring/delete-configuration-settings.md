---
title: Excluir um conjunto existente de definições de configuração de CDR no Skype for Business Server
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
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumo: saiba como remover as definições de configuração de CDR no Skype for Business Server.'
ms.openlocfilehash: ca6691d6a1a19e0d9219a256986b683b719da885
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816961"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="7b1a9-103">Excluir um conjunto existente de definições de configuração de CDR no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7b1a9-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="7b1a9-104">**Resumo:** Saiba como remover as definições de configuração de CDR no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="7b1a9-p101">O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="7b1a9-107">Quando você instala o Skype for Business Server, um único conjunto global de definições de configuração de CDR é criado para você.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="7b1a9-108">Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="7b1a9-109">Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="7b1a9-110">Se você excluir as configurações no escopo do site, o CDR será gerenciado nesse site usando as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="7b1a9-111">Observe que você também pode "excluir" as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="7b1a9-112">Contudo, elas não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="7b1a9-113">Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="7b1a9-114">Por exemplo, por padrão, a purgação está habilitada em um conjunto de definições de configuração de CDR.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="7b1a9-115">Digamos que você modifique o conjunto global para que a exclusão seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="7b1a9-116">Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="7b1a9-117">Nesse caso, isso significa que a exclusão será habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="7b1a9-118">Você pode remover as definições de configuração de CDR usando o Painel de Controle do Skype for Business Server ou o cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7b1a9-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="7b1a9-119">Para remover as definições de configuração de CDR com o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7b1a9-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7b1a9-120">No Painel de Controle do Skype for Business Server, clique **em Monitoramento e Arquivamento.**</span><span class="sxs-lookup"><span data-stu-id="7b1a9-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="7b1a9-121">Na guia **Registro de Detalhes das** Chamada, selecione a coleção (ou coleções) das configurações de CDR a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-121">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="7b1a9-122">Para selecionar várias coleções, clique na primeira coleção, mantenha a tecla Ctrl e clique em coleções adicionais.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-122">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="7b1a9-123">Clique **em Editar** e em **Excluir.**</span><span class="sxs-lookup"><span data-stu-id="7b1a9-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="7b1a9-124">Na caixa de diálogo Painel de Controle do Skype for Business Server, clique em **OK.**</span><span class="sxs-lookup"><span data-stu-id="7b1a9-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7b1a9-125">Removendo definições de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7b1a9-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7b1a9-126">Você pode excluir definições de configuração do registro de detalhes das chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="7b1a9-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="7b1a9-127">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7b1a9-128">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="7b1a9-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="7b1a9-129">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7b1a9-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="7b1a9-130">Para remover um conjunto especificado de definições de configuração de CDR</span><span class="sxs-lookup"><span data-stu-id="7b1a9-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="7b1a9-131">Este comando remove as definições de configuração de CDR aplicadas ao site redmond:</span><span class="sxs-lookup"><span data-stu-id="7b1a9-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="7b1a9-132">Para remover todas as definições de configuração de CDR aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="7b1a9-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="7b1a9-133">Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="7b1a9-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```PowerShell

### To remove all the CDR configuration settings that disable call detail recording

 This command removes all the CDR configuration settings where Call Detail recording has been disabled:
    
  ```PowerShell
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="7b1a9-134">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7b1a9-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7b1a9-135">Confira também</span><span class="sxs-lookup"><span data-stu-id="7b1a9-135">See also</span></span>

[<span data-ttu-id="7b1a9-136">Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de Qualidade da Experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7b1a9-136">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

