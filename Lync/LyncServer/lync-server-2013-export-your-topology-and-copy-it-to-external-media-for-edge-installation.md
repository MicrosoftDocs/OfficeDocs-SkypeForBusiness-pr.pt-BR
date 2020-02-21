---
title: Exportar sua topologia e copiá-la para a mídia externa para instalação de borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52903a2e7ae1b9a3a994a1199e32d8d7c4bd1e03
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a><span data-ttu-id="81d3a-102">Exporte sua topologia do Lync Server 2013 e copie-a para a mídia externa para instalação de borda</span><span class="sxs-lookup"><span data-stu-id="81d3a-102">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="81d3a-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="81d3a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="81d3a-104">Depois de publicar sua topologia, o assistente de implantação do Lync Server precisa acessar os dados do repositório de gerenciamento central para iniciar o processo de implantação no servidor.</span><span class="sxs-lookup"><span data-stu-id="81d3a-104">After you publish your topology, the Lync Server Deployment Wizard needs access to the Central Management store data in order to start the deployment process on the server.</span></span> <span data-ttu-id="81d3a-105">Na rede interna, os dados estão disponíveis diretamente nos servidores, mas os servidores de borda que não estão no domínio interno não podem acessar os dados.</span><span class="sxs-lookup"><span data-stu-id="81d3a-105">In the internal network, the data is available directly from the servers, but Edge Servers that are not in the internal domain cannot access the data.</span></span> <span data-ttu-id="81d3a-106">Para disponibilizar os dados de configuração de topologia para uma implantação de servidor de borda, você deve exportar os dados de topologia para um arquivo e copiá-los para a mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que está disponível no servidor de borda) antes de executar o Lync Server Dep loyment assistente no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="81d3a-106">To make the topology configuration data available for an Edge Server deployment, you must export the topology data to a file and copy it to external media (for example, a USB drive or a network share that is available from the Edge Server) before you run the Lync Server Deployment Wizard on the Edge Server.</span></span> <span data-ttu-id="81d3a-107">Use o procedimento a seguir para tornar os dados de configuração de topologia disponíveis no servidor de borda que você está implantando.</span><span class="sxs-lookup"><span data-stu-id="81d3a-107">Use the following procedure to make your topology configuration data available on the Edge Server that you are deploying.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="81d3a-108">Após instalar o Lync Server 2013 em um servidor de borda, você gerencia o servidor de borda usando as ferramentas administrativas da rede interna, que replicam automaticamente a configuração para qualquer servidor de borda em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="81d3a-108">After you install Lync Server 2013 on an Edge Server, you manage the Edge Server using the administrative tools in the internal network, which automatically replicate configuration to any Edge Servers in your deployment.</span></span> <span data-ttu-id="81d3a-109">A única exceção é a atribuição e instalação de certificados e a interrupção e início de serviços, que devem ser feitos no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="81d3a-109">The only exception is assigning and installing certificates and stopping and starting services, both of which must be done on the Edge Server.</span></span>



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a><span data-ttu-id="81d3a-110">Para disponibilizar os dados de topologia em um servidor de borda usando o Shell de gerenciamento do Lync Server</span><span class="sxs-lookup"><span data-stu-id="81d3a-110">To make your topology data available on an Edge Server by using Lync Server Management Shell</span></span>

1.  <span data-ttu-id="81d3a-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="81d3a-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="81d3a-112">No Shell de gerenciamento do Lync Server, execute o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="81d3a-112">In the Lync Server Management Shell, run the following cmdlet:</span></span>
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  <span data-ttu-id="81d3a-113">Copie o arquivo exportado para a mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que está disponível no servidor de borda durante a implantação).</span><span class="sxs-lookup"><span data-stu-id="81d3a-113">Copy the exported file to external media (for example, a USB drive or a network share that is available from the Edge Server during deployment).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

