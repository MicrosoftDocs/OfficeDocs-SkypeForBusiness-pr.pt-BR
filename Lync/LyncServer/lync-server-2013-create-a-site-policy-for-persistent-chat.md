---
title: 'Lync Server 2013: criar uma política de site para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a site policy for Persistent Chat
ms:assetid: 1327ff5c-b859-4010-a240-e0b2b084b5bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204693(v=OCS.15)
ms:contentKeyID: 48183470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ed149f39363610f1bc7d17cbdb08f30710eed904
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-site-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="18420-102">Criar uma política de site para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18420-102">Create a site policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18420-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="18420-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="18420-104">Para cada site implantado, você pode criar uma política de chat persistente específica do site.</span><span class="sxs-lookup"><span data-stu-id="18420-104">For each site you have deployed, you can create a site-specific Persistent Chat policy.</span></span>

<span data-ttu-id="18420-105">A configuração da política de local substitui a política global, mas apenas para o local específico e coberto por essa política.</span><span class="sxs-lookup"><span data-stu-id="18420-105">The configuration in the site policy overrides the global policy, but only for the specific site covered by the site policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="18420-106">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="18420-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="18420-107">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="18420-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="18420-108">Para definir as definições de configuração do servidor de chat persistente, confira <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções de servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="18420-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-persistent-chat-policy-for-a-site"></a><span data-ttu-id="18420-109">Para criar uma política de chat persistente para um site</span><span class="sxs-lookup"><span data-stu-id="18420-109">To create a Persistent Chat policy for a site</span></span>

1.  <span data-ttu-id="18420-110">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="18420-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="18420-111">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="18420-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="18420-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="18420-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="18420-113">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="18420-113">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="18420-114">Você também pode usar os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="18420-114">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="18420-115">Para obter detalhes, consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="18420-115">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

4.  <span data-ttu-id="18420-116">Clique em **Novo** e, em seguida, em **Política de site**.</span><span class="sxs-lookup"><span data-stu-id="18420-116">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="18420-117">Em **Selecionar um Site**, clique no site para o qual a política será aplicada.</span><span class="sxs-lookup"><span data-stu-id="18420-117">In **Select a Site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="18420-118">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="18420-118">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="18420-119">Em **Nome**, especifique um nome para a nova política de site (por exemplo, Redmond).</span><span class="sxs-lookup"><span data-stu-id="18420-119">In **Name**, specify a name for the new site policy (for example, Redmond).</span></span>
    
      - <span data-ttu-id="18420-120">Em **Descrição**, forneça detalhes sobre o que é a política de site (por exemplo, política de sala de chat para Redmond).</span><span class="sxs-lookup"><span data-stu-id="18420-120">In **Description**, provide details about what the site policy is (for example, chat room policy for Redmond).</span></span>
    
      - <span data-ttu-id="18420-121">Para controlar o Chat Persistente para todos os sites não controlados especificamente por meio de uma política de site, marque ou desmarque a caixa de seleção **Habilitar Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="18420-121">To control Persistent Chat for all sites not specifically controlled through a site policy, select or clear the **Enable Persistent Chat** check box.</span></span>

7.  <span data-ttu-id="18420-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="18420-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

