---
title: 'Lync Server 2013: Instalando software opcional'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing optional software
ms:assetid: b95b3301-fa1e-4b96-9af4-05b43d39db8d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615032(v=OCS.15)
ms:contentKeyID: 51541509
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ce81d2005a9bbed5432f2c78f3d8df5507d6679
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="installing-optional-software-in-lync-server-2013"></a><span data-ttu-id="c6e3a-102">Instalando software opcional no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6e3a-102">Installing optional software in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6e3a-103">_**Última modificação do tópico:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c6e3a-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c6e3a-104">A ferramenta de planejamento do Microsoft Lync Server 2013 foi projetada para exportar para o Microsoft Excel e o Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-104">The Microsoft Lync Server 2013, Planning Tool is designed to export to Microsoft Excel and Microsoft Visio.</span></span> <span data-ttu-id="c6e3a-105">Embora esses aplicativos não sejam necessários para a operação da ferramenta de planejamento, eles adicionam um valor significativo à implantação e à documentação do seu design.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-105">While these applications are not required for the operation of the Planning Tool, they do add significant value to the deployment and documentation of your design.</span></span>

<div>

## <a name="optional-software"></a><span data-ttu-id="c6e3a-106">Software opcional</span><span class="sxs-lookup"><span data-stu-id="c6e3a-106">Optional Software</span></span>

<div>

## <a name="microsoft-excel"></a><span data-ttu-id="c6e3a-107">Microsoft Excel</span><span class="sxs-lookup"><span data-stu-id="c6e3a-107">Microsoft Excel</span></span>

<span data-ttu-id="c6e3a-108">Exportar seu design para o Microsoft Excel cria um relatório que exibe sete guias na planilha:</span><span class="sxs-lookup"><span data-stu-id="c6e3a-108">Exporting your design to Microsoft Excel creates a report that displays seven tabs in the spreadsheet:</span></span>

  - <span data-ttu-id="c6e3a-109">Resumo – exibe informações sobre a configuração do site, incluindo contagem de usuário, configurações de capacidade e informações de perfil do servidor.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-109">Summary – Displays information on site configuration, including user count, capacity settings, and server profile information.</span></span>

  - <span data-ttu-id="c6e3a-110">Perfil de hardware – Exibe um relatório sobre as configurações de hardware recomendadas para servidores especificados na topologia, incluindo CPU, memória, disco e interface de rede.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-110">Hardware Profile – Displays a report on the recommended hardware configurations for servers that are specified in the topology, including CPU, memory, disk, and network interface.</span></span> <span data-ttu-id="c6e3a-111">A quantidade e as especificações recomendadas para os componentes do servidor também estão incluídas.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-111">The quantity and recommended specifications for the server components are also included.</span></span> <span data-ttu-id="c6e3a-112">Além disso, cada servidor é definido pelo site para fornecer uma representação completa dos requisitos de servidor por site.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-112">In addition, each server is defined by site to provide a complete representation of server requirements by site.</span></span>

  - <span data-ttu-id="c6e3a-113">Requisitos de portas – exibe um relatório de todas as portas habilitadas e a associação ao balanceamento de carga do sistema de nomes de domínio (DNS LB) e aos balanceadores de carga de hardware (HLB).</span><span class="sxs-lookup"><span data-stu-id="c6e3a-113">Ports Requirements – Displays a report of all ports that are enabled, and the association to Domain Name System load balancing (DNS LB) and hardware load balancers (HLB).</span></span> <span data-ttu-id="c6e3a-114">Você deve usar este relatório para planejar suas configurações de firewall e DNS LB e HLB.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-114">You should use this report to plan your firewall and DNS LB and HLB configurations.</span></span>

  - <span data-ttu-id="c6e3a-115">Relatório de resumo – exibe o resumo geral das configurações necessárias para configurar sua rede de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-115">Summary Report – Displays the general summary of the settings that are required to set up your Edge Server network.</span></span>

  - <span data-ttu-id="c6e3a-116">Relatório de certificados – exibe o nome da entidade e os nomes alternativos da entidade que são necessários para os certificados necessários para obter os servidores de borda em execução.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-116">Certificates Report – Displays the subject name and subject alternate names that are required for the certificates needed to get the Edge Servers running.</span></span>

  - <span data-ttu-id="c6e3a-117">Relatório de firewall – exibe as portas de origem e de destino e endereços IP para interfaces externas e internas.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-117">Firewall Report – Displays the source and destination ports and IP addresses for both External and Internal interfaces.</span></span>

  - <span data-ttu-id="c6e3a-118">Relatório DNS – exibe o nome de domínio totalmente qualificado (FQDN) e os endereços IP/VIP necessários para cada entrada DNS que você criar.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-118">DNS Report – Displays the fully qualified domain name (FQDN) and IP/VIP addresses required for each DNS entry that you create.</span></span>

