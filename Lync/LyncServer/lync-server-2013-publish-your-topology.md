---
title: 'Lync Server 2013: Publicar sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823662"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a><span data-ttu-id="a10a2-102">Publicar sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a10a2-102">Publish your topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a10a2-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a10a2-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a10a2-104">Toda vez que você usa o construtor de topologias para criar sua topologia, você deve publicar a topologia em um banco de dados no repositório de gerenciamento central para que os dados possam ser usados para implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a10a2-104">Each time you use Topology Builder to build your topology, you must publish the topology to a database in the Central Management store so that the data can be used to deploy Lync Server 2013.</span></span> <span data-ttu-id="a10a2-105">Use o procedimento a seguir para publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="a10a2-105">Use the following procedure to publish your topology.</span></span>

<div>

## <a name="to-publish-the-topology"></a><span data-ttu-id="a10a2-106">Para publicar a topologia</span><span class="sxs-lookup"><span data-stu-id="a10a2-106">To publish the topology</span></span>

1.  <span data-ttu-id="a10a2-107">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-107">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="a10a2-108">No construtor de topologias, na árvore de console, clique com o botão direito do mouse no **Lync 2013**e clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-108">In Topology Builder, in the console tree, right-click **Lync 2013**, and then click **Publish Topology**.</span></span>

3.  <span data-ttu-id="a10a2-109">Na página **Bem-vindo** do assistente, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-109">On the **Welcome** page of the wizard, click **Next**.</span></span>

4.  <span data-ttu-id="a10a2-110">No **Construtor de topologias localizou uma** página de repositório de CMS, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-110">On the **Topology Builder found a CMS store** page, click **Next**.</span></span>

5.  <span data-ttu-id="a10a2-111">Na página **Criar outros bancos de dados**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-111">On the **Create other databases** page, click **Next**.</span></span>

6.  <span data-ttu-id="a10a2-112">Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="a10a2-112">When the status indicates that database creation succeeded, do the following:</span></span>
    
      - <span data-ttu-id="a10a2-113">Para exibir o log, clique em **Exibir log**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-113">To view the log, click **View log**.</span></span>
    
      - <span data-ttu-id="a10a2-114">Para fechar o assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="a10a2-114">To close the wizard, click **Finish**.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="a10a2-115">Se esta for uma nova instalação de um servidor de borda ou de um pool de bordas, você deverá exportar a configuração do servidor de borda de um servidor front-end existente, um pool de front-end ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="a10a2-115">If this is a new installation of an Edge Server or Edge pool, you must export the Edge Server configuration from an existing Front End Server, Front End pool, or Standard Edition server.</span></span> <span data-ttu-id="a10a2-116">Para exportar a configuração, confira <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação do Edge</A>.</span><span class="sxs-lookup"><span data-stu-id="a10a2-116">To export the configuration, see <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Export your Lync Server 2013 topology and copy it to external media for edge installation</A>.</span></span> <span data-ttu-id="a10a2-117">Você vai importar o arquivo de configuração da mídia externa ou do compartilhamento de rede durante a fase de configuração e implantação dos servidores de borda por meio do assistente de implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a10a2-117">You will import the configuration file from the external media or network share during the setup and deployment phase of the Edge Servers through the Lync Server Deployment Wizard.</span></span><BR><span data-ttu-id="a10a2-118">Depois que os servidores de borda estiverem operacionais e o banco de dados do repositório de gerenciamento de configuração local estiver sendo replicado com a implantação interna, as atualizações subsequentes para a configuração do Lync Server 2013 serão publicadas e replicadas para os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="a10a2-118">Once the Edge Servers are operational and the local configuration management store database is replicating with the internal deployment, subsequent updates to the Lync Server 2013 configuration will be published and replicated to the Edge Servers.</span></span>

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

