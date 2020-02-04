---
title: 'Lync Server 2013: Criar e verificar registros DNS SRV'
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
ms.openlocfilehash: 8440d2ae91d535c8c4747c923b1b17dda9bb0f46
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a><span data-ttu-id="f8bb0-102">Criar e verificar registros DNS SRV no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f8bb0-102">Create and verify DNS SRV records in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8bb0-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="f8bb0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="f8bb0-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio minimamente como membro do grupo Domain admins ou um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-104">To successfully complete this procedure, you should be logged on to the server or domain minimally as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f8bb0-105">Este tópico descreve como configurar os registros de DNS (sistema de nomes de domínio) que você precisa criar nas implantações do Lync Server 2013 e aqueles necessários para a entrada automática do cliente.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-105">This topic describes how to configure the Domain Name System (DNS) records that you are required to create in Lync Server 2013 deployments and those required for automatic client sign in.</span></span> <span data-ttu-id="f8bb0-106">Quando você cria um pool de front-end, o programa de instalação cria objetos e configurações do Active Directory para o pool, incluindo o nome de domínio totalmente qualificado (FQDN) do pool.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-106">When you create a Front End pool, Setup creates Active Directory objects and settings for the pool, including the pool fully qualified domain name (FQDN).</span></span> <span data-ttu-id="f8bb0-107">Objetos e configurações semelhantes são criados para um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-107">Similar objects and settings are created for a Standard Edition server.</span></span> <span data-ttu-id="f8bb0-108">Para que os clientes possam se conectar ao servidor do pool ou da edição Standard, o FQDN do pool ou do servidor Standard Edition deve ser registrado no DNS.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-108">For clients to be able to connect to the pool or Standard Edition server, the FQDN of the pool or Standard Edition server must be registered in DNS.</span></span> <span data-ttu-id="f8bb0-109">Você deve criar registros SRV DNS no seu DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-109">You must create DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f8bb0-110">Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-110">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<div>

## <a name="to-configure-a-dns-srv-record"></a><span data-ttu-id="f8bb0-111">Para configurar um registro SRV DNS</span><span class="sxs-lookup"><span data-stu-id="f8bb0-111">To configure a DNS SRV record</span></span>

1.  <span data-ttu-id="f8bb0-112">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-112">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f8bb0-113">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio SIP no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-113">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and then right-click the SIP domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="f8bb0-114">Clique em **outros novos registros**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-114">Click **Other New Records**.</span></span>

4.  <span data-ttu-id="f8bb0-115">Em **Selecionar um tipo de registro de recurso**, clique em **Local do serviço(SRV)**, e depois clique em **Criar registro**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-115">In **Select a resource record type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

5.  <span data-ttu-id="f8bb0-116">Clique em **serviço**e, em seguida, digite \*\* \_sipinternaltls\*\*.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-116">Click **Service**, and then type **\_sipinternaltls**.</span></span>

6.  <span data-ttu-id="f8bb0-117">Clique em **protocolo**e digite \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-117">Click **Protocol**, and then type **\_tcp**.</span></span>

7.  <span data-ttu-id="f8bb0-118">Clique em **Número da porta** e digite **5061**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-118">Click **Port Number**, and then type **5061**.</span></span>

8.  <span data-ttu-id="f8bb0-119">Clique em **Host que oferece este serviço** e digite o FQDN do pool ou o servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-119">Click **Host offering this service**, and then type the FQDN of the pool or Standard Edition server.</span></span>

9.  <span data-ttu-id="f8bb0-120">Clique em **OK** e em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-120">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a><span data-ttu-id="f8bb0-121">Para verificar a criação de um registro SRV DNS</span><span class="sxs-lookup"><span data-stu-id="f8bb0-121">To verify the creation of a DNS SRV record</span></span>

1.  <span data-ttu-id="f8bb0-122">Faça logon em um computador cliente do domínio com uma conta que seja membro do grupo Usuários autenticados ou que tenha permissões equivalentes.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-122">Log on to a client computer in the domain with an account that is a member of the Authenticated Users group or has equivalent permissions.</span></span>

