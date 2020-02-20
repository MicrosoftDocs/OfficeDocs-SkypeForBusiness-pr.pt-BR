---
title: 'Lync Server 2013: criar e verificar registros DNS SRV'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 677b657f5bb7dacad6f1379aa4923052ba4ab1c5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152033"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="2d926-102">Criar e verificar registros DNS SRV no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d926-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d926-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="2d926-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="2d926-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span><span class="sxs-lookup"><span data-stu-id="2d926-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="2d926-105">Este tópico descreve como configurar os registros de DNS (sistema de nomes de domínio) que você precisa criar nas implantações do Lync Server 2013 e aqueles necessários para entrar no cliente automático.</span><span class="sxs-lookup"><span data-stu-id="2d926-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="2d926-106">Quando você cria um pool de front-ends, a instalação cria objetos e configurações do Active Directory para o pool, incluindo o nome de domínio totalmente qualificado (FQDN) do pool.</span><span class="sxs-lookup"><span data-stu-id="2d926-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="2d926-107">São criados objetos e configurações semelhantes para um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2d926-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="2d926-108">Para que os clientes possam se conectar ao pool ou ao servidor Standard Edition, o FQDN do pool ou do servidor Standard Edition deve ser registrado no DNS.</span><span class="sxs-lookup"><span data-stu-id="2d926-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="2d926-109">Você deve criar registros SRV de DNS no DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="2d926-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="2d926-110">Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.</span><span class="sxs-lookup"><span data-stu-id="2d926-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="2d926-111">Para configurar um registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="2d926-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="2d926-112">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="2d926-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="2d926-113">Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio SIP no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="2d926-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="2d926-114">Clique em **Outros Registros Novos**.</span><span class="sxs-lookup"><span data-stu-id="2d926-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="2d926-115">Em **Selecione um tipo de registro de recurso**, clique em **Local do Serviço (SRV)** e, em seguida, clique em **Criar Registro**.</span><span class="sxs-lookup"><span data-stu-id="2d926-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="2d926-116">Clique em **serviço**e digite \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="2d926-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="2d926-117">Clique em **protocolo**e digite \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="2d926-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="2d926-118">Clique em **Número da Porta** e digite **5061**.</span><span class="sxs-lookup"><span data-stu-id="2d926-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="2d926-119">Clique em **host que oferece este serviço**e digite o FQDN do pool ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="2d926-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="2d926-120">Clique em **OK** e em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="2d926-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="2d926-121">Para verificar a criação de um registro SRV de DNS</span><span class="sxs-lookup"><span data-stu-id="2d926-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="2d926-122">Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.</span><span class="sxs-lookup"><span data-stu-id="2d926-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="2d926-123">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2d926-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="2d926-124">Na caixa **Abrir**, digite **cmd** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d926-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="2d926-125">No prompt de comando, digite **nslookup** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2d926-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="2d926-126">Digite **set type=srv** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2d926-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="2d926-127">Digite \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="2d926-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="2d926-128">A saída exibida para o registro de TLS (segurança de camada de transporte) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="2d926-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="2d926-129">Servidor: \<servidor\>DNS. contoso.com</span><span class="sxs-lookup"><span data-stu-id="2d926-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="2d926-130">Endereço: \<endereço IP do servidor DNS\></span><span class="sxs-lookup"><span data-stu-id="2d926-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="2d926-131">Resposta não-autorizada:</span><span class="sxs-lookup"><span data-stu-id="2d926-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="2d926-132">\_sipinternaltls. \_local do serviço SRV do TCP.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="2d926-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="2d926-133">prioridade = 0</span><span class="sxs-lookup"><span data-stu-id="2d926-133">priority = 0</span></span>
    
    <span data-ttu-id="2d926-134">Weight = 0</span><span class="sxs-lookup"><span data-stu-id="2d926-134">weight = 0</span></span>
    
    <span data-ttu-id="2d926-135">porta = 5061</span><span class="sxs-lookup"><span data-stu-id="2d926-135">port = 5061</span></span>
    
    <span data-ttu-id="2d926-136">nome da SVR = poolname.contoso.com (ou um registro do servidor Standard Edition A)</span><span class="sxs-lookup"><span data-stu-id="2d926-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="2d926-137">poolname.contoso.com Internet address = \<endereço IP virtual do balanceador de carga\> ou \<endereço IP de um único servidor Enterprise Edition para pools com apenas um servidor\> Enterprise Edition \<ou endereço IP do servidor Standard Edition\></span><span class="sxs-lookup"><span data-stu-id="2d926-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="2d926-138">Quando terminar, no prompt de comando, digite **exit** e pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="2d926-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="2d926-139">Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido</span><span class="sxs-lookup"><span data-stu-id="2d926-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="2d926-140">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="2d926-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="2d926-141">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="2d926-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="2d926-142">Na caixa **Abrir**, digite **cmd** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d926-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="2d926-143">No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<ends ou FQDN do servidor\>Standard Edition e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="2d926-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="2d926-144">Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="2d926-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

