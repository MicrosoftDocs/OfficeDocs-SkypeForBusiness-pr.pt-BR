---
title: Verificar o ambiente do Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a7b44ee656462510ad6a27cf2e11bae30608f0b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147864"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a><span data-ttu-id="744a3-102">Verificar o ambiente do Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="744a3-102">Verify Office Communications Server 2007 R2 environment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="744a3-103">_**Última modificação do tópico:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="744a3-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="744a3-104">Antes de implantar o Lync Server 2013 em um estado de coexistência com o Office Communications Server 2007 R2, você precisa verificar se os serviços do Office Communications Server 2007 R2 estão configurados e iniciados.</span><span class="sxs-lookup"><span data-stu-id="744a3-104">Prior to deploying Lync Server 2013 in a coexistence state with Office Communications Server 2007 R2, you need to verify the Office Communications Server 2007 R2 services are configured and started.</span></span>

<span data-ttu-id="744a3-105">**Verificar se o pool é iniciado usando a ferramenta administrativa do Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="744a3-105">**Verify the Pool is started using the Office Communications Server 2007 R2 Administrative Tool**</span></span>

1.  <span data-ttu-id="744a3-106">Abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="744a3-106">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="744a3-107">Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="744a3-107">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="744a3-108">Certifique-se de que os serviços estejam sendo executado no servidor Standard Edition ou pool Enterprise.</span><span class="sxs-lookup"><span data-stu-id="744a3-108">Ensure that the services are running on the Standard Edition server or Enterprise pool.</span></span>
    
    <span data-ttu-id="744a3-109">![Console de administração do Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Console de administração do Office Communications Server 2007 R2")</span><span class="sxs-lookup"><span data-stu-id="744a3-109">![Office Communications Server 2007 R2 Admin Console](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Office Communications Server 2007 R2 Admin Console")</span></span>

<span data-ttu-id="744a3-110">**Revisar usuários configurados para o Office Communications Server 2007 R2**</span><span class="sxs-lookup"><span data-stu-id="744a3-110">**Review Users configured for Office Communications Server 2007 R2**</span></span>

1.  <span data-ttu-id="744a3-111">Abra a ferramenta administrativa do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="744a3-111">Open the Office Communications Server 2007 R2 administrative tool.</span></span>

2.  <span data-ttu-id="744a3-112">Expanda o nó **Floresta**, expanda o nó **ServidoresStandard Edition** ou **Pools Enterprise** e expanda o pool ou o nome do servidor.</span><span class="sxs-lookup"><span data-stu-id="744a3-112">Expand the **Forest** node, expand the **Standard Edition Servers** or **Enterprise pools** node, and then expand the pool or server name.</span></span>

3.  <span data-ttu-id="744a3-113">Clique em **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="744a3-113">Click **Users**.</span></span>

4.  <span data-ttu-id="744a3-114">Verifique a lista de usuários do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="744a3-114">Verify the list of Office Communications Server 2007 R2 users.</span></span>
    
    <span data-ttu-id="744a3-115">![Listar usuários na ferramenta de administração do OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Listar usuários na ferramenta de administração do OCS")</span><span class="sxs-lookup"><span data-stu-id="744a3-115">![List fo users in OCS Admin tool](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "List fo users in OCS Admin tool")</span></span>

<span data-ttu-id="744a3-116">**Verificar a configuração de parceiro federado XMPP herdado**</span><span class="sxs-lookup"><span data-stu-id="744a3-116">**Verify legacy XMPP Federated Partner Configuration**</span></span>

1.  <span data-ttu-id="744a3-117">No servidor XMPP herdado, navegue até o mini-aplicativo Serviços\\de ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="744a3-117">From the legacy XMPP server, navigate to the Administrative Tools\\Services applet.</span></span>

2.  <span data-ttu-id="744a3-118">Verifique se o serviço do Gateway XMPP do Office Communications Server foi inicializado.</span><span class="sxs-lookup"><span data-stu-id="744a3-118">Verify that the Office Communications Server XMPP Gateway service is started.</span></span>
    
    <span data-ttu-id="744a3-119">![Serviço de Gateway XMPP do Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Serviço de Gateway XMPP do Office Communications Server")</span><span class="sxs-lookup"><span data-stu-id="744a3-119">![Office Communications Server XMPP Gateway Service](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Office Communications Server XMPP Gateway Service")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

