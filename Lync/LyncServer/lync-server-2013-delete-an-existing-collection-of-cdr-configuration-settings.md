---
title: 'Lync Server 2013: excluir uma coleção existente de definições de configuração de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of CDR configuration settings
ms:assetid: 8ebf5da8-c0fc-498c-8d85-527d3be8479a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688128(v=OCS.15)
ms:contentKeyID: 49733726
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c50df73d59c588094693009ab4c84f2a7809ba5f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="505e7-102">Excluir uma coleção existente de definições de configuração de CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="505e7-102">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="505e7-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="505e7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="505e7-p101">O registro de detalhes das chamadas (CDR) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="505e7-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="505e7-106">Quando você instala o Microsoft Lync Server 2013, uma única coleção global de definições de configuração de CDR é criada para você.</span><span class="sxs-lookup"><span data-stu-id="505e7-106">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="505e7-107">Os administradores têm a opção de criar coleções de definições personalizadas que podem ser aplicadas a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="505e7-107">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="505e7-108">Através do design, as definições configuradas no escopo do site têm precedência sobre aquelas no escopo global.</span><span class="sxs-lookup"><span data-stu-id="505e7-108">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="505e7-109">Se você excluir as definições no escopo do site, então o CDR será gerenciado nesse site usando as definições globais.</span><span class="sxs-lookup"><span data-stu-id="505e7-109">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="505e7-p103">Observe que também é possível "excluir" as definições globais. No entanto, as definições globais não serão realmente removidas. Em vez disso, todas as propriedades nessa coleção serão redefinidas para os valores padrão. Por exemplo, como padrão, a limpeza está ativada em uma coleção de definições de configuração de CDR. Suponha que você modifique a coleção global de forma que a limpeza seja desativada. Se você excluir as definições globais mais tarde, todas as propriedades serão redefinidas para seus valores padrão. Neste caso, isso significa que a limpeza será novamente ativada.</span><span class="sxs-lookup"><span data-stu-id="505e7-p103">Note that you can also “delete” the global settings. However, the global settings will not actually be removed. Instead, all the properties in that collection will be reset to their default values. For example, by default purging is enabled in a collection of CDR configuration settings. Suppose you modify the global collection so that purging is disabled. If you later delete the global settings, all the properties will be reset to their default values. In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="505e7-117">Você pode remover as configurações de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="505e7-117">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="505e7-118">Para remover as configurações de configuração de CDR com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="505e7-118">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="505e7-119">No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="505e7-119">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="505e7-p104">Na guia **Registro de Detalhes de Chamada**, selecione a coleção (ou coleções) de definições de CDR a ser removida. Para selecionar várias coleções, clique na primeira coleção, mantenha pressionada a tecla CTRL e clique em mais coleções.</span><span class="sxs-lookup"><span data-stu-id="505e7-p104">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed. To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="505e7-122">Clique em **Editar** e então em **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="505e7-122">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="505e7-123">Na caixa de diálogo painel de controle do Lync Server, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="505e7-123">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="505e7-124">Como remover as definições de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="505e7-124">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="505e7-125">Você pode excluir as configurações de registro de detalhes da chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="505e7-125">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="505e7-126">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="505e7-126">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="505e7-127">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="505e7-127">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="505e7-128">Para remover uma coleção especificada das definições de configuração de CDR</span><span class="sxs-lookup"><span data-stu-id="505e7-128">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="505e7-129">Este comando remove as definições de configuração de CDR aplicadas ao site da Redmond:</span><span class="sxs-lookup"><span data-stu-id="505e7-129">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="505e7-130">Para remover todas as definições de configuração de CDR aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="505e7-130">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="505e7-131">Este comando remove todas as definições de configuração de CDR aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="505e7-131">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="505e7-132">Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes de chamada</span><span class="sxs-lookup"><span data-stu-id="505e7-132">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="505e7-133">Este comando remove todas as definições de configuração de CDR onde a gravação de detalhes de chamada foi desativada:</span><span class="sxs-lookup"><span data-stu-id="505e7-133">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="505e7-134">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="505e7-134">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

