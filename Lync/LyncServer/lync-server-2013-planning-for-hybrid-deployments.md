---
title: 'Lync Server 2013: Planejando implantações híbridas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for hybrid deployments
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205403(v=OCS.15)
ms:contentKeyID: 48185910
ms.date: 05/25/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b528e22e24635d47755096cd4bf81d4066feb3c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-hybrid-deployments"></a><span data-ttu-id="d57ac-102">Planejamento de implantações híbridas do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d57ac-102">Planning for Lync Server 2013 hybrid deployments</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d57ac-103">_**Tópico da última modificação:** 2016-05-25_</span><span class="sxs-lookup"><span data-stu-id="d57ac-103">_**Topic Last Modified:** 2016-05-25_</span></span>

<span data-ttu-id="d57ac-104">Você deve considerar os requisitos a seguir para usuários e sua infraestrutura de rede durante o planejamento de uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="d57ac-104">You should consider the following requirements for users and your network infrastructure while planning for a hybrid deployment.</span></span>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="d57ac-105">Requisitos de infraestrutura</span><span class="sxs-lookup"><span data-stu-id="d57ac-105">Infrastructure Requirements</span></span>

<span data-ttu-id="d57ac-106">Você deve ter os seguintes itens configurados no seu ambiente para implementar e implantar uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="d57ac-106">You must have the following configured in your environment in order to implement and deploy a hybrid deployment.</span></span>

  - <span data-ttu-id="d57ac-107">Um locatário do Microsoft Office 365 com o Skype for Business online habilitado.</span><span class="sxs-lookup"><span data-stu-id="d57ac-107">A Microsoft Office 365 tenant with Skype for Business Online enabled.</span></span> <span data-ttu-id="d57ac-108">Observe que você pode usar apenas um único locatário para uma configuração híbrida com sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="d57ac-108">Note that you can use only a single tenant for a hybrid configuration with your on-premises deployment.</span></span>

  - <span data-ttu-id="d57ac-109">Uma única implantação local (infraestrutura) do Skype for Business Server ou do Lync Server que é implantada em uma topologia com suporte.</span><span class="sxs-lookup"><span data-stu-id="d57ac-109">A single on-premises deployment (infrastructure) of Skype for Business Server or Lync Server that is deployed in a supported topology.</span></span> <span data-ttu-id="d57ac-110">Consulte requisitos de topologia.</span><span class="sxs-lookup"><span data-stu-id="d57ac-110">See Topology Requirements.</span></span>
    
    <span data-ttu-id="d57ac-111">Para obter informações sobre como configurar sua implantação do Lync Server 2013 ou do Lync Server 2010 para híbrido, confira Configurando implantações híbridas do [Lync server 2013](lync-server-2013-configuring-hybrid-deployments.md).</span><span class="sxs-lookup"><span data-stu-id="d57ac-111">For information about configuring your Lync Server 2013 or Lync Server 2010 deployment for hybrid, see [Configuring Lync Server 2013 hybrid deployments](lync-server-2013-configuring-hybrid-deployments.md).</span></span>

  - <span data-ttu-id="d57ac-112">Ferramentas administrativas do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d57ac-112">Skype for Business Server 2015 administrative tools.</span></span> <span data-ttu-id="d57ac-113">Se você estiver usando o Lync Server 2013 ou o Lync Server 2010, poderá usar as ferramentas administrativas do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57ac-113">If you are using Lync Server 2013 or Lync Server 2010, you can use the Lync Server 2013 administrative tools.</span></span>

  - <span data-ttu-id="d57ac-114">Para dar suporte ao logon único com o Office 365 para que os usuários possam usar as mesmas credenciais de logon para entrar no Office como se estivessem no local, você pode usar os recursos de sincronização de senha do Azure Active Directory (AAD) Connect.</span><span class="sxs-lookup"><span data-stu-id="d57ac-114">To support Single Sign-on with Office 365 so that users can use the same login credentials for signing in to Office as they do on-premises, you can use the password sync features of Azure Active Directory (AAD) Connect.</span></span> <span data-ttu-id="d57ac-115">É possível também usar Serviços de Federação do Active Directory (AD FS) para login único com o Office 365.</span><span class="sxs-lookup"><span data-stu-id="d57ac-115">You can also use Active Directory Federation Services (AD FS) for single sign-on with Office 365.</span></span>
    
    <span data-ttu-id="d57ac-116">Para obter mais informações, consulte [integrando suas identidades locais com o Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span><span class="sxs-lookup"><span data-stu-id="d57ac-116">For more information, see [Integrating your on-premises identities with Azure Active Directory](http://go.microsoft.com/fwlink/p/?linkid=619754).</span></span>

  - <span data-ttu-id="d57ac-117">Uma única solução de sincronização de diretório para manter seus objetos locais e online do Active Directory sincronizados.</span><span class="sxs-lookup"><span data-stu-id="d57ac-117">A single directory synchronization solution to keep your on-premises and online Active Directory objects synchronized.</span></span> <span data-ttu-id="d57ac-118">Para obter detalhes sobre a sincronização de diretório, consulte [ferramentas de integração de diretório](http://go.microsoft.com/fwlink/p/?linkid=530320).</span><span class="sxs-lookup"><span data-stu-id="d57ac-118">For details about Directory Synchronization, see [Directory Integration Tools](http://go.microsoft.com/fwlink/p/?linkid=530320).</span></span>

</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="d57ac-119">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="d57ac-119">Lync Client Support</span></span>

<span data-ttu-id="d57ac-120">Há algumas diferenças nos recursos com suporte em clientes do Lync, bem como os recursos disponíveis em ambientes locais e online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-120">There are some differences in the features supported in Lync clients, as well as the features available in on-premises and online environments.</span></span> <span data-ttu-id="d57ac-121">Antes de decidir onde você deseja usuários domésticos em sua organização, você pode ver o suporte do cliente para as várias configurações do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d57ac-121">Before you decide where you want to home users in your organization, you can view the client support for the various configurations of Lync Server.</span></span> <span data-ttu-id="d57ac-122">Os clientes a seguir são compatíveis com o Skype for Business online em uma implantação híbrida do Lync:</span><span class="sxs-lookup"><span data-stu-id="d57ac-122">The following clients are supported with Skype for Business Online in a Lync hybrid deployment:</span></span>

  - <span data-ttu-id="d57ac-123">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="d57ac-123">Lync 2010</span></span>

  - <span data-ttu-id="d57ac-124">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="d57ac-124">Lync 2013</span></span>

  - <span data-ttu-id="d57ac-125">Aplicativo Lync Windows Store</span><span class="sxs-lookup"><span data-stu-id="d57ac-125">Lync Windows Store app</span></span>

  - <span data-ttu-id="d57ac-126">Lync Web App</span><span class="sxs-lookup"><span data-stu-id="d57ac-126">Lync Web App</span></span>

  - <span data-ttu-id="d57ac-127">Lync Mobile</span><span class="sxs-lookup"><span data-stu-id="d57ac-127">Lync Mobile</span></span>

  - <span data-ttu-id="d57ac-128">Lync para Mac 2011</span><span class="sxs-lookup"><span data-stu-id="d57ac-128">Lync for Mac 2011</span></span>

  - <span data-ttu-id="d57ac-129">Sistema de Salas do Lync</span><span class="sxs-lookup"><span data-stu-id="d57ac-129">Lync Room System</span></span>

  - <span data-ttu-id="d57ac-130">Lync Basic 2013</span><span class="sxs-lookup"><span data-stu-id="d57ac-130">Lync Basic 2013</span></span>

<span data-ttu-id="d57ac-131">Para obter detalhes sobre o suporte ao cliente, consulte os seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="d57ac-131">For details about client support, see the following topics:</span></span>

  - [<span data-ttu-id="d57ac-132">Clientes para Lync Online</span><span class="sxs-lookup"><span data-stu-id="d57ac-132">Clients for Lync Online</span></span>](http://go.microsoft.com/fwlink/?linkid=281902)

  - [<span data-ttu-id="d57ac-133">Tabelas de comparação dos clientes para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d57ac-133">Client comparison tables for Lync Server 2013</span></span>](lync-server-2013-desktop-client-comparison-tables.md)

  - [<span data-ttu-id="d57ac-134">Tabela de comparação de clientes móveis para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d57ac-134">Mobile client comparison tables for Lync Server 2013</span></span>](lync-server-2013-mobile-client-comparison-tables.md)

</div>

<span id="BKMK_Topology"></span>

<div>

## <a name="topology-requirements"></a><span data-ttu-id="d57ac-135">Requisitos de topologia</span><span class="sxs-lookup"><span data-stu-id="d57ac-135">Topology Requirements</span></span>

<span data-ttu-id="d57ac-136">Para configurar sua implantação do Hybrid com o Skype for Business Online, você precisa ter uma das seguintes topologias compatíveis:</span><span class="sxs-lookup"><span data-stu-id="d57ac-136">To configure your deployment for hybrid with Skype for Business Online, you need to have one of the following supported topologies:</span></span>

  - <span data-ttu-id="d57ac-137">Uma implantação do Skype for Business Server 2015 com todos os servidores que executam o Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d57ac-137">A Skype for Business Server 2015 deployment with all servers running Skype for Business Server 2015.</span></span>

  - <span data-ttu-id="d57ac-138">Uma implantação do Lync Server 2013 com todos os servidores que executam o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d57ac-138">A Lync Server 2013 deployment with all servers running Lync Server 2013.</span></span>

  - <span data-ttu-id="d57ac-139">Uma implantação do Lync Server 2010 com todos os servidores que executam o Lync Server 2010 com as atualizações cumulativas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d57ac-139">A Lync Server 2010 deployment with all servers running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="d57ac-140">O servidor de borda de Federação e o próximo servidor de salto do servidor de borda de Federação devem estar executando o Lync Server 2010 com as atualizações cumulativas mais recentes.</span><span class="sxs-lookup"><span data-stu-id="d57ac-140">The federation Edge Server and next hop server from the federation Edge Server must be running Lync Server 2010 with the latest cumulative updates.</span></span>
    
      - <span data-ttu-id="d57ac-141">O Skype for Business Server 2015 ou o Lync Server 2013 ferramentas administrativas devem ser instalados em pelo menos um servidor ou estação de trabalho de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="d57ac-141">The Skype for Business Server 2015 or Lync Server 2013 Administrative Tools must be installed on at least one server or management workstation.</span></span>

  - <span data-ttu-id="d57ac-142">Uma implantação mista do Lync Server 2013 e do Skype for Business Server 2015 com as funções de servidor a seguir em pelo menos um site que executa o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="d57ac-142">A mixed Lync Server 2013 and Skype for Business Server 2015 deployment with the following server roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="d57ac-143">Pelo menos um servidor Pool Enterprise ou Standard Edition. </span><span class="sxs-lookup"><span data-stu-id="d57ac-143">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="d57ac-144">O Pool de Diretores associado à federação SIP, se ela existir.</span><span class="sxs-lookup"><span data-stu-id="d57ac-144">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="d57ac-145">O Pool de Borda associado à federação SIP.</span><span class="sxs-lookup"><span data-stu-id="d57ac-145">The Edge Pool associated with SIP federation</span></span>

  - <span data-ttu-id="d57ac-146">Uma implantação mista do Lync Server 2010 e do Skype for Business Server 2015 com as funções seguintes servidores em pelo menos um site que executa o Skype for Business Server 2015:</span><span class="sxs-lookup"><span data-stu-id="d57ac-146">A mixed Lync Server 2010 and Skype for Business Server 2015 deployment with the following servers roles in at least one site running Skype for Business Server 2015:</span></span>
    
      - <span data-ttu-id="d57ac-147">Pelo menos um servidor Pool Enterprise ou Standard Edition. </span><span class="sxs-lookup"><span data-stu-id="d57ac-147">At least one Enterprise Pool or Standard Edition server</span></span>
    
      - <span data-ttu-id="d57ac-148">O Pool de Diretores associado à federação SIP, se ela existir.</span><span class="sxs-lookup"><span data-stu-id="d57ac-148">The Director Pool associated with SIP federation, if it exists</span></span>
    
      - <span data-ttu-id="d57ac-149">O Pool de Borda associado à federação SIP do site.</span><span class="sxs-lookup"><span data-stu-id="d57ac-149">The Edge Pool associated with SIP federation for the Site</span></span>

  - <span data-ttu-id="d57ac-150">Uma implantação mista do Lync Server 2010 e Lync Server 2013 com as funções de servidor a seguir em pelo menos um site executando o Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="d57ac-150">A mixed Lync Server 2010 and Lync Server 2013 deployment with the following server roles in at least one site running Lync Server 2013:</span></span>
    
      - <span data-ttu-id="d57ac-151">Pelo menos um servidor Pool Enterprise ou Standard Edition no site.</span><span class="sxs-lookup"><span data-stu-id="d57ac-151">At least one Enterprise Pool or Standard Edition server in the site</span></span>
    
      - <span data-ttu-id="d57ac-152">O Pool de Diretores associado à federação SIP, se ela existir no site.</span><span class="sxs-lookup"><span data-stu-id="d57ac-152">The Director Pool associated with SIP federation, if it exists in the site</span></span>
    
      - <span data-ttu-id="d57ac-153">O Pool de Borda associado à federação SIP do site.</span><span class="sxs-lookup"><span data-stu-id="d57ac-153">The Edge Pool associated with SIP federation for the site</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d57ac-154">Todo o gerenciamento de usuários, incluindo as movimentações de usuários entre o skypeforbusiness (local e o UNRESOLVED_TOKEN_VAL) online, precisa ser feito usando a versão mais recente instalada das ferramentas administrativas.</span><span class="sxs-lookup"><span data-stu-id="d57ac-154">All user management, including user moves between on-premises and UNRESOLVED_TOKEN_VAL(skypeforbusiness) Online, needs to be done using the latest installed version of the administrative tools.</span></span> <span data-ttu-id="d57ac-155">As ferramentas administrativas devem ser instaladas em um servidor separado que conecta o acesso à implantação local existente e à Internet.</span><span class="sxs-lookup"><span data-stu-id="d57ac-155">The administrative tools must be installed on a separate server that has connect access to the existing on-premises deployment and to the Internet.</span></span> <span data-ttu-id="d57ac-156">O cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">move-CsUser</A> para mover os usuários da sua implantação local para o UNRESOLVED_TOKEN_VAL (skype16_online) deve ser executado nas ferramentas administrativas conectadas à sua implantação local.</span><span class="sxs-lookup"><span data-stu-id="d57ac-156">The <A href="https://docs.microsoft.com/powershell/module/skype/Move-CsUser">Move-CsUser</A> cmdlet to move users from your on-premises deployment to UNRESOLVED_TOKEN_VAL(skype16_online) must be run from the administrative tools connected to your on-premises deployment.</span></span>



</div>

<span data-ttu-id="d57ac-157">Para obter mais informações sobre as topologias com suporte, consulte [topologias compatíveis no Lync server 2013](lync-server-2013-supported-topologies.md)e as [topologias de referência do Lync Server 2013 para implantações híbridas da empresa](http://go.microsoft.com/fwlink/p/?linkid=398709).</span><span class="sxs-lookup"><span data-stu-id="d57ac-157">For more information about supported topologies, see [Supported topologies in Lync Server 2013](lync-server-2013-supported-topologies.md), and [Lync Server 2013 Reference Topologies for Enterprise Hybrid Deployments](http://go.microsoft.com/fwlink/p/?linkid=398709).</span></span>

<span data-ttu-id="d57ac-158">Para obter informações de solução de problemas de implantações híbridas e conexão do PowerShell com o Lync Online, consulte [Lync Online: Lync PowerShell e solução de problemas híbrida](http://go.microsoft.com/fwlink/p/?linkid=306718).</span><span class="sxs-lookup"><span data-stu-id="d57ac-158">For troubleshooting information about hybrid deployments and connecting PowerShell to Lync Online, see [Lync Online: Lync PowerShell and Hybrid Troubleshooting](http://go.microsoft.com/fwlink/p/?linkid=306718).</span></span>

</div>

<div>

## <a name="requirements-for-federation-allowedblocked-lists"></a><span data-ttu-id="d57ac-159">Requisitos para listas de agrupamento permitidas/bloqueados</span><span class="sxs-lookup"><span data-stu-id="d57ac-159">Requirements for Federation Allowed/Blocked Lists</span></span>

<span data-ttu-id="d57ac-p108">A lista Domínios permitidos contém domínios com um FQDN (nome de domínio totalmente qualificado) de Borda parceiro configurado. Por vezes, eles são chamados de *servidores parceiros permitidos* ou *parceiros de federação diretos*. Você deve estar familiarizado com a diferença entre a federação aberta e a federação fechada, conhecidas respectivamente como *descoberta de parceiros* e *lista de domínios dos parceiros permitidos* nas implantações locais.</span><span class="sxs-lookup"><span data-stu-id="d57ac-p108">The Allowed domains list includes domains that have a partner Edge fully qualified domain name (FQDN) configured. These are sometimes referred to as *allowed partner servers* or *direct federation partners*. You should be familiar with the difference between Open Federation and Closed Federation, referred to as *partner discovery* and *allowed partner domain list*, respectively, in on-premises deployments.</span></span>

<span data-ttu-id="d57ac-163">Os seguintes requisitos devem ser atendidos para configurar com êxito uma implantação híbrida:</span><span class="sxs-lookup"><span data-stu-id="d57ac-163">The following requirements must be met to successfully configure a hybrid deployment:</span></span>

  - <span data-ttu-id="d57ac-p109">O domínio correspondente deve ser o mesmo configurado para sua implantação local e seu locatário do Office 365. Se a descoberta de parceiros estiver habilitada na implantação local, a federação aberta deverá ser configurada para seu locatário online. Caso contrário, a federação fechada deverá ser configurada para seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-p109">Domain matching must be configured the same for your on-premises deployment and your Office 365 tenant. If partner discovery is enabled on the on-premises deployment, then open federation must be configured for your online tenant. If partner discovery is not enabled, then closed federation must be configured for your online tenant.</span></span>

  - <span data-ttu-id="d57ac-167">A lista de domínios bloqueados da implantação local deve corresponder exatamente à do seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-167">The Blocked domains list in the on-premises deployment must exactly match the Blocked domains list for your online tenant.</span></span>

  - <span data-ttu-id="d57ac-168">A lista de domínios permitidos da implantação local deve corresponder exatamente à do seu locatário online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-168">The Allowed domains list in the on-premises deployment must exactly match the Allowed domains list for your online tenant.</span></span>

  - <span data-ttu-id="d57ac-169">A Federação deve estar habilitada para comunicações externas do locatário online, que é configurado usando o painel de controle do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-169">Federation must be enabled for the external communications for the online tenant, which is configured by using the Lync Online Control Panel.</span></span>

</div>

<div>

## <a name="dns-settings"></a><span data-ttu-id="d57ac-170">Configurações de DNS</span><span class="sxs-lookup"><span data-stu-id="d57ac-170">DNS Settings</span></span>

<span data-ttu-id="d57ac-171">Ao criar registros DNS para implantações híbridas, todos os registros DNS externos do Lync devem apontar para a infraestrutura local.</span><span class="sxs-lookup"><span data-stu-id="d57ac-171">When creating DNS records for hybrid deployments, all Lync external DNS records should point to the on-premises infrastructure.</span></span> <span data-ttu-id="d57ac-172">Para obter detalhes sobre os registros de DNS necessários, consulte [requisitos do sistema de nomes de domínio (DNS) para o Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d57ac-172">For details on required DNS records, please refer to [Domain Name System (DNS) requirements for Lync Server 2013](lync-server-2013-domain-name-system-dns-requirements.md).</span></span>

<span data-ttu-id="d57ac-173">Além disso será necessário garantir que a resolução DNS descrita na tabela a seguir funciona em sua implantação local:</span><span class="sxs-lookup"><span data-stu-id="d57ac-173">Additionally you need to ensure that the DNS resolution described in the following table works in your on-premises deployment:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-174">Registro DNS</span><span class="sxs-lookup"><span data-stu-id="d57ac-174">DNS record</span></span></p></td>
<td><p><span data-ttu-id="d57ac-175">Pode ser resolvido por</span><span class="sxs-lookup"><span data-stu-id="d57ac-175">Resolvable by</span></span></p></td>
<td><p><span data-ttu-id="d57ac-176">Requisitos de DNS</span><span class="sxs-lookup"><span data-stu-id="d57ac-176">DNS requirement</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57ac-177">Registro SRV DNS para sipfederationtls. _ TCP. &lt;sipdomain.com&gt; para todos os domínios SIP suportados para acessar IP externo da borda</span><span class="sxs-lookup"><span data-stu-id="d57ac-177">DNS SRV record for _sipfederationtls._tcp.&lt;sipdomain.com&gt; for all supported SIP domains resolving to Access Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="d57ac-178">Servidor(es) de borda</span><span class="sxs-lookup"><span data-stu-id="d57ac-178">Edge server(s)</span></span></p></td>
<td><p><span data-ttu-id="d57ac-p111">Habilitar a comunicação federada em uma configuração híbrida. O servidor de borda precisa saber para onde encaminhar o tráfego federado para o domínio SIP que está dividido entre as instalações local e online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-p111">Enable federated communication in a hybrid configuration. The Edge Server needs to know where to route federated traffic for the SIP domain that is split between on premises and online.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-181">Registro(s) A de DNS para FQDN do serviço de webconferência de borda, como webcon.contoso.com, que resolve IP(s) de borda de webconferência</span><span class="sxs-lookup"><span data-stu-id="d57ac-181">DNS A record(s) for Edge Web Conferencing Service FQDN, e.g. webcon.contoso.com resolving to Web Conferencing Edge external IP(s)</span></span></p></td>
<td><p><span data-ttu-id="d57ac-182">Computadores de usuários conectados à rede corporativa interna</span><span class="sxs-lookup"><span data-stu-id="d57ac-182">Internal corporate network connected users’ computers</span></span></p></td>
<td><p><span data-ttu-id="d57ac-p112">Habilitar usuários online para apresentar ou visualizar conteúdo em reuniões hospedadas localmente. O conteúdo inclui arquivos do PowerPoint, quadros de comunicações, votações e observações compartilhadas. </span><span class="sxs-lookup"><span data-stu-id="d57ac-p112">Enable online users to present or view content in on-premises hosted meetings. Content includes PowerPoint files, whiteboards, polls, and shared notes.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d57ac-185">Dependendo de como o DNS está configurado na sua organização, talvez seja necessário adicionar esses registros à zona DNS hospedada interna para os domínios SIP correspondentes para proporcionar resolução de DNS interna para esses registros.</span><span class="sxs-lookup"><span data-stu-id="d57ac-185">Depending on how DNS is configured in your organization, you may need to add these records to the internal hosted DNS zone for the corresponding SIP domain(s) to provide internal DNS resolution to these records.</span></span>

</div>

<div>

## <a name="firewall-considerations"></a><span data-ttu-id="d57ac-186">Considerações sobre o firewall</span><span class="sxs-lookup"><span data-stu-id="d57ac-186">Firewall Considerations</span></span>

<span data-ttu-id="d57ac-p113">Os computadores de sua rede devem ser capazes de realizar pesquisas DNS padrão na Internet. Se esses computadores puderem acessar os sites padrão da Internet, sua rede atenderá a esse requisito.</span><span class="sxs-lookup"><span data-stu-id="d57ac-p113">Computers on your network must be able to perform standard Internet DNS lookups. If these computers can reach standard Internet sites, your network meets this requirement.</span></span>

<span data-ttu-id="d57ac-189">Dependendo da localização do seu data center do Microsoft Online Services, você também deve configurar seus dispositivos de firewall de rede para aceitar conexões com base em nomes de domínio curinga (por exemplo, \*todo o tráfego de. Outlook.com).</span><span class="sxs-lookup"><span data-stu-id="d57ac-189">Depending on the location of your Microsoft Online Services data center, you must also configure your network firewall devices to accept connections based on wildcard domain names (for example, all traffic from \*.outlook.com).</span></span> <span data-ttu-id="d57ac-190">Se os firewalls de sua organização não oferecem suporte às configurações de nome com coringa, você deve determinar manualmente o intervalo de endereço IP que deseja permitir e as portas especificadas.</span><span class="sxs-lookup"><span data-stu-id="d57ac-190">If your organization’s firewalls do not support wildcard name configurations, you will have to manually determine the IP address ranges that you would like to allow and the specified ports.</span></span>

<span data-ttu-id="d57ac-191">Consulte o tópico da ajuda sobre [URLs e intervalos de endereços IP do 365 do Office](http://go.microsoft.com/fwlink/p/?linkid=252942).</span><span class="sxs-lookup"><span data-stu-id="d57ac-191">Refer to the Help topic [Office 365 URLs and IP address ranges](http://go.microsoft.com/fwlink/p/?linkid=252942).</span></span>

</div>

<span id="b"></span>

<div>

## <a name="port-and-protocol-requirements"></a><span data-ttu-id="d57ac-192">Requisitos de protocolo e porta</span><span class="sxs-lookup"><span data-stu-id="d57ac-192">Port and Protocol Requirements</span></span>

<span data-ttu-id="d57ac-193">Além dos requisitos de porta para comunicação interna do Lync Server 2013, você também deve configurar as portas a seguir.</span><span class="sxs-lookup"><span data-stu-id="d57ac-193">In addition to the port requirements for internal Lync Server 2013 communication, you must also configure the following ports.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d57ac-194">Protocolo/porta</span><span class="sxs-lookup"><span data-stu-id="d57ac-194">Protocol / Port</span></span></th>
<th><span data-ttu-id="d57ac-195">Aplicativos</span><span class="sxs-lookup"><span data-stu-id="d57ac-195">Applications</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-196">TCP 443</span><span class="sxs-lookup"><span data-stu-id="d57ac-196">TCP 443</span></span></p></td>
<td><p><span data-ttu-id="d57ac-197">Abrir entrada</span><span class="sxs-lookup"><span data-stu-id="d57ac-197">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="d57ac-198">Serviços de Federação do Active Directory (função de servidor de Federação)</span><span class="sxs-lookup"><span data-stu-id="d57ac-198">Active Directory Federation Services (federation server role)</span></span></p>
<p><span data-ttu-id="d57ac-199">Para obter mais informações, consulte <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">noções básicas sobre os serviços de função do AD FS</a>.</span><span class="sxs-lookup"><span data-stu-id="d57ac-199">For more information, see <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Understanding AD FS Role Services</a>.</span></span></p></li>
<li><p><span data-ttu-id="d57ac-200">Serviços de Federação do Active Directory (função de servidor proxy)</span><span class="sxs-lookup"><span data-stu-id="d57ac-200">Active Directory Federation Services (proxy server role)</span></span></p></li>
<li><p><span data-ttu-id="d57ac-201">Portal do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="d57ac-201">Microsoft Online Services Portal</span></span></p></li>
<li><p><span data-ttu-id="d57ac-202">Portal da minha empresa</span><span class="sxs-lookup"><span data-stu-id="d57ac-202">My Company Portal</span></span></p></li>
<li><p><span data-ttu-id="d57ac-203">Outlook Web App</span><span class="sxs-lookup"><span data-stu-id="d57ac-203">Outlook Web App</span></span></p></li>
<li><p><span data-ttu-id="d57ac-204">Cliente do Lync (comunicação do Lync Server local com o Lync Online)</span><span class="sxs-lookup"><span data-stu-id="d57ac-204">Lync client (communication to Lync Online from on-premises Lync Server)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57ac-205">TCP 80 e 443</span><span class="sxs-lookup"><span data-stu-id="d57ac-205">TCP 80 and 443</span></span></p></td>
<td><p><span data-ttu-id="d57ac-206">Abrir entrada</span><span class="sxs-lookup"><span data-stu-id="d57ac-206">Open inbound</span></span></p>
<ul>
<li><p><span data-ttu-id="d57ac-207">Ferramenta de sincronização de diretório do Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="d57ac-207">Microsoft Online Services Directory Synchronization Tool</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-208">TCP 5061</span><span class="sxs-lookup"><span data-stu-id="d57ac-208">TCP 5061</span></span></p></td>
<td><p><span data-ttu-id="d57ac-209">Entrada/saída aberta no servidor de borda</span><span class="sxs-lookup"><span data-stu-id="d57ac-209">Open inbound/outbound on the Edge Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57ac-210">PSOM/TLS 443</span><span class="sxs-lookup"><span data-stu-id="d57ac-210">PSOM/TLS 443</span></span></p></td>
<td><p><span data-ttu-id="d57ac-211">Entrada/saída aberta para sessões de compartilhamento de dados</span><span class="sxs-lookup"><span data-stu-id="d57ac-211">Open inbound/outbound for data sharing sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-212">STUN/TCP 443</span><span class="sxs-lookup"><span data-stu-id="d57ac-212">STUN/TCP 443</span></span></p></td>
<td><p><span data-ttu-id="d57ac-213">Entrada/saída aberta para o áudio, vídeo, sessões de compartilhamento de aplicativos</span><span class="sxs-lookup"><span data-stu-id="d57ac-213">Open inbound/outbound for audio, video, application sharing sessions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d57ac-214">STUN/UDP 3478</span><span class="sxs-lookup"><span data-stu-id="d57ac-214">STUN/UDP 3478</span></span></p></td>
<td><p><span data-ttu-id="d57ac-215">Entrada/saída aberta para sessões de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="d57ac-215">Open inbound/outbound for audio and video sessions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d57ac-216">RTP/TCP 50000-59999</span><span class="sxs-lookup"><span data-stu-id="d57ac-216">RTP/TCP 50000-59999</span></span></p></td>
<td><p><span data-ttu-id="d57ac-217">Abrir saída para sessões de áudio e vídeo</span><span class="sxs-lookup"><span data-stu-id="d57ac-217">Open outbound for audio and video sessions</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="user-accounts-and-data"></a><span data-ttu-id="d57ac-218">Contas de usuário e dados</span><span class="sxs-lookup"><span data-stu-id="d57ac-218">User Accounts and Data</span></span>

<span data-ttu-id="d57ac-219">Em uma implantação híbrida do Lync Server 2013, todos os usuários que você deseja Home no Lync Online devem ser criados primeiro na implantação local, para que a conta de usuário seja criada nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d57ac-219">In a Lync Server 2013 hybrid deployment, any user that you want to home in Lync Online must first be created in the on-premises deployment, so that the user account is created in Active Directory Domain Services.</span></span> <span data-ttu-id="d57ac-220">Em seguida, você pode mover o usuário para o Skype for Business Online, o que vai mover a lista de contatos do usuário.</span><span class="sxs-lookup"><span data-stu-id="d57ac-220">You can then move the user to Skype for Business Online, which will move the user’s contact list.</span></span>

<span data-ttu-id="d57ac-221">Ao sincronizar contas de usuário entre suas implantações locais do Lync e do Lync Online com o AD FS e o DirSync, você precisa sincronizar as contas do anúncio para todos os usuários do Lync em sua organização entre suas implantações locais e online do Lync, mesmo se os usuários Não são movidos para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-221">When you synchronize user accounts between your Lync on-premises and Lync Online deployments with AD FS and Dirsync, you need to synchronize the AD accounts for all Lync users in your organization between your on-premises and online Lync deployments, even if users are not moved to Lync Online.</span></span> <span data-ttu-id="d57ac-222">Se você não sincronizar todos os usuários, a comunicação entre os usuários locais e online na sua organização poderá não funcionar conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="d57ac-222">If you do not synchronize all users, communication between on-premises and online users in your organization may not work as expected.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d57ac-223">Se o usuário for criado usando o portal online do Office 365, a conta de usuário não será sincronizada com o Active Directory local e o usuário não existirá no Active Directory local.</span><span class="sxs-lookup"><span data-stu-id="d57ac-223">If the user is created by using the online portal for Office 365, the user account will not be synchronized with on-premises Active Directory, and the user will not exist in the on-premises Active Directory.</span></span> <span data-ttu-id="d57ac-224">Se você já tiver criado usuários no Lync Online e quiser configurar o híbrido com um Lync Server local, consulte <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">movendo usuários do Lync Online para o Lync local no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="d57ac-224">If you have already created users in Lync Online, and want to configure hybrid with an on-premises Lync Server, see <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="d57ac-225">Você também deve considerar os seguintes problemas relacionados ao usuário ao se planejar para uma implantação híbrida.</span><span class="sxs-lookup"><span data-stu-id="d57ac-225">You should also consider the following user-related issues when planning for a hybrid deployment.</span></span>

  - <span data-ttu-id="d57ac-226">**Contatos do usuário**   o limite de contatos para usuários do Lync Online é 250.</span><span class="sxs-lookup"><span data-stu-id="d57ac-226">**User contacts**   The limit for contacts for Lync Online users is 250.</span></span> <span data-ttu-id="d57ac-227">Todos os contatos além desse número serão removidos da lista de contatos do usuário quando a conta for movida para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-227">Any contacts beyond that number will be removed from the user’s contact list when the account is moved to Lync Online.</span></span>

  - <span data-ttu-id="d57ac-228">\*\*\*\*   As listas de contatos de mensagens instantâneas e de presença, grupos e listas de controle de acesso (ACLs) são migrados com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="d57ac-228">**Instant Messaging and Presence**   User contact lists, groups, and access control lists (ACLs) are migrated with the user account.</span></span>

  - <span data-ttu-id="d57ac-229">**Dados de conferência, conteúdo da reunião e reuniões**   agendadas esse conteúdo não é migrado com a conta de usuário.</span><span class="sxs-lookup"><span data-stu-id="d57ac-229">**Conferencing data, meeting content, and scheduled meetings**   This content is not migrated with the user account.</span></span> <span data-ttu-id="d57ac-230">Os usuários devem reagendar as reuniões depois que as contas são migradas para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-230">Users must reschedule meetings after their accounts are migrated to Lync Online.</span></span>

</div>

<div>

## <a name="user-policies-and-features"></a><span data-ttu-id="d57ac-231">Políticas e recursos do usuário</span><span class="sxs-lookup"><span data-stu-id="d57ac-231">User Policies and Features</span></span>

  - <span data-ttu-id="d57ac-232">Em um ambiente híbrido do Lync Server 2013, os usuários podem ser habilitados para mensagens instantâneas, voz e reuniões locais ou online, mas não ambos simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="d57ac-232">In a Lync Server 2013 hybrid environment, users can be enabled for Instant Messaging, voice, and meetings either on-premises or online, but not both simultaneously.</span></span>

  - <span data-ttu-id="d57ac-233">**Cliente do Lync**     alguns usuários podem precisar de uma nova versão do cliente quando forem movidos para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-233">**Lync Client**    Some users may require a new client version when they are moved to Lync Online.</span></span> <span data-ttu-id="d57ac-234">Para o Office Communications Server 2007 R2, os usuários devem ser movidos para um pool do Lync Server 2013 antes da migração para o Lync Online.</span><span class="sxs-lookup"><span data-stu-id="d57ac-234">For Office Communications Server 2007 R2, users must be moved to a Lync Server 2013 pool prior to migration to Lync Online.</span></span>
    
    <span data-ttu-id="d57ac-235">Para obter mais informações sobre o suporte ao cliente, consulte [clientes para Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) e [clientes Lync compatíveis e configurações de porta de rede](http://go.microsoft.com/fwlink/p/?linkid=281901).</span><span class="sxs-lookup"><span data-stu-id="d57ac-235">For more information about client support, see [Clients for Lync Online](http://go.microsoft.com/fwlink/p/?linkid=281902) and [Supported Lync clients and network port configurations](http://go.microsoft.com/fwlink/p/?linkid=281901).</span></span>

  - <span data-ttu-id="d57ac-236">**Políticas locais e configurações (não pertencentes ao usuário)**   online e políticas locais exigem configuração separada.</span><span class="sxs-lookup"><span data-stu-id="d57ac-236">**On-premises policies and configuration (non-user)**   Online and on-premises policies require separate configuration.</span></span> <span data-ttu-id="d57ac-237">Você não pode definir políticas globais que se apliquem a ambas.</span><span class="sxs-lookup"><span data-stu-id="d57ac-237">You cannot set global policies that apply to both.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

