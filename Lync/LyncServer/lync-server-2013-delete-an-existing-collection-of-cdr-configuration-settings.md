---
title: 'Lync Server 2013: excluir um conjunto existente de definições de configuração de CDR'
description: 'Lync Server 2013: excluir um conjunto existente de definições de configuração de CDR.'
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
ms.openlocfilehash: e80f6d9e9d878dad258e494095b10c402029932b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572887"
---
# <a name="delete-an-existing-collection-of-cdr-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="37435-103">Excluir um conjunto existente de definições de configuração de CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="37435-103">Delete an existing collection of CDR configuration settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37435-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="37435-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="37435-p101">O CDR (registro de detalhes de chamadas) permite rastrear o uso de aspectos como as sessões de mensagens instantâneas ponto a ponto, chamadas de telefone VoIP e chamadas de conferência. Esses dados de uso incluem informações os usuários envolvidos na chamadas, o horário e o período da chamada.</span><span class="sxs-lookup"><span data-stu-id="37435-p101">Call Detail Recording (CDR) enables you to track usage of such things as peer-to-peer instant messaging sessions, Voice over Internet Protocol (VoIP) phone calls, and conferencing calls. This usage data includes information about who called whom, when they called, and how long they talked.</span></span>

<span data-ttu-id="37435-107">Quando você instala o Microsoft Lync Server 2013, um único conjunto global de definições de configuração de CDR é criado para você.</span><span class="sxs-lookup"><span data-stu-id="37435-107">When you install Microsoft Lync Server 2013, a single, global collection of CDR configuration settings is created for you.</span></span> <span data-ttu-id="37435-108">Os administradores também têm a opção de criar conjuntos personalizados de definições que podem ser aplicados a sites individuais.</span><span class="sxs-lookup"><span data-stu-id="37435-108">Administrators also have the option of creating custom setting collections that can be applied to individual sites.</span></span> <span data-ttu-id="37435-109">Por design, as configurações no escopo do site têm precedência sobre configurações no escopo global.</span><span class="sxs-lookup"><span data-stu-id="37435-109">By design, settings configured at the site scope take precedence over settings configured at the global scope.</span></span> <span data-ttu-id="37435-110">Se você excluir as configurações no escopo do site, o CDR será gerenciado nesse site usando as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="37435-110">If you delete site-scoped settings, then CDR will be managed in that site by using the global settings.</span></span>

<span data-ttu-id="37435-111">Observe que você também pode “excluir” as definições globais.</span><span class="sxs-lookup"><span data-stu-id="37435-111">Note that you can also “delete” the global settings.</span></span> <span data-ttu-id="37435-112">Contudo, elas não serão realmente removidas.</span><span class="sxs-lookup"><span data-stu-id="37435-112">However, the global settings will not actually be removed.</span></span> <span data-ttu-id="37435-113">Em vez disso, todas as propriedades naquele conjunto serão redefinidas de acordo com os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="37435-113">Instead, all the properties in that collection will be reset to their default values.</span></span> <span data-ttu-id="37435-114">Por exemplo, por padrão, a limpeza é habilitada em um conjunto de definições de configuração de CDR.</span><span class="sxs-lookup"><span data-stu-id="37435-114">For example, by default purging is enabled in a collection of CDR configuration settings.</span></span> <span data-ttu-id="37435-115">Digamos que você modifique o conjunto global para que a exclusão seja desabilitada.</span><span class="sxs-lookup"><span data-stu-id="37435-115">Suppose you modify the global collection so that purging is disabled.</span></span> <span data-ttu-id="37435-116">Se depois você resolver apagar as definições globais, todas as propriedades serão redefinidas para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="37435-116">If you later delete the global settings, all the properties will be reset to their default values.</span></span> <span data-ttu-id="37435-117">Nesse caso, isso significa que a exclusão será habilitada novamente.</span><span class="sxs-lookup"><span data-stu-id="37435-117">In this case, that means that purging will once again be enabled.</span></span>

<span data-ttu-id="37435-118">Você pode remover as definições de configuração de CDR usando o painel de controle do Lync Server ou o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="37435-118">You can remove CDR configuration settings by using the Lync Server Control Panel or the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

<div>

