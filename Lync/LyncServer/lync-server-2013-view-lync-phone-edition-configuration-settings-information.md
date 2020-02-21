---
title: 'Lync Server 2013: exibir informações de definições de configuração do Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db68b4612e2adb08a391d6ee3d8e590aefbb7a8f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="adaca-102">Exibir as informações de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adaca-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="adaca-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="adaca-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="adaca-104">Você pode exibir informações de configuração sobre dispositivos que executam o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="adaca-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="adaca-105">As informações são organizadas em conjuntos.</span><span class="sxs-lookup"><span data-stu-id="adaca-105">The information is organized into collections.</span></span> <span data-ttu-id="adaca-106">Ao instalar o Lync Server, você obtém uma coleção de configurações do Lync Phone Edition que se aplicam a todos os dispositivos que executam o Lync Phone Edition em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="adaca-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="adaca-107">Você também pode criar novos conjuntos de configurações para um site específico.</span><span class="sxs-lookup"><span data-stu-id="adaca-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="adaca-108">As configurações de site tem precedência sobre configurações globais.</span><span class="sxs-lookup"><span data-stu-id="adaca-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="adaca-109">Cada conjunto de configurações consiste em um nome, o escopo (global ou site), configuração de segurança SIP, nível de log, nível do QoS (Qualidade de Serviço) de voz, configuração de bloqueio de telefone e detalhes de bloqueio de telefone, isto é, o comprimento mínimo do PIN (número de identificação pessoal) de desbloqueio e o tempo para que o telefone se bloqueie sozinho.</span><span class="sxs-lookup"><span data-stu-id="adaca-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="adaca-110">Para exibir informações de configuração sobre dispositivos que executam o Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="adaca-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="adaca-111">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="adaca-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="adaca-112">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="adaca-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="adaca-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="adaca-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="adaca-114">Na barra de navegação esquerda, clique em **Clientes**, e então clique no botão de navegação **Configuração de Dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="adaca-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="adaca-p103">Na página **Configuração de Dispositivo**, clique no conjunto de configurações sobre o qual deseja visualizar informações. O nome, escopo, configuração de segurança SIP, nível de qualidade de voz e a configuração de bloqueio de telefone são listados na página principal. Para visualizar o nível de log e os detalhes de bloqueio de telefone, clique no menu **Editar**, e então clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="adaca-p103">On the **Device Configuration** page, click the collection of settings you want to view information about. The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page. To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="adaca-118">Exibindo informações de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="adaca-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="adaca-119">Você pode exibir as definições de configuração do Lync Phone Edition usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="adaca-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="adaca-120">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="adaca-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="adaca-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="adaca-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="adaca-122">Para exibir as informações de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="adaca-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="adaca-123">Para exibir informações sobre todas as suas definições de configuração do Lync Phone Edition, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="adaca-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="adaca-124">O comando retorna informações parecidas com as seguintes:</span><span class="sxs-lookup"><span data-stu-id="adaca-124">The command returns information similar to the following:</span></span>
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

<span data-ttu-id="adaca-125">Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="adaca-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="adaca-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="adaca-126">See Also</span></span>


[<span data-ttu-id="adaca-127">Criar ou modificar um conjunto de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adaca-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="adaca-128">Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adaca-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="adaca-129">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adaca-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="adaca-130">Impor bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="adaca-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

