---
title: 'Lync Server 2013: Configurar FQDNs da web farm'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure web farm FQDNs
ms:assetid: cb25dbbd-dcea-4997-8e14-e5007dd7d3ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429722(v=OCS.15)
ms:contentKeyID: 48185481
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd01b02cef8d806f390b6b700fa42acd37e27d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733761"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="aec8a-102">Configurar FQDNs da web farm para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="aec8a-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aec8a-103">_**Tópico da última modificação:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="aec8a-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="aec8a-104">Quando você definiu a configuração do servidor Standard Edition, do servidor de front-end, do director ou do diretor do criador no construtor de topologias, você configura um nome de domínio totalmente qualificado (FQDN) dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="aec8a-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="aec8a-105">Durante o processo de logon de um cliente hospedado no servidor Standard Edition ou no pool de front-end, os FQDNs dos serviços Web configurados são enviados por meio de provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="aec8a-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="aec8a-106">Se você precisar adicionar ou alterar a URL de serviços Web externos, use o construtor de topologias para configurar ou reconfigurar a configuração de serviços Web usando o procedimento deste tópico.</span><span class="sxs-lookup"><span data-stu-id="aec8a-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="aec8a-107">Para configurar um FQDN do pool externo para serviços Web</span><span class="sxs-lookup"><span data-stu-id="aec8a-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="aec8a-108">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="aec8a-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="aec8a-109">No construtor de topologias, na árvore de console, em **front-ends da edição padrão**, **front-ends**e **directors**da edição Enterprise, clique com o botão direito do mouse no nome do pool que você precisa editar e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="aec8a-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="aec8a-110">Na seção **Serviços Web** , adicione ou edite o **FQDN dos serviços Web externos**.</span><span class="sxs-lookup"><span data-stu-id="aec8a-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="aec8a-111">Revise e ajuste as **portas de escuta** para http e HTTPS.</span><span class="sxs-lookup"><span data-stu-id="aec8a-111">Review and adjust the **Listening ports** for both HTTP and HTTPS.</span></span> <span data-ttu-id="aec8a-112">Os padrões serão:</span><span class="sxs-lookup"><span data-stu-id="aec8a-112">The defaults will be:</span></span>
    
      - <span data-ttu-id="aec8a-113">**Portas de escuta:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="aec8a-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="aec8a-114">**Portas publicadas:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="aec8a-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="aec8a-115">Onde as **portas de escuta** são a porta que os serviços Web externos serão configurados para receber solicitações do proxy reverso, e as **portas publicadas** são as portas publicadas externamente pelo proxy reverso e são comunicadas aos clientes durante o provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="aec8a-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="aec8a-116">Quando tiver concluído suas adições e atualizações, clique em **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="aec8a-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="aec8a-117">Clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="aec8a-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="aec8a-118">Após a publicação ser concluída com êxito, pode ser apresentado um link que informa que há etapas adicionais que precisam ser executadas.</span><span class="sxs-lookup"><span data-stu-id="aec8a-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="aec8a-119">O link, se clicado, abre uma lista de servidores afetados pelas alterações feitas no construtor de topologias que exigirão que você execute novamente o assistente de implantação do Lync Server em cada servidor listado para atualizar a configuração de componentes adicionados, removidos ou alterados.</span><span class="sxs-lookup"><span data-stu-id="aec8a-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="aec8a-120">Repita essas etapas para cada servidor Standard Edition, o pool de front-end, o diretor ou o pool do diretor da organização.</span><span class="sxs-lookup"><span data-stu-id="aec8a-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

