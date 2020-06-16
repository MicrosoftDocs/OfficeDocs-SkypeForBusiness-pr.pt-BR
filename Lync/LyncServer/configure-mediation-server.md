---
title: Configurar o servidor de mediação
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82da1720cab2e6895c53565da17c9411faabdfbd
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="3f674-102">Configurar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="3f674-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3f674-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3f674-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3f674-104">Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do servidor herdado do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="3f674-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="3f674-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span><span class="sxs-lookup"><span data-stu-id="3f674-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="3f674-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span><span class="sxs-lookup"><span data-stu-id="3f674-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="3f674-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span><span class="sxs-lookup"><span data-stu-id="3f674-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="3f674-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span><span class="sxs-lookup"><span data-stu-id="3f674-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f674-109">Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, IP-PBXs e serviços de tronco SIP que funcionam com o Lync Server 2013, consulte "programa de interoperabilidade aberta da comunicação unificada da Microsoft" em <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A> .</span><span class="sxs-lookup"><span data-stu-id="3f674-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="https://go.microsoft.com/fwlink/p/?linkid=206015">https://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="3f674-110">Para configurar o Servidor de Mediação usando o Construtor de Topologias</span><span class="sxs-lookup"><span data-stu-id="3f674-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="3f674-111">Abra uma topologia existente no Construtor de Topologias.</span><span class="sxs-lookup"><span data-stu-id="3f674-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="3f674-112">No painel esquerdo, navegue até **Gateways PSTN**.</span><span class="sxs-lookup"><span data-stu-id="3f674-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="3f674-113">Clique com o botão direito nos **Gateways PSTN** e, clique em **Novo Gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="3f674-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="3f674-114">Complete a página **Definir Novo Gateway IP/PSTN** com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="3f674-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="3f674-115">Enter the gateway FQDN or IP address.</span><span class="sxs-lookup"><span data-stu-id="3f674-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="3f674-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span><span class="sxs-lookup"><span data-stu-id="3f674-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="3f674-117">Aceite o valor padrão do **Porta de Escuta do Gateway IP/PSTN** ou insira a nova porta de escuta se ela for modificada.</span><span class="sxs-lookup"><span data-stu-id="3f674-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="3f674-118">Defina o **Protocolo de Transporte SIP**.</span><span class="sxs-lookup"><span data-stu-id="3f674-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="3f674-119">No painel esquerdo, navegue até o **Pool de Front-Ends Enterprise Edition** ou o **Servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="3f674-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="3f674-120">Clique com o botão direito no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="3f674-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="3f674-121">Em **Servidor de Mediação**, defina as **Portas de Escuta**.</span><span class="sxs-lookup"><span data-stu-id="3f674-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="3f674-122">Em seguida, associe o gateway PSTN mais recente criado, o selecionando e clicando em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3f674-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="3f674-123">Em **Construtor de Topologias**, selecione o nó superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3f674-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="3f674-124">No menu **Ação**, selecione **Publicar Topologia** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="3f674-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="3f674-125">Quando o **Assistente para Publicação** for concluído, clique em \*\*Concluir \*\* para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="3f674-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3f674-126">É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">altere as rotas de voz para usar o novo servidor de mediação do Lync Server 2013</A> para garantir que as rotas de voz estejam apontando para o servidor de mediação correto.</span><span class="sxs-lookup"><span data-stu-id="3f674-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

