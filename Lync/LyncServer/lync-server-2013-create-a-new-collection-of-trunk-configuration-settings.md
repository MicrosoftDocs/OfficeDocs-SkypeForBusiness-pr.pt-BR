---
title: 'Lync Server 2013: criar uma nova coleção de definições de configuração de tronco'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a new collection of trunk configuration settings
ms:assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688054(v=OCS.15)
ms:contentKeyID: 49733647
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c578fd670661413df0a8fb81cb1ce0316db13f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836139"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-new-collection-of-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="9be89-102">Criar uma nova coleção de definições de configuração de tronco no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9be89-102">Create a new collection of trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9be89-103">_**Tópico da última modificação:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9be89-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9be89-104">As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="9be89-104">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider.</span></span> <span data-ttu-id="9be89-105">Essas configurações realizam atividades como especificar:</span><span class="sxs-lookup"><span data-stu-id="9be89-105">These settings do such things as specify:</span></span>

  - <span data-ttu-id="9be89-106">Se o desvio de mídia deve ser ativado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="9be89-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="9be89-107">As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.</span><span class="sxs-lookup"><span data-stu-id="9be89-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="9be89-108">Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="9be89-109">Ao instalar o Microsoft Lync Server 2013, uma coleção global de configurações de tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="9be89-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="9be89-110">Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="9be89-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span>

<span data-ttu-id="9be89-111">Ao criar definições de configuração de tronco SIP usando o painel de controle do Lync Server, as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="9be89-111">When creating SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9be89-112">Configuração de UI</span><span class="sxs-lookup"><span data-stu-id="9be89-112">UI Setting</span></span></th>
<th><span data-ttu-id="9be89-113">Parâmetro do PowerShell</span><span class="sxs-lookup"><span data-stu-id="9be89-113">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="9be89-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="9be89-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9be89-115">Nome</span><span class="sxs-lookup"><span data-stu-id="9be89-115">Name</span></span></p></td>
<td><p><span data-ttu-id="9be89-116">Identidade</span><span class="sxs-lookup"><span data-stu-id="9be89-116">Identity</span></span></p></td>
<td><p><span data-ttu-id="9be89-p103">Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="9be89-119">Description</span></span></p></td>
<td><p><span data-ttu-id="9be89-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="9be89-120">Description</span></span></p></td>
<td><p><span data-ttu-id="9be89-121">Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).</span><span class="sxs-lookup"><span data-stu-id="9be89-121">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-122">Máximo de diálogos iniciais suportados</span><span class="sxs-lookup"><span data-stu-id="9be89-122">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="9be89-123">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="9be89-123">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="9be89-124">O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9be89-124">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-125">Nível de suporte de criptografia</span><span class="sxs-lookup"><span data-stu-id="9be89-125">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="9be89-126">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="9be89-126">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="9be89-127">Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="9be89-127">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="9be89-128">Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia.</span><span class="sxs-lookup"><span data-stu-id="9be89-128">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="9be89-129">A configuração de mídia é definida usando cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="9be89-129">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="9be89-130">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="9be89-130">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9be89-131">- Obrigatório: Deve se utilizar a criptografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="9be89-131">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="9be89-132">- Optional: O SRTP será utilizado se o gateway lhe fornecer apoio.</span><span class="sxs-lookup"><span data-stu-id="9be89-132">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="9be89-133">Não suportado: A encriptação de SRTP não é suportada e, portanto, não será usada.</span><span class="sxs-lookup"><span data-stu-id="9be89-133">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="9be89-p105">SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.</span><span class="sxs-lookup"><span data-stu-id="9be89-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-136">Suporte</span><span class="sxs-lookup"><span data-stu-id="9be89-136">Refer support</span></span></p></td>
<td><p><span data-ttu-id="9be89-137">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="9be89-137">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="9be89-138">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="9be89-138">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="9be89-139">Se definido como <strong>Habilitar envio ao gateway</strong>, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="9be89-139">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="9be89-140">Se definido como <strong>Habilitar refer usando controle de chamada terceirizado</strong>, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host.</span><span class="sxs-lookup"><span data-stu-id="9be89-140">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="9be89-141">o 3pcc também é conhecido &quot;como controle de terceiros&quot; e ocorre quando um terceiro é usado para conectar um par de chamadores (por exemplo, um operador fazendo uma chamada da pessoa para a pessoa B).</span><span class="sxs-lookup"><span data-stu-id="9be89-141">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-142">Habilitar bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="9be89-142">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="9be89-143">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="9be89-143">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="9be89-p107">Indica se o bypass de mídia foi habilitado para esse tronco. O bypass de mídia só pode ser habilitado se <strong>Processamento centralizado de mídia</strong> também for habilitado.</span><span class="sxs-lookup"><span data-stu-id="9be89-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-146">Processamento centralizado de mídia</span><span class="sxs-lookup"><span data-stu-id="9be89-146">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="9be89-147">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="9be89-147">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="9be89-p108">Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)</span><span class="sxs-lookup"><span data-stu-id="9be89-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-150">Habilitar RTP com trava</span><span class="sxs-lookup"><span data-stu-id="9be89-150">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="9be89-151">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="9be89-151">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="9be89-p109">Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.</span><span class="sxs-lookup"><span data-stu-id="9be89-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-154">Habilitar histórico de encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="9be89-154">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="9be89-155">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="9be89-155">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="9be89-156">Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-156">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-157">Habilitar dados de encaminhamento P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="9be89-157">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="9be89-158">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="9be89-158">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="9be89-p110">Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="9be89-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-161">Habilitar timer de failover do roteamento de saída</span><span class="sxs-lookup"><span data-stu-id="9be89-161">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="9be89-162">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="9be89-162">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="9be89-p111">Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="9be89-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-165">Uso associado de PSTNsages</span><span class="sxs-lookup"><span data-stu-id="9be89-165">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="9be89-166">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="9be89-166">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="9be89-167">Conjunto de usos PSTN atribuídos ao tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-167">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-168">Número convertido para testar</span><span class="sxs-lookup"><span data-stu-id="9be89-168">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="9be89-169">N/D</span><span class="sxs-lookup"><span data-stu-id="9be89-169">N/A</span></span></p></td>
<td><p><span data-ttu-id="9be89-170">Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-170">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-171">Regras de conversão associadas</span><span class="sxs-lookup"><span data-stu-id="9be89-171">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="9be89-172">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9be89-172">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9be89-173">Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).</span><span class="sxs-lookup"><span data-stu-id="9be89-173">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-174">Regras de conversão do número chamado</span><span class="sxs-lookup"><span data-stu-id="9be89-174">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="9be89-175">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="9be89-175">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="9be89-176">Conjunto de regras de conversão de número de chamada de saída atribuídas ao tronco.</span><span class="sxs-lookup"><span data-stu-id="9be89-176">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-177">Número de telefone a ser de testado.</span><span class="sxs-lookup"><span data-stu-id="9be89-177">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="9be89-178">N/D</span><span class="sxs-lookup"><span data-stu-id="9be89-178">N/A</span></span></p></td>
<td><p><span data-ttu-id="9be89-179">Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.</span><span class="sxs-lookup"><span data-stu-id="9be89-179">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9be89-180">Número de chamada</span><span class="sxs-lookup"><span data-stu-id="9be89-180">Calling number</span></span></p></td>
<td><p><span data-ttu-id="9be89-181">N/D</span><span class="sxs-lookup"><span data-stu-id="9be89-181">N/A</span></span></p></td>
<td><p><span data-ttu-id="9be89-182">Indica que o número de telefone a ser testado é o número do chamador.</span><span class="sxs-lookup"><span data-stu-id="9be89-182">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9be89-183">Número chamado</span><span class="sxs-lookup"><span data-stu-id="9be89-183">Called number</span></span></p></td>
<td><p><span data-ttu-id="9be89-184">N/D</span><span class="sxs-lookup"><span data-stu-id="9be89-184">N/A</span></span></p></td>
<td><p><span data-ttu-id="9be89-185">Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="9be89-185">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="9be89-186">Os cmdlets CsTrunkConfiguration do Lync Server dão suporte a propriedades adicionais não mostradas no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9be89-186">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="9be89-187">Para obter mais informações, consulte o tópico da ajuda para o cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="9be89-187">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration">New-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-create-new-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="9be89-188">Para criar novas definições de configuração de tronco usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="9be89-188">To create new trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="9be89-189">No painel de controle do Lync Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="9be89-189">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="9be89-190">Na guia **Configuração de Tronco**, clique em **Novo** e, em seguida, clique em **Tronco do site** para criar a nova definição no escopo do site, ou **Tronco do pool** para criar as novas definições no escopo do serviço.</span><span class="sxs-lookup"><span data-stu-id="9be89-190">On the **Trunk Configuration** tab, click **New**, and then click **Site trunk** to create the new settings at the site scope, or **Pool trunk** to create the new settings at the service scope.</span></span>

