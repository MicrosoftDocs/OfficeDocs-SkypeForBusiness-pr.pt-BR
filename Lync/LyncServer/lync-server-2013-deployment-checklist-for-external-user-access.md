---
title: 'Lync Server 2013: Llista de verificação de implantação para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for external user access
ms:assetid: 3f55f502-88a0-4315-8783-45a32a0b78ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425910(v=OCS.15)
ms:contentKeyID: 48183947
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c8831e8bd94040095fabd9fb335113b62b5287b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829518"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="4bcb9-102">Llista de verificação de implantação para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bcb9-102">Deployment checklist for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bcb9-103">_**Tópico da última modificação:** 2014-02-04_</span><span class="sxs-lookup"><span data-stu-id="4bcb9-103">_**Topic Last Modified:** 2014-02-04_</span></span>

<span data-ttu-id="4bcb9-104">Antes de implantar a sua rede de perímetro e implementar o suporte para usuários externos, você já deve ter implantado seus servidores internos do Microsoft Lync Server 2013, incluindo um pool de front-ends ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-104">Before you deploy your perimeter network and implement support for external users, you must already have deployed your Microsoft Lync Server 2013 internal servers, including a Front End pool or a Standard Edition server.</span></span> <span data-ttu-id="4bcb9-105">Se você planeja implantar os diretores opcionais na sua rede interna, também deve implantá-los antes de implantar servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-105">If you plan to deploy the optional Directors in your internal network, you should also deploy them prior to deploying Edge Servers.</span></span> <span data-ttu-id="4bcb9-106">Para obter detalhes sobre o processo de implantação do diretor, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-106">For details about the Director deployment process, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md) in the Planning documentation.</span></span>

<span data-ttu-id="4bcb9-107">O Microsoft Lync Server 2013 inclui ferramentas para facilitar o planejamento e a implantação de servidores internos e de servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-107">Microsoft Lync Server 2013 includes tools to facilitate planning and deployment of both internal servers and Edge Servers.</span></span> <span data-ttu-id="4bcb9-108">Após a conclusão da topologia, publique a definição de topologia resultante em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-108">After the topology is completed, publish the resulting topology definition to your production environment.</span></span> <span data-ttu-id="4bcb9-109">Para fazer isso, você deve ser membro do grupo **Domain admins** e do grupo **RTCUniversalServerAdmins** .</span><span class="sxs-lookup"><span data-stu-id="4bcb9-109">To do this, you must be a member of the **Domain Admins** group and the **RTCUniversalServerAdmins** group.</span></span>

  - <span data-ttu-id="4bcb9-110">**Ferramenta de planejamento**   o Office Communications Server 2007 R2 incluía uma ferramenta de planejamento e uma ferramenta de planejamento de borda que você pode usar para ajudar a orientar o design da topologia.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-110">**Planning Tool**   Office Communications Server 2007 R2 included a Planning Tool and an Edge Planning Tool that you could use to help guide topology design.</span></span> <span data-ttu-id="4bcb9-111">No Lync Server 2010, essas duas ferramentas foram combinadas em uma única ferramenta de planejamento que tem recursos e funcionalidades adicionais, como coletar contagem de usuários, requisitos de voz, tipos de acesso de usuário externo e opções de Federação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-111">In Lync Server 2010, these two tools were combined into a single Planning Tool that has additional features and functionality, such as collecting planned user count, voice requirements, external user access types, and federation options.</span></span> <span data-ttu-id="4bcb9-112">Além disso, você pode planejar os parâmetros de rede de sua infraestrutura, como endereços IP, tipos de balanceador de carga e outras considerações de rede do perímetro.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-112">Additionally, you can plan your infrastructure’s network parameters, such as IP addresses, load balancer types and other perimeter network considerations.</span></span>

  - <span data-ttu-id="4bcb9-113">**Construtor Topology Builder**   o construtor de topologias do Lync Server 2013 ajuda você a definir sua topologia e seus componentes.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-113">**Topology Builder**   Lync Server 2013 Topology Builder helps you define your topology and components.</span></span> <span data-ttu-id="4bcb9-114">O construtor de topologias é essencial para implantar servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-114">Topology Builder is essential to deploying servers running Lync Server 2013.</span></span> <span data-ttu-id="4bcb9-115">O construtor de topologias publica os resultados em um repositório de gerenciamento central que é usado para configurar todos os servidores que executam o Lync Server 2013 em sua organização.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-115">Topology Builder publishes the results to a Central Management store that is used to configure all of the servers running Lync Server 2013 in your organization.</span></span> <span data-ttu-id="4bcb9-116">Não é possível instalar o Lync Server 2013 em servidores sem usar o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-116">You cannot install Lync Server 2013 on servers without using Topology Builder.</span></span>

