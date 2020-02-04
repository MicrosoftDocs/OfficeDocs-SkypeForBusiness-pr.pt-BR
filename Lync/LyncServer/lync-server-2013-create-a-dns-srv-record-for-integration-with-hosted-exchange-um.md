---
title: Criar um registro DNS SRV para integração com Exchange UM hospedado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a><span data-ttu-id="b141f-102">Criar um registro DNS SRV para integração com Exchange UM hospedado</span><span class="sxs-lookup"><span data-stu-id="b141f-102">Create a DNS SRV record for integration with hosted Exchange UM</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b141f-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="b141f-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="b141f-104">Este tópico descreve como configurar o registro SRV do sistema de nome de domínio (DNS) necessário para um servidor de borda do Lync Server 2013 para direcionar para um serviço do Exchange hospedado, como o Microsoft Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b141f-104">This topic describes how to configure the Domain Name System (DNS) SRV record that is required for a Lync Server 2013 Edge Server to route to a hosted Exchange service such as Microsoft Exchange Online.</span></span>

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a><span data-ttu-id="b141f-105">Para criar um registro SRV DNS externo para o serviço hospedado do Exchange</span><span class="sxs-lookup"><span data-stu-id="b141f-105">To create an external DNS SRV record for the hosted Exchange service</span></span>

1.  <span data-ttu-id="b141f-106">Faça logon no servidor DNS externo como membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="b141f-106">Log on to the external DNS server as a member of the DnsAdmins group.</span></span>

2.  <span data-ttu-id="b141f-107">Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="b141f-107">Click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

3.  <span data-ttu-id="b141f-108">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e selecione o domínio SIP no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="b141f-108">In the console tree for your SIP domain, expand **Forward Lookup Zones**, and select the SIP domain in which Lync Server 2013 will be installed.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="b141f-109">Você deve criar o registro SRV DNS no domínio SIP no qual o Lync Server está ou será instalado.</span><span class="sxs-lookup"><span data-stu-id="b141f-109">You must create the DNS SRV record in the SIP domain in which Lync Server is or will be installed.</span></span> <span data-ttu-id="b141f-110">Quando você cria o registro SRV, o FQDN usado para o host que oferece este campo de serviço deve ser o FQDN externo do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="b141f-110">When you create the SRV record, the FQDN used for the Host offering this service field must be the external FQDN of the Edge pool.</span></span> <span data-ttu-id="b141f-111">Por exemplo, se o FQDN externo do seu pool de bordas for edge01.contoso.net, insira esse valor.</span><span class="sxs-lookup"><span data-stu-id="b141f-111">For example, if the external FQDN of your Edge pool is edge01.contoso.net, enter that value.</span></span> <span data-ttu-id="b141f-112">Isso também deve estar no mesmo domínio que o registro de hosts DNS (A).</span><span class="sxs-lookup"><span data-stu-id="b141f-112">This must also be in the same domain as the DNS Hosts (A) record.</span></span>

    
    </div>

4.  <span data-ttu-id="b141f-113">Clique com o botão direito do mouse no domínio selecionado e, em seguida, clique em **outros novos registros**.</span><span class="sxs-lookup"><span data-stu-id="b141f-113">Right-click the selected domain, and then click **Other New Records**.</span></span>

5.  <span data-ttu-id="b141f-114">Em **tipo de registro de recurso**, clique em **local do serviço (SRV)** e, em seguida, clique em **criar registro**.</span><span class="sxs-lookup"><span data-stu-id="b141f-114">In **Resource Record Type**, click **Service Location (SRV)**, and then click **Create Record**.</span></span>

6.  <span data-ttu-id="b141f-115">Em **novo registro de recurso**, clique em **serviço**e, em seguida, digite \*\* \_sipfederationtls\*\*.</span><span class="sxs-lookup"><span data-stu-id="b141f-115">In **New Resource Record**, click **Service**, and then type **\_sipfederationtls**.</span></span>

7.  <span data-ttu-id="b141f-116">Clique em **protocolo**e digite \*\* \_TCP\*\*.</span><span class="sxs-lookup"><span data-stu-id="b141f-116">Click **Protocol**, and then type **\_tcp**.</span></span>

8.  <span data-ttu-id="b141f-117">Clique em **Número da porta** e digite **5061**.</span><span class="sxs-lookup"><span data-stu-id="b141f-117">Click **Port Number**, and then type **5061**.</span></span>

9.  <span data-ttu-id="b141f-118">Clique em **host que oferece esse serviço**e digite o nome de domínio totalmente qualificado (FQDN) do pool de bordas do lync Server 2013 que fornece acesso ao seu sistema do lync Server 2013 para clientes externos confiáveis.</span><span class="sxs-lookup"><span data-stu-id="b141f-118">Click **Host offering this service**, and then type the fully qualified domain name (FQDN) of the Lync Server 2013 Edge pool that provides access to your Lync Server 2013 system for trusted external clients.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="b141f-119">O domínio também deve ser configurado como um domínio autoritativo aceito nas configurações do Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="b141f-119">The domain must also be set up as an authoritative, accepted domain in your Exchange Online settings.</span></span> <span data-ttu-id="b141f-120">Para obter detalhes, consulte criar domínios aceitos em <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span><span class="sxs-lookup"><span data-stu-id="b141f-120">For details, see Create Accepted Domains at <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.</span></span>

    
    </div>

10. <span data-ttu-id="b141f-121">Clique em **OK** e em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="b141f-121">Click **OK**, and then click **Done**.</span></span>

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a><span data-ttu-id="b141f-122">Para verificar se o registro SRV DNS foi criado com êxito</span><span class="sxs-lookup"><span data-stu-id="b141f-122">To verify that the DNS SRV record was created successfully</span></span>

1.  <span data-ttu-id="b141f-123">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="b141f-123">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="b141f-124">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="b141f-124">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="b141f-125">No prompt de comando, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="b141f-125">At the command prompt, run the following command:</span></span>
    
        nslookup <FQDN Lync Edge Pool>

4.  <span data-ttu-id="b141f-126">Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="b141f-126">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b141f-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="b141f-127">See Also</span></span>


[<span data-ttu-id="b141f-128">Criar registros de DNS para servidores de proxy reverso no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b141f-128">Create DNS records for reverse proxy servers in Lync Server 2013</span></span>](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

