---
title: 'Lync Server 2013: Implantando Aplicativo ou Servidor de Filial Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying a Survivable Branch Appliance or Server
ms:assetid: cb780c14-dc5f-41ba-8092-f20ae905bd16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398849(v=OCS.15)
ms:contentKeyID: 48185643
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7cf894fe6650ff3c06eaaa37f6ba05d70f50eeb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829566"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-a-survivable-branch-appliance-or-server-with-lync-server-2013"></a><span data-ttu-id="c5fc8-102">Implantando Aplicativo ou Servidor de Filial Persistente com Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fc8-102">Deploying a Survivable Branch Appliance or Server with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5fc8-103">_**Tópico da última modificação:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="c5fc8-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="c5fc8-104">O recurso de voz corporativo resistente refere-se à resiliência de filiais, ou seja, a capacidade de fornecer serviço contínuo de voz empresarial a usuários de sites de filiais em caso de o link para o site central ficar indisponível.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-104">Resilient Enterprise Voice refers to branch-site resiliency, that is, the ability to provide continuous Enterprise Voice service to branch site users in the event that the link to the central site becomes unavailable.</span></span>

<span data-ttu-id="c5fc8-105">Para sites de filiais de pequeno e médio porte (sites de filiais com 25 a 1.000 usuários), recomendamos implantar um aparelho de ramificação sobreviventes, que encerrará chamadas PSTN (rede telefônica pública comutada) usando seu gateway PSTN embutido ou um tronco SIP para um telefone provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-105">For small and medium-sized branch sites (branch sites with 25 to 1,000 users), we recommend deploying a Survivable Branch Appliance, which will terminate public switched telephone network (PSTN) calls by using its built-in PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="c5fc8-106">Um aparelho de ramificação sobreviventes é um dispositivo de terceiros que inclui um servidor blade executando o sistema operacional Windows Server 2008 R2, o Lync Server 2013 registrador, o software do servidor de mediação e um gateway PSTN, tudo em um chassi único de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-106">A Survivable Branch Appliance is a third-party device that includes a blade server running the Windows Server 2008 R2 operating system, Lync Server 2013 Registrar, Mediation Server software, and a PSTN gateway, all in a single appliance chassis.</span></span>

<span data-ttu-id="c5fc8-107">Para sites de filiais com 1.000 a 5.000 usuários e sem conexão de longa distância, recomendamos um servidor de ramificação sobreviventes conectado a um gateway PSTN ou um tronco SIP para um provedor de serviços de telefonia.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-107">For branch sites with 1,000 to 5,000 users and no resilient WAN, we recommend a Survivable Branch Server connected to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span> <span data-ttu-id="c5fc8-108">Um servidor de ramificação sobreviventes é um computador baseado no Windows Server que tem o software servidor de registrador e mediação instalado.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-108">A Survivable Branch Server is a Windows Server-based computer that has Registrar and Mediation Server software installed on it.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5fc8-109">Para sites de filiais com mais de 5.000 usuários e administradores dedicados do Lync Server, recomendamos uma implantação completa do Lync Server 2013, separada do site central.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-109">For branch sites with more than 5,000 users and dedicated Lync Server administrators, we recommend a full Lync Server 2013 deployment, separate from that of the central site.</span></span><BR><span data-ttu-id="c5fc8-110">Para obter detalhes sobre como escolher a melhor solução de resiliência para os sites de filiais em sua organização, incluindo pré-requisitos e considerações de planejamento, consulte <A href="lync-server-2013-branch-site-resiliency-requirements.md">requisitos de resiliência de site para o Lync Server 2013</A> na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-110">For details about choosing the best resiliency solution for the branch sites in your organization, including prerequisites and planning considerations, see <A href="lync-server-2013-branch-site-resiliency-requirements.md">Branch-site resiliency requirements for Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c5fc8-111">Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="c5fc8-111">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new chat rooms or view the room card for existing rooms.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5fc8-112">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c5fc8-112">In This Section</span></span>

  - [<span data-ttu-id="c5fc8-113">Implantando um servidor ou aparelho de filial persistente com o Lync Server 2013 - Tarefas do site central</span><span class="sxs-lookup"><span data-stu-id="c5fc8-113">Deploying a Survivable Branch Appliance or Server with Lync Server 2013 - central site tasks</span></span>](lync-server-2013-deploying-a-survivable-branch-appliance-or-server-central-site-tasks.md)

  - [<span data-ttu-id="c5fc8-114">Implantar Servidor ou Aparelho de Filial Persistente com Lync Server 2013 - tarefa de site de filial</span><span class="sxs-lookup"><span data-stu-id="c5fc8-114">Deploy a Survivable Branch Appliance or Server with Lync Server 2013 - branch site task</span></span>](lync-server-2013-deploy-a-survivable-branch-appliance-or-server-branch-site-task.md)

  - [<span data-ttu-id="c5fc8-115">Configurando usuários para resiliência de site da filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fc8-115">Configuring users for branch site resiliency in Lync Server 2013</span></span>](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

  - [<span data-ttu-id="c5fc8-116">Usuários domésticos em um Home users on a Aparelho de Filial Persistente ou Servidor no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fc8-116">Home users on a Survivable Branch Appliance or Server in Lync Server 2013</span></span>](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)

  - [<span data-ttu-id="c5fc8-117">Anexos: Servidores e Aplicativos de Filial Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fc8-117">Appendices: Survivable Branch Appliances and Servers in Lync Server 2013</span></span>](lync-server-2013-appendices-survivable-branch-appliances-and-servers.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c5fc8-118">Confira também</span><span class="sxs-lookup"><span data-stu-id="c5fc8-118">See Also</span></span>


[<span data-ttu-id="c5fc8-119">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5fc8-119">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

