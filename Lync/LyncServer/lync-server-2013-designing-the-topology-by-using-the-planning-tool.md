---
title: 'Lync Server 2013: criando a topologia usando a ferramenta de planejamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the topology by using the Planning Tool
ms:assetid: 2a352f62-c5cb-4ef1-9aa9-7f0c1ab47455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558631(v=OCS.15)
ms:contentKeyID: 51541454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 590bfae33e12cca2e2305eab9d842f0e2f105838
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762499"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="8753d-102">Criando a topologia do Lync Server 2013 usando a ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="8753d-102">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8753d-103">_**Tópico da última modificação:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="8753d-103">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="8753d-104">O Microsoft Lync Server 2013, ferramenta de planejamento é uma ferramenta de planejamento orientada por assistente que faz perguntas sobre a topologia do Lync Server 2013 que você está criando.</span><span class="sxs-lookup"><span data-stu-id="8753d-104">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="8753d-105">A ferramenta de planejamento usa as informações fornecidas, combinadas com práticas preferenciais de design e capacidade de topologia, para apresentar uma topologia recomendada com base nas respostas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="8753d-105">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="8753d-106">Você pode baixar a ferramenta de planejamento no centro de download da[http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)Microsoft ().</span><span class="sxs-lookup"><span data-stu-id="8753d-106">You can download the Planning Tool from the Microsoft Downloads Center ([http://go.microsoft.com/fwlink/?LinkID=282725](http://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="8753d-107">Por fim, o objetivo da ferramenta de planejamento é facilitar a complexidade potencial de criar uma topologia completa do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8753d-107">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="8753d-108">A ferramenta também fornece referências contextuais à documentação de planejamento e implantação dentro da ferramenta, contanto que uma conexão com a Internet esteja disponível para se conectar ao site Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="8753d-108">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="8753d-109">Após personalizar a topologia com os endereços TCP/IP da infraestrutura e FQDNs (nomes de domínio totalmente qualificados), a ferramenta de planejamento disponibiliza uma série de relatórios que abrangem o nome DNS, as regras de firewall, os certificados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="8753d-109">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="8753d-110">A ferramenta de planejamento também fornece a capacidade de exportar informações em dois formatos:</span><span class="sxs-lookup"><span data-stu-id="8753d-110">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="8753d-111">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="8753d-111">Microsoft Excel</span></span>

  - <span data-ttu-id="8753d-112">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="8753d-112">Microsoft Visio</span></span>

<span data-ttu-id="8753d-113">Os tópicos a seguir introduzem e detalham a ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="8753d-113">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8753d-114">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="8753d-114">In This Section</span></span>

  - [<span data-ttu-id="8753d-115">Instalando a Ferramenta de Planejamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-115">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="8753d-116">Instalação de software opcional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-116">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="8753d-117">Navegar pela ferramenta de planejamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-117">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="8753d-118">Criar o design de topologia inicial para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-118">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="8753d-119">Revisando os Relatórios do Administrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8753d-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="8753d-120">See Also</span></span>


[<span data-ttu-id="8753d-121">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-121">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="8753d-122">Planejamento de Servidores Front-End, sistema de mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8753d-122">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

