---
title: 'Lync Server 2013: editando o design'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Editing the design
ms:assetid: 08f639ba-0e5f-4ae7-9191-c3d96c25b169
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558608(v=OCS.15)
ms:contentKeyID: 51541445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb643fdbcee35a8b24533bed17d003427a8a0ea8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="affa2-102">Editando o design no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="affa2-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="affa2-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="affa2-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="affa2-104">Após concluir as perguntas de entrevista inicial, você pode editar o FQDN (nome de domínio totalmente qualificado) e os endereços IP para o site.</span><span class="sxs-lookup"><span data-stu-id="affa2-104">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site.</span></span> <span data-ttu-id="affa2-105">Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="affa2-105">To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="affa2-106">A ferramenta de planejamento exibe a topologia do site para o site selecionado.</span><span class="sxs-lookup"><span data-stu-id="affa2-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="affa2-107">Na parte inferior da página do site, existem quatro guias:</span><span class="sxs-lookup"><span data-stu-id="affa2-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="affa2-108">![Topologia do site da ferramenta de planejamento](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia do site da ferramenta de planejamento")</span><span class="sxs-lookup"><span data-stu-id="affa2-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="affa2-109">Topologia do site – A página exibida atualmente com uma visão geral visual da topologia, conforme recomendado.</span><span class="sxs-lookup"><span data-stu-id="affa2-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="affa2-110">Diagrama de rede de borda – a página do diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="affa2-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="affa2-111">O diagrama exibe a configuração de rede para uma topologia recomendada do Lync Server 2013, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga do DNS (sistema de nomes de domínio) e hardware.</span><span class="sxs-lookup"><span data-stu-id="affa2-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="affa2-112">Relatório de administração de borda – O Relatório de administração de borda contém um total de quatro relatórios:</span><span class="sxs-lookup"><span data-stu-id="affa2-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="affa2-113">![Página de relatório de administração de borda](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página de relatório de administração de borda")</span><span class="sxs-lookup"><span data-stu-id="affa2-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="affa2-114">Relatório resumido – Um relatório geral de configurações para a Rede de borda.</span><span class="sxs-lookup"><span data-stu-id="affa2-114">Summary Report – A general report of settings for the Edge network configuration.</span></span> <span data-ttu-id="affa2-115">Se você editar os valores na página do **diagrama de rede de borda** para os valores de topologia TCP/IP e FQDN do que serão usados na implantação real, esses endereços e nomes serão representados aqui.</span><span class="sxs-lookup"><span data-stu-id="affa2-115">If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here.</span></span> <span data-ttu-id="affa2-116">Caso contrário, o texto padrão será exibido.</span><span class="sxs-lookup"><span data-stu-id="affa2-116">Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="affa2-117">Relatório de certificado – O relatório de certificado listará o nome da entidade ou os nomes alternativos da entidade dos certificados que são exigidos para a topologia.</span><span class="sxs-lookup"><span data-stu-id="affa2-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="affa2-118">Relatório de firewall – O relatório de firewall lista as informações necessárias para configurar os firewalls de perímetro na infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="affa2-118">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure.</span></span> <span data-ttu-id="affa2-119">Isso inclui os endereços IP (os valores padrão ou editados), função de servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e anotações relevantes.</span><span class="sxs-lookup"><span data-stu-id="affa2-119">This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="affa2-120">Relatório DNS – o relatório DNS lista informações relevantes para as entradas de DNS que devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="affa2-120">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create.</span></span> <span data-ttu-id="affa2-121">Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.</span><span class="sxs-lookup"><span data-stu-id="affa2-121">The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="affa2-122">Resumo do site – o resumo do site apresenta uma visão geral das seleções que você fez respondendo às perguntas de entrevista inicial ou preenchendo os valores em **sites de design**.</span><span class="sxs-lookup"><span data-stu-id="affa2-122">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**.</span></span> <span data-ttu-id="affa2-123">As informações sobre capacidade também são apresentadas.</span><span class="sxs-lookup"><span data-stu-id="affa2-123">Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="affa2-124">As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.</span><span class="sxs-lookup"><span data-stu-id="affa2-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="affa2-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="affa2-125">See Also</span></span>


[<span data-ttu-id="affa2-126">Editando o diagrama de configuração de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="affa2-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

