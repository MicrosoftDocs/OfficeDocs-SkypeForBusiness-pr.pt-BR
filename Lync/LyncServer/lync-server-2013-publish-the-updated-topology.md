---
title: 'Lync Server 2013: Postar a topologia atualizada'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="c607a-102">Postar a topologia atualizada no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c607a-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c607a-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c607a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c607a-104">Depois de atualizar sua topologia no construtor de topologias, você deve publicar a topologia no repositório de gerenciamento central antes de poder configurar e usar o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c607a-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="c607a-105">Cópias somente leitura dos dados são replicadas para todos os servidores da topologia para mantê-los em sincronia com as alterações da topologia e de outras configurações.</span><span class="sxs-lookup"><span data-stu-id="c607a-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="c607a-106">Para publicar uma topologia atualizada</span><span class="sxs-lookup"><span data-stu-id="c607a-106">To publish an updated topology</span></span>

<span data-ttu-id="c607a-107">Antes de publicar sua topologia, instale os bancos de dados do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c607a-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="c607a-108">Use o construtor de topologias para instalar bancos de dados selecionando **ação** e **instalar banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="c607a-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="c607a-109">Em um computador que está executando o Lync Server 2013 ou no qual as ferramentas administrativas do Lync Server estão instaladas, faça logon usando uma conta que seja membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** , e que tem permissões de controle total (ou seja, ler, gravar e modificar) no repositório de arquivos a ser usado para o repositório de arquivos do servidor de chat persistente (para que o construtor de topologias possa configurar as listas de controle de acesso discricional (DACLs) necessárias ou uma conta com direitos de usuário equivalentes.</span><span class="sxs-lookup"><span data-stu-id="c607a-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="c607a-110">Iniciar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c607a-110">Start Topology Builder.</span></span> <span data-ttu-id="c607a-111">Selecione **baixar a topologia de implantação existente**ou **abrir a topologia de um arquivo local** se você salvá-lo localmente.</span><span class="sxs-lookup"><span data-stu-id="c607a-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="c607a-112">Na árvore de console, clique com o botão direito do mouse no **Lync Server 2013**e, em seguida, clique em **publicar topologia**.</span><span class="sxs-lookup"><span data-stu-id="c607a-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="c607a-113">Na página **Publicar a topologia**, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="c607a-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="c607a-114">Na página **Assistente de publicação concluído**, verifique se a topologia foi publicada com êxito e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="c607a-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c607a-115">Após publicar a topologia, você deve configurar o suporte para o servidor de chat persistente antes que qualquer conteúdo possa ser arquivado.</span><span class="sxs-lookup"><span data-stu-id="c607a-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

