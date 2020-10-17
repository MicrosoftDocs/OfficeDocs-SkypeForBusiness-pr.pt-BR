---
title: 'Lync Server 2013: Implantando um servidor ou aparelho de filial persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 258f53cf16287b29c739c5a232376fa629b401f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531348"
---
# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="ee778-102">Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee778-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee778-103">_**Última modificação do tópico:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="ee778-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="ee778-104">O Enterprise Voice resistente refere-se à resiliência de site de filial, ou seja, a capacidade de fornecer serviço de Enterprise Voice contínuo para usuários de filiais no caso de o link para o site central se tornar indisponível.</span><span class="sxs-lookup"><span data-stu-id="ee778-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="ee778-105">Para sites de filiais de pequeno e médio porte (sites de filiais com 25 a 1.000 usuários), recomendamos a implantação de um aparelho de filial persistente, que encerrará chamadas PSTN (rede telefônica pública comutada) usando seu gateway PSTN interno ou um tronco SIP para um provedor de serviços de telefonia.</span><span class="sxs-lookup"><span data-stu-id="ee778-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ee778-106">Um aparelho de filial persistente é um dispositivo de terceiros que inclui um servidor de lâmina executando o sistema operacional Windows Server 2008 R2, o servidor do Lync Server 2013, o software do servidor de mediação e um gateway PSTN, tudo em um chassi único de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ee778-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="ee778-107">Para sites de filiais com 1.000 a 5.000 usuários e nenhuma WAN resistente, recomendamos um servidor de filial persistente conectado a um gateway PSTN ou um tronco SIP para um provedor de serviços de telefonia.</span><span class="sxs-lookup"><span data-stu-id="ee778-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="ee778-108">Um servidor de filial persistente é um computador baseado no Windows Server que tem o software servidor de registrador e mediação instalado nele.</span><span class="sxs-lookup"><span data-stu-id="ee778-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ee778-109">Para sites de filiais com mais de 5.000 usuários e administradores dedicados do Lync Server, recomendamos uma implantação completa do Lync Server 2013, separada do site central.</span><span class="sxs-lookup"><span data-stu-id="ee778-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="ee778-110">Para obter detalhes sobre como escolher a melhor solução de resiliência para os sites de filial em sua organização, incluindo pré-requisitos e considerações de planejamento, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliência Requirements for Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ee778-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ee778-111">Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="ee778-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee778-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="ee778-112">In This Section</span></span>

  - [<span data-ttu-id="ee778-113">Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefas do site central</span><span class="sxs-lookup"><span data-stu-id="ee778-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="ee778-114">Implantar um servidor ou aparelho de filial persistente com o Lync Server 2013-tarefa do site de filial</span><span class="sxs-lookup"><span data-stu-id="ee778-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="ee778-115">Configurando usuários para resiliência de site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee778-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="ee778-116">Usuários domésticos em um aparelho de filial persistente ou servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee778-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="ee778-117">Apêndices: servidores e aparelhos de filial persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee778-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ee778-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="ee778-118">See Also</span></span>


[<span data-ttu-id="ee778-119">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ee778-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