<span data-ttu-id="4bcb9-117">Se você tiver projetado a topologia de borda durante o processo de planejamento, incluindo a execução do construtor de topologias para definir sua topologia de borda, você pode usar esses resultados para iniciar a implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-117">If you designed your edge topology during your planning process, including running Topology Builder to define your edge topology, you can use those results to start your Edge Server deployment.</span></span> <span data-ttu-id="4bcb9-118">Se você não concluiu a criação da sua topologia de borda anteriormente ou deseja alterar as informações especificadas anteriormente, deverá concluir a execução do construtor de topologias antes de prosseguir com outras etapas de implantação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-118">If you did not finish building your edge topology earlier or you want to change the information you previously specified, you must finish running Topology Builder before proceeding with other deployment steps.</span></span> <span data-ttu-id="4bcb9-119">Para obter detalhes sobre como criar sua topologia, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4bcb9-119">For details about how to build your topology, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<span data-ttu-id="4bcb9-120">Para obter detalhes sobre a ferramenta de planejamento e o construtor de topologias, consulte [iniciar o processo de planejamento do Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) na documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-120">For details about the Planning Tool and Topology Builder, see [Beginning the planning process for Lync Server 2013](lync-server-2013-beginning-the-planning-process.md) in the Planning documentation.</span></span>

<span data-ttu-id="4bcb9-121">A tabela a seguir fornece uma visão geral do processo de implantação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-121">The following table provides an overview of the Edge Server deployment process.</span></span> <span data-ttu-id="4bcb9-122">Para revisar as decisões de planejamento que devem ser tomadas antes de implantar o acesso de usuários externos, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="4bcb9-122">To review the planning decisions that must be made before deploying external user access, see [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4bcb9-123">As informações na tabela a seguir se concentram em uma nova implantação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-123">The information in the following table focuses on a new deployment.</span></span> <span data-ttu-id="4bcb9-124">Se você implantou servidores de borda em um ambiente do Lync Server 2010, do Office Communications Server 2007 R2 ou do Office Communications Server 2007, consulte a <A href="migration.md">migração</A> para obter detalhes sobre a migração para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-124">If you have deployed Edge Servers in a Lync Server 2010, Office Communications Server 2007 R2 or Office Communications Server 2007 environment, see the <A href="migration.md">Migration</A> for details about migrating to Lync Server 2013.</span></span> <span data-ttu-id="4bcb9-125">Não há suporte para a migração de nenhuma versão anterior ao Office Communications Server 2007 R2, incluindo o Office Communications Server 2007, o Live Communications Server 2005 e o Live Communications Server 2003.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-125">Migration is not supported from any version prior to Office Communications Server 2007 R2, including Office Communications Server 2007, Live Communications Server 2005, and Live Communications Server 2003.</span></span>



</div>

<span data-ttu-id="4bcb9-126">Para melhorar o desempenho e a segurança do servidor de borda e facilitar a implantação, aplique as seguintes práticas recomendadas ao implantar seus servidores de rede de perímetro e de borda:</span><span class="sxs-lookup"><span data-stu-id="4bcb9-126">To enhance Edge Server performance and security, and to facilitate deployment, apply the following best practices when you deploy your perimeter network and Edge Servers:</span></span>

  - <span data-ttu-id="4bcb9-127">Implante os servidores de borda somente depois de testar e verificar a operação do Lync Server 2013 dentro da sua organização.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-127">Deploy Edge Servers only after you have tested and verified operation of Lync Server 2013 inside your organization.</span></span>

  - <span data-ttu-id="4bcb9-128">Recomendamos que você implante os servidores de borda em um grupo de trabalho em vez de um domínio.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-128">We recommend that you deploy Edge Servers in a workgroup rather than a domain.</span></span> <span data-ttu-id="4bcb9-129">Isso simplifica a instalação e mantém os serviços de domínio Active Directory (AD DS) fora da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-129">Doing so simplifies installation and keeps Active Directory Domain Services (AD DS) out of the perimeter network.</span></span> <span data-ttu-id="4bcb9-130">Localizar o AD DS na rede de perímetro pode apresentar um risco de segurança significativo.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-130">Locating AD DS in the perimeter network can present a significant security risk.</span></span>

  - <span data-ttu-id="4bcb9-131">Ingressar em um servidor de borda em um domínio localizado inteiramente na rede de perímetro é compatível, mas não é recomendado.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-131">Joining an Edge Server to a domain located entirely in the perimeter network is supported but not recommended.</span></span> <span data-ttu-id="4bcb9-132">Um servidor de borda como parte do domínio interno viola os limites de rede confiáveis, em que a Internet é menos confiável, a rede de perímetro é mais confiável do que a Internet, e a rede interna é mais confiável.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-132">An Edge Server as part of the internal domain violates trusted network boundaries, where the Internet is least trusted, perimeter network is more trusted than the Internet, and the internal network is most trusted.</span></span> <span data-ttu-id="4bcb9-133">Um servidor de borda como membro do domínio é automaticamente parte da rede mais confiável, mas reside em uma rede menos confiável (o perímetro).</span><span class="sxs-lookup"><span data-stu-id="4bcb9-133">An Edge server as a member of the domain is automatically a part of the most trusted network, but resides in a less trusted network (the perimeter).</span></span>

