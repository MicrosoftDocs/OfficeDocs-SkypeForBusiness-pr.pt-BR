---
title: 'Lync Server 2013: habilitar gravação de detalhes da chamada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable call detail recording
ms:assetid: 3b28e432-596f-45a5-a070-577d6fa748d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520980(v=OCS.15)
ms:contentKeyID: 48183865
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d9227c1b3486ea20d6a1dc9c82311bfd17633bf
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197304"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-call-detail-recording-in-lync-server-2013"></a><span data-ttu-id="7ba12-102">Habilitar a gravação de detalhes da chamada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ba12-102">Enable call detail recording in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ba12-103">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="7ba12-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="7ba12-104">O CDR (registro de detalhes das chamadas) registra informações de uso e diagnóstico sobre atividades ponto a ponto, incluindo mensagens de instância, chamadas VoIP, compartilhamento de aplicativos, transferência de arquivos e reuniões.</span><span class="sxs-lookup"><span data-stu-id="7ba12-104">Call detail recording (CDR) records usage and diagnostic information about peer-to-peer activities including instance messaging, Voice over Internet Protocol (VoIP) calls, application sharing, file transfer, and meetings.</span></span> <span data-ttu-id="7ba12-105">Os dados de uso podem ser utilizados para calcular o retorno sobre o investimento, enquanto os dados de diagnóstico podem ser usados para solucionar problemas de atividades ponto a ponto e reuniões.</span><span class="sxs-lookup"><span data-stu-id="7ba12-105">The usage data can be used to calculate return on investment (ROI) and the diagnostic data can be used to troubleshoot peer-to-peer activities and meetings.</span></span>

<span data-ttu-id="7ba12-106">Use o procedimento a seguir para habilitar o CDR para toda a sua organização ou para cada site em sua organização.</span><span class="sxs-lookup"><span data-stu-id="7ba12-106">Use the following procedure to enable CDR for your whole organization or each site in your organization.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ba12-107">Para habilitar o CDR, você deve configurar o monitoramento e um banco de dados de monitoramento.</span><span class="sxs-lookup"><span data-stu-id="7ba12-107">In order to enable CDR you must configure monitoring and a monitoring database.</span></span> <span data-ttu-id="7ba12-108">Para obter detalhes, consulte <A href="lync-server-2013-deploying-monitoring.md">Deploying Monitoring in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7ba12-108">For details, see <A href="lync-server-2013-deploying-monitoring.md">Deploying monitoring in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="to-enable-cdr-with-lync-server-control-panel"></a><span data-ttu-id="7ba12-109">Para habilitar o CDR com o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="7ba12-109">To enable CDR with Lync Server Control Panel</span></span>

1.  <span data-ttu-id="7ba12-110">A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7ba12-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="7ba12-111">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7ba12-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7ba12-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7ba12-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ba12-113">Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e clique em **Registro de Detalhes de Chamada**.</span><span class="sxs-lookup"><span data-stu-id="7ba12-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Call Detail Recording**.</span></span>

4.  <span data-ttu-id="7ba12-114">Na página **registro de detalhes das chamadas** , clique no site apropriado na tabela, clique em **ação**e em **habilitar CDR**.</span><span class="sxs-lookup"><span data-stu-id="7ba12-114">On the **Call Detail Recording** page, click the appropriate site from the table, click **Action**, and then click **Enable CDR**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ba12-115">O CDR está habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="7ba12-115">CDR is enabled by default.</span></span>

    
    </div>

</div>

<div>

## <a name="enabling-cdr-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ba12-116">Habilitar o CDR usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ba12-116">Enabling CDR by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="7ba12-117">Você pode habilitar o CDR usando o Windows PowerShell e o cmdlet **set-CsCdrConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="7ba12-117">You can enable CDR by using Windows PowerShell and the **Set-CsCdrConfiguration** cmdlet.</span></span> <span data-ttu-id="7ba12-118">Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ba12-118">You can run this cmdlet either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="7ba12-119">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="7ba12-119">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-cdr-for-a-single-location"></a><span data-ttu-id="7ba12-120">Para habilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="7ba12-120">To enable CDR for a single location</span></span>

  - <span data-ttu-id="7ba12-121">Para desabilitar o CDR, defina o parâmetro EnableCDR como true ($True).</span><span class="sxs-lookup"><span data-stu-id="7ba12-121">To disable CDR, set the EnableCDR parameter to True ($True).</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $True

</div>

<div>

## <a name="to-disable-cdr-for-a-single-location"></a><span data-ttu-id="7ba12-122">Para desabilitar o CDR para um único local</span><span class="sxs-lookup"><span data-stu-id="7ba12-122">To disable CDR for a single location</span></span>

  - <span data-ttu-id="7ba12-123">Para desabilitar o CDR, defina o parâmetro EnableCDR como false ($False).</span><span class="sxs-lookup"><span data-stu-id="7ba12-123">To disable CDR, set the EnableCDR parameter to False ($False).</span></span> <span data-ttu-id="7ba12-124">Desabilitar o CDR não desinstala o monitoramento.</span><span class="sxs-lookup"><span data-stu-id="7ba12-124">Disabling CDR does not uninstall monitoring.</span></span> <span data-ttu-id="7ba12-125">Ele pausa a coleta e o armazenamento de dados de CDR.</span><span class="sxs-lookup"><span data-stu-id="7ba12-125">It pauses the collection and storage of CDR data.</span></span>
    
        Set-CsCdrConfiguration -Identity "site:Redmond" -EnableCDR $False

</div>

<div>

## <a name="to-use-a-single-command-to-enable-cdr-in-multiple-locations"></a><span data-ttu-id="7ba12-126">Para usar um único comando para habilitar o CDR em vários locais</span><span class="sxs-lookup"><span data-stu-id="7ba12-126">To use a single command to enable CDR in multiple locations</span></span>

  - <span data-ttu-id="7ba12-127">Este comando habilita o CDR para todas as definições de configuração de CDR atualmente em uso na sua organização.</span><span class="sxs-lookup"><span data-stu-id="7ba12-127">This command enables CDR for all the CDR configuration settings currently in use in your organization.</span></span>
    
        Get-CsCdrConfiguration | Set-CsCdrConfiguration "site:Redmond" -EnableCDR $True

</div>

<span data-ttu-id="7ba12-128">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) .</span><span class="sxs-lookup"><span data-stu-id="7ba12-128">For more information, see the help topic for the [Set-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsCdrConfiguration) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7ba12-129">Confira também</span><span class="sxs-lookup"><span data-stu-id="7ba12-129">See Also</span></span>


[<span data-ttu-id="7ba12-130">Planejamento de monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ba12-130">Planning for monitoring in Lync Server 2013</span></span>](lync-server-2013-planning-for-monitoring.md)  
[<span data-ttu-id="7ba12-131">Implantando o monitoramento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ba12-131">Deploying monitoring in Lync Server 2013</span></span>](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

