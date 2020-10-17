---
title: Atualizar registros de DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d45abd1599666079705f3e77b74ac2ba81d9df71
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503508"
---
# <a name="update-dns-srv-records"></a><span data-ttu-id="58e0f-102">Atualizar registros de DNS SRV</span><span class="sxs-lookup"><span data-stu-id="58e0f-102">Update DNS SRV records</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58e0f-103">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="58e0f-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="58e0f-104">Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="58e0f-104">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="58e0f-105">Este tópico descreve como atualizar os registros DNS (sistema de nomes de domínio) após a migração para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58e0f-105">This topic describes how to update the Domain Name System (DNS) records after migrating to Lync Server 2013.</span></span> <span data-ttu-id="58e0f-106">Após todos os usuários terem sido movidos para o Lync Server 2013, mas antes de o pool ou diretor herdado do Lync Server 2010 ser descomissionado, você deve atualizar os registros SRV DNS no seu DNS interno para cada domínio SIP.</span><span class="sxs-lookup"><span data-stu-id="58e0f-106">After all users have been moved to Lync Server 2013, but before the legacy Lync Server 2010 pool or Director is decommissioned, you must update the DNS SRV records in your internal DNS for every SIP domain.</span></span> <span data-ttu-id="58e0f-107">Este procedimento supõe que o DNS interno tem zonas para os domínios de usuário do SIP.</span><span class="sxs-lookup"><span data-stu-id="58e0f-107">This procedure assumes that your internal DNS has zones for your SIP user domains.</span></span>

<span data-ttu-id="58e0f-108">**Para configurar um registro SRV de DNS**</span><span class="sxs-lookup"><span data-stu-id="58e0f-108">**To configure a DNS SRV record**</span></span>

1.  <span data-ttu-id="58e0f-109">No servidor DNS, clique em **Iniciar**, clique em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="58e0f-109">On the DNS server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="58e0f-110">Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**, expanda o domínio SIP no qual o Lync Server 2013 está instalado e navegue até a configuração \*\* \_ TCP\*\* .</span><span class="sxs-lookup"><span data-stu-id="58e0f-110">In the console tree for your SIP domain, expand **Forward Lookup Zones**, expand the SIP domain in which Lync Server 2013 is installed, and navigate to the **\_tcp** setting.</span></span>

3.  <span data-ttu-id="58e0f-111">No painel direito, clique com o botão direito do mouse em \*\* \_ sipinternaltls\*\* e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="58e0f-111">In the right pane, right click **\_sipinternaltls** and select **Properties**.</span></span>

4.  <span data-ttu-id="58e0f-112">Em **host que oferece esse serviço**, atualize o FQDN do host para apontar para o pool do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="58e0f-112">In **Host offering this service**, update the host FQDN to point to the Lync Server 2013 pool.</span></span>

5.  <span data-ttu-id="58e0f-113">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="58e0f-113">Click **OK**.</span></span>

<span data-ttu-id="58e0f-114">**Para verificar se o FQDN do servidor Standard Edition ou pool de Front-Ends pode ser resolvido**</span><span class="sxs-lookup"><span data-stu-id="58e0f-114">**To verify that the FQDN of the Front End pool or Standard Edition server can be resolved**</span></span>

1.  <span data-ttu-id="58e0f-115">Faça logon em um computador cliente no domínio.</span><span class="sxs-lookup"><span data-stu-id="58e0f-115">Log on to a client computer in the domain.</span></span>

2.  <span data-ttu-id="58e0f-116">Clique em **Iniciar** e em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="58e0f-116">Click **Start**, and then click **Run**.</span></span>

3.  <span data-ttu-id="58e0f-117">Na caixa **Abrir**, digite **cmd** e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="58e0f-117">In the **Open** box, type **cmd**, and then click **OK**.</span></span>

4.  <span data-ttu-id="58e0f-118">No prompt de comando, digite **nslookup** \<FQDN of the Front End pool\> ou \<FQDN of the Standard Edition server\> e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="58e0f-118">At the command prompt, type **nslookup** \<FQDN of the Front End pool\> or \<FQDN of the Standard Edition server\>, and then press ENTER.</span></span>

5.  <span data-ttu-id="58e0f-119">Verifique se recebeu uma resposta que resolve para o endereço IP apropriado para o FQDN.</span><span class="sxs-lookup"><span data-stu-id="58e0f-119">Verify that you receive a reply that resolves to the appropriate IP address for the FQDN.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