<div>

## <a name="deployment-process-for-edge-servers"></a><span data-ttu-id="4bcb9-134">Processo de implantação para servidores de borda</span><span class="sxs-lookup"><span data-stu-id="4bcb9-134">Deployment Process for Edge Servers</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4bcb9-135">Fase</span><span class="sxs-lookup"><span data-stu-id="4bcb9-135">Phase</span></span></th>
<th><span data-ttu-id="4bcb9-136">Etapas</span><span class="sxs-lookup"><span data-stu-id="4bcb9-136">Steps</span></span></th>
<th><span data-ttu-id="4bcb9-137">Permissões</span><span class="sxs-lookup"><span data-stu-id="4bcb9-137">Permissions</span></span></th>
<th><span data-ttu-id="4bcb9-138">Documentação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-138">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4bcb9-139">Crie a topologia de borda apropriada e determine os componentes apropriados.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-139">Create the appropriate edge topology and determine the appropriate components.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bcb9-140">Execute o construtor de topologias para definir as configurações do servidor de borda e criar e publicar a topologia e, em seguida, use o Shell de gerenciamento do Lync Server para exportar o arquivo de configuração de topologia.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-140">Run Topology Builder to configure Edge Server settings and create and publish the topology, and then use Lync Server Management Shell to export the topology configuration file.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bcb9-141">Grupo <strong>Administradores de domínio</strong> e grupo <strong>RTCUniversalServerAdmins</strong> ou <strong>CsAdmins</strong></span><span class="sxs-lookup"><span data-stu-id="4bcb9-141"><strong>Domain Admins</strong> group and <strong>RTCUniversalServerAdmins</strong> or <strong>CsAdmins</strong> group</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="4bcb9-142">Você pode definir uma topologia usando uma conta que seja membro do grupo usuários local, mas publicar uma topologia requer uma conta que seja membro do grupo <STRONG>Domain admins</STRONG> e do grupo <STRONG>RTCUniversalServerAdmins</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="4bcb9-142">You can define a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the <STRONG>Domain Admins</STRONG> group and the <STRONG>RTCUniversalServerAdmins</STRONG> group.</span></span>


</div></td>
<td><p><span data-ttu-id="4bcb9-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de Edge e Director no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-143"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bcb9-144">Prepare-se para a instalação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-144">Prepare for setup.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4bcb9-145">Certifique-se de que os pré-requisitos do sistema sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-145">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-146">Configurar endereços IP (IPv4 e IPv6, se usados) para interfaces de rede internas e públicas voltadas para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-146">Configure IP addresses (IPv4 and IPv6, if used) for both internal and public facing network interfaces on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-147">Configurar registros DNS internos e externos (host A e AAAA para IPv4 e IPv6), incluindo a configuração do sufixo DNS no computador a ser implantado como um servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-147">Configure internal and external DNS records (host A and AAAA for IPv4 and IPv6), including configuring the DNS suffix on the computer to be deployed as an Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-148">Adicionais Criar e instalar certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-148">(Optional) Create and install public certificates.</span></span> <span data-ttu-id="4bcb9-149">O tempo necessário para obter certificados depende de qual a autoridade de certificação (CA) emite o certificado.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-149">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="4bcb9-150">Se você não executar esta etapa neste ponto, deverá fazê-lo durante a instalação do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-150">If you do not perform this step at this point, you must do it during Edge Server installation.</span></span> <span data-ttu-id="4bcb9-151">Os serviços de servidor de borda não podem ser iniciados até que os certificados sejam obtidos e instalados.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-151">The Edge Server services cannot be started until certificates are obtained and installed.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-152">Provisionar o suporte para conectividade de IM pública, se sua implantação for dar suporte a comunicações com o Windows Live, AOL ou Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4bcb9-152">Provision support for public IM connectivity, if your deployment is to support communications with Windows Live, AOL, or Yahoo!</span></span> <span data-ttu-id="4bcb9-153">Eles.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-153">users.</span></span></p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4bcb9-154">A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-154">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="4bcb9-155">Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4bcb9-155">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="4bcb9-156">Messenger até a data de encerramento do serviço.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-156">Messenger until the service shut down date.</span></span> <span data-ttu-id="4bcb9-157">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4bcb9-157">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="4bcb9-158">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-158">has been announced.</span></span> <span data-ttu-id="4bcb9-159">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-159">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
> <LI>
> <P><span data-ttu-id="4bcb9-160">O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo!</span><span class="sxs-lookup"><span data-stu-id="4bcb9-160">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="4bcb9-161">Spam.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-161">Messenger.</span></span> <span data-ttu-id="4bcb9-162">A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-162">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
> <LI>
> <P><span data-ttu-id="4bcb9-163">Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-163">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="4bcb9-164">A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-164">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="4bcb9-165">A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-165">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>


