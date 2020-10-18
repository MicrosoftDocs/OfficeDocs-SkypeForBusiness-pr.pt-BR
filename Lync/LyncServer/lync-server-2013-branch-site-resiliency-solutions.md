---
title: 'Lync Server 2013: soluções de resiliência de site de filial'
description: 'Lync Server 2013: soluções de resiliência de site de filial.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 796ed22344f02bca16571ff5f156c6bb80b1fcfd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572957"
---
# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="e366e-103">Soluções de resiliência de site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e366e-103">Branch-site resiliency solutions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e366e-104">_**Última modificação do tópico:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="e366e-104">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="e366e-105">Há algumas vantagens óbvias para fornecer resiliência de site de filial para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e366e-105">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="e366e-106">Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter o serviço Enterprise Voice e a caixa postal (se você definir configurações de redirecionamento de caixa postal; para obter detalhes, consulte [Branch-site resiliência Requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="e366e-106">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="e366e-107">No entanto, para sites com menos de 25 usuários, uma solução de resiliência pode não fornecer um retorno de investimento suficiente.</span><span class="sxs-lookup"><span data-stu-id="e366e-107">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="e366e-p102">Se decidir fornecer a resiliência do site de filial, você tem três opções. Use a tabela a seguir para ajudá-lo a determinar qual opção é a melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e366e-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e366e-110">Se você…</span><span class="sxs-lookup"><span data-stu-id="e366e-110">If you…</span></span></th>
<th><span data-ttu-id="e366e-111">Recomendamos que você use um(a)…</span><span class="sxs-lookup"><span data-stu-id="e366e-111">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e366e-112">Hospede entre 25 e 1.000 usuários no seu site de filial se o retorno sobre o investimento não suportar uma implantação completa ou em um local em que o suporte administrativo não estiver disponível</span><span class="sxs-lookup"><span data-stu-id="e366e-112">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="e366e-113">Aplicativo de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="e366e-113">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="e366e-114">O aparelho de filial persistente é um servidor de lâmina padrão da indústria com um registrador de servidor do Lync e servidor de mediação executando no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="e366e-114">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="e366e-115">O aparelho de filial persistente também contém um gateway PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="e366e-115">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="e366e-116">Dispositivos qualificados de terceiros (desenvolvidos pelos parceiros da Microsoft no programa de qualificação/certificação SBA [aparelho de filial persistente]) fornece uma conexão PSTN contínua caso uma WAN falhe, mas essa abordagem não fornece a presença e a conferência resilientes porque esses recursos dependem do servidores Front-End no site central.</span><span class="sxs-lookup"><span data-stu-id="e366e-116">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="e366e-117">Para obter detalhes sobre aparelhos de filial persistente, consulte &quot; detalhes do aparelho de filial persistente, &quot; posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e366e-117">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="e366e-118"><strong>Observação:</strong> Se você optar por usar também um tronco SIP com seu aparelho de filial persistente, entre em contato com seu fornecedor de aparelho de filial persistente para saber mais sobre qual provedor de serviços é melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="e366e-118"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e366e-119">Host entre 1000 e 2000 usuários no seu site de filial, não tem uma conexão WAN resiliente e tenha administradores treinados do Lync Server disponíveis</span><span class="sxs-lookup"><span data-stu-id="e366e-119">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="e366e-120">Servidor de filial persistente ou dois aparelhos de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e366e-120">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="e366e-121">O servidor de filial persistente é uma reunião do Windows Server, requisitos de hardware específicos que tem o software de servidor de mediação e registrador do Lync Server instalado.</span><span class="sxs-lookup"><span data-stu-id="e366e-121">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="e366e-122">Ele deve ser conectado a um gateway PSTN ou a um tronco SIP a um provedor de serviço telefônico.</span><span class="sxs-lookup"><span data-stu-id="e366e-122">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="e366e-123">Para obter detalhes sobre servidores de filial persistente, consulte &quot; detalhes do servidor de filial persistente, &quot; posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="e366e-123">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e366e-124">Se você precisar de recursos de presença e conferência, além de recursos de voz para até 5000 usuários, e tiver administradores treinados do Lync Server disponíveis</span><span class="sxs-lookup"><span data-stu-id="e366e-124">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="e366e-125">Implante como um site central com um servidor Standard Edition e não como um site de filial.</span><span class="sxs-lookup"><span data-stu-id="e366e-125">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="e366e-126">Uma implantação completa do Lync Server fornece uma conexão PSTN contínua e uma presença e conferência resiliente no caso de falha da WAN.</span><span class="sxs-lookup"><span data-stu-id="e366e-126">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="e366e-127">Para obter detalhes sobre a preparação para esta solução, consulte <a href="lync-server-2013-planning-for-your-organization.md">Organization Planning for Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinando seus requisitos de sistema para o Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinando seus requisitos de infraestrutura para o Lync Server 2013</a>e outras seções relevantes da documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="e366e-127">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="e366e-128">Topologia de resiliência</span><span class="sxs-lookup"><span data-stu-id="e366e-128">Resiliency Topologies</span></span>

<span data-ttu-id="e366e-129">A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.</span><span class="sxs-lookup"><span data-stu-id="e366e-129">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="e366e-130">**Opções de resiliência do site de filial**</span><span class="sxs-lookup"><span data-stu-id="e366e-130">**Branch site resiliency options**</span></span>

