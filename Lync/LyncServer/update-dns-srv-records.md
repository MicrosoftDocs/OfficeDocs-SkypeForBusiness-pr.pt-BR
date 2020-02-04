---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e00093859a6e252c019183617b4548dfc00218a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738612"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a><span data-ttu-id="f8f57-102">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="f8f57-102">Update DNS SRV records</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8f57-103">_**Tópico da última modificação:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="f8f57-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="f8f57-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="f8f57-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="f8f57-105">Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8f57-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="f8f57-106">Depois que todos os usuários tiverem sido movidos para o Lync Server 2013, mas antes de o pool ou diretor herdado do Lync Server 2010 ser encerrado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="f8f57-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="f8f57-107">Este procedimento pressupõe que o seu DNS interno tem zonas para seus domínios de usuário SIP.</span><span class="sxs-lookup"><span data-stu-id="f8f57-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="f8f57-108">**Para configurar um registro SRV DNS**</span><span class="sxs-lookup"><span data-stu-id="f8f57-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="f8f57-109">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="f8f57-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="f8f57-110">Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Lync Server 2013 está instalado e \*\* \_\*\* navegue até a configuração TCP.</span><span class="sxs-lookup"><span data-stu-id="f8f57-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="f8f57-111">No painel direito, clique com o botão direito do mouse em \*\* \_sipinternaltls\*\* e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="f8f57-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="f8f57-112">Em **host oferecendo esse serviço**, atualize o FQDN do host para apontar para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f8f57-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="f8f57-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f57-113">Click **OK**.</span></span>

<span data-ttu-id="f8f57-114">**Para verificar se o FQDN do servidor de front-end ou do servidor Standard Edition pode ser resolvido**</span><span class="sxs-lookup"><span data-stu-id="f8f57-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="f8f57-115">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="f8f57-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="f8f57-116">Clique em  \*\*Iniciar \*\* e em  \*\*Executar \*\*.</span><span class="sxs-lookup"><span data-stu-id="f8f57-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="f8f57-117">Na caixa **abrir** , digite **cmd**e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="f8f57-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="f8f57-118">No prompt de comando, digite FQDN do **nslookup** \<do pool\> de front- \<end ou FQDN do servidor\>Standard Edition e, em seguida, pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="f8f57-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="f8f57-119">Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="f8f57-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

