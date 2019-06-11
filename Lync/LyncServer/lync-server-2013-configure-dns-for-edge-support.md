---
title: 'Lync Server 2013: Configurar DNS para suporte à borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79e1712b3425c7cce4020799b37f10aba894aeb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836392"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="2a967-102">Configurar DNS para suporte à borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a967-102">Configure DNS for edge support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a967-103">_**Tópico da última modificação:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="2a967-103">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="2a967-104">Você deve configurar registros DNS (sistema de nomes de domínio) para interfaces de borda internas e externas, incluindo ambas as interfaces do servidor de borda e proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="2a967-104">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="2a967-105">Por padrão, os servidores de borda não fazem parte de um domínio e não terão um nome de domínio totalmente qualificado (nome de domínio totalmente qualificado).</span><span class="sxs-lookup"><span data-stu-id="2a967-105">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="2a967-106">O servidor de borda é chamado apenas pelo nome curto (máquina), não por um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="2a967-106">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="2a967-107">No entanto, o construtor de topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="2a967-107">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="2a967-108">O nome do servidor de borda deve corresponder ao FQDN usado pelo construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="2a967-108">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="2a967-109">Para fazer isso, você define um sufixo DNS que, quando combinado com o nome do computador, resulta no FQDN esperado.</span><span class="sxs-lookup"><span data-stu-id="2a967-109">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="2a967-110">Use o procedimento a seguir em "para adicionar o sufixo DNS ao nome do computador e no servidor de borda que não está associado a um domínio" para adicionar o sufixo DNS ao nome do computador.</span><span class="sxs-lookup"><span data-stu-id="2a967-110">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a967-111">Por padrão, o DNS usa um algoritmo de rodízio para girar a ordem dos dados de registro de recurso retornados nas respostas de consulta onde vários registros de recursos do mesmo tipo existem para um nome de domínio DNS consultado.</span><span class="sxs-lookup"><span data-stu-id="2a967-111">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="2a967-112">O balanceamento de carga de DNS do Lync Server 2013 depende do rodízio do DNS como parte do mecanismo de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="2a967-112">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="2a967-113">Verifique se a configuração de rodízio não foi desabilitada.</span><span class="sxs-lookup"><span data-stu-id="2a967-113">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="2a967-114">Se você estiver usando um servidor DNS que não está executando um sistema operacional Windows, verifique se a ordem de registro de recursos de rodízio está habilitada.</span><span class="sxs-lookup"><span data-stu-id="2a967-114">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="2a967-115">Use os procedimentos a seguir em "**para criar um registro SRV DNS**" para criar e verificar cada registro SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="2a967-115">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="2a967-116">Use o procedimento em "**criar um registro DNS**a" para definir os registros DNS a necessários para o acesso de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="2a967-116">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="2a967-117">Para confirmar se os registros estão configurados e funcionando corretamente, consulte "**para verificar um registro DNS**" neste tópico.</span><span class="sxs-lookup"><span data-stu-id="2a967-117">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="2a967-118">Para obter detalhes sobre cada registro necessário para dar suporte a acesso externo a usuários, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a967-118">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="2a967-119">Para adicionar o sufixo DNS ao nome do computador em um servidor de borda que não está associado a um domínio</span><span class="sxs-lookup"><span data-stu-id="2a967-119">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="2a967-120">No computador, clique em **Iniciar**, clique com o botão direito do mouse em **computador**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="2a967-120">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="2a967-121">Em **nome do computador, domínio e configurações de grupo de trabalho**, clique em **alterar configurações**.</span><span class="sxs-lookup"><span data-stu-id="2a967-121">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="2a967-122">Na guia **nome do computador** , clique em **alterar**.</span><span class="sxs-lookup"><span data-stu-id="2a967-122">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="2a967-123">Em **nome do computador/alterações de domínio**, clique em **mais**.</span><span class="sxs-lookup"><span data-stu-id="2a967-123">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="2a967-124">Em **sufixo DNS e nome NetBIOS do computador**, no **sufixo DNS primário deste computador**, digite o nome do seu domínio interno (por exemplo, Corp.contoso.com) e clique em **OK** três vezes.</span><span class="sxs-lookup"><span data-stu-id="2a967-124">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="2a967-125">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="2a967-125">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="2a967-126">Para criar um registro SRV DNS</span><span class="sxs-lookup"><span data-stu-id="2a967-126">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="2a967-127">No servidor DNS apropriado, clique em **Iniciar**, clique em **painel de controle**, clique em **Ferramentas administrativas**e clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2a967-127">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="2a967-128">Você precisa configurar o DNS para que haja: 1) entradas DNS externas para pesquisas de DNS externas por usuários remotos e parceiros federados; 2) entradas para pesquisas de DNS para uso pelos servidores de borda dentro da rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada), incluindo registros para os servidores internos que executam o Lync Server 2013; e 3) entradas DNS internas para pesquisas pelos clientes internos e servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2a967-128">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="2a967-129">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio onde o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="2a967-129">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="2a967-130">Clique em **outros novos registros**.</span><span class="sxs-lookup"><span data-stu-id="2a967-130">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="2a967-131">Em **Selecione um tipo de registro de recurso**, digite **local do serviço (SRV)** e clique em **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="2a967-131">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="2a967-132">Forneça todas as informações necessárias para o registro SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="2a967-132">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="2a967-133">Para criar um registro de DNS A</span><span class="sxs-lookup"><span data-stu-id="2a967-133">To create a DNS A record</span></span>

1.  <span data-ttu-id="2a967-134">No servidor DNS, clique em **Iniciar**, clique em **painel de controle**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2a967-134">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="2a967-135">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="2a967-135">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="2a967-136">Clique em **novo host (A)**.</span><span class="sxs-lookup"><span data-stu-id="2a967-136">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="2a967-137">Forneça todas as informações necessárias para o registro SRV DNS.</span><span class="sxs-lookup"><span data-stu-id="2a967-137">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="2a967-138">Para verificar um registro DNS</span><span class="sxs-lookup"><span data-stu-id="2a967-138">To verify a DNS record</span></span>

1.  <span data-ttu-id="2a967-139">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="2a967-139">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="2a967-140">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="2a967-140">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="2a967-141">No prompt de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2a967-141">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="2a967-142">Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="2a967-142">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2a967-143">Confira também</span><span class="sxs-lookup"><span data-stu-id="2a967-143">See Also</span></span>


[<span data-ttu-id="2a967-144">Criar um registro DNS SRV para integração com Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="2a967-144">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="2a967-145">Determinar requisitios de DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2a967-145">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

