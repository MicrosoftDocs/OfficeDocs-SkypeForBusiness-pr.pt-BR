---
title: 'Lync Server 2013: configurar FQDNs de farm da Web'
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
ms.openlocfilehash: 50813855e4181add65ff279933a952116768dcec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42133890"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-web-farm-fqdns-for-lync-server-2013"></a><span data-ttu-id="42312-102">Configurar FQDNs do Web farm para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="42312-102">Configure web farm FQDNs for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42312-103">_**Última modificação do tópico:** 2013-03-29_</span><span class="sxs-lookup"><span data-stu-id="42312-103">_**Topic Last Modified:** 2013-03-29_</span></span>

<span data-ttu-id="42312-104">Ao definir a configuração do servidor Standard Edition, pool de front-ends, diretor ou pool de diretores no construtor de topologias, você configura um FQDN (nome de domínio totalmente qualificado) dos serviços Web externos.</span><span class="sxs-lookup"><span data-stu-id="42312-104">When you defined the configuration of the Standard Edition server, Front End pool, Director or Director pool in Topology Builder, you configure an external web services fully qualified domain name (FQDN).</span></span> <span data-ttu-id="42312-105">Durante o processo de logon de um cliente hospedado no servidor Standard Edition ou no pool de front-ends, os FQDNs de serviços Web configurados são enviados por meio de provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="42312-105">During the log on process of a client homed in the Standard Edition server or Front End pool, the configured web services FQDNs are sent by way of in-band provisioning.</span></span> <span data-ttu-id="42312-106">Se você precisar adicionar ou alterar a URL de serviços Web externos, use o construtor de topologias para configurar ou reconfigurar a configuração dos serviços Web usando o procedimento neste tópico.</span><span class="sxs-lookup"><span data-stu-id="42312-106">If you need to add or change the external web services URL, you use Topology Builder to configure or reconfigure the web services configuration using the procedure in this topic.</span></span>

<div>

## <a name="to-configure-an-external-pool-fqdn-for-web-services"></a><span data-ttu-id="42312-107">Para configurar um FQDN de pool externo para serviços da Web</span><span class="sxs-lookup"><span data-stu-id="42312-107">To configure an external pool FQDN for web services</span></span>

1.  <span data-ttu-id="42312-108">Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="42312-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="42312-109">No construtor de topologias, na árvore de console em **front-ends Standard Edition**, **front-ends Enterprise Edition**e **diretores**, clique com o botão direito do mouse no nome do pool que você precisa editar e clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="42312-109">In Topology Builder, in the console tree under **Standard Edition Front Ends**, **Enterprise Edition Front Ends**, and **Directors**, right-click the pool name that you need to edit, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="42312-110">Na seção **Serviços da Web**, adicione ou edite o **FQDN de serviços da Web externos**.</span><span class="sxs-lookup"><span data-stu-id="42312-110">In the **Web services** section, add or edit the **External web services FQDN**.</span></span>

4.  <span data-ttu-id="42312-p102">Revise e ajuste as **Portas do ouvinte** para HTTP e HTTPS. Os padrões serão:</span><span class="sxs-lookup"><span data-stu-id="42312-p102">Review and adjust the **Listening ports** for both HTTP and HTTPS. The defaults will be:</span></span>
    
      - <span data-ttu-id="42312-113">**Portas do ouvinte:** HTTP 8080, HTTPS 4443</span><span class="sxs-lookup"><span data-stu-id="42312-113">**Listening ports:** HTTP 8080, HTTPS 4443</span></span>
    
      - <span data-ttu-id="42312-114">**Portas publicadas:** HTTP 80, HTTPS 443</span><span class="sxs-lookup"><span data-stu-id="42312-114">**Published ports:** HTTP 80, HTTPS 443</span></span>
    
    <span data-ttu-id="42312-115">Onde as **Portas do ouvinte** são as portas onde os serviços da Web externos serão configurados para receber solicitações do proxy inverso e as **Portas publicadas** são as portas publicadas externamente pelo proxy inverso e são comunicadas para clientes durante o provisionamento em banda.</span><span class="sxs-lookup"><span data-stu-id="42312-115">Where the **Listening ports** is the port that the external web services will be configured to receive requests from the reverse proxy, and the **Published ports** is the ports that are published externally by the reverse proxy and is communicated to clients during in-band provisioning.</span></span>

5.  <span data-ttu-id="42312-116">Ao concluir as adições e atualizações, clique em **OK** para continuar.</span><span class="sxs-lookup"><span data-stu-id="42312-116">When you have completed your additions and updates, click **OK** to continue.</span></span>

6.  <span data-ttu-id="42312-117">Clique com o botão direito do mouse em **Lync Server 2013**e clique em **publicar**.</span><span class="sxs-lookup"><span data-stu-id="42312-117">Right-click **Lync Server 2013**, and then click **Publish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="42312-118">Após a publicação concluir com sucesso, um link pode ser apresentado informando que existem etapas adicionais que precisam ser realizadas.</span><span class="sxs-lookup"><span data-stu-id="42312-118">After publishing successfully completes, a link may be presented that informs you that there are additional steps that need to be taken.</span></span> <span data-ttu-id="42312-119">O link, se clicado, abre uma lista de servidores afetados pelas alterações feitas no construtor de topologias que exigirão que você execute novamente o assistente de implantação do Lync Server em cada servidor listado para atualizar a configuração dos componentes adicionados, removidos ou alterados.</span><span class="sxs-lookup"><span data-stu-id="42312-119">The link, if clicked, opens a list of servers affected by the changes made in Topology Builder that will require you to re-run the Lync Server Deployment Wizard on each listed server to update the configuration for added, removed, or changed components.</span></span>

    
    </div>

7.  <span data-ttu-id="42312-120">Repita essas etapas para cada servidor Standard Edition, pool de front-ends, diretor ou pool diretor na organização.</span><span class="sxs-lookup"><span data-stu-id="42312-120">Repeat these steps for each Standard Edition server, Front End pool, Director or Director pool in the organization.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