</div></li>
<li><p><span data-ttu-id="4bcb9-166">Provisionar suporte para XMPP e suporte de Federação para o Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 Partners, se a sua implantação usar esses</span><span class="sxs-lookup"><span data-stu-id="4bcb9-166">Provision support for XMPP and federation support for Office Communications Server 2007, Office Communications Server 2007 R2, Lync Server 2010 partners, if your deployment will use these</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-167">Configurar firewalls.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-167">Configure firewalls.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4bcb9-168">Conforme apropriado para a sua organização</span><span class="sxs-lookup"><span data-stu-id="4bcb9-168">As appropriate to your organization</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparando para a instalação de servidores na rede de perímetro do Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-169"><a href="lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md">Preparing for installation of servers in the perimeter network for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bcb9-170">Configurar o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-170">Set up reverse proxy.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bcb9-171">Configurar o proxy inverso (por exemplo, para Microsoft Forefront Threat Management Gateway 2010 ou Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) na rede de perímetro, obter os certificados públicos necessários e configurar o regras de publicação na Web no servidor proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-171">Set up the reverse proxy (for example, for Microsoft Forefront Threat Management Gateway 2010 or Microsoft Internet Security and Acceleration (ISA) Server with Service Pack 1) in the perimeter network, obtain the necessary public certificates, and configure the web publishing rules on the reverse proxy server.</span></span></p>
<p><span data-ttu-id="4bcb9-172">Prepare o proxy reverso para serviços de mobilidade se você tiver planejado para a mobilidade e estiver implantando os serviços de mobilidade no pool de front-ends ou no servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-172">Prepare the reverse proxy for Mobility services if you have planned for Mobility and are deploying the Mobility services on the Front End pool or Standard Edition server.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bcb9-173">Grupo <strong>Administradores</strong> ou administrador de proxy reverso</span><span class="sxs-lookup"><span data-stu-id="4bcb9-173"><strong>Administrators</strong> group or Reverse Proxy administrator</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Configurando servidores proxy inversos para o Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-174"><a href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bcb9-175">Configurar um diretor (opcional).</span><span class="sxs-lookup"><span data-stu-id="4bcb9-175">Setup a Director (optional).</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="4bcb9-176">Adicionais Instale e configure um ou mais directors na rede interna.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-176">(Optional) Install and configure one or more Directors in the internal network.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="4bcb9-177">Grupo <strong>Administradores</strong></span><span class="sxs-lookup"><span data-stu-id="4bcb9-177"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-178"><a href="lync-server-2013-setting-up-the-director.md">Configurando o diretor do Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-178"><a href="lync-server-2013-setting-up-the-director.md">Setting up the Director in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bcb9-179">Configurar servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-179">Set up Edge Servers.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4bcb9-180">Instale o software de pré-requisito.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-180">Install prerequisite software.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-181">Transportar o arquivo de configuração de topologia exportado para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-181">Transport the exported topology configuration file to each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-182">Instale o software do Lync Server 2013 em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-182">Install the Lync Server 2013 software on each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-183">Configurar os servidores de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-183">Configure the Edge Servers.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-184">Solicitar e instalar certificados para cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-184">Request and install certificates for each Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-185">Inicie os serviços do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-185">Start the Edge Server services.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4bcb9-186">Grupo <strong>Administradores</strong></span><span class="sxs-lookup"><span data-stu-id="4bcb9-186"><strong>Administrators</strong> group</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-187"><a href="lync-server-2013-setting-up-edge-servers.md">Configurando servidores de borda no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-187"><a href="lync-server-2013-setting-up-edge-servers.md">Setting up Edge Servers in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4bcb9-188">Configurar a implantação para acesso ao usuário externo.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-188">Configure deployment for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4bcb9-189">Use o painel de controle do Lync Server para configurar o suporte para cada um dos seguintes (conforme aplicável):</span><span class="sxs-lookup"><span data-stu-id="4bcb9-189">Use the Lync Server Control Panel to configure support for each of the following (as applicable):</span></span></p>
<ul>
<li><p><span data-ttu-id="4bcb9-190">Retransmissão de mídia</span><span class="sxs-lookup"><span data-stu-id="4bcb9-190">Media relay</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-191">Roteiro de Federação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-191">Federation route</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-192">Acesso de usuário remoto</span><span class="sxs-lookup"><span data-stu-id="4bcb9-192">Remote user access</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-193">Federação com o Lync Server, o Office Communications Server e o Live Communications Server</span><span class="sxs-lookup"><span data-stu-id="4bcb9-193">Federation with Lync Server, Office Communications Server and Live Communications Server</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-194">Conectividade de mensagem de chat Pública</span><span class="sxs-lookup"><span data-stu-id="4bcb9-194">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-195">Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="4bcb9-195">XMPP federation</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-196">Usuários anônimos</span><span class="sxs-lookup"><span data-stu-id="4bcb9-196">Anonymous users</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="4bcb9-197">Configurar contas de usuário para acesso de usuário remoto, Federação, conectividade de mensagem de chat pública, suporte a XMPP e usuários anônimos (conforme aplicável)</span><span class="sxs-lookup"><span data-stu-id="4bcb9-197">Configure user accounts for remote user access, federation, public IM connectivity, XMPP and anonymous user support (as applicable)</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4bcb9-198">Grupo <strong>RTCUniversalServerAdmins</strong> ou conta de usuário atribuída à função <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="4bcb9-198"><strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-199">Configurando o <a href="lync-server-2013-configuring-support-for-external-user-access.md">suporte para acesso de usuários externos no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-199"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4bcb9-200">Verifique a configuração do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-200">Verify your Edge Server configuration.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="4bcb9-201">Verifique a conectividade do servidor e a replicação de dados de configuração de servidores internos.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-201">Verify server connectivity and replication of configuration data from internal servers.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-202">Verifique se usuários externos podem se conectar, incluindo usuários remotos, usuários em domínios federados, usuários de mensagens de chat públicas e usuários anônimos, conforme apropriado para a sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4bcb9-202">Verify that external users can connect, including remote users, users in federated domains, public IM users, and anonymous users, as appropriate to your deployment.</span></span></p></li>
<li><p><span data-ttu-id="4bcb9-203">Verificar a configuração e a comunicação usando o analisador de conectividade remota do Lync Server<a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span><span class="sxs-lookup"><span data-stu-id="4bcb9-203">Verify configuration and communication using the Lync Server Remote Connectivity Analyzer <a href="https://www.testocsconnectivity.com" class="uri">https://www.testocsconnectivity.com</a></span></span></p></li>
<li><p><span data-ttu-id="4bcb9-204">Solucionar problemas de configuração e dificuldade de comunicação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-204">Troubleshoot configuration and communication difficulties</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="4bcb9-205">Para verificar a replicação, grupo <strong>RTCUniversalServerAdmins</strong> ou conta de usuário atribuída à função <strong>CSAdministrator</strong></span><span class="sxs-lookup"><span data-stu-id="4bcb9-205">For verification of replication, <strong>RTCUniversalServerAdmins</strong> group or user account that is assigned to the <strong>CSAdministrator</strong> role</span></span></p>
<p><span data-ttu-id="4bcb9-206">Para verificar a conectividade do usuário, um usuário para cada tipo de acesso de usuário externo ao qual você dá suporte</span><span class="sxs-lookup"><span data-stu-id="4bcb9-206">For verification of user connectivity, a user for each type of external user access that you support</span></span></p>
<p><span data-ttu-id="4bcb9-207">Usuários remotos</span><span class="sxs-lookup"><span data-stu-id="4bcb9-207">Remote users</span></span></p></td>
<td><p><span data-ttu-id="4bcb9-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a> na documentação de implantação</span><span class="sxs-lookup"><span data-stu-id="4bcb9-208"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a> in the Deployment documentation</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

