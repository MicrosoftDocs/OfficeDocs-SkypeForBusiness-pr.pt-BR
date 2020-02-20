---
title: 'Lync Server 2013: principais recursos de segurança'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Key security features in Lync Server 2013
ms:assetid: bf2a3b8f-73c6-47e1-8c9e-ca1dc1a502bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn342829(v=OCS.15)
ms:contentKeyID: 56107266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a03a5c312123d714eebe8d49674a19ce712e37bc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145239"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="502ae-102">Principais recursos de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="502ae-102">Key security features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="502ae-103">_**Última modificação do tópico:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="502ae-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="502ae-104">O Lync Server 2013 inclui vários recursos de segurança, incluindo autenticação de servidor para servidor, controle de acesso baseado em função e armazenamento centralizado de dados de configuração.</span><span class="sxs-lookup"><span data-stu-id="502ae-104">Lync Server 2013 includes several security features, including server-to-server authentication, role-based access control, and centralized storage of configuration data.</span></span>

<span data-ttu-id="502ae-105">Este artigo fornece uma visão geral de alto nível da segurança do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="502ae-105">This article provides a high level overview of Lync Server 2013 security.</span></span>

<div>

## <a name="key-security-features-in-lync-server-2013"></a><span data-ttu-id="502ae-106">Principais recursos de segurança no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="502ae-106">Key Security Features in Lync Server 2013</span></span>

<span data-ttu-id="502ae-107">A segurança é um tópico muito amplo.</span><span class="sxs-lookup"><span data-stu-id="502ae-107">Security is a very broad topic.</span></span> <span data-ttu-id="502ae-108">A segurança alcança todos os recursos do Lync Server 2013, bem como os bancos de dados, serviços e hardware que compõem um ecossistema do Lync.</span><span class="sxs-lookup"><span data-stu-id="502ae-108">Security reaches across every feature of Lync Server 2013 as well as databases, services, and hardware that make up a Lync ecosystem.</span></span> <span data-ttu-id="502ae-109">Este artigo descreve alguns dos recursos no Lync Server 2013 em particular que são projetados para segurança.</span><span class="sxs-lookup"><span data-stu-id="502ae-109">This article outlines some of the features in Lync Server 2013 in particular that are designed for security.</span></span>

<div>

## <a name="planning-and-design-tools"></a><span data-ttu-id="502ae-110">Ferramentas de planejamento e design</span><span class="sxs-lookup"><span data-stu-id="502ae-110">Planning and Design Tools</span></span>

<span data-ttu-id="502ae-111">O Lync Server 2013 fornece duas ferramentas para facilitar o planejamento e o design e reduzir a chance de configuração indefinida de componentes do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="502ae-111">Lync Server 2013 provides two tools to facilitate planning and design and to reduce the chance of misconfiguring Lync Server components.</span></span>

  - <span data-ttu-id="502ae-112">A **ferramenta de planejamento de topologia** automatiza grande parte do processo de design de topologia.</span><span class="sxs-lookup"><span data-stu-id="502ae-112">**Topology Planning Tool** automates much of the topology design process.</span></span> <span data-ttu-id="502ae-113">Você pode exportar os resultados da ferramenta de planejamento para o construtor de topologias, que é a ferramenta necessária para instalar cada servidor que executa o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="502ae-113">You can export the results from the Planning Tool to Topology Builder, which is the tool that is required to install each server running Lync Server 2013.</span></span>

  - <span data-ttu-id="502ae-114">O **Construtor de topologias** armazena todas as informações de configuração no repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="502ae-114">**Topology Builder** stores all configuration information in the Central Management store.</span></span>

<span data-ttu-id="502ae-115">Para obter detalhes sobre essas ferramentas, consulte [Planning for Lync Server 2013](lync-server-2013-planning.md).</span><span class="sxs-lookup"><span data-stu-id="502ae-115">For details about these tools, see [Planning for Lync Server 2013](lync-server-2013-planning.md).</span></span>

</div>

<div>

