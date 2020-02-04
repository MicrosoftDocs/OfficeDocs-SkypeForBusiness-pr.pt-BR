---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify federation and remote access for external users
ms:assetid: a383fefb-c428-4462-93fd-15ba540fa867
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688163(v=OCS.15)
ms:contentKeyID: 49733768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 61ad994eb7769dff067195520c2c6fde955910f4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="6cb64-102">Verificar o acesso remoto e de federação para usuários externos</span><span class="sxs-lookup"><span data-stu-id="6cb64-102">Verify federation and remote access for external users</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cb64-103">_**Tópico da última modificação:** 2012-09-18_</span><span class="sxs-lookup"><span data-stu-id="6cb64-103">_**Topic Last Modified:** 2012-09-18_</span></span>

<span data-ttu-id="6cb64-104">Após a transição da rota de Federação para o servidor de borda do Lync Server 2013, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="6cb64-104">After transitioning the federation route to the Lync Server 2013 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="6cb64-105">Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.</span><span class="sxs-lookup"><span data-stu-id="6cb64-105">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="6cb64-106">Testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="6cb64-106">Test Connectivity of External Users and External access</span></span>

  - <span data-ttu-id="6cb64-107">Usuários de pelo menos um domínio federado, um usuário interno no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6cb64-107">Users from at least one federated domain, an internal user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6cb64-108">Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6cb64-108">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>

  - <span data-ttu-id="6cb64-109">Os usuários de cada provedor de serviços de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicam com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6cb64-109">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Lync Server 2013 and a user on Lync Server 2010.</span></span>

  - <span data-ttu-id="6cb64-110">Verifique se usuários anônimos podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="6cb64-110">Verify that anonymous users are able to join conferences.</span></span>

  - <span data-ttu-id="6cb64-111">Um usuário hospedado no Lync Server 2010 usando acesso de usuário remoto (fazendo logon no Lync Server 2010 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6cb64-111">A user hosted on Lync Server 2010 using remote user access (logging into Lync Server 2010 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6cb64-112">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6cb64-112">Test IM, presence, A/V, and desktop sharing.</span></span>

  - <span data-ttu-id="6cb64-113">Um usuário hospedado no Lync Server 2013 usando acesso de usuário remoto (fazendo logon no Lync Server 2013 de fora da intranet, mas sem VPN) com um usuário no Lync Server 2013 e um usuário no Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="6cb64-113">A user hosted on Lync Server 2013 using remote user access (logging into Lync Server 2013 from outside the intranet but without VPN) with a user on Lync Server 2013, and a user on Lync Server 2010.</span></span> <span data-ttu-id="6cb64-114">Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="6cb64-114">Test IM, presence, A/V, and desktop sharing.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