2.  <span data-ttu-id="f8bb0-123">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-123">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f8bb0-124">Na caixa **abrir** , digite **cmd**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-124">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f8bb0-125">No prompt de comando, digite **nslookup**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-125">At the command prompt, type **nslookup**, and then press ENTER.</span></span>

5.  <span data-ttu-id="f8bb0-126">Digite **set type = SRV**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-126">Type **set type=srv**, and then press ENTER.</span></span>

6.  <span data-ttu-id="f8bb0-127">Digite \*\* \_sipinternaltls.\_ tcp.contoso.com\*\*e, em seguida, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-127">Type **\_sipinternaltls.\_tcp.contoso.com**, and then press ENTER.</span></span> <span data-ttu-id="f8bb0-128">A saída exibida para o registro do Transport Layer Security (TLS) é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="f8bb0-128">The output displayed for the Transport Layer Security (TLS) record is as follows:</span></span>
    
    <span data-ttu-id="f8bb0-129">Servidor: \<DNS server\>. contoso.com</span><span class="sxs-lookup"><span data-stu-id="f8bb0-129">Server: \<dns server\>.contoso.com</span></span>
    
    <span data-ttu-id="f8bb0-130">Endereço: \<endereço IP do servidor DNS\></span><span class="sxs-lookup"><span data-stu-id="f8bb0-130">Address: \<IP address of DNS server\></span></span>
    
    <span data-ttu-id="f8bb0-131">Resposta não autoritativa:</span><span class="sxs-lookup"><span data-stu-id="f8bb0-131">Non-authoritative answer:</span></span>
    
    <span data-ttu-id="f8bb0-132">\_sipinternaltls. \_localização do serviço SRV TCP.contoso.com:</span><span class="sxs-lookup"><span data-stu-id="f8bb0-132">\_sipinternaltls.\_tcp.contoso.com SRV service location:</span></span>
    
    <span data-ttu-id="f8bb0-133">prioridade = 0</span><span class="sxs-lookup"><span data-stu-id="f8bb0-133">priority = 0</span></span>
    
    <span data-ttu-id="f8bb0-134">Weight = 0</span><span class="sxs-lookup"><span data-stu-id="f8bb0-134">weight = 0</span></span>
    
    <span data-ttu-id="f8bb0-135">porta = 5061</span><span class="sxs-lookup"><span data-stu-id="f8bb0-135">port = 5061</span></span>
    
    <span data-ttu-id="f8bb0-136">SVR hostname = poolname.contoso.com (ou Standard Edition Server A um registro)</span><span class="sxs-lookup"><span data-stu-id="f8bb0-136">svr hostname = poolname.contoso.com (or Standard Edition server A record)</span></span>
    
    <span data-ttu-id="f8bb0-137">Endereço de Internet poolname.contoso.com \<= endereço IP virtual do balanceador de\> carga \<ou endereço IP de um único servidor Enterprise Edition para pools com apenas um servidor\> Enterprise \<Edition ou endereço IP do servidor Standard Edition\></span><span class="sxs-lookup"><span data-stu-id="f8bb0-137">poolname.contoso.com internet address = \<virtual IP Address of the load balancer\> or \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\> or \<IP address of the Standard Edition server\></span></span>

7.  <span data-ttu-id="f8bb0-138">Quando tiver terminado, no prompt de comando, digite **Exit**e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-138">When you are finished, at the command prompt, type **exit**, and then press ENTER.</span></span>

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a><span data-ttu-id="f8bb0-139">Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido</span><span class="sxs-lookup"><span data-stu-id="f8bb0-139">To verify that the FQDN of the Front End pool or Standard Edition server can be resolved</span></span>

1.  <span data-ttu-id="f8bb0-140">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-140">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f8bb0-141">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-141">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f8bb0-142">Na caixa **abrir** , digite **cmd**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-142">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f8bb0-143">No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<end ou FQDN do servidor\>Standard Edition e, em seguida, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-143">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="f8bb0-144">Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="f8bb0-144">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

