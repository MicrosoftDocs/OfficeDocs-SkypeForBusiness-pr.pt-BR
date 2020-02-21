---
title: 'Lync Server 2013: Configurando rotas de voz para chamadas de saída'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a697dae1be3d59692746303f230968782db4f38f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195544"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a><span data-ttu-id="b835f-102">Configurando rotas de voz para chamadas de saída no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b835f-102">Configuring voice routes for outbound calls in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b835f-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b835f-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b835f-104">Uma rota de voz do Lync Server 2013 associa números de telefone de destino com um ou mais gateways PSTN (rede telefônica pública comutada) ou troncos SIP e um ou mais registros de uso de PSTN.</span><span class="sxs-lookup"><span data-stu-id="b835f-104">A Lync Server 2013 voice route associates destination phone numbers with one or more public switched telephone network (PSTN) gateways or SIP trunks and one or more PSTN usage records.</span></span>

<span data-ttu-id="b835f-105">**Para exibir rotas de voz usando o painel de controle do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="b835f-105">**To view voice routes by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="b835f-106">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b835f-106">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b835f-107">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b835f-107">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="b835f-108">Clique em **Roteamento de voz**.</span><span class="sxs-lookup"><span data-stu-id="b835f-108">Click **Voice Routing**.</span></span>

3.  <span data-ttu-id="b835f-109">Clique em **Rota**.</span><span class="sxs-lookup"><span data-stu-id="b835f-109">Click **Route**.</span></span>

4.  <span data-ttu-id="b835f-p102">Clique duas vezes em uma rota de voz para visualizar propriedades adicionais a partir da lista de rotas de voz ou selecione a rota e clique em **Editar**. Então, clique em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="b835f-p102">Double-click a voice route to view additional properties from the list of voice routes, or select the route and click **Edit**. Then click **Show details**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b835f-112">Você só pode visualizar informações detalhadas para uma única rota por vez.</span><span class="sxs-lookup"><span data-stu-id="b835f-112">You can only view detailed information for a single route at a time.</span></span>

    
    </div>

<span data-ttu-id="b835f-113">**Para exibir rotas de voz usando o Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b835f-113">**To view voice routes by using Windows PowerShell**</span></span>

  - <span data-ttu-id="b835f-114">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b835f-114">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="b835f-115">As rotas de voz podem ser visualizadas usando o Windows PowerShell e o cmdlet **Get-CsVoiceRoute** .</span><span class="sxs-lookup"><span data-stu-id="b835f-115">Voice routes can be viewed by using Windows PowerShell and the **Get-CsVoiceRoute** cmdlet.</span></span> <span data-ttu-id="b835f-116">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b835f-116">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b835f-117">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.</span><span class="sxs-lookup"><span data-stu-id="b835f-117">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>
    
    <span data-ttu-id="b835f-118">Para exibir informações sobre todas as suas rotas de voz, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="b835f-118">To view information about all of your voice routes, type the following command in the Lync Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsVoiceRoute
    
    <span data-ttu-id="b835f-119">Isto retorna informações semelhantes à seguinte:</span><span class="sxs-lookup"><span data-stu-id="b835f-119">That will return information similar to this:</span></span>
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> <span data-ttu-id="b835f-120">Para obter detalhes, consulte <A href="lync-server-2013-voice-routes.md">rotas de voz no Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="b835f-120">For details, see <A href="lync-server-2013-voice-routes.md">Voice routes in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b835f-121">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b835f-121">In This Section</span></span>

  - [<span data-ttu-id="b835f-122">Criar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b835f-122">Create a voice route in Lync Server 2013</span></span>](lync-server-2013-create-a-voice-route.md)

  - [<span data-ttu-id="b835f-123">Modificar uma rota de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b835f-123">Modify a voice route in Lync Server 2013</span></span>](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b835f-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="b835f-124">See Also</span></span>


[<span data-ttu-id="b835f-125">Gerenciando o roteamento de voz no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b835f-125">Managing voice routing in Lync Server 2013</span></span>](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

