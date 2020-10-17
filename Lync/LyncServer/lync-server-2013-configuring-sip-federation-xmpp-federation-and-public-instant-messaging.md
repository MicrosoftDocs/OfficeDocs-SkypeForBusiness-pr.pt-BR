---
title: Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring SIP federation, XMPP federation and public instant messaging
ms:assetid: a6d04f0b-5cb8-4084-a3a2-d501938971f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205134(v=OCS.15)
ms:contentKeyID: 48184998
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f3fa4f3b78f53df101da42a2e6b7630cdfb71dd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48537068"
---
# <a name="configuring-sip-federation-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a><span data-ttu-id="060c2-102">Configurando Federação SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="060c2-102">Configuring SIP federation, XMPP federation and public instant messaging in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="060c2-103">_**Última modificação do tópico:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="060c2-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="060c2-104">Federação, conectividade de mensagem instantânea pública e protocolo XMPP (Extensible Messaging and Presence Protocol) definem uma classe diferente de usuários externos – os usuários federados.</span><span class="sxs-lookup"><span data-stu-id="060c2-104">Federation, public instant messaging connectivity and Extensible Messaging and Presence Protocol (XMPP) define a different class of external users – Federated users.</span></span> <span data-ttu-id="060c2-105">Os usuários de uma implantação federada do Lync Server ou do XMPP têm acesso a um conjunto limitado de serviços e são autenticados pela implantação externa.</span><span class="sxs-lookup"><span data-stu-id="060c2-105">Users of a federated Lync Server deployment or XMPP deployment have access to a limited set of services and are authenticated by the external deployment.</span></span> <span data-ttu-id="060c2-106">Os usuários remotos são membros da sua implantação do Lync Server e têm acesso a todos os serviços oferecidos pela sua implantação.</span><span class="sxs-lookup"><span data-stu-id="060c2-106">Remote users are members of your Lync Server deployment and have access to all services offered by your deployment.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="060c2-107">Uma data de fim de vida de junho de 2014 para AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="060c2-107">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="060c2-108">foi anunciado.</span><span class="sxs-lookup"><span data-stu-id="060c2-108">has been announced.</span></span> <span data-ttu-id="060c2-109">Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="060c2-109">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="060c2-110">A conectividade de mensagens instantâneas públicas é um tipo especial de Federação que permite que um cliente do Lync Server acesse parceiros de mensagens instantâneas públicas configurados usando o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="060c2-110">Public instant messaging connectivity is a special type of federation that allows a Lync Server client to access configured public Instant Messaging partners using the Lync 2013.</span></span> <span data-ttu-id="060c2-111">Os parceiros atuais de conectividade de mensagem instantânea pública são:</span><span class="sxs-lookup"><span data-stu-id="060c2-111">The current public instant messaging connectivity partners are:</span></span>

  - <span></span>  
    <span data-ttu-id="060c2-112">America Online</span><span class="sxs-lookup"><span data-stu-id="060c2-112">America Online</span></span>

  - <span></span>  
    <span data-ttu-id="060c2-113">Windows Live</span><span class="sxs-lookup"><span data-stu-id="060c2-113">Windows Live</span></span>

  - <span></span>  
    <span data-ttu-id="060c2-114">Instant\!</span><span class="sxs-lookup"><span data-stu-id="060c2-114">Yahoo\!</span></span>

<span data-ttu-id="060c2-115">Uma configuração de conectividade de mensagem instantânea pública permite que os usuários do Lync acessem usuários de conectividade de mensagem instantânea pública através de:</span><span class="sxs-lookup"><span data-stu-id="060c2-115">A public instant messaging connectivity configuration allows Lync users access to public instant messaging connectivity users by:</span></span>

  - <span data-ttu-id="060c2-116">IM e presença</span><span class="sxs-lookup"><span data-stu-id="060c2-116">IM and Presence</span></span>

  - <span data-ttu-id="060c2-117">Visibilidade de contatos de  conectividade de mensagem instantânea pública no cliente Lync</span><span class="sxs-lookup"><span data-stu-id="060c2-117">Visibility of public instant messaging connectivity contacts in Lync client</span></span>

  - <span data-ttu-id="060c2-118">Conversas entre duas pessoas com os contatos</span><span class="sxs-lookup"><span data-stu-id="060c2-118">Person to person IM conversations with contacts</span></span>

  - <span data-ttu-id="060c2-119">Chamadas de áudio e vídeo com usuários do Windows Live</span><span class="sxs-lookup"><span data-stu-id="060c2-119">Audio and video calls with Windows Live users</span></span>

