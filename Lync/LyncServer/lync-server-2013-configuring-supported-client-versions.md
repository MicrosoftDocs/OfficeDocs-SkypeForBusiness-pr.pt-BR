---
title: 'Lync Server 2013: Configurando versões de cliente suportadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring supported client versions
ms:assetid: aebf7b48-9aa2-4a06-adc5-0c9d11b6358d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412832(v=OCS.15)
ms:contentKeyID: 48185137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 34d74de1ae5e25c372e51783d8321ebc8699eaef
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-supported-client-versions-in-lync-server-2013"></a><span data-ttu-id="b9e91-102">Configurando as versões de cliente suportadas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9e91-102">Configuring supported client versions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9e91-103">_**Última modificação do tópico:** 2012-12-14_</span><span class="sxs-lookup"><span data-stu-id="b9e91-103">_**Topic Last Modified:** 2012-12-14_</span></span>

<span data-ttu-id="b9e91-104">No Lync Server 2013, você pode configurar políticas de versão do cliente para especificar as versões dos clientes com suporte no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="b9e91-104">In Lync Server 2013, you can set up client version policies to specify the versions of clients that are supported in your environment.</span></span> <span data-ttu-id="b9e91-105">Além disso, você pode usar a configuração de versão do cliente global para especificar uma ação padrão para clientes que ainda não têm uma política de versão definida e, portanto, não são explicitamente suportadas ou restritas.</span><span class="sxs-lookup"><span data-stu-id="b9e91-105">Additionally, you can use the global client version configuration to specify a default action for clients that do not already have a version policy defined and, therefore, are not explicitly supported or restricted.</span></span>

<span data-ttu-id="b9e91-106">Você também pode usar as políticas de versão do cliente para gerenciar as atualizações do cliente.</span><span class="sxs-lookup"><span data-stu-id="b9e91-106">You can also use client version policies to manage client updates.</span></span> <span data-ttu-id="b9e91-107">Ao definir uma política de versão de cliente e usar as opções **permitir e atualizar** e **bloquear e atualizar**, os clientes receberão software atualizado do serviço de atualização do Windows Server (se você estiver usando esse serviço) ou do Microsoft Update.</span><span class="sxs-lookup"><span data-stu-id="b9e91-107">When you set a client version policy and use the options **Allow and upgrade** and **Block and upgrade**, clients will receive updated software from the Windows Server Update Service (if you are using this service) or from Microsoft Update.</span></span>

<div>

## <a name="client-version-policy-settings"></a><span data-ttu-id="b9e91-108">Configurações de política de versão do cliente</span><span class="sxs-lookup"><span data-stu-id="b9e91-108">Client Version Policy Settings</span></span>

<span data-ttu-id="b9e91-109">A política de versão de cliente padrão requer que todos os clientes executem o Lync.</span><span class="sxs-lookup"><span data-stu-id="b9e91-109">The default client version policy requires that all clients run Lync.</span></span> <span data-ttu-id="b9e91-110">Se os clientes do seu ambiente estiverem executando versões anteriores do Communicator, talvez seja necessário reconfigurar as regras de versão do cliente para impedir que os clientes e dispositivos sejam bloqueados ou atualizados inesperadamente ao se conectar ao Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b9e91-110">If clients in your environment are running earlier versions of Communicator, you may need to reconfigure the Client Version rules to prevent clients and devices from being unexpectedly blocked or updated when connecting to Lync Server 2013.</span></span> <span data-ttu-id="b9e91-111">Você pode modificar a regra padrão ou pode adicionar uma regra superior na lista política de versão do cliente para substituir a regra padrão.</span><span class="sxs-lookup"><span data-stu-id="b9e91-111">You can modify the default rule, or you can add a rule higher in the Client Version Policy list to override the default rule.</span></span> <span data-ttu-id="b9e91-112">Além disso, como as atualizações cumulativas (CUs) são lançadas, você deve configurar a política de versão do cliente para exigir as atualizações mais recentes.</span><span class="sxs-lookup"><span data-stu-id="b9e91-112">Additionally, as Cumulative Updates (CUs) are released, you should configure the Client Version Policy to require the latest updates.</span></span> <span data-ttu-id="b9e91-113">Para obter detalhes, consulte [especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) na documentação operações.</span><span class="sxs-lookup"><span data-stu-id="b9e91-113">For details, see [Specifying the client applications that can be used to log on to Lync Server 2013](lync-server-2013-specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013.md) in the Operations documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

