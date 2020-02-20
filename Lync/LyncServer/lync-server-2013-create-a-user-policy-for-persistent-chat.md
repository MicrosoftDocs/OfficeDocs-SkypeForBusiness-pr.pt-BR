---
title: 'Lync Server 2013: criar uma política de usuário para chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a user policy for Persistent Chat
ms:assetid: aa3774af-d442-4206-8a68-2fbb9102e9d6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205170(v=OCS.15)
ms:contentKeyID: 48185103
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e0326aa66a1b398153b64c0dc626b8aceb2d24e
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145540"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-user-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="28cd4-102">Criar uma política de usuário para chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="28cd4-102">Create a user policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="28cd4-103">_**Última modificação do tópico:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="28cd4-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="28cd4-104">No painel de controle do Lync Server, você define as políticas de usuário que podem ser atribuídas aos usuários em **usuários**.</span><span class="sxs-lookup"><span data-stu-id="28cd4-104">In the Lync Server Control Panel, you define user policies that can be assigned to users in **Users**.</span></span>

<span data-ttu-id="28cd4-105">A política de usuário substitui a política global e as políticas de site, mas somente para os usuários específicos atribuídos à política de usuário.</span><span class="sxs-lookup"><span data-stu-id="28cd4-105">The user policy overrides the global policy and site policies, but only for the specific users who are assigned the user policy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="28cd4-106">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar o suporte do servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="28cd4-106">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="28cd4-107">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="28cd4-107">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="28cd4-108">Para definir as definições de configuração do servidor de chat persistente, confira <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções de servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="28cd4-108">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-a-user-policy-for-persistent-chat"></a><span data-ttu-id="28cd4-109">Para criar uma política de usuário para chat persistente</span><span class="sxs-lookup"><span data-stu-id="28cd4-109">To create a user policy for Persistent Chat</span></span>

1.  <span data-ttu-id="28cd4-110">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator ou CsUserAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="28cd4-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="28cd4-111">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e insira a URL do administrador.</span><span class="sxs-lookup"><span data-stu-id="28cd4-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="28cd4-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="28cd4-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="28cd4-113">Você também pode usar os cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28cd4-113">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="28cd4-114">Consulte <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configurando o servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="28cd4-114">See <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="28cd4-115">Na barra de navegação esquerda, clique em **Chat Persistente** e clique em **Política de Chat Persistente**.</span><span class="sxs-lookup"><span data-stu-id="28cd4-115">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="28cd4-116">Clique em **Novo** e, em seguida, em **Política de usuário**.</span><span class="sxs-lookup"><span data-stu-id="28cd4-116">Click **New**, and then click **User policy**.</span></span>

5.  <span data-ttu-id="28cd4-117">Em **Nova Política de Chat Persistente**, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28cd4-117">In **New Persistent Chat Policy**, do the following:</span></span>
    
      - <span data-ttu-id="28cd4-118">Em **Nome**, especifique um nome para a nova política de usuário.</span><span class="sxs-lookup"><span data-stu-id="28cd4-118">In **Name**, specify a name for the new user policy.</span></span>
    
      - <span data-ttu-id="28cd4-119">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política de chat persistente para usuário específico).</span><span class="sxs-lookup"><span data-stu-id="28cd4-119">In **Description**, provide details about what the user policy is (for example, Persistent Chat policy for specific user).</span></span>
    
      - <span data-ttu-id="28cd4-120">Para controlar o chat persistente para todos os usuários que não são especificamente controlados por meio de uma política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="28cd4-120">To control Persistent Chat for all users who are not specifically controlled through a user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="28cd4-121">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="28cd4-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

