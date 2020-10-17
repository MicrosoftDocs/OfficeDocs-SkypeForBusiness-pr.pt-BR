---
title: 'Lync Server 2013: Configurando políticas de usuário para arquivamento no Lync Server'
description: 'Lync Server 2013: configuração de políticas de usuário para arquivamento no Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e33abf6cf16c9c1367162aa8beee91874f4c725
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554077"
---
# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="bdd7d-103">Configurando políticas de usuário para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd7d-103">Setting up user policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd7d-104">_**Última modificação do tópico:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="bdd7d-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="bdd7d-105">Habilitar ou desabilitar o arquivamento para usuários específicos hospedados no Lync Server 2013 requer a criação e configuração de uma ou mais políticas de usuário e, em seguida, a aplicação da política apropriada a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-105">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="bdd7d-106">As políticas de usuário substituem as políticas globais e do site, mas somente para os usuários hospedados no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-106">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="bdd7d-107">Os usuários sempre estão hospedados no Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-107">Users are always homed in Lync Server.</span></span> <span data-ttu-id="bdd7d-108">Se a integração com o Microsoft Exchange estiver habilitada, os usuários cujas caixas de correio estão no Microsoft Exchange Server 2013 não precisam ter suas políticas de arquivamento no Lync Server gerenciadas.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-108">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="bdd7d-109">Esses usuários com arquivamento serão gerenciados pelo Exchange In-Place isenção.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-109">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="bdd7d-110">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-110">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bdd7d-111">Se você habilitou a integração do Microsoft Exchange para sua implantação, as políticas de retenção do Exchange In-Place controlam se o arquivamento está habilitado para os usuários hospedados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-111">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="bdd7d-112">O arquivamento desses usuários exige que eles tenham suas caixas de correio colocadas em In-Place isenção.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-112">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="bdd7d-113">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-113">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="bdd7d-114">Você deve especificar todas as opções apropriadas nas configurações de arquivamento antes de habilitar o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="bdd7d-115">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="bdd7d-115">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bdd7d-116">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bdd7d-116">In This Section</span></span>

  - [<span data-ttu-id="bdd7d-117">Criando e Configurando políticas de usuário para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd7d-117">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="bdd7d-118">Aplicando uma política de arquivamento do Lync Server a um usuário no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd7d-118">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

