---
title: 'Lync Server 2013: exibir informações sobre as configurações de configuração do Lync Phone Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a><span data-ttu-id="4463f-102">Exibir as informações de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4463f-102">View Lync Phone Edition configuration settings information in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4463f-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4463f-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4463f-104">Você pode exibir informações de configuração sobre os dispositivos que executam o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="4463f-104">You can view configuration information about devices running Lync Phone Edition.</span></span> <span data-ttu-id="4463f-105">As informações são organizadas em coleções.</span><span class="sxs-lookup"><span data-stu-id="4463f-105">The information is organized into collections.</span></span> <span data-ttu-id="4463f-106">Ao instalar o Lync Server, você obtém uma coleção de configurações do Lync Phone Edition que se aplicam a todos os dispositivos que executam o Lync Phone Edition na sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4463f-106">When you install Lync Server, you get a collection of Lync Phone Edition settings that apply to all the devices running Lync Phone Edition in your deployment.</span></span> <span data-ttu-id="4463f-107">Você também pode criar novos conjuntos de configurações para um site específico.</span><span class="sxs-lookup"><span data-stu-id="4463f-107">You can also create new collections of settings for a specific site.</span></span> <span data-ttu-id="4463f-108">As configurações do site têm precedência sobre as configurações globais.</span><span class="sxs-lookup"><span data-stu-id="4463f-108">Site settings take precedence over global settings.</span></span> <span data-ttu-id="4463f-109">Cada conjunto de configurações consiste em um nome, o escopo (global ou de site), a configuração de segurança SIP, o nível de log, o nível de qualidade do serviço (QoS), a configuração de bloqueio de telefone e os detalhes do bloqueio de telefone, ou seja, o comprimento mínimo da identificação pessoal de desbloquear número (PIN) e hora antes do telefone bloquear a si mesmo.</span><span class="sxs-lookup"><span data-stu-id="4463f-109">Each collection of settings consists of a name, the scope (global or site), SIP security setting, logging level, voice quality of service (QoS) level, phone-lock setting, and phone-lock details, that is, the minimum length of the unlock personal identification number (PIN) and time before the phone locks itself.</span></span>

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a><span data-ttu-id="4463f-110">Para ver as informações de configuração sobre os dispositivos que executam o Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4463f-110">To view configuration information about devices running Lync Phone Edition</span></span>

1.  <span data-ttu-id="4463f-111">Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="4463f-111">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4463f-112">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4463f-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4463f-113">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4463f-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4463f-114">Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de dispositivo** .</span><span class="sxs-lookup"><span data-stu-id="4463f-114">In the left navigation bar, click **Clients**, and then click the **Device Configuration** navigation button.</span></span>

4.  <span data-ttu-id="4463f-115">Na página **configuração de dispositivo** , clique no conjunto de configurações sobre as quais você deseja ver informações.</span><span class="sxs-lookup"><span data-stu-id="4463f-115">On the **Device Configuration** page, click the collection of settings you want to view information about.</span></span> <span data-ttu-id="4463f-116">O nome, o escopo, a configuração de segurança SIP, o nível de qualidade de voz e a configuração de bloqueio de telefone são listados na página principal.</span><span class="sxs-lookup"><span data-stu-id="4463f-116">The name, scope, SIP security setting, voice quality level, and phone lock setting are listed on the main page.</span></span> <span data-ttu-id="4463f-117">Para ver os detalhes do nível de log e bloqueio de telefone, clique no menu **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="4463f-117">To view the logging level and phone lock details, click the **Edit** menu, and then click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4463f-118">Exibindo as informações de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4463f-118">Viewing Lync Phone Edition Configuration Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4463f-119">Você pode exibir as configurações do Lync Phone Edition usando o Shell de gerenciamento do Lync Server e o cmdlet **Get-CsUCPhoneConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="4463f-119">You can view Lync Phone Edition configuration settings by using Lync Server Management Shell and the **Get-CsUCPhoneConfiguration** cmdlet.</span></span> <span data-ttu-id="4463f-120">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4463f-120">You can run this cmdlet can from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4463f-121">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="4463f-121">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a><span data-ttu-id="4463f-122">Para exibir as informações de configuração do Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4463f-122">To view Lync Phone Edition configuration information</span></span>

  - <span data-ttu-id="4463f-123">Para ver informações sobre todas as suas configurações do Lync Phone Edition, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="4463f-123">To view information about all your Lync Phone Edition configuration settings, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsUCPhoneConfiguration
    
    <span data-ttu-id="4463f-124">O comando retorna informações semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="4463f-124">The command returns information similar to the following:</span></span>
    
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

<span data-ttu-id="4463f-125">Para obter detalhes, consulte [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span><span class="sxs-lookup"><span data-stu-id="4463f-125">For details, see [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4463f-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="4463f-126">See Also</span></span>


[<span data-ttu-id="4463f-127">Criar ou modificar uma coleção de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4463f-127">Create or modify a collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="4463f-128">Excluir uma coleção existente de definições de configuração do Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4463f-128">Delete an existing collection of Lync Phone Edition configuration settings in Lync Server 2013</span></span>](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[<span data-ttu-id="4463f-129">Definir configurações de segurança para o Lync Phone Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4463f-129">Configure security settings for Lync Phone Edition in Lync Server 2013</span></span>](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[<span data-ttu-id="4463f-130">Impor o bloqueio de telefone no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4463f-130">Enforce phone locking in Lync Server 2013</span></span>](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

