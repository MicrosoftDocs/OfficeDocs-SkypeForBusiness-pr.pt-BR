---
title: Excluir um conjunto existente de definições de configuração de CDR em Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
description: 'Resumo: Saiba como remover as definições de configuração de CDR em Skype para Business Server.'
ms.openlocfilehash: ed8f729d78ea64b230d91d9142d0ba7dae743b0e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21003696"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="75fbe-103">Excluir um conjunto existente de definições de configuração de CDR em Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="75fbe-103">Delete an existing collection of CDR configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="75fbe-104">**Resumo:** Saiba como remover as definições de configuração de CDR em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="75fbe-104">**Summary:** Learn how to remove CDR configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="75fbe-p101">O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="75fbe-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>
  
<span data-ttu-id="75fbe-107">Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de CDR é criada para você.</span><span class="sxs-lookup"><span data-stu-id="75fbe-107">When you install Skype for Business Server, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="75fbe-108">Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a locais individuais.</span><span class="sxs-lookup"><span data-stu-id="75fbe-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="75fbe-109">Através do design, as definições configuradas no escopo do site têm precedência sobre aquelas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="75fbe-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="75fbe-110">Se você excluir as definições no escopo do site, então o CDR será gerenciado nesse site usando as definições globais.</span><span class="sxs-lookup"><span data-stu-id="75fbe-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="75fbe-111">Observe que você também pode "excluir" as definições globais.</span><span class="sxs-lookup"><span data-stu-id="75fbe-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="75fbe-112">Contudo, elas não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="75fbe-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="75fbe-113">Em vez disso, todas as propriedades nessa coleção serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="75fbe-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="75fbe-114">Por exemplo, como padrão, a limpeza está ativada em uma coleção de definições de configuração de CDR.</span><span class="sxs-lookup"><span data-stu-id="75fbe-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="75fbe-115">Suponha que você modifique a coleção global de forma que a limpeza seja desativada.</span><span class="sxs-lookup"><span data-stu-id="75fbe-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="75fbe-116">Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="75fbe-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="75fbe-117">Nesse caso, isso significa que a exclusão será habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="75fbe-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="75fbe-118">Você pode remover as definições de configuração de CDR usando o Skype para painel de controle do Business Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="75fbe-118">You can remove CDR configuration settings by using the Skype for Business Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-remove-cdr-configuration-settings-with-skype-for-business-server-control-panel"></a><span data-ttu-id="75fbe-119">Para remover as definições de configuração de CDR com Skype para painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="75fbe-119">To remove CDR configuration settings with Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="75fbe-120">No painel de controle do servidor de negócios do Skype, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="75fbe-120">In Skype for Business Server Control Panel, click **Monitoring and Archiving**.</span></span> 
    
2. <span data-ttu-id="75fbe-p104">Na guia **Registro de Detalhes de Chamada**, selecione a coleção (ou coleções) de definições de CDR a ser removida. Para selecionar várias coleções, clique na primeira coleção, mantenha pressionada a tecla CTRL e clique em mais coleções.</span><span class="sxs-lookup"><span data-stu-id="75fbe-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>
    
3. <span data-ttu-id="75fbe-123">Clique em **Editar** e então em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="75fbe-123">Click **Edit**, and then click **Delete**.</span></span>
    
4. <span data-ttu-id="75fbe-124">No Skype para caixa de diálogo Painel de controle do Business Server, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="75fbe-124">In the Skype for Business Server Control Panel dialog box, click **OK**.</span></span>
    
## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="75fbe-125">Removendo definições de configuração de CDR usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="75fbe-125">Removing CDR configuration settings by using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="75fbe-126">Você pode excluir um registro de definições de configuração usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** de detalhes de chamada.</span><span class="sxs-lookup"><span data-stu-id="75fbe-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="75fbe-127">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="75fbe-127">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="75fbe-128">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="75fbe-128">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="75fbe-129">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="75fbe-129">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="75fbe-130">Para remover uma coleção especificada das definições de configuração de CDR</span><span class="sxs-lookup"><span data-stu-id="75fbe-130">To remove a specified collection of CDR configuration settings</span></span>

 <span data-ttu-id="75fbe-131">Este comando remove as definições de configuração de CDR aplicadas ao site da Redmond:</span><span class="sxs-lookup"><span data-stu-id="75fbe-131">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsCdrConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="75fbe-132">Para remover todas as definições de configuração de CDR aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="75fbe-132">To remove all the CDR configuration settings applied to the site scope</span></span>

 <span data-ttu-id="75fbe-133">Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="75fbe-133">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration
  ```

### <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="75fbe-134">Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes de chamada</span><span class="sxs-lookup"><span data-stu-id="75fbe-134">To remove all the CDR configuration settings that disable call detail recording</span></span>

 <span data-ttu-id="75fbe-135">Este comando remove todas as definições de configuração de CDR onde a gravação de detalhes de chamada foi desativada:</span><span class="sxs-lookup"><span data-stu-id="75fbe-135">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
  ```
  Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration
  ```

<span data-ttu-id="75fbe-136">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="75fbe-136">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-cscdrconfiguration?view=skype-ps) cmdlet.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="75fbe-137">Consulte também</span><span class="sxs-lookup"><span data-stu-id="75fbe-137">See also</span></span>

[<span data-ttu-id="75fbe-138">Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="75fbe-138">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

