---
title: 'Lync Server 2013: Aplicar uma política de Chat Persistente a um usuário ou grupo de usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2fbed0a752c1bf97bab5a4f67fadf12d8077a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845007"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a><span data-ttu-id="0a5ed-102">Aplicar uma política de Chat Persistente a um usuário ou grupo de usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a5ed-102">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a5ed-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="0a5ed-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="0a5ed-104">Se um usuário tiver sido habilitado para o Lync Server 2013, você poderá aplicar políticas adequadas a usuários específicos para habilitá-los ou desabilitá-los para o servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-104">If a user has been enabled for Lync Server 2013, you can apply appropriate policies to specific users to enable or disable them for Persistent Chat Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0a5ed-105">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-105">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="0a5ed-106">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-106">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0a5ed-107">Para definir as configurações de servidor de chat persistente, consulte <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções do servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-107">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="0a5ed-108">Use o procedimento deste tópico para aplicar uma política de usuário de chat persistente criada anteriormente a uma ou mais contas de usuário ou grupos de usuários.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-108">Use the procedure in this topic to apply a previously created Persistent Chat user policy to one or more user accounts or user groups.</span></span>

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a><span data-ttu-id="0a5ed-109">Para aplicar uma política de usuário de chat persistente a uma conta de usuário</span><span class="sxs-lookup"><span data-stu-id="0a5ed-109">To apply a Persistent Chat user policy to a user account</span></span>

1.  <span data-ttu-id="0a5ed-110">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-110">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="0a5ed-111">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-111">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="0a5ed-112">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="0a5ed-112">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="0a5ed-113">Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-113">In the left navigation bar, click **Users**, and then search on the user account that you want to configure.</span></span>

4.  <span data-ttu-id="0a5ed-114">Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-114">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="0a5ed-115">Em **Editar usuário do Lync Server** na **política de chat persistente**, selecione a política de usuário de chat persistente que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-115">In **Edit Lync Server User** under **Persistent Chat policy**, select the Persistent Chat user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0a5ed-116">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam a política em vigor padrão.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-116">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default effective policy.</span></span> <span data-ttu-id="0a5ed-117">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-117">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="0a5ed-118">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="0a5ed-118">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

