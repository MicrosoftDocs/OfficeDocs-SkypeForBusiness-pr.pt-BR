---
title: 'Lync Server 2013: Coleta de dados'
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
ms.openlocfilehash: e7c3d066aff26e06c003a31a58b4771d67f54f34
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="data-collection-in-lync-server-2013"></a><span data-ttu-id="cbea3-102">Coleta de dados no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cbea3-102">Data collection in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbea3-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="cbea3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="cbea3-104">No software de comunicação do Microsoft Lync Server 2013, você pode executar o Microsoft Lync Server 2013, ferramenta de planejamento sem documentar os endereços IP existentes e propostos e os nomes de domínio totalmente qualificados do servidor de borda (FQDNs), mas é muito mais difícil de fazer Portanto, sem causar erros de configuração.</span><span class="sxs-lookup"><span data-stu-id="cbea3-104">In Microsoft Lync Server 2013 communications software, you can run the Microsoft Lync Server 2013, Planning Tool without documenting your existing and proposed IP addresses and Edge Server fully qualified domain names (FQDNs), but it is significantly harder to do so without causing configuration errors.</span></span> <span data-ttu-id="cbea3-105">Por exemplo, se a coexistência for necessária por um período de tempo, um erro comum será reutilizar FQDNs de uma implantação de borda existente para a implantação de borda do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cbea3-105">For example, if coexistence is required for a period of time, a common mistake is to reuse FQDNs from an existing Edge deployment for your Lync Server 2013 Edge deployment.</span></span> <span data-ttu-id="cbea3-106">Ao ter os endereços IP existentes e propostos e FQDNs gravados em uma planilha, tabela ou outro formulário Visual, você ajuda a evitar problemas de instalação durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="cbea3-106">By having the existing and proposed IP addresses and FQDNs written down in a spreadsheet, table, or other visual form, you help prevent setup problems during installation.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="cbea3-107">Se você usou versões anteriores da ferramenta de planejamento, talvez tenha usado a ferramenta para criar sua topologia e o documento de topologia exportado para uso no construtor de topologias para publicar sua topologia.</span><span class="sxs-lookup"><span data-stu-id="cbea3-107">If you have used previous versions of the Planning Tool, you may have used the tool to create your topology and the exported the topology document for use in Topology Builder to publish your topology.</span></span> <span data-ttu-id="cbea3-108">A capacidade de exportar a topologia foi removida da ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="cbea3-108">The ability to export the topology was removed from Planning Tool.</span></span> <span data-ttu-id="cbea3-109">Usar uma versão anterior da ferramenta de planejamento para criar um documento de topologia para o Lync Server 2013 é altamente desencorajado e produzirá resultados inesperados.</span><span class="sxs-lookup"><span data-stu-id="cbea3-109">Using a previous version of the Planning Tool to create a topology document for Lync Server 2013 is strongly discouraged, and will produce unexpected results.</span></span>



</div>

<span data-ttu-id="cbea3-110">Portanto, a abordagem recomendada é usar o modelo de coleta de dados a seguir, que corresponde à sua topologia de borda, para coletar os vários endereços IP e FQDN que você precisará inserir na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="cbea3-110">Therefore, the recommended approach is to use the following data collection template, which corresponds to your Edge topology, to gather the various FQDN and IP addresses that you will need to enter into the Planning Tool.</span></span> <span data-ttu-id="cbea3-111">Ao documentar a configuração atual e proposta, você pode colocar os valores no contexto apropriado para o seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="cbea3-111">By documenting the current and proposed configuration, you can put the values in the proper context for your production environment.</span></span> <span data-ttu-id="cbea3-112">E você é obrigado a pensar sobre como você configurará a coexistência e recursos como URLs simples, compartilhamentos de arquivos e balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="cbea3-112">And, you are forced to think about how you will configure coexistence and features such as simple URLs, file shares, and load balancing.</span></span>

<span data-ttu-id="cbea3-113">Para implantar com êxito o Microsoft Lync Server 2013, você precisa entender a interação e a confiança dos componentes individuais.</span><span class="sxs-lookup"><span data-stu-id="cbea3-113">To successfully deploy Microsoft Lync Server 2013, you need to understand the interaction of and reliance on the individual components.</span></span> <span data-ttu-id="cbea3-114">Coletando dados da infraestrutura de rede e do servidor existentes e aplicando as diretrizes de planejamento nessas seções, você pode integrar componentes do Lync Server 2013 Edge Server à sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="cbea3-114">By collecting data from your existing network and server infrastructure, and applying the planning guidance in these sections, you can integrate Lync Server 2013 Edge Server components into your infrastructure.</span></span>