<span data-ttu-id="e366e-131">![Opções de resiliência de ramificação de voz](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opções de resiliência de ramificação de voz")</span><span class="sxs-lookup"><span data-stu-id="e366e-131">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="e366e-132">Detalhes do aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="e366e-132">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="e366e-133">O aparelho de filial persistente do Lync Server inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="e366e-133">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="e366e-134">Um Registrador para a autenticação do usuário, registro e roteamento de chamada</span><span class="sxs-lookup"><span data-stu-id="e366e-134">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="e366e-135">Um Servidor de Mediação para a manipulação de sinalização entre o Registrador e o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="e366e-135">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="e366e-136">Um gateway PSTN para o roteamento de chamadas ao PSTN como um transporte fallback no caso de uma interrupção da WAN</span><span class="sxs-lookup"><span data-stu-id="e366e-136">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="e366e-137">SQL Server Express para armazenamento de dados do usuário local</span><span class="sxs-lookup"><span data-stu-id="e366e-137">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="e366e-138">O aparelho de filial persistente também inclui troncos PSTN, portas analógicas e um adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="e366e-138">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="e366e-139">Se a conexão WAN do site de filial com um site central ficar indisponível, os usuários da filial interna continuarão a ser registrados com o registrador de dispositivos de filial persistente e obterão o serviço de voz sem interrupção usando a conexão de aparelho de filial persistente para o PSTN.</span><span class="sxs-lookup"><span data-stu-id="e366e-139">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="e366e-140">Os usuários do site de filial que se conectam de casa ou de outro locais remotos serão capazes de se registrar com um servidor Registrador em um site central quando um link de WAN ao site de filial estiver indisponível.</span><span class="sxs-lookup"><span data-stu-id="e366e-140">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="e366e-141">Esses usuários terão a funcionalidade de comunicações completamente unificadas com única exceção de que as chamadas de entrada ao site de filial irão para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="e366e-141">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="e366e-142">Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deve ser restabelecida aos usuários do site de filial.</span><span class="sxs-lookup"><span data-stu-id="e366e-142">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="e366e-143">Nem o failover para o aparelho de filial persistente nem a restauração do serviço requer a presença de um administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="e366e-143">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="e366e-144">O Lync Server oferece suporte para até dois dispositivos de filial persistente em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="e366e-144">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e366e-145">Os usuários hospedados em um aparelho de filial persistente do Lync Server não podem criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="e366e-145">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="e366e-146">Visão geral de implantação de aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="e366e-146">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="e366e-147">O aparelho de filial persistente é fabricado por fabricantes de equipamentos originais em parceria com a Microsoft e implantado em nome de revendedores de valor agregado.</span><span class="sxs-lookup"><span data-stu-id="e366e-147">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="e366e-148">Essa implantação deve ocorrer somente depois que o Lync Server tiver sido implantado no site central, uma conexão WAN com o site de filial estiver em vigor e os usuários do site de filial estiverem habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="e366e-148">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="e366e-149">Para obter detalhes sobre essas fases, consulte [implantando um servidor ou aparelho de filial persistente com o Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="e366e-149">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e366e-150">Fase</span><span class="sxs-lookup"><span data-stu-id="e366e-150">Phase</span></span></th>
<th><span data-ttu-id="e366e-151">Etapas</span><span class="sxs-lookup"><span data-stu-id="e366e-151">Steps</span></span></th>
<th><span data-ttu-id="e366e-152">Direitos do usuário</span><span class="sxs-lookup"><span data-stu-id="e366e-152">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e366e-153">Configurar os serviços de domínio do Active Directory para o aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="e366e-153">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="e366e-154"><strong>No site central:</strong></span><span class="sxs-lookup"><span data-stu-id="e366e-154"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="e366e-155">Crie uma conta de usuário de domínio (ou uma identidade corporativa) para o técnico que instalará e ativará o aparelho de filial persistente no site de filial.</span><span class="sxs-lookup"><span data-stu-id="e366e-155">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="e366e-156">Crie uma conta de computador (com o FQDN (nome de domínio totalmente qualificado) aplicável para o aparelho de filial persistente nos serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e366e-156">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="e366e-157">No construtor de topologias, crie e publique o aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e366e-157">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e366e-158">O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="e366e-158">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="e366e-159">O aparelho de filial persistente deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="e366e-159">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e366e-160">Instale e ative o aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e366e-160">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="e366e-161"><strong>No site de filial:</strong></span><span class="sxs-lookup"><span data-stu-id="e366e-161"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="e366e-162">Conecte o aparelho de filial persistente a uma porta Ethernet e uma porta PSTN.</span><span class="sxs-lookup"><span data-stu-id="e366e-162">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="e366e-163">Inicie o aparelho de filial persistente.</span><span class="sxs-lookup"><span data-stu-id="e366e-163">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="e366e-164">Ingresse o aparelho de filial persistente no domínio, usando a conta de usuário de domínio criada para o aparelho de filial persistente no site central.</span><span class="sxs-lookup"><span data-stu-id="e366e-164">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="e366e-165">Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador.</span><span class="sxs-lookup"><span data-stu-id="e366e-165">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="e366e-166">Configure o aparelho de filial persistente usando a interface de usuário do OEM.</span><span class="sxs-lookup"><span data-stu-id="e366e-166">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="e366e-167">Teste a conectividade do PSTN.</span><span class="sxs-lookup"><span data-stu-id="e366e-167">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="e366e-168">O usuário técnico deve ser um membro do RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="e366e-168">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="e366e-169">Detalhes do servidor de filial persistente</span><span class="sxs-lookup"><span data-stu-id="e366e-169">Survivable Branch Server Details</span></span>

<span data-ttu-id="e366e-170">Em Construtor de topologia, crie o site de filial, adicione o servidor de filial persistente a esse site e, em seguida, execute o assistente de implantação do Lync Server no computador onde você deseja instalar a função.</span><span class="sxs-lookup"><span data-stu-id="e366e-170">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e366e-171">Confira também</span><span class="sxs-lookup"><span data-stu-id="e366e-171">See Also</span></span>


[<span data-ttu-id="e366e-172">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e366e-172">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

