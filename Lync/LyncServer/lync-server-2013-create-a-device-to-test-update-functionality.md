---
title: 'Lync Server 2013: criar um dispositivo para testar a funcionalidade de atualização'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 227ca68433cfcc41f966e220ffc826357b50d54b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034933"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="4263b-102">Criar um dispositivo para testar a funcionalidade de atualização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4263b-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4263b-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="4263b-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="4263b-104">É possível adicionar um dispositivo de teste à página **Dispositivo de Teste** e usar esse dispositivo para verificar a funcionalidade de novas atualizações antes de implantar as atualizações nos dispositivos de produção.</span><span class="sxs-lookup"><span data-stu-id="4263b-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="4263b-105">Você pode testar um dispositivo globalmente (em todo o seu ambiente do Lync Server) ou em um único site.</span><span class="sxs-lookup"><span data-stu-id="4263b-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="4263b-106">Identifique um dispositivo de teste pelo seu endereço MAC (Controle de Acesso de Mídia) ou pelo número de série.</span><span class="sxs-lookup"><span data-stu-id="4263b-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="4263b-107">Quando você adiciona um dispositivo, ele aparece na lista na página **dispositivo de teste** do painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4263b-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="4263b-108">Para adicionar um dispositivo de teste</span><span class="sxs-lookup"><span data-stu-id="4263b-108">To add a test device</span></span>

1.  <span data-ttu-id="4263b-109">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4263b-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4263b-110">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4263b-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4263b-111">Na barra de navegação esquerda, clique em **Cliente** e em **Dispositivo de Teste**.</span><span class="sxs-lookup"><span data-stu-id="4263b-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="4263b-112">Clique em **Novo** e em **Dispositivo de teste global** ou **Dispositivo de teste de site**.</span><span class="sxs-lookup"><span data-stu-id="4263b-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="4263b-113">Siga um destes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="4263b-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="4263b-114">Se você clicou em **Dispositivo de teste global**, vá para a próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="4263b-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="4263b-115">Se você clicou em **Dispositivo de teste de site**, selecione um site na lista de sites disponíveis e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="4263b-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="4263b-116">Em **Novo Dispositivo de Teste**, digite um nome para o dispositivo em **Nome do dispositivo**.</span><span class="sxs-lookup"><span data-stu-id="4263b-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="4263b-117">Em **Tipo de identificador**, clique em **Endereço MAC** ou **Número de série**.</span><span class="sxs-lookup"><span data-stu-id="4263b-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="4263b-118">Na caixa **Identificador exclusivo**, digite o endereço MAC ou número de série do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="4263b-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="4263b-119">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="4263b-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4263b-120">Criando dispositivos de teste usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4263b-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="4263b-121">Os dispositivos de teste podem ser criados usando o Windows PowerShell e o cmdlet New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="4263b-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="4263b-122">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4263b-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="4263b-123">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="4263b-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="4263b-124">Ao criar dispositivos de teste usando este cmdlet, você deve fazer duas coisas:</span><span class="sxs-lookup"><span data-stu-id="4263b-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="4263b-125">Especificar o MACAddress ou SerialNumber como o IdentifierType.</span><span class="sxs-lookup"><span data-stu-id="4263b-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="4263b-p104">Incluir o escopo ao especificar a Identidade do dispositivo. Para criar um novo dispositivo no escopo global, use uma sintaxe semelhante a seguinte:</span><span class="sxs-lookup"><span data-stu-id="4263b-p104">Include the scope when specifying the device Identity. To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="4263b-128">Para criar um dispositivo de teste no escopo do site, use uma sintaxe semelhante a esta:</span><span class="sxs-lookup"><span data-stu-id="4263b-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="4263b-129">Para criar um dispositivo de teste usando o endereço MAC</span><span class="sxs-lookup"><span data-stu-id="4263b-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="4263b-130">Este comando cria um dispositivo de teste no escopo global e usando o endereço MAC como o IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="4263b-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="4263b-131">Para criar um dispositivo de teste usando o número de série</span><span class="sxs-lookup"><span data-stu-id="4263b-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="4263b-132">Este comando cria um novo dispositivo de teste no escopo local (o local Redmond) e usa o número de série como o IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="4263b-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="4263b-133">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="4263b-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