3.  <span data-ttu-id="9be89-p113">Na caixa de diálogo **Selecionar um site** ou **Selecionar um serviço** (a caixa de diálogo que aparece depende se você está criando definições de escopo do site ou de escopo do serviço), selecione um local para a nova definição de configuração e, em seguida, clique em **OK**. Se a caixa de diálogo está em branco, significa que não há lugar para criar uma nova definição; por exemplo, se a caixa de diálogo **Selecionar um site** está em branco, significa que todos os sites já possuem um conjunto de sites de configuração de tronco atribuído, e cada site (e cada serviço) pode hospedar apenas um conjunto. Nesse caso, você pode tanto excluir o conjunto existente e criar um novo conjunto ou simplesmente modificar o conjunto existente.</span><span class="sxs-lookup"><span data-stu-id="9be89-p113">In the **Select a Site** or the **Select a Service** dialog box (the dialog box that appears will depend on whether you are creating site-scoped or service-scoped settings) select the location for the new configuration settings and then click **OK**. If the dialog box is blank, that means there is no place to create the new settings; for example, if the **Select a Site** dialog box is blank that means that all of your sites have already been assigned a collection of trunk configuration sites, and each site (and each service) can only host one such collection. In that case, you can either delete the existing collection and create a new collection, or simply modify the existing collection.</span></span>

4.  <span data-ttu-id="9be89-194">Na caixa de diálogo **Nova configuração de tronco**, faça as seleções apropriadas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9be89-194">In the **New Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

5.  <span data-ttu-id="9be89-p114">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="9be89-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

6.  <span data-ttu-id="9be89-197">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9be89-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="9be89-198">Na caixa de diálogo **painel de controle do Microsoft Lync Server 2013** , clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="9be89-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

