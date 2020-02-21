---
title: 'Lync Server 2013: editar o diagrama de configuração de rede'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 225702f30aa19bf53c8b3f65c9731ea29b16a686
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a><span data-ttu-id="5b1ec-102">Editando o diagrama de configuração de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1ec-102">Editing the network configuration diagram in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5b1ec-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="5b1ec-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="5b1ec-104">A maior parte do trabalho que um designer faz no Lync Server 2013, a ferramenta de planejamento consiste em definir as entradas para os endereços IP e FQDNs (nomes de domínio totalmente qualificados) para as entradas no diagrama de rede.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-104">Most of the work that a designer does in the Lync Server 2013, Planning Tool consists of defining the entries for the IP addresses and fully qualified domain names (FQDNs) for the entries on the network diagram.</span></span> <span data-ttu-id="5b1ec-105">As informações inseridas nesta página são transferidas para os relatórios e outras informações contidas na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-105">The information that is entered on this page carries over into the reports and other information contained in the Planning Tool.</span></span>

<span data-ttu-id="5b1ec-106">![Diagrama de rede da ferramenta de planejamento](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Diagrama de rede da ferramenta de planejamento")</span><span class="sxs-lookup"><span data-stu-id="5b1ec-106">![Planning Tool Network diagram](images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Planning Tool Network diagram")</span></span>

<span data-ttu-id="5b1ec-107">A ferramenta de planejamento cria um diagrama de rede com texto padrão para endereços IP e FQDNs.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-107">The Planning Tool creates a network diagram with default text for IP addresses and FQDNs.</span></span>

<span data-ttu-id="5b1ec-108">Para editar os valores de entrada e diagrama de rede:</span><span class="sxs-lookup"><span data-stu-id="5b1ec-108">To edit the network diagram and input values:</span></span>

1.  <span data-ttu-id="5b1ec-109">Escolha uma seção da rede para começar a trabalhar.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-109">Choose a section of the network to begin working on.</span></span> <span data-ttu-id="5b1ec-110">Por exemplo, clique duas vezes no texto **Access1.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-110">For example, double-click the text, **access1.contoso.com**.</span></span> <span data-ttu-id="5b1ec-111">Na caixa de diálogo que é aberta, digite o FQDN real do servidor access1.contoso.com e o endereço IP real, substituindo o 131.107.155.3.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-111">In the dialog box that opens, type the actual FQDN of the server access1.contoso.com and the actual IP address, replacing the 131.107.155.3.</span></span>

2.  <span data-ttu-id="5b1ec-112">Clique em **OK** para salvar as entradas.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-112">Click **OK** to save the entries.</span></span>

3.  <span data-ttu-id="5b1ec-113">Continue a editar os endereços IP e os FQDNs, fornecendo endereços IP virtuais para balanceadores de carga de hardware ou entradas de servidor para balanceamento de carga do DNS (Sistema de Nome de Domínio) para servidores em pools.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-113">Continue to edit IP addresses and FQDNs, providing virtual IP addresses for hardware load balancers or server entries for Domain Name System (DNS) load balancing for servers in pools.</span></span>

<span data-ttu-id="5b1ec-p103">Um recurso útil da Ferramenta de Planejamento é que ela pode atribuir incrementalmente um intervalo de endereços IP e nomes de host do servidor, em vez de exigir que o designer edite cada servidor separado em um pool. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5b1ec-p103">A helpful feature of the Planning Tool is that it can incrementally assign a range of IP addresses and server host names, rather than requiring the designer to edit each separate server in a pool. For example:</span></span>

1.  <span data-ttu-id="5b1ec-116">Clique duas vezes nos Servidores Front-End em pool.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-116">Double-click the pooled Front End Servers.</span></span> <span data-ttu-id="5b1ec-117">Quando a caixa de diálogo abrir, selecione **Deseja usar os IPs e o FQDN como pontos de partida para todos os servidores equivalentes neste cluster?**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-117">When the dialog box opens, select **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?**.</span></span>

2.  <span data-ttu-id="5b1ec-118">Por exemplo, o valor inicial para o primeiro servidor é fe0101.contoso.com e um endereço IP de 192.168.21.122.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-118">For example, the starting value for the first server is fe0101.contoso.com and an IP address of 192.168.21.122.</span></span>

3.  <span data-ttu-id="5b1ec-119">Digite **FE0.contoso.com** em **FQDN do servidor front-end**, digite **192.168.21.131** no **endereço IP do servidor front-end**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-119">Type **fe0.contoso.com** in **Front End Server FQDN**, type **192.168.21.131** in **Front End Server IP address**, and then click **OK**.</span></span>

4.  <span data-ttu-id="5b1ec-120">O recurso de incremento automático atualiza todos os servidores no pool para fe01 até fe06 e todos os endereços IP de 192.168.21.131 para 136.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-120">The auto-increment feature updates all servers in the pool to fe01 through fe06, and all IP address from 192.168.21.131 to 136.</span></span>

<span data-ttu-id="5b1ec-121">Depois de concluir todas as edições, salve a topologia executando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="5b1ec-121">After you have completed all edits, save the topology by completing the following steps:</span></span>

<span data-ttu-id="5b1ec-122">Para salvar o design da ferramenta de planejamento, clique em **arquivo**e, em seguida, clique em **salvar topologia** ou **salvar topologia como**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-122">To save the Planning Tool design, click **File**, and then click **Save Topology** or **Save Topology As**.</span></span> <span data-ttu-id="5b1ec-123">Se uma caixa de diálogo **Salvar Ferramenta de Planejamento como** for exibida, digite um nome para o arquivo em **Nome do arquivo** e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5b1ec-123">If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5b1ec-124">Confira também</span><span class="sxs-lookup"><span data-stu-id="5b1ec-124">See Also</span></span>


[<span data-ttu-id="5b1ec-125">Editando o design no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5b1ec-125">Editing the design in Lync Server 2013</span></span>](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

