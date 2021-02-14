---
title: Excluir definições de configuração de Qualidade da Experiência no Skype for Business Server
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
ms.assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
description: 'Resumo: saiba como excluir as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.'
ms.openlocfilehash: 45150b6aa2e6f48eedb28f180cfff8f291f58abc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816931"
---
# <a name="delete-quality-of-experience-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="6a993-103">Excluir definições de configuração de Qualidade da Experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a993-103">Delete Quality of Experience configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="6a993-104">**Resumo:** Saiba como excluir as configurações de QoE (Qualidade da Experiência) no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a993-104">**Summary:** Learn how to delete Quality of Experience (QoE) settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="6a993-p101">Os atributos métricos da Qualidade da Experiência (QoE) rastreiam a qualidade das chamadas de áudio e vídeo feitas na organização, inclusive o número de pacotes de rede perdidos, o ruído de fundo e a quantidade de "jitter" (diferenças no atraso de pacotes). Esses atributos métricos são armazenados em um banco de dados separado de outros dados (como registros de detalhes das chamadas), permitindo a habilitação e desabilitação do QoE, independentemente de outros registros de dados.</span><span class="sxs-lookup"><span data-stu-id="6a993-p101">Quality of Experience (QoE) metrics track the quality of audio and video calls made in your organization, including such things as the number of network packets lost, background noise, and the amount of "jitter" (differences in packet delay). These metrics are stored in a database apart from other data (such as call detail records), which allows you to enable and disable QoE independent of other data recording.</span></span>
  
<span data-ttu-id="6a993-107">Quando você instala o Skype for Business Server, um único conjunto global de definições de configuração de QoE é criado para você.</span><span class="sxs-lookup"><span data-stu-id="6a993-107">When you install Skype for Business Server, a single, global collection of QoE configuration settings is created for you.</span></span> <span data-ttu-id="6a993-108">Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="6a993-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="6a993-109">Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global.</span><span class="sxs-lookup"><span data-stu-id="6a993-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="6a993-110">Se você excluir definições no escopo do site, o QoE será gerenciado naquele site usando as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="6a993-110">If you delete site-scoped settings, then QoE will be managed in that site by using the global settings.</span></span>
  
<span data-ttu-id="6a993-111">Observe que você também pode "excluir" as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="6a993-111">Note that you can also "delete" the global settings.</span></span> <span data-ttu-id="6a993-112">Contudo, elas não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="6a993-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="6a993-113">Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="6a993-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="6a993-114">Por exemplo, por padrão, a exclusão é habilitada em um conjunto de configurações de QoE.</span><span class="sxs-lookup"><span data-stu-id="6a993-114">For example, by default purging is enabled in a collection of QoE configuration settings.</span></span> <span data-ttu-id="6a993-115">Digamos que você modifique o conjunto global para que a exclusão seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="6a993-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="6a993-116">Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="6a993-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="6a993-117">Nesse caso, isso significa que a exclusão será habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="6a993-117">In this case, that means that purging will once again be enabled.</span></span>
  
<span data-ttu-id="6a993-118">Você pode remover as definições de configuração de QoE usando o Painel de Controle do Skype for Business Server ou o cmdlet [Remove-CsQoEConfiguration.](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="6a993-118">You can remove QoE configuration settings by using the Skype for Business Server Control Panel or by using the [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-delete-qoe-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6a993-119">Para excluir as definições de configuração de QoE usando o Painel de Controle do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a993-119">To delete QoE configuration settings by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6a993-120">Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6a993-120">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="6a993-121">Para obter detalhes, consulte **Delegate Setup Permissions**.</span><span class="sxs-lookup"><span data-stu-id="6a993-121">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="6a993-122">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a993-122">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="6a993-123">Na barra de navegação esquerda, clique em **Monitoramento e arquivamento** e em **Dados de Qualidade da Experiência**.</span><span class="sxs-lookup"><span data-stu-id="6a993-123">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>
    
4. <span data-ttu-id="6a993-124">Na página **Dados de Qualidade de Experiência**, clique na política que quiser, clique em **Editar** e em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="6a993-124">On the **Quality of Experience Data** page, click the policy that you want, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="6a993-125">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="6a993-125">Click **OK**.</span></span>
    
## <a name="removing-qoe-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6a993-126">Removendo definições de configuração de QoE usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6a993-126">Removing QoE Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6a993-127">Você pode excluir as definições de configuração de QoE usando o Windows PowerShell e o cmdlet **Remove-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="6a993-127">You can delete QoE configuration settings by using Windows PowerShell and the **Remove-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="6a993-128">Você pode executar esse cmdlet no Shell de Gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6a993-128">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6a993-129">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Skype for Business Server, consulte o artigo do blog ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="6a993-129">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6a993-130">O processo é o mesmo no Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6a993-130">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-remove-a-specified-collection-of-qoe-configuration-settings"></a><span data-ttu-id="6a993-131">Para remover um conjunto especificado de definições de configuração de QoE</span><span class="sxs-lookup"><span data-stu-id="6a993-131">To remove a specified collection of QoE configuration settings</span></span>

 <span data-ttu-id="6a993-132">Esse comando remove as definições de configuração de QoE aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="6a993-132">This command removes the QoE configuration settings applied to the Redmond site:</span></span>
    
  ```PowerShell
  Remove-CsQoEConfiguration -Identity "site:Redmond"
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="6a993-133">Para remover todas as definições de configuração de QoE aplicadas no escopo do site</span><span class="sxs-lookup"><span data-stu-id="6a993-133">To remove all of the QoE configuration settings applied to the site scope</span></span>

 <span data-ttu-id="6a993-134">Esse comando remove todas as definições de configuração de QoE aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="6a993-134">This command removes all the QoE configuration settings applied to the site scope:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration
  ```

### <a name="to-remove-all-of-the-qoe-configuration-settings-where-qoe-monitoring-is-disabled"></a><span data-ttu-id="6a993-135">Para remover todas as definições de configuração de QoE onde o monitoramento de QoE for desabilitado</span><span class="sxs-lookup"><span data-stu-id="6a993-135">To remove all of the QoE configuration settings where QoE monitoring is disabled</span></span>

 <span data-ttu-id="6a993-136">Este comando remove todas as definições de configuração de QoE onde o monitoramento de QoE foi desabilitado:</span><span class="sxs-lookup"><span data-stu-id="6a993-136">This command removes all the QoE configuration settings where QoE monitoring has been disabled:</span></span>
    
  ```PowerShell
  Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration
  ```

<span data-ttu-id="6a993-137">Para obter detalhes, [consulte Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6a993-137">For details, see [Remove-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6a993-138">Confira também</span><span class="sxs-lookup"><span data-stu-id="6a993-138">See also</span></span>

[<span data-ttu-id="6a993-139">Limpar manualmente o registro de detalhes das chamadas e os bancos de dados de Qualidade da Experiência no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="6a993-139">Manually purge the call detail recording and Quality of Experience databases in Skype for Business Server</span></span>](../../deploy/deploy-monitoring/purgecall-detail-recording-and-qoe.md)

