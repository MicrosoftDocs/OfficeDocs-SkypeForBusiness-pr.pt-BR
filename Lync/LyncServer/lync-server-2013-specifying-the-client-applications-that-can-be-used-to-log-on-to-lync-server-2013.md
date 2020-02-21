---
title: 'Lync Server 2013: especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Specifying the client applications that can be used to log on to Lync Server 2013
ms:assetid: d256a581-9a48-4d1a-82cc-2e1f520d7d2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182591(v=OCS.15)
ms:contentKeyID: 48185450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81bae91ba4e9eec75e455ab1b3bc03b45c1a4c96
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181774"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="specifying-the-client-applications-that-can-be-used-to-log-on-to-lync-server-2013"></a><span data-ttu-id="47106-102">Especificando os aplicativos cliente que podem ser usados para fazer logon no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47106-102">Specifying the client applications that can be used to log on to Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="47106-103">_**Última modificação do tópico:** 2012-12-11_</span><span class="sxs-lookup"><span data-stu-id="47106-103">_**Topic Last Modified:** 2012-12-11_</span></span>

<span data-ttu-id="47106-104">O Lync Server 2013 permite que você especifique a versão de clientes que são compatíveis com o seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="47106-104">Lync Server 2013 enables you to specify the version of clients that are supported in your environment.</span></span> <span data-ttu-id="47106-105">O uso de políticas de versão do cliente pode ajudar a reduzir os custos associados ao suporte a várias versões de cliente.</span><span class="sxs-lookup"><span data-stu-id="47106-105">Using client version policies can help reduce the costs associated with supporting multiple client versions.</span></span> <span data-ttu-id="47106-106">Também pode melhorar a experiência geral do usuário, porque quando as versões anteriores e posteriores dos clientes interagem, os recursos disponíveis podem ser limitados pela versão anterior do cliente.</span><span class="sxs-lookup"><span data-stu-id="47106-106">It can also improve the overall user experience, because when earlier and later versions of clients interact, the available features can be limited by the earlier version of the client.</span></span>

<span data-ttu-id="47106-107">Há três componentes do controle de versão do cliente:</span><span class="sxs-lookup"><span data-stu-id="47106-107">There are three components of client version control:</span></span>

  - <span data-ttu-id="47106-108">As definições de configuração de versão do cliente são usadas para ativar ou desativar o controle de versão do cliente, globalmente ou para sites específicos.</span><span class="sxs-lookup"><span data-stu-id="47106-108">Client version configuration settings are used to turn client version control on or off, either globally or for particular sites.</span></span>

  - <span data-ttu-id="47106-109">As políticas de versão do cliente são usadas para atribuir um conjunto de regras globalmente ou para um determinado site, pool ou grupo de usuários.</span><span class="sxs-lookup"><span data-stu-id="47106-109">Client version policies are used to assign a set of rules globally, or to a particular site, pool, or group of users.</span></span>

  - <span data-ttu-id="47106-110">As regras de política de versão do cliente compõem uma política de versão do cliente e são usadas para definir as ações que devem ser executadas quando os usuários tentam fazer logon com clientes e versões de cliente específicos.</span><span class="sxs-lookup"><span data-stu-id="47106-110">Client version policy rules make up a client version policy, and are used to define the actions that should be taken when users attempt to log on with specific clients and client versions.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="47106-111">Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.</span><span class="sxs-lookup"><span data-stu-id="47106-111">Because anonymous users are not associated with a user, site, or service, anonymous users are affected by global-level policies only.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="47106-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="47106-112">In This Section</span></span>

  - [<span data-ttu-id="47106-113">Definições de configuração de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47106-113">Client version configuration settings in Lync Server 2013</span></span>](lync-server-2013-client-version-configuration-settings.md)

  - [<span data-ttu-id="47106-114">Políticas de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47106-114">Client version policies in Lync Server 2013</span></span>](lync-server-2013-client-version-policies.md)

  - [<span data-ttu-id="47106-115">Regras de versão do cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47106-115">Client version rules in Lync Server 2013</span></span>](lync-server-2013-client-version-rules.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="47106-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="47106-116">See Also</span></span>


[<span data-ttu-id="47106-117">Gerenciando dispositivos, telefones e aplicativos cliente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="47106-117">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

