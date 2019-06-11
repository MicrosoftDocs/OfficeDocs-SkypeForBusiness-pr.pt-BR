---
title: Configurando federação SIP, federação XMPP e sistema de mensagens instântaneas público
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f82e154347c0a77dd4367678fefd518b1abf2fc7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836180"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="51479-102">Configurando federação SIP, federação XMPP e sistema de mensagens instântaneas público no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51479-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51479-103">_**Tópico da última modificação:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="51479-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="51479-104">Federação, conectividade de mensagens instantâneas públicas e protocolo de presença e mensagens extensíveis (XMPP) definem uma classe diferente de usuários externos – usuários federados.</span><span class="sxs-lookup"><span data-stu-id="51479-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="51479-105">Os usuários de uma implantação do Lync Server federado ou implantação do XMPP têm acesso a um conjunto limitado de serviços e são autenticados pela implantação externa.</span><span class="sxs-lookup"><span data-stu-id="51479-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="51479-106">Os usuários remotos são membros da implantação do Lync Server e têm acesso a todos os serviços oferecidos pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="51479-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="51479-107">Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="51479-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="51479-108">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="51479-108">has been announced.</span></span> <span data-ttu-id="51479-109">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51479-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="51479-110">A conectividade de mensagens instantâneas públicas é um tipo especial de Federação que permite que um cliente do Lync Server acesse parceiros de mensagens instantâneas públicas configurados usando o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="51479-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="51479-111">Os atuais parceiros de conectividade de mensagens instantâneas públicas são:</span><span class="sxs-lookup"><span data-stu-id="51479-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="51479-112">America Online</span><span class="sxs-lookup"><span data-stu-id="51479-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="51479-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="51479-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="51479-114">Instant\!</span><span class="sxs-lookup"><span data-stu-id="51479-114">Yahoo\!</span></span>

<span data-ttu-id="51479-115">Uma configuração pública de conectividade de mensagens instantâneas permite que os usuários do Lync acessem usuários de conectividade de mensagens instantâneas públicas:</span><span class="sxs-lookup"><span data-stu-id="51479-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="51479-116">Mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="51479-116">IM and Presence</span></span>

  - <span data-ttu-id="51479-117">Visibilidade de contatos públicos de conectividade de mensagens instantâneas no cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="51479-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="51479-118">Pessoa a quem você conversa mensagens instantâneas com contatos</span><span class="sxs-lookup"><span data-stu-id="51479-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="51479-119">Chamadas de áudio e vídeo com usuários do Windows Live</span><span class="sxs-lookup"><span data-stu-id="51479-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="51479-120">A Federação do Lync Server define um contrato entre a implantação do Lync Server e outras implantações do Office Communications Server 2007 R2 ou Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51479-120">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments.</span></span> <span data-ttu-id="51479-121">Uma configuração federada do Lync Server permite que os usuários do Lync acessem usuários federados da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="51479-121">A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="51479-122">Mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="51479-122">IM and Presence</span></span>

  - <span data-ttu-id="51479-123">Criação de contatos federados no cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="51479-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="51479-124">A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença.</span><span class="sxs-lookup"><span data-stu-id="51479-124">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol.</span></span> <span data-ttu-id="51479-125">Uma configuração do XMPP permite que os usuários do Lync acessem usuários de domínio do XMPP permitidos da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="51479-125">An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="51479-126">Mensagem instantânea e presença – pessoa para pessoa apenas</span><span class="sxs-lookup"><span data-stu-id="51479-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="51479-127">Criação de contatos federados do XMPP no cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="51479-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="51479-p106">O recurso XMPP do Lync Server 2013 é testado pela Microsoft e ela oferece suporte para federação de mensagens instantâneas com o Google Talk. Para quaisquer outros sistemas XMPP, entre em contato com o fornecedor do mesmo para verificar se eles suportam federação com o Lync Server 2013, e para quaisquer recomendações de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="51479-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="51479-130">Federação externa do servidor de borda, conectividade de mensagens instantâneas públicas e processo de implantação de usuários do XMPP</span><span class="sxs-lookup"><span data-stu-id="51479-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="51479-131">Fase</span><span class="sxs-lookup"><span data-stu-id="51479-131">Phase</span></span></th>
