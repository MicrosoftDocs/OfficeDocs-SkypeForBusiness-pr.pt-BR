---
title: Configurando políticas para arquivamento ao usar a integração com o Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 948d57d753c774737d0a1c6b98bd24560d47606b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="2e746-102">Configurando políticas para arquivamento no Lync Server 2013 ao usar a integração com o Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2e746-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e746-103">_**Última modificação do tópico:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2e746-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2e746-104">Se os usuários hospedados no Exchange 2013 tiverem suas caixas de correio colocadas no bloqueio in-loco, as políticas de bloqueio in-loco do Exchange controlarão o arquivamento desses usuários.</span><span class="sxs-lookup"><span data-stu-id="2e746-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="2e746-105">Se você usar a integração do Microsoft Exchange para sua implantação, as políticas do Exchange 2013 substituem as políticas de arquivamento do Lync Server para usuários hospedados no Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2e746-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="2e746-106">Para obter informações sobre como configurar políticas de arquivamento do Exchange, consulte a documentação do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="2e746-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="2e746-107">Para obter detalhes sobre como configurar as políticas de usuário para usuários hospedados no Lync Server 2013, consulte [setting up User Policies for Archiving in Lync server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="2e746-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="2e746-108">Para obter detalhes sobre como as políticas funcionam, consulte [How Archiving Works in Lync Server 2013](lync-server-2013-how-archiving-works.md) na documentação de planejamento, documentação de implantação ou operações.</span><span class="sxs-lookup"><span data-stu-id="2e746-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="2e746-109">Se você implantar o Exchange 2013 e o Lync Server 2013 na mesma floresta, suas políticas de bloqueio in-loco do Exchange 2013 controlarão o arquivamento.</span><span class="sxs-lookup"><span data-stu-id="2e746-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="2e746-110">Se você implantar o Exchange 2013 e o Lync Server 2013 em florestas separadas, consulte "Implantando o Lync Server e o Microsoft Exchange em florestas diferentes" na <A href="lync-server-2013-deployment-checklist-for-archiving.md">lista de verificação de implantação para arquivamento no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="2e746-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

