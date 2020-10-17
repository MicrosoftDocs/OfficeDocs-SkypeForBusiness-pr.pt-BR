---
title: Verifique o acesso remoto e de federação para usuários externos
description: Verificar a Federação e o acesso remoto para usuários externos.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ac36f2e1b6c5ddfd889810ba2a3ab4d82b7ae33
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555067"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="1e69e-103">Verifique o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="1e69e-103">Verify federation and remote access for external users</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e69e-104">_**Última modificação do tópico:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="1e69e-104">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="1e69e-105">Após a transição da rota de Federação para o servidor de borda do Lync Server 2013, você deve executar alguns testes funcionais para verificar se a Federação é realizada conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="1e69e-105">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="1e69e-106">Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.</span><span class="sxs-lookup"><span data-stu-id="1e69e-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="1e69e-107">Teste a conectividade de usuários externos e do acesso externo</span><span class="sxs-lookup"><span data-stu-id="1e69e-107">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="1e69e-108">Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e69e-108">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1e69e-109">Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e69e-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="1e69e-110">Os usuários de cada provedor de serviços públicos de IM que sua organização suporta (e para o qual o provisionamento foi concluído) comunicando-se com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e69e-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="1e69e-111">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="1e69e-111">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="1e69e-112">Um usuário hospedado no Lync Server 2010 usando acesso de usuário remoto (fazendo logon no Lync Server 2010 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e69e-112">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1e69e-113">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e69e-113">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="1e69e-114">Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e69e-114">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="1e69e-115">Testar a IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1e69e-115">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

