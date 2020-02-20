---
title: 'Lync Server 2013: pré-requisitos para federação com um cliente do Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Prerequisites for federating with a Lync Online customer
ms:assetid: f57d8f8a-2b1e-4186-a74f-1d7c6872bfdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202196(v=OCS.15)
ms:contentKeyID: 48185838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75a6c619b859756151e9d11ee3250d1e4e7bb882
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="prerequisites-for-federating-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="f044d-102">Pré-requisitos para federação com um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f044d-102">Prerequisites for federating with a Lync Online customer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f044d-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f044d-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f044d-104">Para federar com um cliente do Lync Online 2010, você já deve ter concluído a implantação inicial e a configuração do Lync Server 2013 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f044d-104">To federate with a Lync Online 2010 customer, you should have already completed initial deployment and configuration of Lync Server 2013 in your organization.</span></span> <span data-ttu-id="f044d-105">Isso inclui:</span><span class="sxs-lookup"><span data-stu-id="f044d-105">This includes the following:</span></span>

  - <span data-ttu-id="f044d-106">Implantar pelo menos um servidor Standard Edition ou um pool de front-ends Enterprise Edition em sua organização.</span><span class="sxs-lookup"><span data-stu-id="f044d-106">Deploying at least one Standard Edition server or one Enterprise Edition Front End pool in your organization.</span></span> <span data-ttu-id="f044d-107">Para obter detalhes sobre a implantação de servidores internos, consulte [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f044d-107">For details about deploying internal servers, see [Deploying Lync Server 2013](lync-server-2013-deploying-lync-server.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="f044d-108">Habilitar contas de usuário interno para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f044d-108">Enabling internal user accounts for Lync Server 2013.</span></span> <span data-ttu-id="f044d-109">Para obter detalhes, consulte [desabilitar ou reabilitar a conta de usuário do Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) na documentação de implantação ou a documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="f044d-109">For details, see [Disable or re-enable user account for Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md) in the Deployment documentation or the Operations documentation.</span></span>

  - <span data-ttu-id="f044d-110">Implantar pelo menos um servidor de borda e os outros componentes necessários para dar suporte ao acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="f044d-110">Deploying at least one Edge Server and the other components required to support external user access.</span></span> <span data-ttu-id="f044d-111">Para obter detalhes, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f044d-111">For details, see [Managing federation and external access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="f044d-112">Habilitar suporte de federação dentro da sua organização e configurar o método adequado para controlar o acesso de domínios federados.</span><span class="sxs-lookup"><span data-stu-id="f044d-112">Enabling federation support within your organization and configuring the appropriate method for controlling access by federated domains.</span></span> <span data-ttu-id="f044d-113">Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) e [gerenciar provedores federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="f044d-113">For details, see [Enable or disable remote user access in Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md) and [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="f044d-114">Habilitar acesso de usuário externo para usuários na sua organização.</span><span class="sxs-lookup"><span data-stu-id="f044d-114">Enabling external user access for users in your organization.</span></span> <span data-ttu-id="f044d-115">Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) e na documentação de implantação ou na documentação de operações.</span><span class="sxs-lookup"><span data-stu-id="f044d-115">For details, see [Assign an external user access policy to a Lync enabled user in Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) and in the Deployment documentation or Operations documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

