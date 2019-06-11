---
title: 'Lync Server 2013: Configurando e atribuindo políticas de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="19ffb-102">Configurar e atribuir políticas de arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ffb-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="19ffb-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="19ffb-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="19ffb-104">No Lync Server 2013, você usa políticas para habilitar e desabilitar o arquivamento para comunicações internas e comunicações externas para usuários que são hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19ffb-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="19ffb-105">Isso inclui as seguintes políticas de arquivamento:</span><span class="sxs-lookup"><span data-stu-id="19ffb-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="19ffb-106">Uma política global criada por padrão quando você implanta o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="19ffb-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="19ffb-107">Políticas opcionais no nível do site e no nível do usuário que você pode criar e usar para especificar como o arquivamento é implementado para sites ou usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="19ffb-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="19ffb-108">Inicialmente, você define as políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir políticas após a implantação.</span><span class="sxs-lookup"><span data-stu-id="19ffb-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="19ffb-109">No painel de controle do Lync Server 2013, você pode usar a página **política** de arquivamento do grupo **arquivamento e monitoramento** para gerenciar políticas em nível global, nível de site e nível de usuário.</span><span class="sxs-lookup"><span data-stu-id="19ffb-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="19ffb-110">Para controlar a implementação do arquivamento, você deve especificar opções em configurações de arquivamento, como se deseja arquivar mensagens instantâneas ou conferências, o uso do modo crítico e as opções de limpeza.</span><span class="sxs-lookup"><span data-stu-id="19ffb-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="19ffb-111">Por padrão, nenhuma opção é habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de site ou de pool.</span><span class="sxs-lookup"><span data-stu-id="19ffb-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="19ffb-112">Você deve especificar todas as opções adequadas nas configurações de arquivamento antes de habilitar o arquivamento para comunicações internas ou externas nas políticas de arquivamento.</span><span class="sxs-lookup"><span data-stu-id="19ffb-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="19ffb-113">Para obter detalhes, consulte <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Gerenciando opções de configuração de arquivamento no Lync Server 2013 para sua organização, sites e pools</A> na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="19ffb-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="19ffb-114">Se você integrar o armazenamento do Lync Server ao armazenamento do Exchange 2013, as políticas de usuário do Exchange terão precedência sobre as políticas de arquivamento do Lync Server 2013, mas somente para os usuários hospedados no Exchange 2013 que tiveram suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="19ffb-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="19ffb-115">Para obter detalhes sobre como as políticas são implementadas, incluindo a hierarquia de políticas, consulte [como o arquivamento funciona no Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="19ffb-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="19ffb-116">Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Gerenciando o arquivamento de comunicações internas e externas no Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="19ffb-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="19ffb-117">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="19ffb-117">In This Section</span></span>

  - [<span data-ttu-id="19ffb-118">Configurando a política global para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ffb-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="19ffb-119">Configurando políticas de site para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ffb-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="19ffb-120">Configurando políticas de arquivamento para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="19ffb-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

