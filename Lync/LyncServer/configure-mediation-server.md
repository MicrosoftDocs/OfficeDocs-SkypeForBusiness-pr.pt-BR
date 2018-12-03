---
title: Configurar o servidor de mediação
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 143d98cebc151473b790246bc78d75e6e2f4185a
ms.sourcegitcommit: a599bdd5057c4fc38e14b4f14961e1a6bf08ee8a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2018
ms.locfileid: "27128162"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="74f70-102">Configurar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="74f70-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody"><span data-ttu-id="74f70-103">

<span> </span></span><span class="sxs-lookup"><span data-stu-id="74f70-103"></span></span>

<span data-ttu-id="74f70-104">_**Tópico modificado em:** 28-09-2012_</span><span class="sxs-lookup"><span data-stu-id="74f70-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="74f70-105">Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do Office Communications Server 2007 R2 servidor de mediação herdado.</span><span class="sxs-lookup"><span data-stu-id="74f70-105">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="74f70-106">Para publicar com êxito, habilitar ou desabilitar uma topologia quando a adição ou remoção de uma função de servidor, você deve estar logado como um usuário que seja membro dos grupos RTCUniversalServerAdmins e administradores de domínio.</span><span class="sxs-lookup"><span data-stu-id="74f70-106">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="74f70-107">Também é possível delegar os direitos de administrador e permissões para adicionar funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="74f70-107">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="74f70-108">Para obter detalhes, consulte Delegate Setup Permissions o servidor Standard Edition ou Enterprise Edition documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="74f70-108">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="74f70-109">Para outras alterações de configuração, apenas a associação ao grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="74f70-109">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74f70-110">Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, IP-PBXs e serviços de tronco SIP que funcionam com o Lync Server 2013, consulte "Microsoft Unified Communications programa de interoperabilidade aberta" em <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span><span class="sxs-lookup"><span data-stu-id="74f70-110">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="74f70-111">Para configurar o servidor de mediação usando o construtor de topologia</span><span class="sxs-lookup"><span data-stu-id="74f70-111">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="74f70-112">Abra uma topologia existente no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="74f70-112">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="74f70-113">No painel esquerdo, navegue até **gateways PSTN**.</span><span class="sxs-lookup"><span data-stu-id="74f70-113">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="74f70-114">Clique com o botão **gateways PSTN**e clique em **Novo Gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="74f70-114">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="74f70-115">Preencha a página **Definir Novo Gateway IP/PSTN** com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="74f70-115">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="74f70-116">Digite o FQDN ou endereço IP do gateway.</span><span class="sxs-lookup"><span data-stu-id="74f70-116">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="74f70-117">O FQDN do gateway é necessário se o gateway usa o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="74f70-117">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="74f70-118">Aceite o valor padrão da **porta de escuta para gateway IP/PSTN** ou insira a nova porta de escuta se ela foi modificada.</span><span class="sxs-lookup"><span data-stu-id="74f70-118">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="74f70-119">Defina o **protocolo de transporte de Sip**.</span><span class="sxs-lookup"><span data-stu-id="74f70-119">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="74f70-120">No painel esquerdo, navegue até o **pool de Front End do Enterprise Edition** ou **Standard Edition Server**.</span><span class="sxs-lookup"><span data-stu-id="74f70-120">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="74f70-121">Com o botão direito do pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="74f70-121">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="74f70-122">Em **Servidor de mediação**, defina as **portas de escuta**.</span><span class="sxs-lookup"><span data-stu-id="74f70-122">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="74f70-123">Em seguida, associe o gateway PSTN recém-criado, selecionando-o e clicando em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="74f70-123">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="74f70-124">No **Construtor de topologias**, selecione o nó superior **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="74f70-124">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="74f70-125">No menu **ação** , selecione **Publicar topologia** e, em seguida, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="74f70-125">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="74f70-126">Quando o **Assistente para publicação** for concluído, clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="74f70-126">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="74f70-127">É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">rotas de voz de alteração para usar o servidor de mediação do Lync Server 2013 novo</A> para garantir que as rotas de voz estejam apontando para o servidor de mediação correto.</span><span class="sxs-lookup"><span data-stu-id="74f70-127">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



<span data-ttu-id="74f70-128"></div>

</div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="74f70-128"></span></span></div>

