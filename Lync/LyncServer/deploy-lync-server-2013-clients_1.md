---
title: Implantar clientes do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 clients
ms:assetid: 508e5dfa-588b-4289-81ce-2043c2d79e04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204883(v=OCS.15)
ms:contentKeyID: 48184100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffc6ee3831968c34bcdb501fcdf543626546e2c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723011"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-clients"></a><span data-ttu-id="95cec-102">Implantar clientes do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95cec-102">Deploy Lync Server 2013 clients</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95cec-103">_**Tópico da última modificação:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="95cec-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="95cec-104">Depois de migrar usuários para o Lync Server 2013, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="95cec-104">After you migrate users to Lync Server 2013, do the following:</span></span>

1.  <span data-ttu-id="95cec-105">Use o filtro de versão do cliente no novo servidor do Lync Server 2013 para permitir somente aos clientes com as atualizações mais recentes instaladas para entrar.</span><span class="sxs-lookup"><span data-stu-id="95cec-105">Use the Client Version Filter on the new Lync Server 2013 server to only allow clients with the most current updates installed to sign in.</span></span>

2.  <span data-ttu-id="95cec-106">Se necessário, defina as configurações de política de grupo necessárias para a inicialização do cliente.</span><span class="sxs-lookup"><span data-stu-id="95cec-106">If necessary, configure the Group Policy settings that are required for client bootstrapping.</span></span> <span data-ttu-id="95cec-107">Para obter detalhes, consulte [configurando as políticas de inicialização do cliente no Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="95cec-107">For details, see [Configuring client bootstrapping policies in Lync Server 2013](lync-server-2013-configuring-client-bootstrapping-policies.md) in the Deployment documentation.</span></span> <span data-ttu-id="95cec-108">A configuração dessas configurações só será necessária se você quiser alterar as políticas de inicialização do cliente existentes ou se quiser definir as novas políticas de inicialização do cliente.</span><span class="sxs-lookup"><span data-stu-id="95cec-108">Configuration of these settings is only necessary if you want to change existing client bootstrapping policies or if you want to set new client bootstrapping policies.</span></span> <span data-ttu-id="95cec-109">Se você não planejar configurar as políticas de inicialização do cliente ou se quiser que as políticas de inicialização do cliente herdadas permaneçam efetivas, nenhuma ação será necessária.</span><span class="sxs-lookup"><span data-stu-id="95cec-109">If you do not plan to configure client bootstrapping policies, or you want legacy client bootstrapping policies to remain in effect, no action is necessary.</span></span>

3.  <span data-ttu-id="95cec-110">Configurar outras políticas de usuário e de cliente para usuários específicos ou grupos de usuários usando o painel de controle do Lync Server 2013, o Shell de gerenciamento do Lync Server 2013 ou ambos.</span><span class="sxs-lookup"><span data-stu-id="95cec-110">Configure other user and client policies for specific users or groups of users by using Lync Server 2013 Control Panel, Lync Server 2013 Management Shell, or both.</span></span> <span data-ttu-id="95cec-111">Para obter detalhes, consulte [configurações novas e alteradas para o Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="95cec-111">For details, see [New and changed settings for Lync 2013](lync-server-2013-new-and-changed-settings-for-lync-2013.md) in the Planning documentation.</span></span>

4.  <span data-ttu-id="95cec-112">Implante a versão mais recente dos clientes do Lync Server 2013 juntamente com as atualizações cumulativas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="95cec-112">Deploy the latest version of Lync Server 2013 clients along with the latest cumulative updates.</span></span> <span data-ttu-id="95cec-113">Para obter detalhes, consulte [implantando clientes e dispositivos no Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="95cec-113">For details, see [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

5.  <span data-ttu-id="95cec-114">Adicionais Se sua organização requer o modo de privacidade de presença avançada do Lync Server 2013, após a conclusão da migração, defina uma regra de política de versão do cliente para impedir que as versões anteriores do cliente sejam conectadas.</span><span class="sxs-lookup"><span data-stu-id="95cec-114">(Optional) If your organization requires Lync Server 2013 enhanced presence privacy mode, after migration is complete, define a Client Version Policy Rule to prevent earlier client versions from signing in.</span></span> <span data-ttu-id="95cec-115">Em seguida, habilite o modo de privacidade de presença avançada.</span><span class="sxs-lookup"><span data-stu-id="95cec-115">Then, enable enhanced presence privacy mode.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="95cec-116">Não habilite o modo de privacidade de presença avançada do Lync 2013 até que todos os usuários em um determinado pool de servidores tenham as versões do cliente mais recentes instaladas.</span><span class="sxs-lookup"><span data-stu-id="95cec-116">Do not enable Lync 2013 enhanced presence privacy mode until every user on a given server pool has the most current client versions installed.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

