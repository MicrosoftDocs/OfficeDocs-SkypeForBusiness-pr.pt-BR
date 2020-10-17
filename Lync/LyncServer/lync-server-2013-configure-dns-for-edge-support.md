---
title: 'Lync Server 2013: configurar DNS para suporte de borda'
description: 'Lync Server 2013: configurar DNS para suporte de borda.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555887"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a><span data-ttu-id="f4421-103">Configurar o DNS para suporte de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4421-103">Configure DNS for edge support in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4421-104">_**Última modificação do tópico:** 2013-02-15_</span><span class="sxs-lookup"><span data-stu-id="f4421-104">_**Topic Last Modified:** 2013-02-15_</span></span>

<span data-ttu-id="f4421-105">Você deve configurar os registros de DNS (Sistema de Nomes de Domínio) para interfaces de borda internas e externas, incluindo ambas as interfaces do Servidor de Borda e do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="f4421-105">You must configure Domain Name System (DNS) records for internal and external edge interfaces, including both Edge Server and reverse proxy interfaces.</span></span> <span data-ttu-id="f4421-106">Como padrão, os Servidores de Borda não são reunidos em um domínio e não têm um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="f4421-106">By default, Edge Servers are not joined to a domain and will not have a fully qualified domain name (fully qualified domain name).</span></span> <span data-ttu-id="f4421-107">O Servidor de Borda é referenciado apenas pelo nome (de máquina) curto, não um nome de domínio totalmente qualificado.</span><span class="sxs-lookup"><span data-stu-id="f4421-107">The Edge Server is only referred to by the short (machine) name, not a fully qualified domain name.</span></span> <span data-ttu-id="f4421-108">No entanto, o construtor de topologias usa FQDNs, não nomes curtos.</span><span class="sxs-lookup"><span data-stu-id="f4421-108">However, Topology Builder uses FQDNs, not short names.</span></span> <span data-ttu-id="f4421-109">O nome do servidor de borda deve corresponder ao FQDN usado pelo construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="f4421-109">The name of the Edge Server must match the FQDN used by Topology Builder.</span></span> <span data-ttu-id="f4421-110">Para isso, você define um sufixo DNS que, ao ser combinado como nome de máquina, resulta no FQDN esperado.</span><span class="sxs-lookup"><span data-stu-id="f4421-110">To do this, you define a DNS suffix that, when combined with the machine name, results in the expected FQDN.</span></span> <span data-ttu-id="f4421-111">Use o seguinte procedimento em "Para adicionar o sufixo DNS do nome do computador em um Servidor de Borda que não está associado a um domínio" para adicionar o sufixo DNS ao nome do computador.</span><span class="sxs-lookup"><span data-stu-id="f4421-111">Use the following procedure in “To add the DNS suffix to the computer name on and Edge Server that is not joined to a domain” to add the DNS suffix to the computer name.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f4421-112">Por padrão, o DNS usa um algoritmo Round Robin para girar a ordem dos dados de registro de recurso retornados nas respostas da consulta, onde há vários registros de recursos do mesmo tipo para um nome de domínio DNS consultado.</span><span class="sxs-lookup"><span data-stu-id="f4421-112">By default, DNS uses a round robin algorithm to rotate the order of resource record data returned in query answers where multiple resource records of the same type exist for a queried DNS domain name.</span></span> <span data-ttu-id="f4421-113">O balanceamento de carga DNS do Lync Server 2013 depende do rodízio de DNS como parte do mecanismo de balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="f4421-113">Lync Server 2013 DNS load balancing, depends on DNS round-robin as a part of the DNS Load Balancing mechanism.</span></span> <span data-ttu-id="f4421-114">Verifique se a configuração Round-Robin não foi desativada.</span><span class="sxs-lookup"><span data-stu-id="f4421-114">Verify that round-robin setting has not been disabled.</span></span> <span data-ttu-id="f4421-115">Se você estiver usando um servidor DNS que não esteja executando um sistema operacional Windows, verifique se a classificação de registro de recurso Round-Robin está habilitada.</span><span class="sxs-lookup"><span data-stu-id="f4421-115">If you are using a DNS server that is not running a Windows operating system, verify that round-robin resource record ordering is enabled.</span></span>



</div>

<span data-ttu-id="f4421-116">Use os procedimentos a seguir em “**Para criar um registro DNS SRV**” para criar e verificar cada registro DNS SRV.</span><span class="sxs-lookup"><span data-stu-id="f4421-116">Use the following procedures in “**To create a DNS SRV record**” to create and verify each DNS SRV record.</span></span> <span data-ttu-id="f4421-117">Use o procedimento em “**Para criar um registro A de DNS**” para definir os registros A de DNS necessários para acesso do usuário externo.</span><span class="sxs-lookup"><span data-stu-id="f4421-117">Use the procedure in “**To create a DNS A record**” to define the DNS A records required for external user access.</span></span> <span data-ttu-id="f4421-118">Para confirmar que os registros estão configurados e funcionando corretamente, consulte “**Para verificar um registro DNS**” neste tópico.</span><span class="sxs-lookup"><span data-stu-id="f4421-118">To confirm that the records are configured and working correctly, see “**To verify a DNS record**” in this topic.</span></span> <span data-ttu-id="f4421-119">Para obter detalhes sobre cada registro necessário para dar suporte ao acesso de usuário externo, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f4421-119">For details about each record required to support external user access, see [Determine DNS requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).</span></span>

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a><span data-ttu-id="f4421-120">Para adicionar o sufixo DNS do nome do computador em um Servidor de Borda que não está associado a um domínio</span><span class="sxs-lookup"><span data-stu-id="f4421-120">To add the DNS suffix to the computer name on an Edge Server that is not joined to a domain</span></span>