<span data-ttu-id="060c2-p104">A federação do Lync Server define um acordo entre sua implantação do Lync Server e outras implantações do Office Communications Server 2007 R2 ou Lync Server. Uma configuração federada do Lync Server permite acesso dos usuários do Lync aos usuários federados através de:</span><span class="sxs-lookup"><span data-stu-id="060c2-p104">Lync Server federation defines an agreement between your Lync Server deployment and other Office Communications Server 2007 R2 or Lync Server deployments. A Lync Server federated configuration allows Lync users access to federated users by:</span></span>

  - <span data-ttu-id="060c2-122">IM e presença</span><span class="sxs-lookup"><span data-stu-id="060c2-122">IM and Presence</span></span>

  - <span data-ttu-id="060c2-123">Criação de contatos federados no cliente Lync</span><span class="sxs-lookup"><span data-stu-id="060c2-123">Creation of federated contacts in the Lync client</span></span>

<span data-ttu-id="060c2-p105">A federação XMPP define uma implantação externa baseada no protocolo XMPP (eXtensible Messaging and Presence Protocol). Uma configuração de XMPP permite o acesso dos usuários do Lync aos usuários de domínio XMPP através de:</span><span class="sxs-lookup"><span data-stu-id="060c2-p105">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol. An XMPP configuration allows Lync users access to allowed XMPP domain users by:</span></span>

  - <span data-ttu-id="060c2-126">IM e presença - apenas entre duas pessoas</span><span class="sxs-lookup"><span data-stu-id="060c2-126">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="060c2-127">Criação de contatos federados XMPP no cliente Lync</span><span class="sxs-lookup"><span data-stu-id="060c2-127">Creation of XMPP federated contacts in the Lync client</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="060c2-128">O recurso XMPP do Lync Server 2013 é testado e suportado pela Microsoft para Federação de mensagens instantâneas com o Google Talk.</span><span class="sxs-lookup"><span data-stu-id="060c2-128">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk.</span></span> <span data-ttu-id="060c2-129">Para qualquer outro sistema XMPP, entre em contato com o fornecedor terceirizado para verificar se eles suportam a Federação com o Lync Server 2013 e para qualquer recomendação de implantação ou solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="060c2-129">For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>



</div>

<div>

## <a name="edge-server-external-federation-public-instant-messaging-connectivity-and-xmpp-users-deployment-process"></a><span data-ttu-id="060c2-130">Federação externa de servidor de borda, conectividade de mensagem instantânea pública e processo de implantação de usuários XMPP</span><span class="sxs-lookup"><span data-stu-id="060c2-130">Edge Server External Federation, Public Instant Messaging Connectivity and XMPP Users Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="060c2-131">Fase</span><span class="sxs-lookup"><span data-stu-id="060c2-131">Phase</span></span></th>
<th><span data-ttu-id="060c2-132">Etapas</span><span class="sxs-lookup"><span data-stu-id="060c2-132">Steps</span></span></th>
<th><span data-ttu-id="060c2-133">Permissões</span><span class="sxs-lookup"><span data-stu-id="060c2-133">Permissions</span></span></th>
<th><span data-ttu-id="060c2-134">Documentação</span><span class="sxs-lookup"><span data-stu-id="060c2-134">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="060c2-135">Determina as opções para adicionar à implantação de borda existente</span><span class="sxs-lookup"><span data-stu-id="060c2-135">Determine the options to add to the existing Edge deployment</span></span></p></td>
<td><p><span data-ttu-id="060c2-136">Execute o construtor de topologias para editar as configurações do servidor de borda e crie e publique a topologia.</span><span class="sxs-lookup"><span data-stu-id="060c2-136">Run Topology Builder to edit Edge Server settings and create and publish the topology.</span></span> <span data-ttu-id="060c2-137">A topologia de borda existente replicará as alterações do repositório de gerenciamento central para o servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="060c2-137">Your existing Edge topology will replicate changes from the Central Management store to the Edge Server.</span></span></p></td>
<td><p><span data-ttu-id="060c2-138">Grupo de administradores de domínio e grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="060c2-138">Domain Admins group and RTCUniversalServerAdmins group</span></span></p>



