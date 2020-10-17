---
title: 'Lync Server 2013: projetando a topologia usando a ferramenta de planejamento'
description: 'Lync Server 2013: projetando a topologia usando a ferramenta de planejamento.'
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
ms.openlocfilehash: fcc10d09d7b8b815e2b4924d06c10de23c14236b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542587"
---
# <a name="designing-the-topology-for-lync-server-2013-by-using-the-planning-tool"></a><span data-ttu-id="50e08-103">Projetando a topologia do Lync Server 2013 usando a ferramenta de planejamento</span><span class="sxs-lookup"><span data-stu-id="50e08-103">Designing the topology for Lync Server 2013 by using the Planning Tool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50e08-104">_**Última modificação do tópico:** 2013-03-04_</span><span class="sxs-lookup"><span data-stu-id="50e08-104">_**Topic Last Modified:** 2013-03-04_</span></span>

<span data-ttu-id="50e08-105">A ferramenta de planejamento do Microsoft Lync Server 2013 é uma ferramenta orientada por um assistente que faz perguntas sobre a topologia 2013 do Lync Server que você está criando.</span><span class="sxs-lookup"><span data-stu-id="50e08-105">The Microsoft Lync Server 2013, Planning Tool is a wizard driven, interview-like tool that asks questions about the Lync Server 2013 topology that you are designing.</span></span> <span data-ttu-id="50e08-106">A ferramenta de planejamento usa as informações fornecidas, combinadas com práticas preferidas para design e capacidade de topologia, para apresentar uma topologia recomendada com base nas respostas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="50e08-106">The Planning Tool uses the information supplied, coupled with preferred practices for topology design and capacity, to present a recommended topology based on the answers supplied.</span></span> <span data-ttu-id="50e08-107">Você pode baixar a ferramenta de planejamento do centro de downloads da Microsoft ( [https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725) ).</span><span class="sxs-lookup"><span data-stu-id="50e08-107">You can download the Planning Tool from the Microsoft Downloads Center ([https://go.microsoft.com/fwlink/?LinkID=282725](https://go.microsoft.com/fwlink/?linkid=282725)).</span></span>

<span data-ttu-id="50e08-108">Em última análise, o objetivo da ferramenta de planejamento é facilitar a complexidade potencial de projetar uma topologia completa do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50e08-108">Ultimately, the goal of the Planning Tool is to ease the potential complexity of designing a complete Lync Server 2013 topology.</span></span> <span data-ttu-id="50e08-109">A ferramenta também fornece referências contextuais à documentação de planejamento e implantação dentro da ferramenta, contanto que uma conexão com a Internet esteja disponível para se conectar ao site Microsoft TechNet.</span><span class="sxs-lookup"><span data-stu-id="50e08-109">The tool also provides contextual references to planning and deployment documentation inside the tool, provided that an Internet connection is available to connect to the Microsoft TechNet website.</span></span>

<span data-ttu-id="50e08-110">Após personalizar a topologia com os endereços TCP/IP da infraestrutura e FQDNs (nomes de domínio totalmente qualificados), a ferramenta de planejamento disponibiliza uma série de relatórios que abrangem a nomenclatura de DNS (sistema de nomes de domínio), regras de firewall, certificados e muito mais.</span><span class="sxs-lookup"><span data-stu-id="50e08-110">After customizing the topology with the infrastructure’s TCP/IP addresses and fully qualified domain names (FQDNs), the Planning Tool makes available a series of reports that cover Domain Name System (DNS) naming, firewall rules, certificates, and more.</span></span>

<span data-ttu-id="50e08-111">A ferramenta de planejamento também oferece a capacidade de exportar informações em dois formatos:</span><span class="sxs-lookup"><span data-stu-id="50e08-111">The Planning Tool also provides the ability to export information in two formats:</span></span>

  - <span data-ttu-id="50e08-112">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="50e08-112">Microsoft Excel</span></span>

  - <span data-ttu-id="50e08-113">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="50e08-113">Microsoft Visio</span></span>

<span data-ttu-id="50e08-114">Os tópicos a seguir apresentam e detalham a ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="50e08-114">The following topics introduce and detail the Planning Tool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="50e08-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="50e08-115">In This Section</span></span>

  - [<span data-ttu-id="50e08-116">Instalando a ferramenta de planejamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-116">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)

  - [<span data-ttu-id="50e08-117">Instalando software opcional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-117">Installing optional software in Lync Server 2013</span></span>](lync-server-2013-installing-optional-software.md)

  - [<span data-ttu-id="50e08-118">Navegando na ferramenta de planejamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-118">Navigating the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-navigating-the-planning-tool.md)

  - [<span data-ttu-id="50e08-119">Criar o design de topologia inicial para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-119">Create the initial topology design for Lync Server 2013</span></span>](lync-server-2013-create-the-initial-topology-design.md)

  - [<span data-ttu-id="50e08-120">Revisando os relatórios do administrador no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-120">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50e08-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="50e08-121">See Also</span></span>


[<span data-ttu-id="50e08-122">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-122">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
[<span data-ttu-id="50e08-123">Planejamento de servidores front-end, mensagens instantâneas e presença no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50e08-123">Planning for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>](lync-server-2013-planning-for-front-end-servers-instant-messaging-and-presence.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