## <a name="central-management-store"></a><span data-ttu-id="502ae-116">Central Management Store</span><span class="sxs-lookup"><span data-stu-id="502ae-116">Central Management Store</span></span>

<span data-ttu-id="502ae-117">No Lync Server 2013, os dados de configuração sobre servidores e serviços fazem parte do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="502ae-117">In Lync Server 2013, configuration data about servers and services is part of the Central Management store.</span></span> <span data-ttu-id="502ae-118">O repositório de gerenciamento central oferece um armazenamento robusto, esquematizado dos dados necessários para definir, configurar, manter, administrar, descrever e operar uma implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="502ae-118">The Central Management store provides a robust, schematized storage of the data needed to define, set up, maintain, administer, describe, and operate a Lync Server deployment.</span></span> <span data-ttu-id="502ae-119">Também valida os dados para garantir a consistência da configuração.</span><span class="sxs-lookup"><span data-stu-id="502ae-119">It also validates the data to ensure configuration consistency.</span></span> <span data-ttu-id="502ae-120">Todas as alterações feitas nesses dados de configuração acontecem no repositório de gerenciamento central, eliminando problemas de "fora de sincronização".</span><span class="sxs-lookup"><span data-stu-id="502ae-120">All changes to this configuration data happen at the Central Management store, eliminating “out-of-sync” issues.</span></span>

<span data-ttu-id="502ae-121">Cópias de somente leitura dos dados são replicadas a todos os servidores na topologia, incluindo Servidores de Borda e Aparelhos de Filia Persistente.</span><span class="sxs-lookup"><span data-stu-id="502ae-121">Read-only copies of the data are replicated to all servers in the topology, including Edge Servers and Survivable Branch Appliances.</span></span> <span data-ttu-id="502ae-122">A replicação é gerenciada por um serviço que, por padrão, é executado sob o contexto do serviço de Rede, reduzindo os direitos e permissões para os de um simples usuário no computador.</span><span class="sxs-lookup"><span data-stu-id="502ae-122">Replication is managed by a service that is, by default, run under the context of the Network service, reducing the rights and permissions to that of a simple user on the computer.</span></span>

</div>

<div>

## <a name="server-to-server-authentication"></a><span data-ttu-id="502ae-123">Autenticação de servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="502ae-123">Server-to-Server Authentication</span></span>

<span data-ttu-id="502ae-124">No Lync Server 2013, a autenticação pode ser configurada entre servidores usando o protocolo de autorização aberta (OAuth).</span><span class="sxs-lookup"><span data-stu-id="502ae-124">In Lync Server 2013, authentication can be configured between servers by using the Open Authorization (OAuth) protocol.</span></span> <span data-ttu-id="502ae-125">Por exemplo, você pode configurar o Lync Server 2013 para autenticar com um servidor que esteja executando o Exchange Server 2013.</span><span class="sxs-lookup"><span data-stu-id="502ae-125">For example, you can configure Lync Server 2013 to authenticate with a server that is running Exchange Server 2013.</span></span> <span data-ttu-id="502ae-126">Usando o protocolo OAuth, o Lync Server e o servidor do Exchange podem confiar um no outro.</span><span class="sxs-lookup"><span data-stu-id="502ae-126">Using the OAuth protocol, the Lync server and the Exchange server can trust each other.</span></span> <span data-ttu-id="502ae-127">Isso fornece a capacidade de integrar os produtos de forma perfeita.</span><span class="sxs-lookup"><span data-stu-id="502ae-127">This provides the ability to integrate the products in a seamless manner.</span></span> <span data-ttu-id="502ae-128">Para obter detalhes, consulte [Managing Server-to-Server Authentication (OAuth) and Partner Applications in Lync server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span><span class="sxs-lookup"><span data-stu-id="502ae-128">For details, see [Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)</span></span>

</div>

<div>

## <a name="windows-powershell-based-management-and-web-based-management-interface"></a><span data-ttu-id="502ae-129">Gerenciamento baseado no Windows PowerShell e interface de gerenciamento baseado na Web</span><span class="sxs-lookup"><span data-stu-id="502ae-129">Windows PowerShell-based management and Web-based Management Interface</span></span>

<span data-ttu-id="502ae-130">O Lync Server 2013 fornece uma interface de gerenciamento poderosa, criada na interface de linha de comando do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="502ae-130">Lync Server 2013 provides a powerful management interface, built on the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="502ae-131">Ela inclui cmdlets para o gerenciamento de segurança e os recursos de segurança do Windows PowerShell estão habilitados por padrão, de modo que os usuários não podem executar scripts com facilidade ou sem ter conhecimento.</span><span class="sxs-lookup"><span data-stu-id="502ae-131">It includes cmdlets for managing security, and Windows PowerShell security features are enabled by default so that users cannot easily or unknowingly run scripts.</span></span> <span data-ttu-id="502ae-132">Isso significa que os padrões do software são definidos para ajudar automaticamente a maximizar a segurança e a reduzir os meios para ataques.</span><span class="sxs-lookup"><span data-stu-id="502ae-132">This means that the software defaults are set to automatically help maximize security and reduce the avenues of attack.</span></span> <span data-ttu-id="502ae-133">Para obter detalhes sobre o suporte de gerenciamento do Windows PowerShell no Lync Server 2013, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="502ae-133">For details about Windows PowerShell management support in Lync Server 2013, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).</span></span>

