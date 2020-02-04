---
title: 'Lync Server 2013: Soluções de resiliência do site de filial'
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
ms.openlocfilehash: 16261d4add87462991c877e85cc6a0ff1e7fdfd4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741831"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="6b774-102">Soluções de resiliência do site de filial no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b774-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b774-103">_**Tópico da última modificação:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="6b774-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="6b774-104">A resiliência de sites de filial proporciona vantagens evidentes à sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b774-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="6b774-105">Especificamente, se você perder a conexão com o site central, os usuários do site de filial continuarão a ter o serviço Enterprise Voice e o correio de voz (se você definir as configurações de redirecionamento de caixa postal, para obter detalhes, consulte [requisitos de resiliência de site de filial para o Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="6b774-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="6b774-106">Entretanto, em sites com menos de 25 usuários, a solução de resiliência poderá não gerar um retorno adequado sobre o investimento.</span><span class="sxs-lookup"><span data-stu-id="6b774-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="6b774-p102">Há três opções para fornecer a resiliência do site de filial. A tabela a seguir o ajudará a determinar qual opção é a melhor para sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b774-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b774-109">Se você…</span><span class="sxs-lookup"><span data-stu-id="6b774-109">If you…</span></span></th>
<th><span data-ttu-id="6b774-110">Recomendamos que você use um(a)…</span><span class="sxs-lookup"><span data-stu-id="6b774-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b774-111">Hospedar entre 25 e 1.000 usuários no seu site de filial e se o retorno sobre o investimento não permitir uma implantação completa ou quando não houver suporte administrativo local disponível</span><span class="sxs-lookup"><span data-stu-id="6b774-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="6b774-112">Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="6b774-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="6b774-113">O appliance de ramificação sobreviventes é um servidor blade padrão do setor com um servidor de registro e mediação do Lync Server executado no Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="6b774-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="6b774-114">O aparelho de ramificação sobreviventes também contém um gateway PSTN (rede telefônica pública comutada).</span><span class="sxs-lookup"><span data-stu-id="6b774-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="6b774-115">Dispositivos qualificados de terceiros (desenvolvidos por parceiros da Microsoft no programa de qualificação/certificação SBA [Aparelho de Filial Persistente]) fornecem uma conexão PSTN contínua em caso de falha da WAN, mas essa abordagem não oferece presença e conferência resilientes porque esses recursos dependem dos Servidores Front-End do site central.</span><span class="sxs-lookup"><span data-stu-id="6b774-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="6b774-116">Para obter detalhes sobre aparelhos de ramificação sobreviventes &quot;, consulte detalhes do aplicativo da&quot; ramificação sobreviventes mais adiante neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6b774-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="6b774-117"><strong>Observação:</strong> Se você decidir usar também um tronco SIP com o seu aparelho de ramificação sobreviventes, entre em contato com o fornecedor da sua agência para saber mais sobre qual provedor de serviços é melhor para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="6b774-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b774-118">Host entre os usuários do 1000 e do 2000 no seu site da sua filial, sem conexão de WAN resistente e com administradores treinados do Lync Server disponíveis</span><span class="sxs-lookup"><span data-stu-id="6b774-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="6b774-119">Servidor de ramificação sobreviventes ou dois aparelhos de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6b774-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="6b774-120">O servidor de ramificação sobreviventes é uma reunião do Windows Server que especifica requisitos de hardware que têm software do Lync Server registrar e Media Server instalado.</span><span class="sxs-lookup"><span data-stu-id="6b774-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="6b774-121">Ele deve estar conectado a um provedor de serviços telefônicos por meio de um gateway PSTN ou de um tronco SIP.</span><span class="sxs-lookup"><span data-stu-id="6b774-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="6b774-122">Para obter detalhes sobre os servidores de ramificação &quot;sobreviventes, consulte detalhes do servidor&quot; de ramificação sobreviventes, posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="6b774-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6b774-123">Se você precisar de recursos de presença e conferência além dos recursos de voz para até 5000 usuários, e tiver administradores do Lync Server treinados disponíveis</span><span class="sxs-lookup"><span data-stu-id="6b774-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="6b774-124">Implante como um site central com um servidor Standard Edition e não como um site de filial.</span><span class="sxs-lookup"><span data-stu-id="6b774-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="6b774-125">Uma implantação completa do Lync Server fornece uma conexão PSTN contínua e uma presença de presença resiliente e uma conferência em caso de falha de WAN.</span><span class="sxs-lookup"><span data-stu-id="6b774-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="6b774-126">Para obter detalhes sobre como se preparar para esta solução, consulte <a href="lync-server-2013-planning-for-your-organization.md">planejamento da organização para o Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">determinando os requisitos do sistema para o Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">determinando os requisitos de infraestrutura do Lync Server 2013</a>e outras seções relevantes da documentação de planejamento.</span><span class="sxs-lookup"><span data-stu-id="6b774-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="6b774-127">Topologias de resiliência</span><span class="sxs-lookup"><span data-stu-id="6b774-127">Resiliency Topologies</span></span>