> [!NOTE]
> <span data-ttu-id="060c2-139">Você pode editar uma topologia usando uma conta que é membro do grupo de usuários locais, mas publicar uma topologia exige uma conta que seja membro de um grupo de administradores de domínio e do grupo RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="060c2-139">You can edit a topology using an account that is a member of the local users group, but publishing a topology requires an account that is a member of the Domain Admins group and the RTCUniversalServerAdmins group</span></span>

</td>
<td><p><span data-ttu-id="060c2-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Criando uma topologia de borda e de diretor no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-140"><a href="lync-server-2013-building-an-edge-and-director-topology.md">Building an edge and Director topology in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060c2-141">Preparar para instalação</span><span class="sxs-lookup"><span data-stu-id="060c2-141">Prepare for setup</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="060c2-142">Garanta que os pré-requisitos do sistema sejam atendidos.</span><span class="sxs-lookup"><span data-stu-id="060c2-142">Ensure that system prerequisites are met.</span></span></p></li>
<li><p><span data-ttu-id="060c2-143">Configure registros DNS internos e externos para suportar conectividade de mensagens instantâneas públicas, federação Lync e federação XMPP</span><span class="sxs-lookup"><span data-stu-id="060c2-143">Configure internal and external DNS records, to support public instant messaging connectivity, Lync Federation and XMPP Federation</span></span></p></li>
<li><p><span data-ttu-id="060c2-144">Configure portas e protocolos no firewall para suportar os tipos de federação que você está implantando</span><span class="sxs-lookup"><span data-stu-id="060c2-144">Configure ports and protocols at the firewall to support the types of federation that you are deploying</span></span></p></li>
<li><p><span data-ttu-id="060c2-p108">Obtenha e instale certificados públicos. O tempo necessário para obter certificados depende de qual autoridade de certificação (CA) emite o certificado. Esta etapa é opcional neste ponto da implantação. Se você não executar essa etapa nesse momento, será necessário fazê-lo durante a configuração do Servidor de Borda. O serviço de Servidor de Borda não pode ser iniciado até que o certificado seja obtido</span><span class="sxs-lookup"><span data-stu-id="060c2-p108">Obtain and install public certificates. The time required to obtain certificates depends on which certification authority (CA) issues the certificate. This step is optional at this point in the deployment. If you do not perform this step at this point, you must do it during Edge Server configuration. The Edge Server service cannot be started until certificates are obtained</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="060c2-150">Conforme for apropriado para sua organização, pois essas funções são geralmente divididas entre vários grupos de trabalho</span><span class="sxs-lookup"><span data-stu-id="060c2-150">As appropriate to your organization, as these roles are typically split amongst numerous work groups</span></span></p></td>
<td><p><span data-ttu-id="060c2-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planejamento para SIP, Federação XMPP e mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-151"><a href="lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md">Planning for SIP, XMPP federation, and public instant messaging in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060c2-152">Configure os Servidores de Borda para cenários de federação</span><span class="sxs-lookup"><span data-stu-id="060c2-152">Set up Edge Servers for Federation Scenarios</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="060c2-153">Transporte o arquivo de configuração de topologia exportado para cada Servidor de Borda ou permita que a replicação seja concluída</span><span class="sxs-lookup"><span data-stu-id="060c2-153">Transport the exported topology configuration file to each Edge Server or allow replication to complete</span></span></p></li>
<li><p><span data-ttu-id="060c2-154">Execute novamente o Assistente de Implantação para instalar componentes de suporte para federação</span><span class="sxs-lookup"><span data-stu-id="060c2-154">Re-Run the Deployment Wizard to install supporting components for Federation</span></span></p></li>
<li><p><span data-ttu-id="060c2-155">Configura os Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="060c2-155">Configure the Edge Servers</span></span></p></li>
<li><p><span data-ttu-id="060c2-156">Solicite e instale certificados para cada Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="060c2-156">Request and install certificates for each Edge Server</span></span></p></li>
<li><p><span data-ttu-id="060c2-157">Reinicie os serviços dos Servidores de Borda