## <a name="to-remove-cdr-configuration-settings-with-lync-server-control-panel"></a><span data-ttu-id="37435-119">Para remover as definições de configuração de CDR com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="37435-119">To remove CDR configuration settings with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="37435-120">No painel de controle do Lync Server, clique em **monitoramento e arquivamento**.</span><span class="sxs-lookup"><span data-stu-id="37435-120">In Lync Server Control Panel, click **Monitoring and Archiving**.</span></span>

2.  <span data-ttu-id="37435-121">Na guia **registro de detalhes das chamadas** , selecione a coleção (ou coleções) das configurações de CDR a serem removidas.</span><span class="sxs-lookup"><span data-stu-id="37435-121">On the **Call Detail Recording** tab, select the collection (or collections) of CDR settings to be removed.</span></span> <span data-ttu-id="37435-122">Para selecionar várias coleções, clique na primeira coleção, pressione a tecla CTRL e clique em coleções adicionais.</span><span class="sxs-lookup"><span data-stu-id="37435-122">To select multiple collections, click the first collection, hold down the Ctrl key, and click additional collections.</span></span>

3.  <span data-ttu-id="37435-123">Clique em **Editar**e em **excluir**.</span><span class="sxs-lookup"><span data-stu-id="37435-123">Click **Edit**, and then click **Delete**.</span></span>

4.  <span data-ttu-id="37435-124">Na caixa de diálogo painel de controle do Lync Server, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="37435-124">In the Lync Server Control Panel dialog box, click **OK**.</span></span>

</div>

<div>

## <a name="removing-cdr-configuration-settings-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="37435-125">Removendo definições de configuração de CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="37435-125">Removing CDR Configuration Settings by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="37435-126">Você pode excluir as definições de configuração de registro de detalhes da chamada usando o Windows PowerShell e o cmdlet **Remove-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="37435-126">You can delete call detail recording configuration settings by using Windows PowerShell and the **Remove-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="37435-127">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="37435-127">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="37435-128">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="37435-128">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-remove-a-specified-collection-of-cdr-configuration-settings"></a><span data-ttu-id="37435-129">Para remover um conjunto especificado de definições de configuração de CDR</span><span class="sxs-lookup"><span data-stu-id="37435-129">To remove a specified collection of CDR configuration settings</span></span>

  - <span data-ttu-id="37435-130">Este comando remove as definições de configuração de CDR aplicadas ao site de Redmond:</span><span class="sxs-lookup"><span data-stu-id="37435-130">This command removes the CDR configuration settings applied to the Redmond site:</span></span>
    
        Remove-CsCdrConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-applied-to-the-site-scope"></a><span data-ttu-id="37435-131">Para remover todas as definições de configuração de CDR aplicadas ao escopo do site</span><span class="sxs-lookup"><span data-stu-id="37435-131">To remove all the CDR configuration settings applied to the site scope</span></span>

  - <span data-ttu-id="37435-132">Este comando Remove todas as definições de configuração de CDR aplicadas ao escopo do site:</span><span class="sxs-lookup"><span data-stu-id="37435-132">This command removes all the CDR configuration settings applied to the site scope:</span></span>
    
        Get-CsCdrConfiguration -Filter "site:*" | Remove-CsCdrConfiguration

</div>

<div>

## <a name="to-remove-all-the-cdr-configuration-settings-that-disable-call-detail-recording"></a><span data-ttu-id="37435-133">Para remover todas as definições de configuração de CDR que desativam a gravação de detalhes da chamada</span><span class="sxs-lookup"><span data-stu-id="37435-133">To remove all the CDR configuration settings that disable call detail recording</span></span>

  - <span data-ttu-id="37435-134">Este comando Remove todas as definições de configuração de CDR onde a gravação de detalhes da chamada foi desativada:</span><span class="sxs-lookup"><span data-stu-id="37435-134">This command removes all the CDR configuration settings where Call Detail recording has been disabled:</span></span>
    
        Get-CsCdrConfiguration | Where-Object {$_.EnableCDR -eq $False} | Remove-CsCdrConfiguration

</div>

<span data-ttu-id="37435-135">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="37435-135">For more information, see the help topic for the [Remove-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsCdrConfiguration) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

