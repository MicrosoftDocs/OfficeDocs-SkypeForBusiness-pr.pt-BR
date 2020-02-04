---
title: 'Lync Server 2013: Selecionar o Servidor de Gerenciamento Central'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Select the Central Management Server
ms:assetid: 1ca6b7d0-125c-4727-aac4-2d683d23394d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204726(v=OCS.15)
ms:contentKeyID: 48183561
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aad97b0f2009b8f90fa64abc66791d5954c637a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732471"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="select-the-central-management-server-in-lync-server-2013"></a><span data-ttu-id="0f100-102">Selecionar o Servidor de Gerenciamento Central no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0f100-102">Select the Central Management Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f100-103">_**Tópico da última modificação:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="0f100-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="0f100-104">Antes de poder definir e configurar sua topologia, você deve primeiro definir o local para instalar o servidor de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="0f100-104">Before you can define and configure your topology, you must first define the location to install the Central Management Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0f100-105">Isso não terá efeito até que você tenha publicado uma topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="0f100-105">This will not take effect until you have published a topology in Topology Builder.</span></span> <span data-ttu-id="0f100-106">Para definir o servidor de gerenciamento central antes de a topologia ser criada e publicada, execute <STRONG>set-CSConfigurationStoreLocation</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="0f100-106">To set the Central Management Server before the topology is created and published, run <STRONG>Set-CSConfigurationStoreLocation</STRONG>.</span></span>



</div>

<div>

## <a name="to-select-the-central-management-server"></a><span data-ttu-id="0f100-107">Para selecionar o servidor de gerenciamento central</span><span class="sxs-lookup"><span data-stu-id="0f100-107">To select the Central Management Server</span></span>

1.  <span data-ttu-id="0f100-108">Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="0f100-108">Start Topology Builder: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="0f100-109">Clique com o botão direito do mouse no nó do Lync Server 2013 e, em seguida, clique em **Editar propriedades**.</span><span class="sxs-lookup"><span data-stu-id="0f100-109">Right-click the Lync Server 2013 node, and then click **Edit Properties**.</span></span>

3.  <span data-ttu-id="0f100-110">No painel do servidor de gerenciamento central, selecione o servidor front-end para instalar o servidor de gerenciamento central e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f100-110">In the Central Management Server pane, select the Front End Server to install the Central Management Server on and then click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

