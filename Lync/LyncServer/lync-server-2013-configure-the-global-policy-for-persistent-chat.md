---
title: 'Lync Server 2013: Configurar a política global para Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure the global policy for Persistent Chat
ms:assetid: 6176eb5c-19de-4c07-bcc0-2e38f8965966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204951(v=OCS.15)
ms:contentKeyID: 48184323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 236023756f8d2c917812d38f5a03da8dd4c40b5b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-global-policy-for-persistent-chat-in-lync-server-2013"></a><span data-ttu-id="46e7c-102">Configurar a política global para Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="46e7c-102">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="46e7c-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="46e7c-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="46e7c-104">Você pode usar a política global padrão sozinha para habilitar as configurações de chat persistente para todos os usuários em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="46e7c-104">You can use the default global policy by itself to enable Persistent Chat settings for all users in your deployment.</span></span> <span data-ttu-id="46e7c-105">Você também pode especificar políticas adicionais para sites e usuários para controlar se o chat persistente está habilitado ou desabilitado para usuários e sites específicos.</span><span class="sxs-lookup"><span data-stu-id="46e7c-105">You can also specify additional policies for sites and users to control whether Persistent Chat is enabled or disabled for specific users and sites.</span></span>

<span data-ttu-id="46e7c-106">Não é possível excluir a política global.</span><span class="sxs-lookup"><span data-stu-id="46e7c-106">You cannot delete the global policy.</span></span> <span data-ttu-id="46e7c-107">Se você tentar excluí-lo, a configuração será redefinida para os valores padrão.</span><span class="sxs-lookup"><span data-stu-id="46e7c-107">If you attempt to delete it, the configuration resets to the default values.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="46e7c-108">Para configurar e usar o servidor de chat persistente, você deve primeiro usar o construtor de topologias para adicionar suporte a servidor de chat persistente à topologia e, em seguida, publicar a topologia.</span><span class="sxs-lookup"><span data-stu-id="46e7c-108">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="46e7c-109">Para obter detalhes, consulte <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">adicionando servidor de chat persistente à sua implantação no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46e7c-109">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="46e7c-110">Para definir as configurações de servidor de chat persistente, consulte <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configurar opções do servidor de chat persistente globalmente ou para pool de servidores de chat persistente no Lync server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46e7c-110">To configure Persistent Chat Server configuration settings, see <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Configure Persistent Chat Server options globally or for Persistent Chat Server pool in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-persistent-chat"></a><span data-ttu-id="46e7c-111">Para configurar a política global para chats persistentes</span><span class="sxs-lookup"><span data-stu-id="46e7c-111">To configure the Global Policy for Persistent Chat</span></span>

1.  <span data-ttu-id="46e7c-112">Usando uma conta de usuário atribuída à função CsPersistentChatAdministrator, CsAdministrator, ou CsUserAdministrator faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="46e7c-112">From a user account that is assigned to the CsPersistentChatAdministrator, CsAdministrator, or CsUserAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="46e7c-113">No menu **Iniciar** , selecione o painel de controle do Lync Server ou abra uma janela do navegador e, em seguida, insira a URL de administração.</span><span class="sxs-lookup"><span data-stu-id="46e7c-113">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="46e7c-114">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="46e7c-114">For details about the different methods that you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="46e7c-115">Você também pode usar cmdlets do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="46e7c-115">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="46e7c-116">Para obter detalhes, consulte Configurando o <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">servidor de chat persistente usando cmdlets do Windows PowerShell</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="46e7c-116">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="46e7c-117">No painel de controle do Lync Server, clique em **chat persistente**e, em seguida, clique em **política de chat persistente**.</span><span class="sxs-lookup"><span data-stu-id="46e7c-117">In Lync Server Control Panel, click **Persistent Chat**, and then click **Persistent Chat Policy**.</span></span>

4.  <span data-ttu-id="46e7c-118">Clique em **Global** na lista de políticas, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="46e7c-118">Click **Global** in the list of policies, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="46e7c-119">Em **Editar Política de Chat Persistent - Global**, siga este procedimento:</span><span class="sxs-lookup"><span data-stu-id="46e7c-119">In **Edit Persistent Chat Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="46e7c-120">Em **Nome**, especifique um novo nome para a política global, se não desejar usar o padrão Global.</span><span class="sxs-lookup"><span data-stu-id="46e7c-120">In **Name**, specify a new name for the global policy, if you do not want to use the default of Global.</span></span>
    
      - <span data-ttu-id="46e7c-121">Em **Descrição**, forneça detalhes sobre o que é a política de usuário (por exemplo, política global para centralSiteName).</span><span class="sxs-lookup"><span data-stu-id="46e7c-121">In **Description**, provide details about what the user policy is (for example, Global policy for centralSiteName).</span></span>
    
      - <span data-ttu-id="46e7c-122">Para controlar o chat persistente para todos os sites e usuários não controlados especificamente por meio de uma política de site ou política de usuário, marque ou desmarque a caixa de seleção **habilitar chat persistente** .</span><span class="sxs-lookup"><span data-stu-id="46e7c-122">To control Persistent Chat for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Enable Persistent Chat** check box.</span></span>

6.  <span data-ttu-id="46e7c-123">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="46e7c-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

