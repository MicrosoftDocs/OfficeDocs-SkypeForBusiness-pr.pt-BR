---
title: 'Lync Server 2013: Configurando políticas de arquivamento para usuários'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5adef442b4e890a8f157208aa6e7055725c014e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="de4c4-102">Configurando políticas de arquivamento para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de4c4-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de4c4-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="de4c4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="de4c4-104">É possível habilitar ou desabilitar o Arquivamento para usuários específicos criando e configurando uma política de Arquivamento para usuários e aplicando a política para usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="de4c4-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="de4c4-105">As políticas de usuário substituem qualquer política global ou locais.</span><span class="sxs-lookup"><span data-stu-id="de4c4-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="de4c4-106">As políticas de arquivamento só se aplicam se você não usar a integração com o Microsoft Exchange ou se você usar a integração com o Microsoft Exchange, mas têm alguns usuários que não estão hospedados no Exchange 2013 e têm suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="de4c4-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="de4c4-107">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [How Archiving Works na](lync-server-2013-how-archiving-works.md) documentação de planejamento, documentação de implantação ou documentação de operações do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de4c4-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="de4c4-108">Se você habilitar a integração com o Microsoft Exchange para sua implantação, as políticas de bloqueio in-loco do Exchange controlarão se o arquivamento está habilitado para os usuários hospedados no Exchange 2013 e ter suas caixas de correio colocadas em bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="de4c4-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="de4c4-109">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="de4c4-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="de4c4-110">Você deve especificar todas as opções adequadas nas configurações de Arquivamento antes de habilitar o Arquivamento de comunicações internas e externas nas políticas de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="de4c4-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="de4c4-111">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving Options in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="de4c4-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="de4c4-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="de4c4-112">In This Section</span></span>

  - [<span data-ttu-id="de4c4-113">Configurando políticas de usuário para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="de4c4-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="de4c4-114">Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="de4c4-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

