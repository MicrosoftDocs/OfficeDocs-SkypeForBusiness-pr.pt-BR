---
title: 'Lync Server 2013: criar um dispositivo para testar a funcionalidade de atualização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="4a717-102">Criar um dispositivo para testar a funcionalidade de atualização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4a717-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4a717-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4a717-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4a717-104">É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações a dispositivos de produção.</span><span class="sxs-lookup"><span data-stu-id="4a717-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="4a717-105">Você pode testar um dispositivo globalmente (em todo o ambiente do Lync Server) ou em um único site.</span><span class="sxs-lookup"><span data-stu-id="4a717-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="4a717-106">Você identifica um dispositivo de teste por seu endereço MAC (Controle de acesso à mídia) ou número de série.</span><span class="sxs-lookup"><span data-stu-id="4a717-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="4a717-107">Quando você adiciona um dispositivo, ele é exibido na lista da página do **dispositivo de teste** do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a717-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="4a717-108">Para adicionar um dispositivo de teste</span><span class="sxs-lookup"><span data-stu-id="4a717-108">To add a test device</span></span>

1.  <span data-ttu-id="4a717-109">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4a717-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4a717-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4a717-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4a717-111">Na barra de navegação à esquerda, clique em **clientes**e em **testar dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4a717-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="4a717-112">Clique em **novo**e, em seguida, clique em **dispositivo de teste global** ou **dispositivo de teste de site**.</span><span class="sxs-lookup"><span data-stu-id="4a717-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="4a717-113">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4a717-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="4a717-114">Se você clicou em **dispositivo de teste global**, pule para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="4a717-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="4a717-115">Se você clicou em **site Test site**, selecione um site da lista de sites disponíveis e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4a717-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="4a717-116">Em **novo dispositivo de teste**, digite um nome para o dispositivo no **nome do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4a717-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="4a717-117">Em **tipo de identificador**, clique em **endereço MAC** ou **número de série**.</span><span class="sxs-lookup"><span data-stu-id="4a717-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="4a717-118">Na caixa **identificador exclusivo** , digite o endereço Mac ou o número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4a717-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="4a717-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4a717-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4a717-120">Criando dispositivos de teste usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4a717-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4a717-121">Os dispositivos de teste podem ser criados usando o Windows PowerShell e o cmdlet New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="4a717-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="4a717-122">Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4a717-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4a717-123">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="4a717-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="4a717-124">Ao criar dispositivos de teste usando este cmdlet, você deve fazer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="4a717-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="4a717-125">Especifique o MACAddress ou o SerialNumber como IdentifierType.</span><span class="sxs-lookup"><span data-stu-id="4a717-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="4a717-126">Inclua o escopo ao especificar a identidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4a717-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="4a717-127">Para criar um novo dispositivo no escopo global, use a sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="4a717-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="4a717-128">Para criar um dispositivo de teste na sintaxe de escopo do site, use a sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="4a717-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="4a717-129">Para criar um dispositivo de teste usando o endereço MAC</span><span class="sxs-lookup"><span data-stu-id="4a717-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="4a717-130">Esse comando cria um dispositivo de teste no escopo global e usando o endereço MAC como Identificadortype:</span><span class="sxs-lookup"><span data-stu-id="4a717-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="4a717-131">Para criar um dispositivo de teste usando o número de série</span><span class="sxs-lookup"><span data-stu-id="4a717-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="4a717-132">Esse comando cria um novo dispositivo de teste no escopo do site (para o site Redmond) e usa o número de série como Identificadortype:</span><span class="sxs-lookup"><span data-stu-id="4a717-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="4a717-133">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="4a717-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

