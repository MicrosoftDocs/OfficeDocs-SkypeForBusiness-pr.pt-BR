---
title: 'Lync Server 2013: exibir o status dos serviços em execução em um computador'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View the status of services running on a computer
ms:assetid: f41918e7-4c02-431e-840a-88a1f36ae499
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182606(v=OCS.15)
ms:contentKeyID: 48185804
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cea9c30dc8a02088c0a02baa9c6d877131360df3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-the-status-of-services-running-on-a-computer-in-lync-server-2013"></a><span data-ttu-id="2b073-102">Exibir o status dos serviços em execução em um computador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b073-102">View the status of services running on a computer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b073-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2b073-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2b073-104">Você pode usar o painel de controle do Lync Server 2013 para exibir todos os serviços que estão sendo executados em um computador específico em sua topologia do Lync Server e ver o status de cada serviço.</span><span class="sxs-lookup"><span data-stu-id="2b073-104">You can use Lync Server 2013 Control Panel to view all the services that are running on a specific computer in your Lync Server topology and see the status of each service.</span></span>

<div>

## <a name="to-view-the-status-of-services-running-on-a-computer"></a><span data-ttu-id="2b073-105">Para exibir o status dos serviços executados em um computador</span><span class="sxs-lookup"><span data-stu-id="2b073-105">To view the status of services running on a computer</span></span>

1.  <span data-ttu-id="2b073-106">Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="2b073-106">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b073-107">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b073-107">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2b073-108">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2b073-108">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b073-109">Na barra de navegação esquerda, clique em **Topologia**.</span><span class="sxs-lookup"><span data-stu-id="2b073-109">In the left navigation bar, click **Topology**.</span></span>

4.  <span data-ttu-id="2b073-110">Na página **Status**, classifique ou pesquise a lista conforme necessário para localizar o computador que deseja e clique no nome do computador.</span><span class="sxs-lookup"><span data-stu-id="2b073-110">On the **Status** page, sort or search the list, as required, to find the computer you’re interested in, and then click the computer name.</span></span>

5.  <span data-ttu-id="2b073-111">Faça qualquer um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="2b073-111">Do any of the following:</span></span>
    
      - <span data-ttu-id="2b073-112">Para ver os status de serviços mais atuais executados no computador, clique em **Obter status de serviço**.</span><span class="sxs-lookup"><span data-stu-id="2b073-112">To see the latest status of services running on the computer, click **Get service status**.</span></span>
    
      - <span data-ttu-id="2b073-113">Para ver uma lista de serviços específicos executados no computador e o status de cada serviço, clique em **Propriedades** e em **Fechar** para retornar à lista.</span><span class="sxs-lookup"><span data-stu-id="2b073-113">To see a list of specific services running on the computer and the status of each service, click **Properties**, and then click **Close** to return to the list.</span></span>

</div>

<div>

## <a name="viewing-service-status-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2b073-114">Exibindo o status do serviço usando os cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2b073-114">Viewing Service Status by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="2b073-115">Você também pode exibir o status do serviço usando o Windows PowerShell e o cmdlet **Get-CsWindowsService** .</span><span class="sxs-lookup"><span data-stu-id="2b073-115">You can also view service status by using Windows PowerShell and the **Get-CsWindowsService** cmdlet.</span></span> <span data-ttu-id="2b073-116">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b073-116">You can run this cmdlet from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="2b073-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="2b073-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-service-status"></a><span data-ttu-id="2b073-118">Para exibir o status do serviço</span><span class="sxs-lookup"><span data-stu-id="2b073-118">To view service status</span></span>

  - <span data-ttu-id="2b073-119">Para exibir o status do serviço em um computador, digite um comando semelhante ao seguinte no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="2b073-119">To view service status on a computer, type a command similar to the following in the Lync Server Management Shell and then press Enter:</span></span>
    
        Get-CsWindowsService -ComputerName atl-cs-001.litwareinc.com | Select-Object RoleName, Status
    
    <span data-ttu-id="2b073-120">Esse comando retorna informações semelhantes às seguintes:</span><span class="sxs-lookup"><span data-stu-id="2b073-120">This command returns information similar to the following:</span></span>
    
        RoleName                                  Status
        --------                                  ------
        {W3SVC}                                   Running
        {CentralManagement}                       Running
        {ClsAgent}                                Running
        {Registrar, UserServer, EdgeServer}       Running
        {ApplicationServer}                       Running
        {ConferencingServer}                      Running
        {MediationServer}                         Running

</div>

<span data-ttu-id="2b073-121">Para obter detalhes, consulte [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span><span class="sxs-lookup"><span data-stu-id="2b073-121">For details, see [Get-CsWindowsService](https://docs.microsoft.com/powershell/module/skype/Get-CsWindowsService).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b073-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="2b073-122">See Also</span></span>


[<span data-ttu-id="2b073-123">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b073-123">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

