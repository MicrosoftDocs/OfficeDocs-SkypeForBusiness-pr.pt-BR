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
ms.openlocfilehash: 0c3f2be2a41aae741a2dae5e3becb522dead8754
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="09e66-102">Configurando políticas de arquivamento para usuários no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e66-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="09e66-103">_**Tópico da última modificação:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="09e66-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="09e66-104">Você pode habilitar ou desabilitar o arquivamento para usuários específicos criando e configurando uma política de arquivamento para usuários e, em seguida, aplicando a política a usuários ou grupos de usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="09e66-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="09e66-105">As políticas de usuário substituem qualquer política global ou local.</span><span class="sxs-lookup"><span data-stu-id="09e66-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="09e66-106">As políticas de arquivamento só se aplicam se você não usar a integração com o Microsoft Exchange ou se usar a integração com o Microsoft Exchange, mas tiver alguns usuários que não são hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="09e66-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="09e66-107">Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [como o arquivamento funciona na documentação de planejamento do Lync Server 2013](lync-server-2013-how-archiving-works.md) , documentação de implantação ou documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="09e66-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="09e66-108">Se você habilitar a integração do Microsoft Exchange para a implantação, as políticas de bloqueio do Exchange in loco controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio colocadas no bloqueio in-loco.</span><span class="sxs-lookup"><span data-stu-id="09e66-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="09e66-109">Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="09e66-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="09e66-110">Você deve especificar todas as opções adequadas nas configurações de Arquivamento antes de habilitar o Arquivamento de comunicações externas ou internas nas políticas de Arquivamento.</span><span class="sxs-lookup"><span data-stu-id="09e66-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="09e66-111">Para obter detalhes, consulte <A href="lync-server-2013-configuring-archiving-options.md">Configurando opções de arquivamento no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="09e66-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="09e66-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="09e66-112">In This Section</span></span>

  - [<span data-ttu-id="09e66-113">Configurando políticas de usuário para arquivamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="09e66-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="09e66-114">Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="09e66-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

