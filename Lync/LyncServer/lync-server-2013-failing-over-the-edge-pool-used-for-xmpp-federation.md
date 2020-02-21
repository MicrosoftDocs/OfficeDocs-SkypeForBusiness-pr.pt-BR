---
title: 'Lync Server 2013: failover do pool de borda usado para Federação XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8aee795b6f4dd1f3ff1077fb739cad9709b2c8ac
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="1c460-102">Failover do pool de borda usado para Federação XMPP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c460-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c460-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="1c460-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="1c460-p101">Na sua organização, há um pool de borda designado como o pool para uso da federação XMPP. Se esse pool parar de funcionar, você deve transferir a federação XMPP para usar um pool de borda diferente antes da federação XMPP poder funcionar novamente.</span><span class="sxs-lookup"><span data-stu-id="1c460-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="1c460-106">Quando você instala pools de borda e habilita a Federação XMPP, é possível simplificar o processo de recuperação de desastres configurando a criação de registros do servidor DNS externos para todos os seus pools de Borda para a federação XMPP, em vez de apenas um.</span><span class="sxs-lookup"><span data-stu-id="1c460-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="1c460-107">Cada um destes registros SRV devem ter um conjunto de prioridade diferente.</span><span class="sxs-lookup"><span data-stu-id="1c460-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="1c460-108">Todo o tráfego da federação XMPP atravessa o pool com o registro SRV com a mais alta prioridade.</span><span class="sxs-lookup"><span data-stu-id="1c460-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="1c460-109">Para obter mais informações sobre como habilitar e configurar a Federação do XMPP, consulte [setting up XMPP Federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="1c460-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="1c460-110">No procedimento a seguir, o EdgePool1 é o pool no qual a federação XMPP foi originalmente hospedada e o EdgePool2 é o pool no qual a federação XMPP está hospedada agora.</span><span class="sxs-lookup"><span data-stu-id="1c460-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="1c460-111">Transferência do pool de borda utilizado para a federação XMPP</span><span class="sxs-lookup"><span data-stu-id="1c460-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="1c460-112">Se você ainda não possuir outro pool de borda implantado (além de um não estiver funcionando no momento), implante esse pool.</span><span class="sxs-lookup"><span data-stu-id="1c460-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="1c460-113">Para obter detalhes, consulte [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="1c460-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="1c460-114">Em cada Servidor de Borda no novo pool de borda no qual a federação XMPP estará hospedada no momento (EdgePool2), execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1c460-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="1c460-115">Execute o seguinte cmdlet para redirecionar a rota da federação XMPP para o EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="1c460-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="1c460-116">Neste exemplo, o Site2 é o site contendo o pool de borda no qual a rota da federação XMPP estará hospedada no momento e o EdgeServer2.contoso.com é o FQDN de um Servidor de Borda nesse pool.</span><span class="sxs-lookup"><span data-stu-id="1c460-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="1c460-117">No servidor DNS externo, altere o registro A de DNS da federação XMPP para apontar para o EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="1c460-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="1c460-p104">Se você ainda não tiver um registro DNS SRV para a federação XMPP que resolva o pool de borda no qual a federação XMPP estará hospedada no momento, é necessário adicioná-lo, conforme no exemplo a seguir. O registro SRV deve ter um valor de porta de 5269.</span><span class="sxs-lookup"><span data-stu-id="1c460-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="1c460-120">Verifique se o pool de borda no qual a federação XMPP estará hospedada no momento possui uma porta 5269 aberta externamente.</span><span class="sxs-lookup"><span data-stu-id="1c460-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="1c460-121">Inicie os serviços em todos os Servidores de Borda no pool de borda no qual a federação XMPP estará hospedada no momento:</span><span class="sxs-lookup"><span data-stu-id="1c460-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

