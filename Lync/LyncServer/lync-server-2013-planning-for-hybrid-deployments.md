---
title: 'Lync Server 2013: planejamento de implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c70002eb7be67c221997465b6cdd5d252df284db
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="ce0e9-102">Planejamento de implantações híbridas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e9-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ce0e9-103">_**Última modificação do tópico:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="ce0e9-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="ce0e9-104">Você deve considerar os requisitos a seguir para usuários e sua infraestrutura de rede ao planejar uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="ce0e9-105">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="ce0e9-105">Infrastructure Requirements</span></span>

<span data-ttu-id="ce0e9-106">Você deve ter o seguinte configurado no seu ambiente para implementar e implantar uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="ce0e9-107">Um locatário do Microsoft Office 365 com o Skype for Business online habilitado.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="ce0e9-108">Observe que você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="ce0e9-109">Uma única implantação local (infraestrutura) do Skype for Business Server ou do Lync Server que é implantada em uma topologia com suporte.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="ce0e9-110">Consulte requisitos de topologia.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="ce0e9-111">Para obter informações sobre como configurar sua implantação do Lync Server 2013 ou do Lync Server 2010 para o híbrido, consulte [Configuring Lync server 2013 Hybrid Deployments](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="ce0e9-112">Ferramentas administrativas do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="ce0e9-113">Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, poderá usar as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="ce0e9-114">Para dar suporte ao logon único com o Office 365 para que os usuários possam usar as mesmas credenciais de logon para entrar no Office como eles fazem no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="ce0e9-115">Você também pode usar o AD FS (serviços de Federação do Active Directory) para logon único com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="ce0e9-116">Para mais informações, confira [Integrar suas identidades locais ao Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="ce0e9-117">Uma solução de sincronização de diretório único para manter os objetos do Active Directory online e on-line sincronizados.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="ce0e9-118">Para obter detalhes sobre a sincronização de diretórios, consulte [ferramentas de integração de diretórios](https://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-118">For details about Directory Synchronization, see [Directory Integration Tools](https://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="ce0e9-119">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="ce0e9-119">Lync Client Support</span></span>

<span data-ttu-id="ce0e9-120">Há algumas diferenças nos recursos suportados nos clientes do Lync, bem como os recursos disponíveis em ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="ce0e9-121">Antes de decidir onde você deseja usuários domésticos em sua organização, você pode exibir o suporte ao cliente para as várias configurações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="ce0e9-122">Os seguintes clientes são compatíveis com o Skype for Business online em uma implantação híbrida do Lync:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="ce0e9-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ce0e9-123">Lync 2010</span></span>

  - <span data-ttu-id="ce0e9-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e9-124">Lync 2013</span></span>

  - <span data-ttu-id="ce0e9-125">Aplicativo Lync da Windows Store</span><span class="sxs-lookup"><span data-stu-id="ce0e9-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="ce0e9-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="ce0e9-126">Lync Web App</span></span>

  - <span data-ttu-id="ce0e9-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="ce0e9-127">Lync Mobile</span></span>

  - <span data-ttu-id="ce0e9-128">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="ce0e9-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="ce0e9-129">Sistema de salas do Lync</span><span class="sxs-lookup"><span data-stu-id="ce0e9-129">Lync Room System</span></span>

  - <span data-ttu-id="ce0e9-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e9-130">Lync Basic 2013</span></span>

<span data-ttu-id="ce0e9-131">Para obter detalhes sobre o suporte ao cliente, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="ce0e9-132">Clientes para Lync Online</span><span class="sxs-lookup"><span data-stu-id="ce0e9-132">Clients for Lync Online</span></span>](https://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="ce0e9-133">Tabelas de comparação de clientes para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e9-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="ce0e9-134">Tabelas de comparação de clientes móveis para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ce0e9-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="ce0e9-135">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="ce0e9-135">Topology Requirements</span></span>

<span data-ttu-id="ce0e9-136">Para configurar sua implantação para o híbrido com o Skype for Business Online, você precisa ter uma das seguintes topologias compatíveis:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="ce0e9-137">Uma implantação do Skype for Business Server 2015 com todos os servidores que executam o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="ce0e9-138">Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="ce0e9-139">Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as atualizações cumulativas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="ce0e9-140">O servidor de borda de Federação e o servidor de próximo salto do servidor de borda de Federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="ce0e9-141">As ferramentas administrativas do Skype for Business Server 2015 ou do Lync Server 2013 devem ser instaladas em pelo menos um servidor ou estação de trabalho de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="ce0e9-142">Uma implantação mista do Lync Server 2013 e do Skype for Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="ce0e9-143">Pelo menos um pool corporativo ou servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ce0e9-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="ce0e9-144">O pool de diretores associado à Federação SIP, se existir</span><span class="sxs-lookup"><span data-stu-id="ce0e9-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="ce0e9-145">O pool de borda associado à Federação SIP</span><span class="sxs-lookup"><span data-stu-id="ce0e9-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="ce0e9-146">Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015 com as seguintes funções de servidor em pelo menos um site executando o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="ce0e9-147">Pelo menos um pool corporativo ou servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="ce0e9-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="ce0e9-148">O pool de diretores associado à Federação SIP, se existir</span><span class="sxs-lookup"><span data-stu-id="ce0e9-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="ce0e9-149">O pool de borda associado à Federação SIP para o site</span><span class="sxs-lookup"><span data-stu-id="ce0e9-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="ce0e9-150">Uma implantação mista do Lync Server 2010 e Lync Server 2013 com as seguintes funções de servidor em pelo menos um site executando o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="ce0e9-151">Pelo menos um pool corporativo ou servidor Standard Edition no site</span><span class="sxs-lookup"><span data-stu-id="ce0e9-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="ce0e9-152">O pool de diretores associado à Federação SIP, se existir no site</span><span class="sxs-lookup"><span data-stu-id="ce0e9-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="ce0e9-153">O pool de borda associado à Federação SIP para o site</span><span class="sxs-lookup"><span data-stu-id="ce0e9-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce0e9-154">Todo o gerenciamento de usuários, incluindo as movimentações de usuários entre o local e o UNRESOLVED_TOKEN_VAL (skypeforbusiness) online, precisa ser feito usando a última versão instalada das ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="ce0e9-155">As ferramentas administrativas devem ser instaladas em um servidor separado que tenha acesso de conexão à implantação local existente e à Internet.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="ce0e9-156">O cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-CsUser</A> para mover os usuários da sua implantação local para o UNRESOLVED_TOKEN_VAL (skype16_online) deve ser executado a partir das ferramentas administrativas conectadas à sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="ce0e9-157">Para obter mais informações sobre as topologias suportadas, consulte [topologias compatíveis no Lync server 2013](lync-server-2013-supported-topologies.md)e [Lync Server 2013 Reference topologias for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](https://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="ce0e9-158">Para obter informações sobre como solucionar problemas de implantações híbridas e conectar o PowerShell ao Lync Online, consulte [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](https://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="ce0e9-159">Requisitos para listas de Federação permitidas/bloqueadas</span><span class="sxs-lookup"><span data-stu-id="ce0e9-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="ce0e9-160">A lista de domínios permitidos inclui domínios que têm um FQDN (nome de domínio totalmente qualificado) de borda de parceiro configurado.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-160">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured.</span></span> <span data-ttu-id="ce0e9-161">Às vezes, eles são chamados de *servidores parceiros permitidos* ou *parceiros de Federação direta*.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-161">These are sometimes referred to as *allowed partner servers* or *direct federation partners*.</span></span> <span data-ttu-id="ce0e9-162">Você deve estar familiarizado com a diferença entre a Federação aberta e a Federação fechada, conhecidas como *descoberta de parceiro* e lista de domínios de *parceiros permitidos*, respectivamente, em implantações locais.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-162">You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="ce0e9-163">Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="ce0e9-164">A correspondência de domínio deve ser configurada da mesma para sua implantação local e seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-164">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant.</span></span> <span data-ttu-id="ce0e9-165">Se a descoberta de parceiros estiver habilitada na implantação local, a Federação deverá ser configurada para seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-165">If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant.</span></span> <span data-ttu-id="ce0e9-166">Se a descoberta de parceiro não estiver habilitada, a Federação fechada deverá ser configurada para seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-166">If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="ce0e9-167">A lista de domínios bloqueados na implantação local deve corresponder exatamente à lista de domínios bloqueados para seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="ce0e9-168">A lista de domínios permitidos na implantação local deve corresponder exatamente à lista de domínios permitidos para seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="ce0e9-169">A Federação deve ser habilitada para comunicações externas para o locatário online, que é configurado usando o painel de controle do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="ce0e9-170">Configurações de DNS</span><span class="sxs-lookup"><span data-stu-id="ce0e9-170">DNS Settings</span></span>

<span data-ttu-id="ce0e9-171">Ao criar registros DNS para implantações híbridas, todos os registros de DNS externos do Lync devem apontar para a infraestrutura local.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="ce0e9-172">Para obter detalhes sobre os registros DNS necessários, consulte [requisitos de DNS (sistema de nomes de domínio) para o Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="ce0e9-173">Além disso, você precisa garantir que a resolução DNS descrita na tabela a seguir funcione em sua implantação local:</span><span class="sxs-lookup"><span data-stu-id="ce0e9-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-174">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="ce0e9-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-175">Resolvível por</span><span class="sxs-lookup"><span data-stu-id="ce0e9-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-176">Requisito de DNS</span><span class="sxs-lookup"><span data-stu-id="ce0e9-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce0e9-177">Registro SRV de DNS para _sipfederationtls. _tcp. &lt;sipdomain.com&gt; para todos os domínios SIP com suporte que resolvem os IP externos de borda de acesso</span><span class="sxs-lookup"><span data-stu-id="ce0e9-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-178">Servidor (es) de borda</span><span class="sxs-lookup"><span data-stu-id="ce0e9-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-179">Habilitar a comunicação federada em uma configuração híbrida.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-179">Enable federated communication in a hybrid configuration.</span></span> <span data-ttu-id="ce0e9-180">O servidor de borda precisa saber onde rotear o tráfego federado para o domínio SIP dividido entre o local e o online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-180">The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-181">Registro (s) de DNS para o FQDN do serviço de webconferência de borda, por exemplo, webcon.contoso.com resolvendo IP (s) externo de borda de Webconferência</span><span class="sxs-lookup"><span data-stu-id="ce0e9-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-182">Computadores de usuários conectados à rede corporativa interna</span><span class="sxs-lookup"><span data-stu-id="ce0e9-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-183">Permitir que os usuários online apresentem ou exibam conteúdo em reuniões hospedadas no local.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-183">Enable online users to present or view content in on-premises hosted meetings.</span></span> <span data-ttu-id="ce0e9-184">O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, pesquisas e anotações compartilhadas.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-184">Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ce0e9-185">Dependendo de como o DNS é configurado em sua organização, talvez seja necessário adicionar esses registros à zona de DNS hospedada internamente para o (s) domínio (s) SIP correspondente para fornecer resolução DNS interna a esses registros.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="ce0e9-186">Considerações do firewall</span><span class="sxs-lookup"><span data-stu-id="ce0e9-186">Firewall Considerations</span></span>

<span data-ttu-id="ce0e9-187">Os computadores em sua rede devem ser capazes de realizar pesquisas de DNS da Internet padrão.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-187">Computers on your network must be able to perform standard Internet DNS lookups.</span></span> <span data-ttu-id="ce0e9-188">Se estes computadores podem atingir sites da Internet padrões, sua rede cumpre este requisito.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-188">If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="ce0e9-189">Dependendo do local do seu data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="ce0e9-190">Se os firewalls da sua organização não dão suporte a configurações de nome de curinga, será necessário determinar manualmente os intervalos de endereços IP que você gostaria de permitir e as portas especificadas.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="ce0e9-191">Consulte o tópico de ajuda sobre [URLs e intervalos de endereços IP do Office 365](https://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-191">Refer to the Help topic [Office 365 URLs and IP address ranges](https://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="ce0e9-192">Requisitos de porta e protocolo</span><span class="sxs-lookup"><span data-stu-id="ce0e9-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="ce0e9-193">Além dos requisitos de porta para a comunicação interna do Lync Server 2013, você também deve configurar as seguintes portas.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ce0e9-194">Protocolo/porta</span><span class="sxs-lookup"><span data-stu-id="ce0e9-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="ce0e9-195">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="ce0e9-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="ce0e9-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-197">Abrir entrada</span><span class="sxs-lookup"><span data-stu-id="ce0e9-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="ce0e9-198">Serviços de Federação do Active Directory (função do servidor de federação)</span><span class="sxs-lookup"><span data-stu-id="ce0e9-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="ce0e9-199">Para obter mais informações, consulte <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS role Services</a>.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-199">For more information, see <a href="https://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="ce0e9-200">Serviços de Federação do Active Directory (função do servidor do proxy)</span><span class="sxs-lookup"><span data-stu-id="ce0e9-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="ce0e9-201">Portal do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="ce0e9-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="ce0e9-202">Portal Minha Empresa</span><span class="sxs-lookup"><span data-stu-id="ce0e9-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="ce0e9-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="ce0e9-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="ce0e9-204">Cliente do Lync (comunicação com o Lync Online do Lync Server local)</span><span class="sxs-lookup"><span data-stu-id="ce0e9-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce0e9-205">TCP 80 e 443</span><span class="sxs-lookup"><span data-stu-id="ce0e9-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-206">Abrir entrada</span><span class="sxs-lookup"><span data-stu-id="ce0e9-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="ce0e9-207">Ferramenta de Sincronização de Diretórios do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="ce0e9-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="ce0e9-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-209">Abrir entrada/saída no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="ce0e9-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce0e9-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="ce0e9-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-211">Abrir entrada/saída para sessões de compartilhamento de dados</span><span class="sxs-lookup"><span data-stu-id="ce0e9-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="ce0e9-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-213">Abrir entrada/saída para áudio, vídeo, sessões de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="ce0e9-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ce0e9-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="ce0e9-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-215">Abrir entrada/saída para sessões de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="ce0e9-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ce0e9-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="ce0e9-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="ce0e9-217">Abrir saída para sessões de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="ce0e9-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="ce0e9-218">Dados e contas de usuário</span><span class="sxs-lookup"><span data-stu-id="ce0e9-218">User Accounts and Data</span></span>

<span data-ttu-id="ce0e9-219">Em uma implantação híbrida do Lync Server 2013, qualquer usuário que você deseja hospedar no Lync Online deve ser criado primeiro na implantação local, para que a conta de usuário seja criada nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="ce0e9-220">Você pode então mover o usuário para o Skype for Business Online, que irá mover a lista de contatos do usuário.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="ce0e9-221">Ao sincronizar as contas de usuário entre suas implantações locais e Lync Online do Lync com o AD FS e o DirSync, você precisa sincronizar as contas do AD para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo que os usuários Não são movidos para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="ce0e9-222">Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online em sua organização poderá não funcionar conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ce0e9-223">Se o usuário for criado usando o portal online para o Office 365, a conta de usuário não será sincronizada com o Active Directory local, e o usuário não existirá no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="ce0e9-224">Se você já criou usuários no Lync Online e deseja configurar o híbrido com um Lync Server local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync no local no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="ce0e9-225">Você também deve considerar os seguintes problemas relacionados ao usuário ao planejar uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="ce0e9-226">**Contatos do usuário**   o limite de contatos para os usuários do Lync Online é de 250.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="ce0e9-227">Qualquer contato além desse número será removido da lista de contatos do usuário quando a conta for movida para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="ce0e9-228">\*\*\*\*   As listas de contatos de mensagens instantâneas e de presença, os grupos e as ACLs (listas de controle de acesso) são migrados com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="ce0e9-229">**Dados de conferência, conteúdo de reunião e reuniões**   agendadas esse conteúdo não é migrado com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="ce0e9-230">Os usuários devem reagendar as reuniões depois que suas contas forem migradas para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="ce0e9-231">Recursos e políticas de usuário</span><span class="sxs-lookup"><span data-stu-id="ce0e9-231">User Policies and Features</span></span>

  - <span data-ttu-id="ce0e9-232">Em um ambiente híbrido do Lync Server 2013, os usuários podem ser habilitados para mensagens instantâneas, voz e reuniões tanto no local quanto no online, mas não em ambos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="ce0e9-233">**Cliente do Lync**     alguns usuários podem exigir uma nova versão do cliente quando forem movidos para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="ce0e9-234">Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um pool do Lync Server 2013 antes da migração para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="ce0e9-235">Para obter mais informações sobre o suporte ao cliente, consulte [clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and Lync [clients and Network Ports supported](https://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="ce0e9-235">For more information about client support, see [Clients for Lync Online](https://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](https://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="ce0e9-236">**Políticas e configurações locais (não-usuário)**   online e políticas locais exigem configuração separada.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="ce0e9-237">Você não pode definir políticas globais que se aplicam a ambos.</span><span class="sxs-lookup"><span data-stu-id="ce0e9-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

