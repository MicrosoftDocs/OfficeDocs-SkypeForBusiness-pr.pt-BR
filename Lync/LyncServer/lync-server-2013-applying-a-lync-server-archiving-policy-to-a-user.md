---
title: 'Lync Server 2013: aplicando uma política de arquivamento do Lync Server a um usuário'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 295f1a0370372d937b07a38eab51cd43d0ef9f5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845010"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="94e69-102">Aplicando uma política de arquivamento do Lync Server a um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="94e69-102">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94e69-103">_**Tópico da última modificação:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="94e69-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="94e69-104">Depois de criar uma política de usuário do Lync Server, você deve aplicá-la a determinados usuários ou grupos de usuários hospedados no Lync Server 2013 para que ele possa entrar em vigor.</span><span class="sxs-lookup"><span data-stu-id="94e69-104">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="94e69-105">Para obter detalhes sobre como criar políticas de usuário para usuários específicos, consulte [criando e Configurando políticas de usuário para arquivamento no Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="94e69-105">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="94e69-106">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="94e69-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="94e69-107">Para configurar e usar arquivamento, você deve primeiro implantar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="94e69-107">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="94e69-108">Para obter detalhes, consulte Implantando o <A href="lync-server-2013-deploying-archiving.md">arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="94e69-108">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="94e69-109">Se você tiver habilitado a integração do Microsoft Exchange para a sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="94e69-109">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="94e69-110">Para obter detalhes, consulte Configurando <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="94e69-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="94e69-111">Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="94e69-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="94e69-112">Para obter detalhes, consulte Configurando <A href="lync-server-2013-configuring-archiving-options.md">Opções de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="94e69-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="94e69-113">Para aplicar uma política de arquivamento do Lync Server a um usuário</span><span class="sxs-lookup"><span data-stu-id="94e69-113">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="94e69-114">Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="94e69-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="94e69-115">Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="94e69-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="94e69-116">Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server 2013, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="94e69-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="94e69-117">Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar.</span><span class="sxs-lookup"><span data-stu-id="94e69-117">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="94e69-118">Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.</span><span class="sxs-lookup"><span data-stu-id="94e69-118">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="94e69-119">Em **Editar o usuário do Lync Server** na **política**de arquivamento, selecione a política de usuário de arquivamento que você deseja aplicar.</span><span class="sxs-lookup"><span data-stu-id="94e69-119">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="94e69-120">As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão.</span><span class="sxs-lookup"><span data-stu-id="94e69-120">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="94e69-121">Essas configurações são aplicadas automaticamente pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="94e69-121">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="94e69-122">Clique em **Confirmar**.</span><span class="sxs-lookup"><span data-stu-id="94e69-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