</div>

<div>

## <a name="microsoft-visio"></a><span data-ttu-id="c6e3a-119">Microsoft Visio</span><span class="sxs-lookup"><span data-stu-id="c6e3a-119">Microsoft Visio</span></span>

<span data-ttu-id="c6e3a-p104">Exportar seu design para o Microsoft Visio cria um diagrama para ser usado com seus objetivos de documentação de sua topologia e infraestrutura configuradas. O diagrama importado pode ser editado e reorganizado a fim de atender às suas necessidades de documentação. O diagrama típico do Visio incluirá:</span><span class="sxs-lookup"><span data-stu-id="c6e3a-p104">Exporting your design to Microsoft Visio creates a diagram for use in your documentation purposes of your configured topology and infrastructure. The imported diagram can be edited and rearranged to meet your documentation needs. The typical Visio diagram will include:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c6e3a-123">Se seu design for grande o suficiente para exigir mais de três servidores front-end, uma página adicional será criada para o pool de front-ends, servidores front-end, o computador que executa o SQL Server, endereços IP e FQDNs.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-123">If your design is large enough to require more than three Front End Servers, an additional page will be created for the Front End pool, Front End Servers, the computer running SQL Server, IP addresses, and FQDNs.</span></span>



</div>

  - <span data-ttu-id="c6e3a-124">Topologia global – diagrama dos sites do Lync Server 2013 configurados.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-124">Global Topology – Diagram of configured Lync Server 2013 sites.</span></span>

  - <span data-ttu-id="c6e3a-125">Guia nome do site – exibe a topologia de configuração do site com o servidor de borda, o firewall, a PSTN (rede telefônica pública comutada) com gateways e a implantação de servidor interno.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-125">Site Name tab – Displays the site configuration topology with Edge Server, firewall, public switched telephone network (PSTN) with gateways, and the internal server deployment.</span></span> <span data-ttu-id="c6e3a-126">A implantação interna consiste em servidores e pools configurados, incluindo o pool de front-ends, servidores baseados em SQL Server, serviços de domínio do Active Directory, diretores, servidores de Unificação de mensagens (UM) do Exchange, servidores de caixa de correio do Exchange, servidores do Office Web Apps Servidores de mediação e servidores de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-126">Internal deployment consists of configured servers and pools, including the Front End pools, SQL Server-based servers, Active Directory Domain Services, Directors, Exchange Unified Messaging (UM) servers, Exchange Mailbox Servers, Office Web Apps Servers, Mediation Servers, and Persistent Chat Servers.</span></span>

  - <span data-ttu-id="c6e3a-127">Diagrama de rede de borda – diagrama detalhando a configuração do servidor de borda com endereços IP e FQDNs associados.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-127">Edge Network Diagram – Diagram detailing the Edge Server configuration with associated IP addresses and FQDNs.</span></span> <span data-ttu-id="c6e3a-128">Balanceamento de carga de DNS e balanceadores de carga de hardware também estão incluídos.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-128">DNS load balancing and hardware load balancers are also included.</span></span> <span data-ttu-id="c6e3a-129">Além disso, os diretores e o servidor front-end ou o pool de front-ends são exibidos, com o DNS LB ou o HLB associado e o endereço IP atribuído (a ferramenta de planejamento suporta endereços IPv4 e IPv6) e FQDN.</span><span class="sxs-lookup"><span data-stu-id="c6e3a-129">Additionally, Directors and the Front End Server or Front End pool are displayed, with associated DNS LB or HLB and the assigned IP address (the Planning Tool supports both IPv4 and IPv6 addresses) and FQDN.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c6e3a-130">Confira também</span><span class="sxs-lookup"><span data-stu-id="c6e3a-130">See Also</span></span>


[<span data-ttu-id="c6e3a-131">Instalando a ferramenta de planejamento no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6e3a-131">Installing the Planning Tool in Lync Server 2013</span></span>](lync-server-2013-installing-the-planning-tool.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

