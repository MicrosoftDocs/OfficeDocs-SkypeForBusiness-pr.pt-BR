---
title: 'Lync Server 2013: Testar o Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test the Director
ms:assetid: 9627a7e2-28cc-429c-b79b-7c7a27573bb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398767(v=OCS.15)
ms:contentKeyID: 48184856
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f889d548ddc9b177113aa3e395ac181095de8008
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844677"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-director-in-lync-server-2013"></a><span data-ttu-id="12193-102">Testar o Diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="12193-102">Test the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12193-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="12193-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="12193-104">Neste estágio, você tem um director ou um pool de directors configurado, mas suas entradas de SRV do sistema de nome de domínio (DNS) ainda apontam para os clientes se conectarem usando um servidor pool ou Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="12193-104">At this stage, you have a Director or Director pool configured, but your Domain Name System (DNS) SRV entries still point clients to log on by using a pool or Standard Edition server.</span></span> <span data-ttu-id="12193-105">Antes de alterar o registro DNS para fazer com que os clientes do Lync 2013 façam logon automaticamente usando o diretor, teste um cliente editando-o manualmente para o diretor.</span><span class="sxs-lookup"><span data-stu-id="12193-105">Before changing the DNS record to make Lync 2013 clients log on automatically by using the Director, test a client by manually pointing it to the Director.</span></span>

<div>

## <a name="to-test-the-deployment"></a><span data-ttu-id="12193-106">Para testar a implantação</span><span class="sxs-lookup"><span data-stu-id="12193-106">To test the deployment</span></span>

1.  <span data-ttu-id="12193-107">Faça logon no computador no qual você tem o painel de controle do Lync Server instalado com uma conta de domínio que faça parte do grupo **CSAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="12193-107">Log on to the computer on which you have the Lync Server Control Panel installed with a domain account that is part of the **CSAdministrator** group.</span></span>

2.  <span data-ttu-id="12193-108">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="12193-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="12193-109">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="12193-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="12193-110">No painel de navegação, clique em **topologia**e, na coluna **status** , confirme se há um servidor verde com uma seta (ou seja, ![ícone do servidor com]o ícone de servidor de seta verde(images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "com seta verde")) para seu diretor ou pool de diretor.</span><span class="sxs-lookup"><span data-stu-id="12193-110">In the navigation pane, click **Topology**, and in the **Status** column confirm that there is a green server with an arrow (that is, ![Server icon with green arrow](images/Gg398767.2263cdb7-7e60-457a-a528-a3a082bd051b(OCS.15).jpg "Server icon with green arrow")) for your Director or Director pool.</span></span>

4.  <span data-ttu-id="12193-111">Conecte dois computadores cliente que tenham o cliente do Lync Server 2013 instalado e faça logon com uma conta de usuário diferente habilitada para o Lync Server 2013 para cada computador.</span><span class="sxs-lookup"><span data-stu-id="12193-111">Connect two client computers that have the Lync Server 2013 client installed and log on with a different user account enabled for Lync Server 2013 to each computer.</span></span>

5.  <span data-ttu-id="12193-112">Em um dos computadores cliente, clique no menu **Opções** , selecione o grupo configurações **pessoais** , clique em **avançado**, clique em **configuração manual**e, em seguida, defina o **nome do servidor interno ou o endereço IP para o endereço IP** totalmente qualificado FQDN (nome de domínio) do novo diretor ou pool do diretor.</span><span class="sxs-lookup"><span data-stu-id="12193-112">On one of the client computers, click the **Options** menu, select the **Personal** settings group, click **Advanced**, click **Manual Configuration**, and then set the **Internal Server name or IP address** to the fully qualified domain name (FQDN) of the new Director or Director pool.</span></span>

6.  <span data-ttu-id="12193-113">Faça logon em ambos os clientes e verifique se o cliente que está fazendo logon usando o diretor é capaz de fazer logon com êxito, veja o status de presença do outro usuário e se ele pode trocar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="12193-113">Log on to both clients and verify that the client logging on by using the Director is able to log on successfully, see the presence status of the other user, and that they can exchange instant messages.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

