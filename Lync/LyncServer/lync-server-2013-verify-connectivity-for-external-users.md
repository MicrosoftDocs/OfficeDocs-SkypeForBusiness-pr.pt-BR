---
title: 'Lync Server 2013: verificar conectividade para usuários externos'
description: 'Lync Server 2013: Verifique a conectividade para usuários externos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity for external users
ms:assetid: 5c02bd6e-1c96-448a-a21d-58c9961c6640
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398402(v=OCS.15)
ms:contentKeyID: 48184249
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50ef728157d01b93e7d0b8420442ce083a42b5b2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547087"
---
# <a name="verify-connectivity-for-external-users-in-lync-server-2013"></a><span data-ttu-id="f4167-103">Verificar a conectividade para usuários externos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f4167-103">Verify connectivity for external users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4167-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f4167-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f4167-105">Para validar a conectividade de usuários externos, é necessário garantir a conectividade dos usuários com o servidor e a porta do Serviço de Borda de Acesso.</span><span class="sxs-lookup"><span data-stu-id="f4167-105">Validating connectivity for external users requires ensuring connectivity from users to the server and port for the Access Edge service.</span></span>

<span data-ttu-id="f4167-106">Um recurso valioso para confirmar sua configuração e a capacidade de se conectar, enviar e receber as mensagens corretas para os cenários que o acesso de usuário externo requer é o site do analisador de conectividade remota ( <http://www.testocsconnectivity.com> ).</span><span class="sxs-lookup"><span data-stu-id="f4167-106">A valuable resource for confirming your configuration and the ability to connect, send and receive the correct messages for the scenarios that external user access requires is the Remote Connectivity Analyzer site (<http://www.testocsconnectivity.com>).</span></span> <span data-ttu-id="f4167-107">O site é gerenciado e mantido pelo suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f4167-107">The site is managed and maintained by Microsoft Support.</span></span> <span data-ttu-id="f4167-108">Para acessar o Analisador de Conectividade Remota, abra o site da Web em um navegador e siga as instruções para selecionar o cenário.</span><span class="sxs-lookup"><span data-stu-id="f4167-108">To reach the Remote Connectivity Analyzer, open the Web site in a browser and follow the instructions to select the scenario.</span></span>

<div>

## <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="f4167-109">Teste a conectividade de usuários externos e do acesso externo</span><span class="sxs-lookup"><span data-stu-id="f4167-109">Test Connectivity of External Users and External access</span></span>

<span data-ttu-id="f4167-110">Os testes de acesso de usuários externos devem incluir todos os tipos de usuário externo aceitos pela sua organização, incluindo um ou todos os seguintes:</span><span class="sxs-lookup"><span data-stu-id="f4167-110">Tests for external user access should include each type of external user that your organization supports, including any or all of the following:</span></span>

  - <span data-ttu-id="f4167-111">Os usuários de pelo menos um domínio federado e o teste de IM, presença, A/V e compartilhamento de área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="f4167-111">Users from at least one federated domain, and test IM, presence, A/V and desktop sharing.</span></span>

  - <span data-ttu-id="f4167-112">Os usuários de cada provedor de serviços públicos de IM que tem suporte em sua empresa (e para o qual o provisionamento foi concluído).</span><span class="sxs-lookup"><span data-stu-id="f4167-112">Users of each public IM service provider that your organization supports (and for which provisioning has been completed).</span></span>

  - <span data-ttu-id="f4167-113">Usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="f4167-113">Anonymous users.</span></span>

  - <span data-ttu-id="f4167-114">Usuários em sua organização que fizeram logon no Lync remotamente, mas sem usar VPN.</span><span class="sxs-lookup"><span data-stu-id="f4167-114">Users within your organization who are logged into Lync remotely, but not using VPN.</span></span>

<span data-ttu-id="f4167-115">Esses testes determinam se o Servidor de Borda:</span><span class="sxs-lookup"><span data-stu-id="f4167-115">These tests determine whether your Edge Server is:</span></span>

  - <span data-ttu-id="f4167-116">Escuta as portas necessárias usando um cliente telnet de fora da rede.</span><span class="sxs-lookup"><span data-stu-id="f4167-116">Listening on the necessary ports by using a telnet client from outside your network.</span></span>
    
      - <span data-ttu-id="f4167-117">Exemplo: telnet sip.contoso.com 443</span><span class="sxs-lookup"><span data-stu-id="f4167-117">Example: telnet sip.contoso.com 443</span></span>
    
      - <span data-ttu-id="f4167-118">Executa o teste anterior nas portas que você está usando no Servidor de Borda ou no pool do Servidor de Borda dependendo da sua implantação.</span><span class="sxs-lookup"><span data-stu-id="f4167-118">Perform the preceding test on ports you are using on the Edge Server or Edge Server pool depending on your deployment.</span></span>

  - <span data-ttu-id="f4167-119">Executa a resolução DNS externa precisa.</span><span class="sxs-lookup"><span data-stu-id="f4167-119">Performing accurate external DNS resolution.</span></span>
    
      - <span data-ttu-id="f4167-p102">De fora da sua rede, execute ping em cada FQDN externo da Borda ou do pool de Borda. Mesmo se o ping falhar, você verá os endereços IP, que poderá comparar com aqueles que você atribuiu.</span><span class="sxs-lookup"><span data-stu-id="f4167-p102">From outside your network ping each of the external FQDN’s of your Edge or Edge pool. Even if the ping fails you will see the IP addresses, which you can compare to the ones you have assigned.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

