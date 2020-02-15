---
title: 'Lync Server 2013: coleta de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Data collection
ms:assetid: e40b03e5-455d-4bbc-831a-c61b1380db53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399008(v=OCS.15)
ms:contentKeyID: 48185722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 025e31ada5ff08b27591ebf27aade875494c1614
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="2b229-102">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b229-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b229-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="2b229-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="2b229-104">No software de comunicações do Microsoft Lync Server 2013, você pode executar o Microsoft Lync Server 2013, ferramenta de planejamento sem documentar seus endereços IP existentes e propostos e os FQDNs (nomes de domínio totalmente qualificados) do servidor de borda, mas é significativamente mais difícil de fazer Portanto, sem causar erros de configuração.</span><span class="sxs-lookup"><span data-stu-id="2b229-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="2b229-105">Por exemplo, se a coexistência for necessária por um período de tempo, um erro comum é reutilizar FQDNs de uma implantação de borda existente para sua implantação de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="2b229-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="2b229-106">Com os endereços IP e os FQDNs existentes e propostos escritos em uma planilha, tabela ou outro formulário Visual, você ajuda a evitar problemas de instalação durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="2b229-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="2b229-107">Se você usou versões anteriores da ferramenta de planejamento, talvez tenha usado a ferramenta para criar sua topologia e o documento de topologia exportado para uso no construtor de topologias para publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="2b229-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="2b229-108">A capacidade de exportar a topologia foi removida da ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2b229-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="2b229-109">O uso de uma versão anterior da ferramenta de planejamento para criar um documento de topologia para o Lync Server 2013 é fortemente desencorajado e produzirá resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="2b229-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="2b229-110">Portanto, a abordagem recomendada é usar o modelo de conjunto de dados a seguir, que corresponde à sua topologia de borda, para coletar os vários endereços IP e FQDN que você precisará inserir na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="2b229-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="2b229-111">Ao documentar a configuração atual e proposta, você pode colocar os valores no contexto apropriado para seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="2b229-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="2b229-112">E, você é obrigado a pensar sobre como você irá configurar a coexistência e recursos como URLs simples, compartilhamento de arquivos e balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="2b229-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="2b229-113">Para implantar o Microsoft Lync Server 2013 com êxito, você precisa entender a interação e a confiança dos componentes individuais.</span><span class="sxs-lookup"><span data-stu-id="2b229-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="2b229-114">Ao coletar dados de sua infraestrutura de rede e de servidor existente e aplicar as diretrizes de planejamento nessas seções, você pode integrar os componentes do servidor de borda do Lync Server 2013 à sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="2b229-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="2b229-115">Apresentado na [escolha de uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md), há três arquiteturas principais com duas variações, para um total de cinco cenários de implantação possíveis.</span><span class="sxs-lookup"><span data-stu-id="2b229-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="2b229-116">Um desses cenários será o ponto de partida para sua coleção de dados.</span><span class="sxs-lookup"><span data-stu-id="2b229-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="2b229-117">Os endereços IP, os nomes de servidor e os nomes de domínio são exemplos que coincidem com o certificado correspondente, o firewall e os diagramas DNS que detalham as informações necessárias para uma solução de planejamento completa.</span><span class="sxs-lookup"><span data-stu-id="2b229-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="2b229-118">Os diagramas e o preenchimento de seus valores obrigatórios de certificado, DNS e firewall são especialmente importantes em comunicações entre equipes, onde o gerenciamento da autoridade de certificação, a configuração de firewall e o DNS é gerenciado por equipes diferentes da equipe que planeja a implantação.</span><span class="sxs-lookup"><span data-stu-id="2b229-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="2b229-119">Os diagramas fornecem informações sobre os componentes necessários que podem ser usados para comunicar esses requisitos para colaboração entre equipes.</span><span class="sxs-lookup"><span data-stu-id="2b229-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="2b229-120">Os diagramas fornecidos são intencionalmente genéricos, mas permitem que a coleção de todos os dados pertinentes seja necessária para a comunicação de requisitos em um cenário de equipe cruzada, onde rede, firewall, criação e gerenciamento de certificados, servidor a implantação e o gerenciamento de servidor são tratados por grupos diferentes.</span><span class="sxs-lookup"><span data-stu-id="2b229-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="2b229-121">Ter os detalhes necessários para a configuração de rede, firewalls, portas e protocolos, certificados e servidores é inestimável quando a implantação do Lync Server está em andamento.</span><span class="sxs-lookup"><span data-stu-id="2b229-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="2b229-122">**Servidor de borda e pool de borda**</span><span class="sxs-lookup"><span data-stu-id="2b229-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="2b229-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="2b229-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="2b229-124">**Proxy reverso**</span><span class="sxs-lookup"><span data-stu-id="2b229-124">**Reverse Proxy**</span></span>

<span data-ttu-id="2b229-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="2b229-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="2b229-126">**Diretor ou pool de diretor**</span><span class="sxs-lookup"><span data-stu-id="2b229-126">**Director or Director pool**</span></span>

<span data-ttu-id="2b229-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="2b229-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

