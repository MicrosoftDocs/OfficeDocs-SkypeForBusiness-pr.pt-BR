---
title: 'Lync Server 2013: verificar comunicações com um cliente do Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify communications with a Lync Online customer
ms:assetid: c8287b15-e1bb-4b26-8354-0ec90b2fcfe7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202189(v=OCS.15)
ms:contentKeyID: 48185378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0269c66ad88f7be7f34874a8e4370fb65b954ccf
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518658"
---
# <a name="verify-communications-with-a-lync-online-customer-in-lync-server-2013"></a><span data-ttu-id="06698-102">Verificar comunicações com um cliente do Lync Online no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06698-102">Verify communications with a Lync Online customer in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06698-103">_**Última modificação do tópico:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="06698-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="06698-104">Para permitir que os usuários do Lync em sua organização se comuniquem com os usuários de um cliente do Microsoft Lync Online 2010, você deve concluir as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="06698-104">To enable Lync users in your organization to communicate with users of a Microsoft Lync Online 2010 customer, you must have completed the following steps:</span></span>

  - <span data-ttu-id="06698-105">Atender a todos os pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="06698-105">Met all prerequisites.</span></span> <span data-ttu-id="06698-106">Isso incluir a implantação de seus servidores internos e de borda, habilitação do suporte á federação para sua organização e configuração das contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="06698-106">This includes deploying your internal and edge servers, enabling federation support for your organization, and setting up user accounts.</span></span> <span data-ttu-id="06698-107">Para obter detalhes, consulte [pré-requisitos para federação com um cliente do Lync Online no Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="06698-107">For details, see [Prerequisites for federating with a Lync Online customer in Lync Server 2013](lync-server-2013-prerequisites-for-federating-with-a-lync-online-customer.md).</span></span>

  - <span data-ttu-id="06698-108">Configurar o suporte ao acesso de domínio em sua implantação interna.</span><span class="sxs-lookup"><span data-stu-id="06698-108">Configured domain access support in your internal deployment.</span></span> <span data-ttu-id="06698-109">Isso inclui a criação de uma entrada de provedor de host e a configuração da implantação para permitir o acesso do domínio do cliente do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="06698-109">This includes creating a host provider entry and configuring your deployment to allow access from the Lync Online customer’s domain.</span></span> <span data-ttu-id="06698-110">Para obter detalhes, consulte [Configurar o suporte de Federação para um domínio do Lync Online no Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span><span class="sxs-lookup"><span data-stu-id="06698-110">For details, see [Configure federation support for a Lync Online domain in Lync Server 2013](lync-server-2013-configure-federation-support-for-a-lync-online-domain.md).</span></span>

  - <span data-ttu-id="06698-111">Configurar suas contas de usuário para suportar a federação.</span><span class="sxs-lookup"><span data-stu-id="06698-111">Configured your user accounts to support federation.</span></span> <span data-ttu-id="06698-112">Para obter detalhes, consulte [Configurar o acesso do usuário para federação com um cliente do Lync Online no Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span><span class="sxs-lookup"><span data-stu-id="06698-112">For details, see [Configure user access for federation with a Lync Online customer in Lync Server 2013](lync-server-2013-configure-user-access-for-federation-with-a-lync-online-customer.md).</span></span>

<span data-ttu-id="06698-113">Após concluir todas essas etapas e o administrador do cliente do Lync Online 2010 conclui todas as configurações de seus serviços online para dar suporte à Federação com sua organização, verifique as comunicações por meio de um usuário interno em sua organização e um usuário do cliente do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="06698-113">After you complete all of these steps and the administrator of the Lync Online 2010 customer completes all configuration of their online services to support federation with your organization, verify communications by testing communications between an internal user in your organization and a user of the Lync Online customer.</span></span> <span data-ttu-id="06698-114">Se a comunicação não tiver êxito, use a ferramenta de registro em log do servidor de borda para capturar arquivos de log e rastreamento a fim de solucionar o problema.</span><span class="sxs-lookup"><span data-stu-id="06698-114">If communication is not successful, use the Logging Tool from your Edge Server to capture log and trace files in order to troubleshoot the problem.</span></span> <span data-ttu-id="06698-115">Para obter detalhes sobre como usar a ferramenta de registro em log, confira [abrir as ferramentas administrativas do Lync Server 2013](lync-server-2013-open-lync-server-administrative-tools.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="06698-115">For details about using the Logging Tool, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md) in the Operations documentation.</span></span> <span data-ttu-id="06698-116">Para obter detalhes sobre a ferramenta de registro em log, consulte a documentação da ferramenta de registro em log do Lync Server 2010 na biblioteca do TechNet em [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265) .</span><span class="sxs-lookup"><span data-stu-id="06698-116">For details about the Logging Tool, see the Lync Server 2010 Logging Tool documentation on the TechNet Library at [https://go.microsoft.com/fwlink/p/?linkId=199265](https://go.microsoft.com/fwlink/p/?linkid=199265).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

