---
title: Configurar o servidor de mediação
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configure Mediation Server
ms:assetid: 583236fd-33cd-4045-81df-baa58ed07779
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204913(v=OCS.15)
ms:contentKeyID: 48184207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eb9b2c7cf8da1d454f310a8ac999dddbc7d34f68
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-mediation-server"></a><span data-ttu-id="b62d4-102">Configurar o servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="b62d4-102">Configure Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b62d4-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b62d4-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b62d4-104">Este procedimento detalha as etapas para configurar o pool do Lync Server 2013 para usar o servidor de mediação do Lync Server 2013, em vez do servidor herdado do Office Communications Server 2007 R2 Media Server.</span><span class="sxs-lookup"><span data-stu-id="b62d4-104">This procedure details the steps to configure the Lync Server 2013 pool to use the Lync Server 2013 Mediation Server, instead of the legacy Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="b62d4-105">Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo RTCUniversalServerAdmins e administradores do domínio.</span><span class="sxs-lookup"><span data-stu-id="b62d4-105">To successfully publish, enable, or disable a topology when adding or removing a server role, you should be logged in as a user who is a member of the RTCUniversalServerAdmins and Domain Admins groups.</span></span> <span data-ttu-id="b62d4-106">Também é possível delegar direitos e permissões de administrador adequadas para adicionar funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="b62d4-106">It is also possible to delegate the proper administrator rights and permissions for adding server roles.</span></span> <span data-ttu-id="b62d4-107">Para obter detalhes, consulte delegar permissões de configuração na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server.</span><span class="sxs-lookup"><span data-stu-id="b62d4-107">For details, see Delegate Setup Permissions in the Standard Edition server or Enterprise Edition server Deployment documentation.</span></span> <span data-ttu-id="b62d4-108">Para outras alterações de configuração, somente a associação no grupo RTCUniversalServerAdmins é necessária.</span><span class="sxs-lookup"><span data-stu-id="b62d4-108">For other configuration changes, only membership in the RTCUniversalServerAdmins group is required.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b62d4-109">Para obter as informações mais recentes sobre como localizar gateways PSTN qualificados, PBXs IP e serviços de entroncamento SIP que funcionam com o Lync Server 2013, consulte "programa de interoperabilidade aberto da <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>Microsoft Unified Communications" em.</span><span class="sxs-lookup"><span data-stu-id="b62d4-109">For the latest information on finding qualified PSTN gateways, IP-PBXs, and SIP trunking services that work with Lync Server 2013, see "Microsoft Unified Communications Open Interoperability Program" at <A href="http://go.microsoft.com/fwlink/p/?linkid=206015">http://go.microsoft.com/fwlink/p/?linkId=206015</A>.</span></span>



</div>

<div>

## <a name="to-configure-mediation-server-using-topology-builder"></a><span data-ttu-id="b62d4-110">Para configurar o servidor de mediação usando o construtor de topologias</span><span class="sxs-lookup"><span data-stu-id="b62d4-110">To configure Mediation Server Using Topology Builder</span></span>

1.  <span data-ttu-id="b62d4-111">Abra uma topologia existente do construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="b62d4-111">Open an existing topology from Topology Builder.</span></span>

2.  <span data-ttu-id="b62d4-112">No painel esquerdo, navegue até **gateways PSTN**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-112">In the left pane, navigate to **PSTN gateways**.</span></span>

3.  <span data-ttu-id="b62d4-113">Clique com o botão direito do mouse em **gateways PSTN**e clique em **novo gateway IP/PSTN**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-113">Right-click **PSTN gateways**, and then click **New IP/PSTN Gateway**.</span></span>

4.  <span data-ttu-id="b62d4-114">Conclua a página **definir o novo gateway IP/PSTN** com as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="b62d4-114">Complete the **Define New IP/PSTN Gateway** page with the following information:</span></span>
    
      - <span data-ttu-id="b62d4-115">Digite o endereço IP ou FQDN do gateway.</span><span class="sxs-lookup"><span data-stu-id="b62d4-115">Enter the gateway FQDN or IP address.</span></span> <span data-ttu-id="b62d4-116">O FQDN do gateway será necessário se o gateway usar o protocolo TLS.</span><span class="sxs-lookup"><span data-stu-id="b62d4-116">The FQDN of the gateway is required if the gateway uses the TLS protocol.</span></span>
    
      - <span data-ttu-id="b62d4-117">Aceite o valor padrão da **porta de escuta do gateway IP/PSTN** ou digite a nova porta de escuta se ela tiver sido modificada.</span><span class="sxs-lookup"><span data-stu-id="b62d4-117">Accept the default value of the **Listening port for IP/PSTN gateway** or enter the new listening port if it was modified.</span></span>
    
      - <span data-ttu-id="b62d4-118">Defina o **protocolo de transporte SIP**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-118">Set the **Sip Transport Protocol**.</span></span>

5.  <span data-ttu-id="b62d4-119">No painel esquerdo, navegue até o **pool de front-end do Enterprise Edition** ou o **servidor Standard Edition**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-119">In the left pane, navigate to the **Enterprise Edition Front End pool** or the **Standard Edition Server**.</span></span>

6.  <span data-ttu-id="b62d4-120">Clique com o botão direito do mouse no pool e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-120">Right-click the pool, and then click **Edit Properties**.</span></span>

7.  <span data-ttu-id="b62d4-121">Em **servidor de mediação**, defina as **portas de escuta**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-121">Under **Mediation Server**, set the **Listening ports**.</span></span>

8.  <span data-ttu-id="b62d4-122">Em seguida, associe o gateway PSTN recém-criado selecionando-o e clicando em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-122">Next, associate the newly created PSTN gateway by selecting it and clicking **Add**.</span></span>

9.  <span data-ttu-id="b62d4-123">Em **Construtor de topologia**, selecione o nó mais superior do **Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-123">In **Topology Builder**, select the top-most node **Lync Server**.</span></span>

10. <span data-ttu-id="b62d4-124">No menu **ação** , selecione **publicar topologia** e clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="b62d4-124">From the **Action** menu, select **Publish Topology** and then click **Next**.</span></span>

11. <span data-ttu-id="b62d4-125">Quando o **Assistente de publicação** for concluído, clique em **concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="b62d4-125">When the **Publishing wizard** completes, click **Finish** to close the wizard.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b62d4-126">É importante que você conclua o próximo tópico, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">altere as rotas de voz para usar o novo servidor de mediação do Lync server 2013</A> para garantir que as rotas de voz aponte para o servidor de mediação correto.</span><span class="sxs-lookup"><span data-stu-id="b62d4-126">It is important that you complete the next topic, <A href="change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md">Change voice routes to use the new Lync Server 2013 Mediation Server</A> to ensure that the voice routes are pointing to the correct Mediation Server.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