</div>

<div>

## <a name="role-based-access-control-rbac"></a><span data-ttu-id="502ae-134">Controle de acesso baseado em função (RBAC)</span><span class="sxs-lookup"><span data-stu-id="502ae-134">Role-Based Access Control (RBAC)</span></span>

<span data-ttu-id="502ae-135">O Microsoft Lync Server 2013 fornece controle de acesso baseado em função (RBAC) para permitir que você delegue tarefas administrativas enquanto mantém altos padrões de segurança.</span><span class="sxs-lookup"><span data-stu-id="502ae-135">Microsoft Lync Server 2013 provides role-based access control (RBAC) to enable you to delegate administrative tasks while maintaining high standards for security.</span></span> <span data-ttu-id="502ae-136">É possível usar o RBAC para seguir o princípio de "privilégios mínimos", no qual os usuários recebem somente os direitos administrativos que seus trabalhos exigem.</span><span class="sxs-lookup"><span data-stu-id="502ae-136">You can use RBAC to follow the principle of "least privilege," in which users are given only the administrative rights that their jobs require.</span></span> <span data-ttu-id="502ae-137">O Lync Server 2013 introduz a capacidade de criar uma nova função e também a capacidade de modificar uma função existente.</span><span class="sxs-lookup"><span data-stu-id="502ae-137">Lync Server 2013 introduces the ability to create a new role and also the ability to modify an existing role.</span></span> <span data-ttu-id="502ae-138">Para obter detalhes, consulte [Planning for Role-Based Access Control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="502ae-138">For details, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

</div>

</div>

<div>

## <a name="network-address-translation-nat"></a><span data-ttu-id="502ae-139">NAT (conversão de endereço de rede)</span><span class="sxs-lookup"><span data-stu-id="502ae-139">Network Address Translation (NAT)</span></span>

<span data-ttu-id="502ae-140">O Lync Server 2013 não oferece suporte ao uso de NAT (conversão de endereço de rede) na interface interna do servidor de borda, mas suporta a colocação da interface externa do serviço de borda de acesso, serviço de borda de Webconferência e serviço de borda A/V por trás de um roteador ou firewall que realiza a conversão de endereço de rede (NAT) para topologias de servidor de borda consolidada</span><span class="sxs-lookup"><span data-stu-id="502ae-140">Lync Server 2013 does not support the use of network address translation (NAT) on the internal interface of the Edge Server, but it does support placing the external interface of the Access Edge service, Web Conferencing Edge service, and A/V Edge service behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span> <span data-ttu-id="502ae-141">Vários servidores de borda atrás de um balanceador de carga de hardware não podem usar NAT.</span><span class="sxs-lookup"><span data-stu-id="502ae-141">Multiple Edge Servers behind a hardware load balancer cannot use NAT.</span></span> <span data-ttu-id="502ae-142">Se vários servidores de borda usarem NAT em suas interfaces externas, será necessário o balanceamento de carga DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="502ae-142">If multiple Edge Servers use NAT on their external interfaces, Domain Name System (DNS) load balancing is required.</span></span> <span data-ttu-id="502ae-143">Por sua vez, o uso do balanceamento de carga DNS permite reduzir o número de endereços IP públicos por servidor de borda em um pool de servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="502ae-143">In turn, using DNS load balancing allows you to reduce the number of public IP addresses per Edge Server in an Edge Server pool.</span></span> <span data-ttu-id="502ae-144">Para obter detalhes, consulte[Planning for External User Access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="502ae-144">For details, see[Planning for external user access in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="502ae-145">Se você federar com empresas que têm uma implantação do Microsoft Office Communications Server 2007 e precisar usar áudio/vídeo entre sua empresa e a empresa federada, os requisitos de porta serão aqueles para a versão mais antiga dos servidores de Borda implantados.</span><span class="sxs-lookup"><span data-stu-id="502ae-145">If you federate with enterprises that have a Microsoft Office Communications Server 2007 deployment and you need to use audio/video between your enterprise and the federated enterprise, the port requirements will be those for the older version of the Edge Servers that are deployed.</span></span> <span data-ttu-id="502ae-146">Por exemplo, os intervalos de portas necessários para essas versões mais antigas devem ser abertos para ambas as empresas até que o parceiro federado atualize seus servidores de borda para o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="502ae-146">For example, the port ranges required for those older versions must be opened for both enterprises until the federated partner upgrades its Edge Servers to Lync Server 2013.</span></span> <span data-ttu-id="502ae-147">A qualquer momento, os requisitos de porta podem ser revisados e reduzidos de acordo com a nova configuração.</span><span class="sxs-lookup"><span data-stu-id="502ae-147">At that time, the port requirements can be reviewed and reduced according to the new configuration.</span></span>



</div>

</div>

<div>

## <a name="simplified-certificates-for-edge-servers"></a><span data-ttu-id="502ae-148">Certificados simplificados para servidores de borda</span><span class="sxs-lookup"><span data-stu-id="502ae-148">Simplified Certificates for Edge Servers</span></span>

<span data-ttu-id="502ae-149">O Assistente de Implantação pode preencher automaticamente os SNs (nomes de entidade) e os SANs (nomes de entidade alternativos), reduzindo a possibilidade de inclusão de entradas desnecessárias e possivelmente perigosas.</span><span class="sxs-lookup"><span data-stu-id="502ae-149">The Deployment Wizard can automatically populate subject names (SNs) and subject alternative names (SANs), reducing the possibility of including unnecessary and potentially unsecure entries.</span></span>

</div>

<div>

## <a name="trustworthy-computing-security-development-lifecycle-sdl"></a><span data-ttu-id="502ae-150">SDL (ciclo de vida de desenvolvimento de segurança) de computação confiável</span><span class="sxs-lookup"><span data-stu-id="502ae-150">Trustworthy Computing Security Development Lifecycle (SDL)</span></span>

<span data-ttu-id="502ae-151">O Lync Server 2013 foi projetado e desenvolvido em conformidade com o SDL (Security Development Lifecycle) de computação confiável da Microsoft, descrito <https://go.microsoft.com/fwlink/?linkid=68761>em.</span><span class="sxs-lookup"><span data-stu-id="502ae-151">Lync Server 2013 is designed and developed in compliance with the Microsoft Trustworthy Computing Security Development Lifecycle (SDL), which is described at <https://go.microsoft.com/fwlink/?linkid=68761>.</span></span>

  - <span data-ttu-id="502ae-152">**Digno de confiança pelo design**   da primeira etapa na criação de um sistema de comunicação unificada mais seguro era criar modelos de ameaças e testar cada recurso conforme ele foi criado.</span><span class="sxs-lookup"><span data-stu-id="502ae-152">**Trustworthy by Design**   The first step in creating a more secure unified communications system was to design threat models and test each feature as it was designed.</span></span> <span data-ttu-id="502ae-153">Além disso, a Microsoft realiza testes fora do comportamento projetado para encontrar vulnerabilidades de segurança resultantes de um comportamento de produto inesperado.</span><span class="sxs-lookup"><span data-stu-id="502ae-153">In addition, Microsoft performs testing outside of the designed behavior in order to find security vulnerabilities resulting from unexpected product behavior.</span></span> <span data-ttu-id="502ae-154">Diversos aprimoramentos relacionados à segurança foram integrados ao processo e práticas de codificação.</span><span class="sxs-lookup"><span data-stu-id="502ae-154">Multiple security-related improvements were built into the coding process and practices.</span></span> <span data-ttu-id="502ae-155">As ferramentas de tempo de compilação detectam estouros de buffer e outras possíveis ameaças de segurança antes que o código seja verificado no produto final.</span><span class="sxs-lookup"><span data-stu-id="502ae-155">Build-time tools detect buffer overruns and other potential security threats before the code is checked in to the final product.</span></span> <span data-ttu-id="502ae-156">É claro que é impossível estar preparado para todas as ameaças de segurança desconhecidas.</span><span class="sxs-lookup"><span data-stu-id="502ae-156">Of course, it is impossible to design against all unknown security threats.</span></span> <span data-ttu-id="502ae-157">Nenhum sistema pode garantir a segurança completa.</span><span class="sxs-lookup"><span data-stu-id="502ae-157">No system can guarantee complete security.</span></span> <span data-ttu-id="502ae-158">No entanto, como o desenvolvimento de produtos adotou princípios de design seguros desde o início, o Lync Server 2013 incorpora tecnologias de segurança padrão do setor como parte fundamental de sua arquitetura.</span><span class="sxs-lookup"><span data-stu-id="502ae-158">However, because product development embraced secure design principles from the start, Lync Server 2013 incorporates industry standard security technologies as a fundamental part of its architecture.</span></span>

  - <span data-ttu-id="502ae-159">**Confiável por**   padrão, as comunicações de rede no Lync Server 2013 são criptografadas.</span><span class="sxs-lookup"><span data-stu-id="502ae-159">**Trustworthy by Default**   By default, network communications in Lync Server 2013 are encrypted.</span></span> <span data-ttu-id="502ae-160">Como todos os servidores usam certificados e autenticação Kerberos, TLS, SSTP (protocolo de transporte em tempo real seguro) e outras técnicas de criptografia padrão da indústria, incluindo criptografia AES (padrão de criptografia avançada) de 128 bits, praticamente todos os Lync Os dados do servidor são protegidos na rede.</span><span class="sxs-lookup"><span data-stu-id="502ae-160">Because all servers use certificates and Kerberos authentication, TLS, Secure Real-Time Transport Protocol (SRTP), and other industry-standard encryption techniques, including 128-bit Advanced Encryption Standard (AES) encryption, virtually all Lync Server data is protected on the network.</span></span> <span data-ttu-id="502ae-161">Além disso, o controle de acesso baseado em função permite implantar servidores que executam o Lync Server 2013 de modo que cada função de servidor execute apenas os serviços e tenha apenas as permissões relacionadas a esses serviços, que são apropriadas para a função de servidor.</span><span class="sxs-lookup"><span data-stu-id="502ae-161">In addition, role-based access control makes it possible to deploy servers running Lync Server 2013 so that each server role runs only the services, and has only the permissions related to those services, that are appropriate for the server role.</span></span>

  - <span data-ttu-id="502ae-162">**Confiável por implantação**   toda a documentação do Lync Server 2013 inclui práticas recomendadas e recomendações para ajudá-lo a determinar e configurar os níveis de segurança ideais para sua implantação e avaliar os riscos de segurança da ativação de opções não padrão.</span><span class="sxs-lookup"><span data-stu-id="502ae-162">**Trustworthy by Deployment**   All Lync Server 2013 documentation includes best practices and recommendations to help you determine and configure the optimal security levels for your deployment and assess the security risks of activating non-default options.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

