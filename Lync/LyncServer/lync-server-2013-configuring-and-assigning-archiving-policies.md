---
title: 'Lync Server 2013: Configurando e atribuindo políticas de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b4e49bb6ba25fb9c7230cdf171dc7d31433619
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="5f19c-102">Configurando e atribuindo políticas de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f19c-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f19c-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5f19c-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5f19c-104">No Lync Server 2013, você usa políticas para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas para usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f19c-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="5f19c-105">Isso inclui as seguintes políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="5f19c-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="5f19c-106">Uma política global criada por padrão ao implantar o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5f19c-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="5f19c-107">Políticas em nível de site e do usuário opcionais que você pode criar e utilizar para especificar como o arquivamento será implementado para sites e usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="5f19c-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="5f19c-108">Inicialmente, você configurou as políticas de arquivamento quando implantou o arquivamento, mas é possível alterar, adicionar e excluir política depois da implantação.</span><span class="sxs-lookup"><span data-stu-id="5f19c-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="5f19c-109">No painel de controle do Lync Server 2013, você pode usar a página **política de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar políticas no nível global, nível do site e nível do usuário.</span><span class="sxs-lookup"><span data-stu-id="5f19c-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5f19c-110">Para controlar a implementação do arquivamento, você deve especificar opções nas configurações de arquivamento, como se deve arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza.</span><span class="sxs-lookup"><span data-stu-id="5f19c-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="5f19c-111">Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento no site ou no pool.</span><span class="sxs-lookup"><span data-stu-id="5f19c-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="5f19c-112">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento para as comunicações internas ou externas nas políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="5f19c-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="5f19c-113">Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving Configuration Options in Lync Server 2013 for Your Organization, sites e pools</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="5f19c-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="5f19c-114">Se você integrar o armazenamento do Lync Server com o armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013, mas apenas para os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="5f19c-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="5f19c-115">Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia das políticas, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="5f19c-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="5f19c-116">Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Managing the Archiving of Internal and external Communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="5f19c-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5f19c-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5f19c-117">In This Section</span></span>

  - [<span data-ttu-id="5f19c-118">Configurando a política global para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f19c-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="5f19c-119">Configurando políticas de site para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f19c-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="5f19c-120">Configurando políticas de arquivamento para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5f19c-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