<span data-ttu-id="6b774-128">A figura a seguir mostra as topologias recomendadas para a resiliência do site de filial.</span><span class="sxs-lookup"><span data-stu-id="6b774-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="6b774-129">**Opções de resiliência do site de filial**</span><span class="sxs-lookup"><span data-stu-id="6b774-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="6b774-130">![Opções de resiliência de ramificação de voz](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Opções de resiliência de ramificação de voz")</span><span class="sxs-lookup"><span data-stu-id="6b774-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="6b774-131">Detalhes do Aparelho de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="6b774-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="6b774-132">O aparelho de ramificação do Lync Server que se resobreviver inclui os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="6b774-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="6b774-133">Um Registrador Avançado para autenticação do usuário, registro e roteamento de chamadas</span><span class="sxs-lookup"><span data-stu-id="6b774-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="6b774-134">Um Servidor de Mediação para tratar a sinalização entre o Registrador Avançado e o gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="6b774-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="6b774-135">Um gateway PSTN para o roteamento de chamadas para a PSTN como um transporte fallback no caso de uma interrupção da WAN</span><span class="sxs-lookup"><span data-stu-id="6b774-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="6b774-136">O SQL Server Express para armazenamento de dados local do usuário</span><span class="sxs-lookup"><span data-stu-id="6b774-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="6b774-137">O aparelho de ramificação sobreviventes também inclui troncos PSTN, portas analógicas e adaptador Ethernet.</span><span class="sxs-lookup"><span data-stu-id="6b774-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="6b774-138">Se a conexão de WAN do site de filial com um site central ficar indisponível, os usuários da ramificação interna continuarão a ser registrados com o registrador de appliances da ramificação sobreviventes e obter serviço de voz ininterrupto usando a conexão de aparelho de ramificação sobreviventes para a PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b774-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="6b774-139">Os usuários do site de filial que se conectarem de casa ou de outros locais remotos serão capazes de se registrar em um servidor do Registrador Avançado em um site central quando um link WAN com o site de filial não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="6b774-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="6b774-140">Esses usuários contarão com total funcionalidade de comunicações unificadas, sendo a única exceção as chamadas de entrada para o site de filial, que irão para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="6b774-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="6b774-141">Quando a conexão WAN voltar a ficar disponível, a funcionalidade total deverá ser restabelecida para os usuários do site de filial.</span><span class="sxs-lookup"><span data-stu-id="6b774-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="6b774-142">Nem o failover para o aparelho de ramificação sobreviventes nem a restauração do serviço exige a presença de um administrador de ti.</span><span class="sxs-lookup"><span data-stu-id="6b774-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="6b774-143">O Lync Server tem suporte para até dois appliances de ramificação sobreviventes em um site de filial.</span><span class="sxs-lookup"><span data-stu-id="6b774-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6b774-144">Os usuários que estiverem hospedados em um aparelho de ramificação de Lync do Lync Server não poderão criar novas salas de chat ou exibir o cartão de sala para salas existentes.</span><span class="sxs-lookup"><span data-stu-id="6b774-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="6b774-145">Visão geral da implantação do aparelho de filial persistente</span><span class="sxs-lookup"><span data-stu-id="6b774-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="6b774-146">O aparelho para filiais sobreviventes é fabricado por fabricantes de equipamento original em parceria com a Microsoft e implantado em nome de revendedores de valor agregado.</span><span class="sxs-lookup"><span data-stu-id="6b774-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="6b774-147">Essa implantação só deve ocorrer após a implantação do Lync Server no site central, uma conexão de WAN com o site de filial e os usuários do site de filiais estiverem habilitados para o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="6b774-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="6b774-148">Para obter detalhes sobre essas fases, consulte [implantando um aplicativo ou aplicativo de ramificação sobreviventes com o Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="6b774-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6b774-149">Fase</span><span class="sxs-lookup"><span data-stu-id="6b774-149">Phase</span></span></th>
<th><span data-ttu-id="6b774-150">Etapas</span><span class="sxs-lookup"><span data-stu-id="6b774-150">Steps</span></span></th>
<th><span data-ttu-id="6b774-151">Direitos do usuário</span><span class="sxs-lookup"><span data-stu-id="6b774-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6b774-152">Configurar os serviços de domínio do Active Directory para o aparelho de ramificação sobreviventes</span><span class="sxs-lookup"><span data-stu-id="6b774-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="6b774-153"><strong>No site central:</strong></span><span class="sxs-lookup"><span data-stu-id="6b774-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="6b774-154">Crie uma conta de usuário de domínio (ou identidade empresarial) para o técnico que instalará e ativará o aparelho de ramificação sobreviventes no site da filial.</span><span class="sxs-lookup"><span data-stu-id="6b774-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="6b774-155">Crie uma conta de computador (com o nome de domínio totalmente qualificado (FQDN) aplicável) para o aparelho de ramificação sobreviventes nos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6b774-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="6b774-156">Em Construtor de topologia, crie e publique o aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6b774-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6b774-157">A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="6b774-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="6b774-158">O aparelho de ramificação sobreviventes deve pertencer ao grupo RTCSBAUniversalServices, que acontece automaticamente quando você usa o construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="6b774-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6b774-159">Instale e ative o aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6b774-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="6b774-160"><strong>No site de filial:</strong></span><span class="sxs-lookup"><span data-stu-id="6b774-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="6b774-161">Conecte o aparelho de ramificação sobreviventes a uma porta Ethernet e a uma porta PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b774-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="6b774-162">Inicie o aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="6b774-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="6b774-163">Ingresse na ramificação da ramificação sobreviventes para o domínio usando a conta de usuário do domínio criada para o aparelho de ramificação sobreviventes no site central.</span><span class="sxs-lookup"><span data-stu-id="6b774-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="6b774-164">Defina o FQDN e o endereço IP para corresponderem ao FQDN criado na conta do computador.</span><span class="sxs-lookup"><span data-stu-id="6b774-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="6b774-165">Configure o aparelho de ramificação sobreviventes usando a interface de usuário do OEM.</span><span class="sxs-lookup"><span data-stu-id="6b774-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="6b774-166">Teste a conectividade PSTN.</span><span class="sxs-lookup"><span data-stu-id="6b774-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="6b774-167">A conta de usuário do técnico deve ser membro do grupo RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="6b774-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="6b774-168">Detalhes do Servidor de Filial Persistente</span><span class="sxs-lookup"><span data-stu-id="6b774-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="6b774-169">Em Construtor de topologias, crie o site de ramificação, adicione o servidor de ramificação sobreviventes a esse site e execute o assistente de implantação do Lync Server no computador onde você deseja instalar a função.</span><span class="sxs-lookup"><span data-stu-id="6b774-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6b774-170">Confira também</span><span class="sxs-lookup"><span data-stu-id="6b774-170">See Also</span></span>


[<span data-ttu-id="6b774-171">Implantando o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b774-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

