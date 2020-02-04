---
title: 'Lync Server 2013: Editando o design'
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
ms.openlocfilehash: dfce3bc4242140364005a9a981282ecb90a42d3b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-design-in-lync-server-2013"></a><span data-ttu-id="9da7f-102">Editando o design no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da7f-102">Editing the design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da7f-103">_**Tópico da última modificação:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="9da7f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="9da7f-p101">Após concluir as perguntas iniciais da entrevista, você poderá editar o nome de domínio totalmente qualificado (FQDN) e o endereço IP do site. Para isso, na página **Topologia Global**, clique duas vezes no site que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="9da7f-p101">After completing the initial interview questions, you can edit the fully qualified domain name (FQDN) and IP addresses for the site. To do this, on the **Global Topology** page, double-click the site that you want to edit.</span></span>

<span data-ttu-id="9da7f-106">A ferramenta de planejamento exibe a topologia de site para o site selecionado.</span><span class="sxs-lookup"><span data-stu-id="9da7f-106">The Planning Tool displays the site topology for the selected site.</span></span> <span data-ttu-id="9da7f-107">Na parte inferior da página do site, existem quatro guias:</span><span class="sxs-lookup"><span data-stu-id="9da7f-107">At the bottom of the site page are four tabs:</span></span>

<span data-ttu-id="9da7f-108">![Topologia do site da ferramenta de planejamento](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Topologia do site da ferramenta de planejamento")</span><span class="sxs-lookup"><span data-stu-id="9da7f-108">![Planning Tool Site Topology](images/Gg558608.e6189c20-360a-42bd-ba90-11bdb5b7551b(OCS.15).jpg "Planning Tool Site Topology")</span></span>

  - <span data-ttu-id="9da7f-109">Topologia do site - A página exibida atualmente com uma visão geral visual da topologia, conforme recomendado.</span><span class="sxs-lookup"><span data-stu-id="9da7f-109">Site Topology – The currently displayed page with a visual overview of the topology as recommended.</span></span>

  - <span data-ttu-id="9da7f-110">Diagrama de rede Edge – a página de diagrama de rede de borda é onde o designer faz a maior parte do trabalho na ferramenta de planejamento.</span><span class="sxs-lookup"><span data-stu-id="9da7f-110">Edge Network Diagram – The Edge Network Diagram page is where the designer does most of the work in the Planning Tool.</span></span> <span data-ttu-id="9da7f-111">O diagrama exibe a configuração de rede para uma topologia do Lync Server 2013 recomendada, com entradas editáveis para endereços IP e FQDNs para servidores, pool e balanceadores de carga de DNS (sistema de nome de domínio) e de hardware.</span><span class="sxs-lookup"><span data-stu-id="9da7f-111">The diagram displays the network configuration for a recommended Lync Server 2013 topology, with editable entries for IP addresses and FQDNs for servers, pool, and both hardware and Domain Name System (DNS) load balancers.</span></span>

  - <span data-ttu-id="9da7f-112">Relatório de administração de borda - O Relatório de administração de borda contém um total de quatro relatórios:</span><span class="sxs-lookup"><span data-stu-id="9da7f-112">Edge Admin Report – The Edge Admin Report contains a total of four reports:</span></span>
    
    <span data-ttu-id="9da7f-113">![Página de relatório de administração de borda](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Página de relatório de administração de borda")</span><span class="sxs-lookup"><span data-stu-id="9da7f-113">![Edge Admin Report page](images/Gg558608.0019cc5e-af39-4cb9-82ce-58f6388242ff(OCS.15).jpg "Edge Admin Report page")</span></span>  
    
      - <span data-ttu-id="9da7f-p104">Relatório resumido - Um relatório geral de configurações para a configuração da Rede de borda. Se você editar os valores na página \*\*Diagrama da rede de borda \*\* para a topologia TCP/IP e os valores do FQDN que irão ser usados na implantação atual, tais endereços e nomes serão representados aqui. De outro modo, o texto padrão aparecerá.</span><span class="sxs-lookup"><span data-stu-id="9da7f-p104">Summary Report – A general report of settings for the Edge network configuration. If you edit the values on the **Edge Network Diagram** page to the topology TCP/IP and FQDN values of that will be used in the actual deployment, those addresses and names will be represented here. Otherwise, the default text will appear.</span></span>
    
      - <span data-ttu-id="9da7f-117">Relatório de certificado - O relatório de certificado listará o nome da entidade ou os nomes alternativos da entidade dos certificados que são exigidos para a topologia.</span><span class="sxs-lookup"><span data-stu-id="9da7f-117">Certificate Report – The certificate report will list the subject name and subject alternative names for the certificates that are required for the topology.</span></span>
    
      - <span data-ttu-id="9da7f-p105">Relatório de firewall - O relatório de firewall lista as informações necessárias para configurar os firewalls de perímetro na infraestrutura. Isso inclui os endereços IP (seja de valores padrão ou editados), função do servidor, IP e porta de origem, IP e porta de destino, protocolo de transporte, protocolo de aplicativo e notas relevantes.</span><span class="sxs-lookup"><span data-stu-id="9da7f-p105">Firewall Report – The firewall report lists information necessary to configure perimeter firewalls in the infrastructure. This includes the IP addresses (either the default or edited values), server role, source IP and port, destination IP and port, transport protocol, application protocol, and relevant notes.</span></span>
    
      - <span data-ttu-id="9da7f-p106">Relatório de DNS - O relatório de DNS lista as informações relevantes para as entradas de DNS que você deve criar. Estão incluídos o tipo de registro, o FQDN, o endereço IP e os comentários necessários para a operação apropriada.</span><span class="sxs-lookup"><span data-stu-id="9da7f-p106">DNS Report – The DNS Report lists relevant information for the DNS entries that you must create. The record type, FQDN, IP address, and comments necessary for the proper operation are included.</span></span>

  - <span data-ttu-id="9da7f-p107">Resumo do site - O resumo do site apresenta uma visão geral das seleções que foram feitas ao responder às perguntas da entrevista inicial ou ao incluir valores em **Criar Sites**. A informação de capacidade também é apresentada.</span><span class="sxs-lookup"><span data-stu-id="9da7f-p107">Site Summary – The site summary presents an overview of the selections that you made by either answering the initial interview questions or filling in the values in **Design Sites**. Capacity information is also presented.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="9da7f-124">As informações na página do Resumo do site são personalizadas para cada design e podem não conter todas as seções ou informações detalhadas aqui.</span><span class="sxs-lookup"><span data-stu-id="9da7f-124">The information on the Site Summary page is customized for each design and may not contain all sections or information detailed here.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="9da7f-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="9da7f-125">See Also</span></span>


[<span data-ttu-id="9da7f-126">Editando o diagrama de configuração de rede no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9da7f-126">Editing the network configuration diagram in Lync Server 2013</span></span>](lync-server-2013-editing-the-network-configuration-diagram.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