1.  <span data-ttu-id="f4421-121">No computador, clique em **Iniciar**, clique com o botão direito do mouse em **cComputador** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f4421-121">On the computer, click **Start**, right-click **Computer**, and then click **Properties**.</span></span>

2.  <span data-ttu-id="f4421-122">Em **Nome do computador, domínio e configurações de grupo de trabalho**, clique em **Alterar configurações**.</span><span class="sxs-lookup"><span data-stu-id="f4421-122">Under **Computer name, domain, and workgroup settings**, click **Change settings**.</span></span>

3.  <span data-ttu-id="f4421-123">Na guia **Nome do Computador**, clique em **Alterar**.</span><span class="sxs-lookup"><span data-stu-id="f4421-123">On the **Computer Name** tab, click **Change**.</span></span>

4.  <span data-ttu-id="f4421-124">Em   **Alterações de Nome/Domínio do Computador**, clique em **Mais**.</span><span class="sxs-lookup"><span data-stu-id="f4421-124">In **Computer Name/Domain Changes**, click **More**.</span></span>

5.  <span data-ttu-id="f4421-125">Em **Sufixo DNS e nome NetBIOS do computador**, no **Sufixo DNS primário deste computador**, digite o nome de seu domínio interno (por exemplo, corp.contoso.com) e clique em **OK** três vezes.</span><span class="sxs-lookup"><span data-stu-id="f4421-125">In **DNS Suffix and NetBIOS Computer Name**, in **Primary DNS suffix of this computer**, type the name of your internal domain (for example, corp.contoso.com), and then click **OK** three times.</span></span>

6.  <span data-ttu-id="f4421-126">Reinicie o computador.</span><span class="sxs-lookup"><span data-stu-id="f4421-126">Restart the computer.</span></span>

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a><span data-ttu-id="f4421-127">Para criar um registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="f4421-127">To create a DNS SRV record</span></span>

1.  <span data-ttu-id="f4421-128">No servidor DNS apropriado, clique em **Iniciar**, clique em **Painel de Controle**, clique em **Ferramentas Administrativas** e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4421-128">On the appropriate DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="f4421-129">Você precisa configurar o DNS para que haja: 1) entradas DNS externas para pesquisas de DNS externas por usuários remotos e parceiros federados; 2) entradas de pesquisa de DNS para uso pelos servidores de borda dentro da rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada), incluindo registros para os servidores internos que executam o Lync Server 2013; e 3) entradas de DNS internas para pesquisas pelos clientes internos e servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f4421-129">You need to configure DNS so that there are: 1) external DNS entries for external DNS lookups by remote users and federated partners; 2) entries for DNS lookups for use by the Edge Servers within the perimeter network (also known as DMZ, demilitarized zone, and screened subnet), including A records for the internal servers running Lync Server 2013; and 3) internal DNS entries for lookups by the internal clients and servers running Lync Server 2013.</span></span>

    
    </div>

2.  <span data-ttu-id="f4421-130">Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio onde o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="f4421-130">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain where Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="f4421-131">Clique em **Outros Registros Novos**.</span><span class="sxs-lookup"><span data-stu-id="f4421-131">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="f4421-132">Em **Selecione um tipo de registro de recurso**, digite o **Local do Serviço (SRV)** e, em seguida, clique em **Criar Registro**.</span><span class="sxs-lookup"><span data-stu-id="f4421-132">In **Select a resource record type**, type **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="f4421-133">Forneça todas as informações exigidas para o registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="f4421-133">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-create-a-dns-a-record"></a><span data-ttu-id="f4421-134">Para criar um registro A de DNS</span><span class="sxs-lookup"><span data-stu-id="f4421-134">To create a DNS A record</span></span>

1.  <span data-ttu-id="f4421-135">No servidor DNS, clique em **Iniciar**, clique em **Painel de Controle**, clique em **Ferramentas Administrativas** e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f4421-135">On the DNS server, click **Start**, click **Control Panel**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f4421-136">Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 está instalado.</span><span class="sxs-lookup"><span data-stu-id="f4421-136">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 is installed.</span></span>

3.  <span data-ttu-id="f4421-137">Clique em **Novo Host (A)**.</span><span class="sxs-lookup"><span data-stu-id="f4421-137">Click **New Host (A)**.</span></span>

4.  <span data-ttu-id="f4421-138">Forneça todas as informações exigidas para o registro SRV de DNS.</span><span class="sxs-lookup"><span data-stu-id="f4421-138">Provide all required information for the DNS SRV record.</span></span>

</div>

<div>

## <a name="to-verify-a-dns-record"></a><span data-ttu-id="f4421-139">Para verificar um registro DNS</span><span class="sxs-lookup"><span data-stu-id="f4421-139">To verify a DNS record</span></span>

1.  <span data-ttu-id="f4421-140">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="f4421-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f4421-141">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f4421-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f4421-142">No prompt de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="f4421-142">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN edge interface>

4.  <span data-ttu-id="f4421-143">Verifique se você recebe uma resposta que resolve o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="f4421-143">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f4421-144">Confira também</span><span class="sxs-lookup"><span data-stu-id="f4421-144">See Also</span></span>


[<span data-ttu-id="f4421-145">Criar um registro SRV de DNS para integração com a UM do Exchange hospedado</span><span class="sxs-lookup"><span data-stu-id="f4421-145">Create a DNS SRV record for integration with hosted Exchange UM</span></span>](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[<span data-ttu-id="f4421-146">Determinar requisitos de DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4421-146">Determine DNS requirements for Lync Server 2013</span></span>](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

