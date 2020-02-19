---
title: 'Lync Server 2013: testar o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da8fbb19ac08886c7603d3b1d60ae3946f7bde32
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="b4b52-102">Testar o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4b52-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4b52-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="b4b52-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="b4b52-104">Neste estágio, você tem um Diretor ou pool de Diretores configurado, mas as entradas SRV do DNS ainda apontam os clientes para fazer logon usando um pool ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="b4b52-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="b4b52-105">Antes de alterar o registro DNS para fazer com que os clientes do Lync 2013 façam logon automaticamente usando o diretor, teste um cliente manualmente apontando-o para o diretor.</span><span class="sxs-lookup"><span data-stu-id="b4b52-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="b4b52-106">Para testar a implantação</span><span class="sxs-lookup"><span data-stu-id="b4b52-106">To test the deployment</span></span>

1.  <span data-ttu-id="b4b52-107">Faça logon no computador em que o painel de controle do Lync Server está instalado com uma conta de domínio que faz parte do grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="b4b52-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="b4b52-108">Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b4b52-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b4b52-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="b4b52-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b4b52-110">No painel de navegação, clique em **topologia**e, na coluna **status** , confirme se há um servidor verde com uma seta (ou seja, ![ícone do servidor com seta verde](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Ícone de servidor com seta verde")) para seu diretor ou pool de diretores.</span><span class="sxs-lookup"><span data-stu-id="b4b52-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="b4b52-111">Conecte dois computadores cliente com o cliente do Lync Server 2013 instalado e faça logon com uma conta de usuário diferente habilitada para o Lync Server 2013 a cada computador.</span><span class="sxs-lookup"><span data-stu-id="b4b52-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="b4b52-112">Em um dos computadores cliente, clique no menu **Opções**, selecione o grupo de configurações **Pessoal**, clique em **Avançado**, em **Configuração Manual** e defina o **Nome do servidor interno ou endereço IP** como o nome totalmente qualificado (FQDN) do novo Diretor ou pool de Diretores.</span><span class="sxs-lookup"><span data-stu-id="b4b52-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="b4b52-113">Faça logon em ambos os clientes e verifique se o cliente que está entrando usando o Diretor consegue fazer logon com êxito, veja o status da presença do outro usuário e se podem trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="b4b52-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

