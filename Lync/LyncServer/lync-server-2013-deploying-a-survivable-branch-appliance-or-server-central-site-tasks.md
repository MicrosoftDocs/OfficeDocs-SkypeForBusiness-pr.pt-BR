---
title: Implantando um servidor ou aparelho de filial persistente - Tarefas do site central
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server - central site tasks
ms:assetid: 0f631a36-fc2e-41cd-8a0d-f27e84f4a89e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398189(v=OCS.15)
ms:contentKeyID: 48183422
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b31e191dc2726c7e7962b0daa4ee5655245117
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013---central-site-tasks"></a><span data-ttu-id="c539c-102">Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013 - Tarefas do site central</span><span class="sxs-lookup"><span data-stu-id="c539c-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c539c-103">_**Tópico da última modificação:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="c539c-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="c539c-104">Conclua as tarefas nesta seção no site central.</span><span class="sxs-lookup"><span data-stu-id="c539c-104">Complete the tasks in this section at the central site.</span></span> <span data-ttu-id="c539c-105">Se você estiver implantando um servidor de ramificação sobreviventes, pule a primeira tarefa.</span><span class="sxs-lookup"><span data-stu-id="c539c-105">If you’re deploying a Survivable Branch Server, skip the first task.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="c539c-106">Antes de executar as tarefas nesta seção, as seguintes condições devem estar em vigor:</span><span class="sxs-lookup"><span data-stu-id="c539c-106">Before you perform the tasks in this section, the following conditions must be in place:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c539c-107">O Lync Server deve ser configurado no site central.</span><span class="sxs-lookup"><span data-stu-id="c539c-107">Lync Server must be set up at the central site.</span></span></P>
> <LI>
> <P><span data-ttu-id="c539c-108">Um técnico de instalação no site de filial deve ser adicionado ao grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="c539c-108">An installation technician at the branch site must be added to the RTCUniversalSBATechnicians group.</span></span></P></LI></UL><span data-ttu-id="c539c-109">Além disso, recomendamos que você faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c539c-109">In addition, we recommend that you do the following:</span></span>
> <UL>
> <LI>
> <P><span data-ttu-id="c539c-110">Implante um servidor DHCP em cada site de ramificação para permitir que os clientes obtenham endereços IP.</span><span class="sxs-lookup"><span data-stu-id="c539c-110">Deploy a DHCP server at each branch site to enable clients to obtain IP addresses.</span></span></P>
> <LI>
> <P><span data-ttu-id="c539c-111">Como uma alternativa para implantar um servidor DHCP em cada site de ramificação, habilite o DHCP do Lync Server no aparelho de ramificação ou servidor de ramificação sobreviventes usando o cmdlet do Shell de gerenciamento do Lync Server <STRONG>set-CsRegistrarConfiguration-EnableDHCPServer $true </STRONG>.</span><span class="sxs-lookup"><span data-stu-id="c539c-111">As an alternative to deploying a DHCP server at each branch site, enable Lync Server DHCP on the Survivable Branch Appliance or Survivable Branch Server by using the Lync Server Management Shell cmdlet <STRONG>Set-CsRegistrarConfiguration –EnableDHCPServer $true</STRONG>.</span></span> <span data-ttu-id="c539c-112">Para obter detalhes, consulte a seção "requisitos de hardware e software" dos <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para o Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="c539c-112">For details, see the “Hardware and Software Requirements” section of <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span></P></LI></UL>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c539c-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c539c-113">In This Section</span></span>

  - [<span data-ttu-id="c539c-114">Adicionar um Aplicativo de Filial Persistente ao Active Directory no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c539c-114">Add a Survivable Branch Appliance to Active Directory in Lync Server 2013</span></span>](lync-server-2013-add-a-survivable-branch-appliance-to-active-directory.md)

  - [<span data-ttu-id="c539c-115">Adicionar sites de filial a sua topologia no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c539c-115">Add branch sites to your topology in Lync Server 2013</span></span>](lync-server-2013-add-branch-sites-to-your-topology.md)

  - [<span data-ttu-id="c539c-116">Definir um Servidor ou Aparelho de Filial Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c539c-116">Define a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-define-a-survivable-branch-appliance-or-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