<th><span data-ttu-id="51479-132">Etapas</span><span class="sxs-lookup"><span data-stu-id="51479-132">Steps</span></span></th>
<th><span data-ttu-id="51479-133">Permissões</span><span class="sxs-lookup"><span data-stu-id="51479-133">Permissions</span></span></th>
<th><span data-ttu-id="51479-134">Documentação</span><span class="sxs-lookup"><span data-stu-id="51479-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="51479-135">Determinar as opções para adicionar à implantação de borda existente</span><span class="sxs-lookup"><span data-stu-id="51479-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="51479-136">Execute o construtor de topologias para editar as configurações do servidor de borda e crie e publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="51479-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="51479-137">A topologia de borda existente replicará as alterações do repositório de gerenciamento central para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51479-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="51479-138">Grupo Administradores de domínio e grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="51479-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="51479-139">Você pode editar uma topologia usando uma conta que seja membro do grupo usuários local, mas publicar uma topologia requer uma conta que seja membro do grupo Administradores do domínio e do grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="51479-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="51479-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de borda e de diretor no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51479-141">Preparar-se para a instalação</span><span class="sxs-lookup"><span data-stu-id="51479-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="51479-142">Certifique-se de que os pré-requisitos do sistema sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="51479-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="51479-143">Configurar registros DNS internos e externos para dar suporte à conectividade de mensagens instantâneas, ao agrupamento do Lync e à Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="51479-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="51479-144">Configurar portas e protocolos no firewall para dar suporte aos tipos de Federação que você está implantando</span><span class="sxs-lookup"><span data-stu-id="51479-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="51479-145">Obter e instalar certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="51479-145">Obtain and install public certificates.</span></span> <span data-ttu-id="51479-146">O tempo necessário para obter certificados depende de qual a autoridade de certificação (CA) emite o certificado.</span><span class="sxs-lookup"><span data-stu-id="51479-146">The time required to obtain certificates depends on which certification authority (CA) issues the certificate.</span></span> <span data-ttu-id="51479-147">Esta etapa é opcional neste ponto da implantação.</span><span class="sxs-lookup"><span data-stu-id="51479-147">This step is optional at this point in the deployment.</span></span> <span data-ttu-id="51479-148">Se você não executar esta etapa neste ponto, deverá fazê-lo durante a configuração do servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="51479-148">If you do not perform this step at this point, you must do it during Edge Server configuration.</span></span> <span data-ttu-id="51479-149">O serviço do servidor de borda não pode ser iniciado até que os certificados sejam obtidos</span><span class="sxs-lookup"><span data-stu-id="51479-149">The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="51479-150">Conforme apropriado para a sua organização, como essas funções geralmente são divididas entre vários grupos de trabalho</span><span class="sxs-lookup"><span data-stu-id="51479-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="51479-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planejando o SIP, a Federação do XMPP e o sistema de mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51479-152">Configurar servidores de borda para cenários de Federação</span><span class="sxs-lookup"><span data-stu-id="51479-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="51479-153">Transportar o arquivo de configuração de topologia exportado para cada servidor de borda ou permitir que a replicação seja concluída</span><span class="sxs-lookup"><span data-stu-id="51479-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="51479-154">Executar novamente o assistente de implantação para instalar componentes de suporte para Federação</span><span class="sxs-lookup"><span data-stu-id="51479-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="51479-155">Configurar os servidores de borda</span><span class="sxs-lookup"><span data-stu-id="51479-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="51479-156">Solicitar e instalar certificados para cada servidor de borda</span><span class="sxs-lookup"><span data-stu-id="51479-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="51479-157">Reiniciar os serviços do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="51479-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="51479-158">Grupo Administradores</span><span class="sxs-lookup"><span data-stu-id="51479-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="51479-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configuração de federação do Lync no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="51479-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurar conectividade de mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="51479-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurando federação de XMPP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="51479-162">Configurar o suporte para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="51479-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="51479-163">Usar o painel de controle do Lync Server acesso externo do usuário</span><span class="sxs-lookup"><span data-stu-id="51479-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="51479-164">Configurar a política de acesso externo para permitir comunicações com usuários federados ou usuários públicos</span><span class="sxs-lookup"><span data-stu-id="51479-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="51479-165">Configurar domínios federados SIP para permitir ou bloquear domínios</span><span class="sxs-lookup"><span data-stu-id="51479-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="51479-166">Habilitar provedores federados SIP para provedores de conectividade de mensagens instantâneas públicas</span><span class="sxs-lookup"><span data-stu-id="51479-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="51479-167">Configurar parceiros federados do XMPP por domínio XMPP</span><span class="sxs-lookup"><span data-stu-id="51479-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="51479-168">Grupo RTCUniversalServerAdmins ou conta de usuário atribuída à função CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="51479-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="51479-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando suporte para acesso de usuário externo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="51479-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar criptografia de mídia para fornecedores públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="51479-171">Verificar a configuração do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="51479-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="51479-172">Verificar a conectividade do servidor e a replicação de dados de configuração de servidores internos</span><span class="sxs-lookup"><span data-stu-id="51479-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="51479-173">Para a verificação da replicação, do grupo RTCUniversalServerAdmins ou da conta de usuário que é atribuída ao CSAdministrator de verificação de roleFor da conectividade do usuário, um usuário para cada tipo de usuário federado</span><span class="sxs-lookup"><span data-stu-id="51479-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="51479-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="51479-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="51479-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemplo de configuração de XMPP no Lync Server 2013 – federação XMPP com Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="51479-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

