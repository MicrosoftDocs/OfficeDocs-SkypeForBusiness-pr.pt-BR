---
title: 'Lync Server 2013: Verificar conectividade para usuários externos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 577ba970e272e2306aae3a587d9ae014ba75ba17
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="e1850-102">Verificar conectividade para usuários externos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1850-102">Verify connectivity for external users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1850-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="e1850-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="e1850-104">Validar a conectividade para usuários externos requer a garantia de conectividade de usuários para o servidor e porta para o serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="e1850-104">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="e1850-105">Um recurso valioso para confirmar a configuração e a capacidade de se conectar, enviar e receber as mensagens corretas para os cenários que o acesso de usuários externos requer é o site do analisador de conectividade remota (<http://www.testocsconnectivity.com>).</span><span class="sxs-lookup"><span data-stu-id="e1850-105">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="e1850-106">O site é gerenciado e mantido pelo suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1850-106">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="e1850-107">Para acessar o analisador de conectividade remota, abra o site em um navegador e siga as instruções para selecionar o cenário.</span><span class="sxs-lookup"><span data-stu-id="e1850-107">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="e1850-108">Testar a conectividade de usuários externos e acesso externo</span><span class="sxs-lookup"><span data-stu-id="e1850-108">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="e1850-109">Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um dos itens a seguir ou todos eles:</span><span class="sxs-lookup"><span data-stu-id="e1850-109">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="e1850-110">Usuários de pelo menos um domínio federado e testem mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="e1850-110">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="e1850-111">Usuários de cada provedor de serviços de mensagens de chat público compatível com a sua organização (e para a qual a configuração foi completada).</span><span class="sxs-lookup"><span data-stu-id="e1850-111">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="e1850-112">Usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="e1850-112">Anonymous users.</span></span>

  - <span data-ttu-id="e1850-113">Os usuários dentro da sua organização que estão conectados ao Lync remotamente, mas não ao uso da VPN.</span><span class="sxs-lookup"><span data-stu-id="e1850-113">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="e1850-114">Estes testes determinam se o servidor de borda é:</span><span class="sxs-lookup"><span data-stu-id="e1850-114">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="e1850-115">Escuta as portas necessárias usando um cliente telnet de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="e1850-115">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="e1850-116">Exemplo: Telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="e1850-116">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="e1850-117">Execute o teste anterior em portas que você está usando no servidor de borda ou no pool do servidor de borda, dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="e1850-117">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="e1850-118">Executa a resolução DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="e1850-118">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="e1850-119">De fora da rede, execute ping em cada um dos FQDNS externos do seu pool de bordas ou bordas.</span><span class="sxs-lookup"><span data-stu-id="e1850-119">From outside your network ping each of the external FQDN’s of your Edge or Edge pool.</span></span> <span data-ttu-id="e1850-120">Mesmo que o ping falhe, você verá os endereços IP, que podem ser comparados àqueles que você atribuiu.</span><span class="sxs-lookup"><span data-stu-id="e1850-120">Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

