---
title: 'Lync Server 2013: habilitar a gravação de detalhes da chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b12359e331e9abd2767285a5ef8c32d56433731e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="1ff61-102">Habilitar a gravação de detalhes de chamadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff61-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff61-103">_**Tópico da última modificação:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="1ff61-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="1ff61-p101">O CDR (registro de detalhes das chamadas) registra informações de utilização e diagnóstico sobre atividades ponto a ponto, incluindo serviço de mensagens instantâneas, chamadas do protocolo VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões. Os dados de uso podem ser utilizados para calcular o ROI (retorno sobre o investimento), enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.</span><span class="sxs-lookup"><span data-stu-id="1ff61-p101">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings. The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="1ff61-106">Use o procedimento a seguir para ativar o CDR para a organização inteira ou para cada local da organização.</span><span class="sxs-lookup"><span data-stu-id="1ff61-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1ff61-107">Para habilitar o CDR, é preciso configurar o monitoramento e o banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="1ff61-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="1ff61-108">Para obter detalhes, consulte Implantando o <A href="lync-server-2013-deploying-monitoring.md">monitoramento no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="1ff61-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="1ff61-109">Para habilitar CDR com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1ff61-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="1ff61-110">Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1ff61-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1ff61-111">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1ff61-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1ff61-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1ff61-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1ff61-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes das Chamadas**.</span><span class="sxs-lookup"><span data-stu-id="1ff61-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="1ff61-114">Na página **Registro de Detalhes das Chamadas**, clique no local apropriado na tabela, em **Ação** e em **Habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="1ff61-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1ff61-115">O CDR é ativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="1ff61-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1ff61-116">Como habilitar o CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1ff61-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="1ff61-117">Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="1ff61-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="1ff61-118">Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1ff61-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="1ff61-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.</span><span class="sxs-lookup"><span data-stu-id="1ff61-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="1ff61-120">Para habilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="1ff61-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="1ff61-121">Para desabilitar o CDR, defina o parâmetro EnableCDR como Verdadeiro ($True).</span><span class="sxs-lookup"><span data-stu-id="1ff61-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="1ff61-122">Para desabilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="1ff61-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="1ff61-p105">Para desabilitar o CDR, defina o parâmetro EnableCDR como Falso ($False). Desabilitar o CDR não desinstalará o monitoramento, apenas pausará a coleta e o armazenamento de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="1ff61-p105">To disable CDR, set the EnableCDR parameter to False ($False). Disabling CDR does not uninstall monitoring. It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="1ff61-126">Para usar um único comando para habilitar o CDR em vários locais</span><span class="sxs-lookup"><span data-stu-id="1ff61-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="1ff61-127">Este comando habilita o CDR para todas as configurações do CDR em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="1ff61-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="1ff61-128">Para obter mais informações, consulte o tópico da ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="1ff61-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1ff61-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="1ff61-129">See Also</span></span>


[<span data-ttu-id="1ff61-130">Planejamento de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff61-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="1ff61-131">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff61-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

