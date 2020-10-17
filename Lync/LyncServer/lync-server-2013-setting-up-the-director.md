---
title: 'Lync Server 2013: Configurando o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up the Director
ms:assetid: 408b76f7-6fdd-4e50-8a3e-e87db12c1394
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425915(v=OCS.15)
ms:contentKeyID: 48183951
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f884fc2b4477a0b9c4e4f4a6e376a99f894dce1e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497558"
---
# <a name="setting-up-the-director-in-lync-server-2013"></a><span data-ttu-id="1544e-102">Configurando o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-102">Setting up the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1544e-103">_**Última modificação do tópico:** 2014-05-05_</span><span class="sxs-lookup"><span data-stu-id="1544e-103">_**Topic Last Modified:** 2014-05-05_</span></span>

<span data-ttu-id="1544e-104">Se você estiver habilitando o acesso para usuários externos implantando servidores de borda, uma opção é implantar um diretor.</span><span class="sxs-lookup"><span data-stu-id="1544e-104">If you’re enabling access for external users by deploying Edge Servers, one option is to deploy a Director.</span></span> <span data-ttu-id="1544e-105">Um diretor é um servidor que executa o Microsoft Lync Server 2013 que autentica solicitações do usuário, mas não hospeda contas de usuário.</span><span class="sxs-lookup"><span data-stu-id="1544e-105">A Director is a server running Microsoft Lync Server 2013 that authenticates user requests, but doesn’t home any user accounts.</span></span> <span data-ttu-id="1544e-106">Agora, isso não é um requisito, mas é muito útil se você estiver preocupado com o desempenho e deseja ajudar a simplificar as solicitações de autenticação.</span><span class="sxs-lookup"><span data-stu-id="1544e-106">Now, this isn’t a requirement, but it is very helpful if you’re worried about performance and want to help streamline authentication requests.</span></span> <span data-ttu-id="1544e-107">Se você decidir que esta é uma boa ideia para sua organização, as etapas para configurar um diretor ou um pool de diretor são semelhantes à configuração de um pool de front-ends Enterprise Edition ou servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="1544e-107">If you decide this is a good idea for your organization, the steps to set up a Director or a Director pool are similar to setting up either an Enterprise Edition Front End pool or Standard Edition server.</span></span> <span data-ttu-id="1544e-108">Depois de definir seus diretores no construtor de topologias, você precisará executar as etapas desta seção.</span><span class="sxs-lookup"><span data-stu-id="1544e-108">After you’ve defined your Director(s) in Topology Builder, you’ll need to perform the steps in this section.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1544e-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="1544e-109">In This Section</span></span>

  - [<span data-ttu-id="1544e-110">Instalar o repositório de configuração local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-110">Install the Local Configuration store in Lync Server 2013</span></span>](lync-server-2013-install-the-local-configuration-store.md)

  - [<span data-ttu-id="1544e-111">Instalar o Lync Server 2013 no Diretor</span><span class="sxs-lookup"><span data-stu-id="1544e-111">Install Lync Server 2013 on the Director</span></span>](lync-server-2013-install-lync-server-on-the-director.md)

  - [<span data-ttu-id="1544e-112">Configurar certificados para o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-112">Configure certificates for the Director in Lync Server 2013</span></span>](lync-server-2013-configure-certificates-for-the-director.md)

  - [<span data-ttu-id="1544e-113">Iniciar os serviços no diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-113">Start services on the Director in Lync Server 2013</span></span>](lync-server-2013-start-services-on-the-director.md)

  - [<span data-ttu-id="1544e-114">Testar o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-114">Test the Director in Lync Server 2013</span></span>](lync-server-2013-test-the-director.md)

  - [<span data-ttu-id="1544e-115">Configurar o Sign-In automático do cliente para usar o diretor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1544e-115">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>](lync-server-2013-configure-automatic-client-sign-in-to-use-the-director.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