<span data-ttu-id="cbea3-115">Introduzidas na [escolha de uma topologia no Lync Server 2013](lync-server-2013-choosing-a-topology.md), há três arquiteturas principais com duas variações, para um total de cinco possíveis cenários de implantação.</span><span class="sxs-lookup"><span data-stu-id="cbea3-115">Introduced in [Choosing a topology in Lync Server 2013](lync-server-2013-choosing-a-topology.md), there are three main architectures with two variations, for a total of five possible deployment scenarios.</span></span> <span data-ttu-id="cbea3-116">Um desses cenários será o ponto de partida para sua coleta de dados.</span><span class="sxs-lookup"><span data-stu-id="cbea3-116">One of these scenarios will be the starting point for your data collection.</span></span> <span data-ttu-id="cbea3-117">Os endereços IP, nomes de servidor e nomes de domínio são exemplos que coincidem com o certificado, o firewall e os diagramas DNS correspondentes que detalham as informações necessárias para uma solução de planejamento completa.</span><span class="sxs-lookup"><span data-stu-id="cbea3-117">The IP addresses, server names, and domain names are examples that coincide with the matching certificate, firewall, and DNS diagrams that detail the information required for a complete planning solution.</span></span> <span data-ttu-id="cbea3-118">Os diagramas e o preenchimento dos seus valores obrigatórios de certificado, DNS e firewall são especialmente importantes em comunicações entre equipes onde o gerenciamento da autoridade de certificação, a configuração de firewall e o DNS são gerenciados por equipes diferentes da equipe que planeja a implantação.</span><span class="sxs-lookup"><span data-stu-id="cbea3-118">The diagrams and filling in your required certificate, DNS and firewall values is especially important in cross-team communications where the management of the certification authority, firewall configuration and DNS is managed by teams other than the team that plans the deployment.</span></span> <span data-ttu-id="cbea3-119">Os diagramas fornecem informações sobre os componentes obrigatórios que podem ser usados para comunicar esses requisitos de colaboração entre a equipe.</span><span class="sxs-lookup"><span data-stu-id="cbea3-119">The diagrams provide information on required components that can be used to communicate these requirements for cross-team collaboration.</span></span>

<span data-ttu-id="cbea3-120">Os diagramas fornecidos são intencionalmente genéricos, mas permitem a coleta de todos os dados pertinentes que seriam necessários para a comunicação de requisitos em um cenário de equipe cruzado em que rede, firewall, criação e gerenciamento de certificados, servidor a implantação e o gerenciamento de servidor são manipulados por grupos diferentes.</span><span class="sxs-lookup"><span data-stu-id="cbea3-120">The provided diagrams are intentionally generic, but allow for the collection of all pertinent data that would be necessary for communication of requirements in a cross team scenario where networking, firewall, certificate creation and management, server deployment, and server management are handled by different groups.</span></span> <span data-ttu-id="cbea3-121">Ter os detalhes necessários para a configuração de redes, firewalls, portas e protocolos, certificados e servidores é inestimável quando a implantação do Lync Server está em andamento.</span><span class="sxs-lookup"><span data-stu-id="cbea3-121">Having the required details for configuration of networking, firewalls, ports and protocols, certificates, and servers is invaluable when the deployment of Lync Server is underway.</span></span>

<span data-ttu-id="cbea3-122">**Servidor de borda e o pool de bordas**</span><span class="sxs-lookup"><span data-stu-id="cbea3-122">**Edge Server and Edge pool**</span></span>

<span data-ttu-id="cbea3-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span><span class="sxs-lookup"><span data-stu-id="cbea3-123">![7624717a-ce99-4ae8-a929-2c4d74a2e47d](images/Gg399008.7624717a-ce99-4ae8-a929-2c4d74a2e47d(OCS.15).jpg "7624717a-ce99-4ae8-a929-2c4d74a2e47d")</span></span>

<span data-ttu-id="cbea3-124">**Proxy reverso**</span><span class="sxs-lookup"><span data-stu-id="cbea3-124">**Reverse Proxy**</span></span>

<span data-ttu-id="cbea3-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span><span class="sxs-lookup"><span data-stu-id="cbea3-125">![cf63fc50-2d11-4334-afc8-2d664ba1b6bb](images/Gg399008.cf63fc50-2d11-4334-afc8-2d664ba1b6bb(OCS.15).jpg "cf63fc50-2d11-4334-afc8-2d664ba1b6bb")</span></span>

<span data-ttu-id="cbea3-126">**Pool de directors ou diretor**</span><span class="sxs-lookup"><span data-stu-id="cbea3-126">**Director or Director pool**</span></span>

<span data-ttu-id="cbea3-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span><span class="sxs-lookup"><span data-stu-id="cbea3-127">![56ba29ff-1309-4d5d-bf5c-35372169e947](images/Gg399008.56ba29ff-1309-4d5d-bf5c-35372169e947(OCS.15).jpg "56ba29ff-1309-4d5d-bf5c-35372169e947")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

