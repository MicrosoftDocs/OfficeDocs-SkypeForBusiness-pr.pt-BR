---
title: 'Lync Server 2013: Configurando o suporte de Federação para um cliente do Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring federation support for a Lync Online customer
ms:assetid: e5f7f38d-ede5-4af3-88c2-026e8a78df12
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202193(v=OCS.15)
ms:contentKeyID: 48185669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cffed0c856577a60a9782850006b82f2c9d45374
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-federation-support-for-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="bd11a-102">Configurando o suporte de Federação para um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd11a-102">Configuring federation support for a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd11a-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="bd11a-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="bd11a-104">Você pode fornecer serviços de comunicação para usuários em sua organização de qualquer uma das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="bd11a-104">You can provide communications services to users in your organization in any of the following ways:</span></span>

  - <span data-ttu-id="bd11a-105">Implantar o Lync Server 2013 em sua organização (conhecido como *serviços locais*) e configurar as contas de usuário do Lync 2013 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="bd11a-105">Deploying Lync Server 2013 in your organization (known as *on-premises services*) and setting up Lync 2013 user accounts in your organization.</span></span>

  - <span data-ttu-id="bd11a-106">Configurar uma conta de cliente 2010 do Microsoft Lync Online com um provedor de hospedagem e configurar contas de usuário com o provedor de hospedagem (conhecido como *serviços online*).</span><span class="sxs-lookup"><span data-stu-id="bd11a-106">Setting up a Microsoft Lync Online 2010 customer account with a Hosting Provider and setting up user accounts with the Hosting Provider (known as *online services*).</span></span>

<span data-ttu-id="bd11a-107">Se você implantar o Lync 2013 em sua organização, poderá federar-se com os domínios de um ou mais clientes do Microsoft Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="bd11a-107">If you deploy Lync 2013 in your organization, you can federate with the domains of one or more Microsoft Lync Online 2010 customers.</span></span> <span data-ttu-id="bd11a-108">Para habilitar a Federação entre usuários de sua implantação local do Lync 2013 e usuários de um cliente do Lync Online 2010, você deve configurar o suporte para o domínio e usuários do cliente do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="bd11a-108">To enable federation between users of your on-premises Lync 2013 deployment and users of a Lync Online 2010 customer, you must configure support for the domain and users of the Lync Online customer.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd11a-109">Esta documentação descreve apenas os procedimentos para configurar sua organização para dar suporte à Federação com um cliente do Lync Online 2010.</span><span class="sxs-lookup"><span data-stu-id="bd11a-109">This documentation describes only the procedures for configuring your organization to support federation with an Lync Online 2010 customer.</span></span> <span data-ttu-id="bd11a-110">Esta documentação não descreve os procedimentos para configurar o cliente do Lync Online 2010 para dar suporte à Federação.</span><span class="sxs-lookup"><span data-stu-id="bd11a-110">This documentation does not describe the procedures for configuring the Lync Online 2010 customer to support federation.</span></span> <span data-ttu-id="bd11a-111">Para obter detalhes sobre o Lync Online Services, consulte Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>online em.</span><span class="sxs-lookup"><span data-stu-id="bd11a-111">For details about Lync Online services, see Lync Online at <A href="https://go.microsoft.com/fwlink/p/?linkid=218941">https://go.microsoft.com/fwlink/p/?linkId=218941</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd11a-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bd11a-112">In This Section</span></span>

  - [<span data-ttu-id="bd11a-113">Pré-requisitos para federação com um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd11a-113">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md)

  - [<span data-ttu-id="bd11a-114">Configurar o suporte de Federação para um domínio do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd11a-114">Configure federation support for a Lync Online domain in Lync Server 2013</span></span>](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md)

  - [<span data-ttu-id="bd11a-115">Configurar o acesso do usuário para federação com um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd11a-115">Configure user access for federation with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md)

  - [<span data-ttu-id="bd11a-116">Verificar comunicações com um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd11a-116">Verify communications with a Lync Online customer in Lync Server 2013</span></span>](lync-server-2013-verify-communications-with-a-lync-online-customer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