</span><span class="sxs-lookup"><span data-stu-id="060c2-157">Restart the Edge Server services</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="060c2-158">Grupo de administradores</span><span class="sxs-lookup"><span data-stu-id="060c2-158">Administrators group</span></span></p></td>
<td><p><span data-ttu-id="060c2-159"><a href="lync-server-2013-setting-up-lync-federation.md">Configurando a Federação do Lync no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-159"><a href="lync-server-2013-setting-up-lync-federation.md">Setting up Lync federation in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="060c2-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Configurando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-160"><a href="lync-server-2013-setting-up-public-instant-messaging-connectivity.md">Setting up public instant messaging connectivity in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="060c2-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Configurando a Federação XMPP no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-161"><a href="lync-server-2013-setting-up-xmpp-federation.md">Setting up XMPP federation in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="060c2-162">Configurar suporte para acesso de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="060c2-162">Configure support for external user access.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="060c2-163">Usar o acesso de usuário externo do painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="060c2-163">Use the Lync Server Control Panel External User Access</span></span></p></li>
<li><p><span data-ttu-id="060c2-164">Configure a Política de Acesso Externo para permitir comunicação com usuários federados ou usuários públicos</span><span class="sxs-lookup"><span data-stu-id="060c2-164">Configure External Access Policy to enable Communications with federated users or public users</span></span></p></li>
<li><p><span data-ttu-id="060c2-165">Configure domínios federados SIP para permitir ou bloquear domínios</span><span class="sxs-lookup"><span data-stu-id="060c2-165">Configure SIP Federated Domains to Allow or Block domains</span></span></p></li>
<li><p><span data-ttu-id="060c2-166">Habilite provedores federados SIP para provedores de conectividade de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="060c2-166">Enable SIP Federated Providers for public instant messaging connectivity providers</span></span></p></li>
<li><p><span data-ttu-id="060c2-167">Configure os parceiros federados XMPP por domínio XMPP</span><span class="sxs-lookup"><span data-stu-id="060c2-167">Configure XMPP Federated Partners per XMPP domain</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="060c2-168">Grupo RTCUniversalServerAdmins ou conta de usuário atribuído à função CSAdministrator</span><span class="sxs-lookup"><span data-stu-id="060c2-168">RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator role</span></span></p></td>
<td><p><span data-ttu-id="060c2-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configurando suporte para acesso de usuário externo no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-169"><a href="lync-server-2013-configuring-support-for-external-user-access.md">Configuring support for external user access in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="060c2-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configurar a criptografia de mídia para provedores públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-170"><a href="lync-server-2013-configure-media-encryption-for-public-providers.md">Configure media encryption for public providers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="060c2-171">Verifique sua configuração do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="060c2-171">Verify your Edge Server configuration</span></span></p></td>
<td><p><span data-ttu-id="060c2-172">Verifique a conectividade de servidor e replicação de dados de configuração de servidores internos</span><span class="sxs-lookup"><span data-stu-id="060c2-172">Verify server connectivity and replication of configuration data from internal servers</span></span></p></td>
<td><p><span data-ttu-id="060c2-173">Para verificar a replicação, o grupo RTCUniversalServerAdmins ou conta do usuário que é atribuído à função CSAdministrator. Para verificação da conectividade do usuário, um usuário para cada tipo de usuário federado</span><span class="sxs-lookup"><span data-stu-id="060c2-173">For verification of replication, RTCUniversalServerAdmins group or user account that is assigned to the CSAdministrator roleFor verification of user connectivity, a user for each type of Federated user</span></span></p></td>
<td><p><span data-ttu-id="060c2-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verificando a implantação de borda no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="060c2-174"><a href="lync-server-2013-verifying-your-edge-deployment.md">Verifying your edge deployment in Lync Server 2013</a></span></span></p>
<p><span data-ttu-id="060c2-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Exemplo de configuração de XMPP no Lync Server 2013 – Federação do XMPP com Google Talk</a></span><span class="sxs-lookup"><span data-stu-id="060c2-175"><a href="lync-server-2013-example-xmpp-configuration-–-xmpp-federation-with-google-talk.md">Example XMPP configuration in Lync Server 2013 – XMPP federation with Google Talk</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

