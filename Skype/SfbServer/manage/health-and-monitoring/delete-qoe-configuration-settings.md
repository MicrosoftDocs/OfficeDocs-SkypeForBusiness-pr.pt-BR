---
title: Excluir definições de configuração de qualidade da experiência no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumo: Saiba como excluir configurações de Quality of Experience (QoE) no Skype para Business Server.'
ms.openlocfilehash: 1324029be12816abcc6c70de34363043df78277a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889843"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="10335-103">Excluir definições de configuração de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="10335-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="10335-104">**Resumo:** Aprenda a excluir definições de qualidade da experiência (QoE) no Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="10335-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="10335-p101">As métricas de Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de tremulação (diferenças no atraso de pacotes). Essas métricas são armazenadas em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação da QoE, independente de outros registros de dados.</span><span class="sxs-lookup"><span data-stu-id="10335-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="10335-107">Quando você instala o Skype para Business Server, uma única coleção global de definições de configuração de QoE é criada para você.</span><span class="sxs-lookup"><span data-stu-id="10335-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="10335-108">Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="10335-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="10335-109">Por design, as configurações no escopo local têm precedência sobre configurações no escopo global.</span><span class="sxs-lookup"><span data-stu-id="10335-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="10335-110">Se você excluir definições no escopo local, a QoE será gerenciada naquele local usando as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="10335-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="10335-111">Observe que você também pode "excluir" as definições globais.</span><span class="sxs-lookup"><span data-stu-id="10335-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="10335-112">No entanto, as definições globais não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="10335-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="10335-113">Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="10335-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="10335-114">Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE.</span><span class="sxs-lookup"><span data-stu-id="10335-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="10335-115">Digamos que você modifique o conjunto global para que a exclusão seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="10335-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="10335-116">Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão.</span><span class="sxs-lookup"><span data-stu-id="10335-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="10335-117">Neste caso, isso significa que a limpeza será novamente ativada.</span><span class="sxs-lookup"><span data-stu-id="10335-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="10335-118">Você pode remover as definições de configuração de QoE usando o Skype para o painel de controle do Business Server ou usando o cmdlet [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="10335-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="10335-119">Para excluir as definições de configuração de QoE usando Skype para o painel de controle do servidor de negócios</span><span class="sxs-lookup"><span data-stu-id="10335-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="10335-p104">Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="10335-p104">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="10335-122">Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="10335-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="10335-123">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de qualidade da experiência**.</span><span class="sxs-lookup"><span data-stu-id="10335-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="10335-124">Na página **Dados de qualidade da experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="10335-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="10335-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="10335-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10335-126">Removendo definições de configuração de QoE usando Cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="10335-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="10335-127">Você pode excluir as definições de configuração de QoE usando o Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="10335-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="10335-128">Você pode executar este cmdlet do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="10335-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="10335-129">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype para Business Server, consulte o artigo do blog ["rápida iniciar: Gerenciando Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="10335-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="10335-130">O processo é o mesmo em Skype para Business Server.</span><span class="sxs-lookup"><span data-stu-id="10335-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="10335-131">Para remover um conjunto especificado de definições de configuração de QoE</span><span class="sxs-lookup"><span data-stu-id="10335-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="10335-132">Esse comando remove as definições de configuração de QoE aplicadas ao local Redmond:</span><span class="sxs-lookup"><span data-stu-id="10335-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="10335-133">Para remover todas as definições de configuração de QoE aplicadas no escopo local</span><span class="sxs-lookup"><span data-stu-id="10335-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="10335-134">Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo local:</span><span class="sxs-lookup"><span data-stu-id="10335-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="10335-135">Para remover todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado</span><span class="sxs-lookup"><span data-stu-id="10335-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="10335-136">Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:</span><span class="sxs-lookup"><span data-stu-id="10335-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="10335-137">Para obter detalhes, consulte [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="10335-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="10335-138">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10335-138">See also</span></span>

[<span data-ttu-id="10335-139">Limpar manualmente o registro de detalhes da chamada e bancos de dados de qualidade da experiência no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="10335-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

