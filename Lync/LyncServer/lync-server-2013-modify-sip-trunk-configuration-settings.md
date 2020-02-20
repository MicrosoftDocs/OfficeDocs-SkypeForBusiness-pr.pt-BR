---
title: 'Lync Server 2013: modificar as definições de configuração do tronco SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify SIP trunk configuration settings
ms:assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688104(v=OCS.15)
ms:contentKeyID: 49733703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e51772b977d89a6417dbae73e79ffed4bd7db60d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149450"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-sip-trunk-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="e1366-102">Modificar as definições de configuração do tronco SIP no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1366-102">Modify SIP trunk configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1366-103">_**Última modificação do tópico:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="e1366-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="e1366-p101">As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:</span><span class="sxs-lookup"><span data-stu-id="e1366-p101">SIP trunk configuration settings define the relationship and capabilities between a Mediation Server and the public switched telephone network (PSTN) gateway, an IP-public branch exchange (PBX), or a Session Border Controller (SBC) at the service provider. These settings do such things as specify:</span></span>

  - <span data-ttu-id="e1366-106">Se o bypass de mídia deve ser habilitado nos troncos.</span><span class="sxs-lookup"><span data-stu-id="e1366-106">Whether media bypass should be enabled on the trunks.</span></span>

  - <span data-ttu-id="e1366-107">As condições nas quais os pacotes RTCP são enviados.</span><span class="sxs-lookup"><span data-stu-id="e1366-107">The conditions under which real-time transport control protocol (RTCP) packets are sent.</span></span>

  - <span data-ttu-id="e1366-108">Se a criptografia SRTP é obrigatória em cada tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-108">Whether or not secure real-time protocol (SRTP) encryption is required on each trunk.</span></span>

<span data-ttu-id="e1366-109">Quando você instala o Microsoft Lync Server 2013, uma coleção global de definições de configuração do tronco SIP é criada para você.</span><span class="sxs-lookup"><span data-stu-id="e1366-109">When you install Microsoft Lync Server 2013, a global collection of SIP trunk configuration settings is created for you.</span></span> <span data-ttu-id="e1366-110">Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).</span><span class="sxs-lookup"><span data-stu-id="e1366-110">In addition, administrators can create custom setting collections at the site scope or at the service scope (for the PSTN gateway service, only).</span></span> <span data-ttu-id="e1366-111">Qualquer uma dessas coleções pode ser modificada posteriormente usando o painel de controle do Lync Server ou o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1366-111">Any of these collections can later be modified using either Lync Server Control Panel or Windows PowerShell.</span></span>

<span data-ttu-id="e1366-112">Ao modificar as definições de configuração do tronco SIP usando o painel de controle do Lync Server, as seguintes opções estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="e1366-112">When modifying SIP trunk configuration settings using Lync Server Control Panel, the following options are available to you:</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1366-113">Configuração de UI</span><span class="sxs-lookup"><span data-stu-id="e1366-113">UI Setting</span></span></th>
<th><span data-ttu-id="e1366-114">Parâmetro do PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1366-114">PowerShell Parameter</span></span></th>
<th><span data-ttu-id="e1366-115">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1366-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1366-116">Nome</span><span class="sxs-lookup"><span data-stu-id="e1366-116">Name</span></span></p></td>
<td><p><span data-ttu-id="e1366-117">Identidade</span><span class="sxs-lookup"><span data-stu-id="e1366-117">Identity</span></span></p></td>
<td><p><span data-ttu-id="e1366-p103">Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-p103">Unique identifier for the collection. This property is read-only; you cannot change the Identity of a collection of trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-120">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1366-120">Description</span></span></p></td>
<td><p><span data-ttu-id="e1366-121">Descrição</span><span class="sxs-lookup"><span data-stu-id="e1366-121">Description</span></span></p></td>
<td><p><span data-ttu-id="e1366-122">Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).</span><span class="sxs-lookup"><span data-stu-id="e1366-122">Provides a way for administrators to store addition information about the settings (for example, the purpose of the trunk configuration).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-123">Máximo de diálogos iniciais suportados</span><span class="sxs-lookup"><span data-stu-id="e1366-123">Maximum early dialogs supported</span></span></p></td>
<td><p><span data-ttu-id="e1366-124">MaxEarlyDialogs</span><span class="sxs-lookup"><span data-stu-id="e1366-124">MaxEarlyDialogs</span></span></p></td>
<td><p><span data-ttu-id="e1366-125">O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="e1366-125">The maximum number of forked responses a PSTN gateway, IP-PBX, or SBC at the service provider can receive to an Invite that it sent to the Mediation Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-126">Nível de suporte de criptografia</span><span class="sxs-lookup"><span data-stu-id="e1366-126">Encryption support level</span></span></p></td>
<td><p><span data-ttu-id="e1366-127">SRTPMode</span><span class="sxs-lookup"><span data-stu-id="e1366-127">SRTPMode</span></span></p></td>
<td><p><span data-ttu-id="e1366-128">Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="e1366-128">Indicates the level of support for protecting media traffic between the Mediation Server and the PSTN Gateway, IP-PBX, or SBC at the service provider.</span></span> <span data-ttu-id="e1366-129">Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia.</span><span class="sxs-lookup"><span data-stu-id="e1366-129">For media bypass cases, this value must be compatible with the EncryptionLevel setting in the media configuration.</span></span> <span data-ttu-id="e1366-130">A configuração de mídia é definida usando os cmdlets <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> e <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">set-CsMediaConfiguration</a> .</span><span class="sxs-lookup"><span data-stu-id="e1366-130">Media configuration is set by using the <a href="https://docs.microsoft.com/powershell/module/skype/New-CsMediaConfiguration">New-CsMediaConfiguration</a> and <a href="https://docs.microsoft.com/powershell/module/skype/Set-CsMediaConfiguration">Set-CsMediaConfiguration</a> cmdlets.</span></span></p>
<p><span data-ttu-id="e1366-131">Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="e1366-131">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="e1366-132">- Obrigatório: Deve se utilizar a criptografia SRTP.</span><span class="sxs-lookup"><span data-stu-id="e1366-132">Required: SRTP encryption must be used.</span></span></p></li>
<li><p><span data-ttu-id="e1366-133">- Optional: O SRTP será utilizado se o gateway lhe fornecer apoio.</span><span class="sxs-lookup"><span data-stu-id="e1366-133">Optional: SRTP will be used if the gateway supports it.</span></span></p></li>
<li><p><span data-ttu-id="e1366-134">Não suportado: A encriptação de SRTP não é suportada e, portanto, não será usada.</span><span class="sxs-lookup"><span data-stu-id="e1366-134">Not Supported: SRTP encryption is not supported and therefore will not be used.</span></span></p></li>
</ul>
<p><span data-ttu-id="e1366-p105">SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.</span><span class="sxs-lookup"><span data-stu-id="e1366-p105">SRTPMode is used only if the gateway is configured to use Transport Layer Security (TLS). If the gateway is configured with Transmission Control Protocol (TCP) as the transport, SRTPMode is internally set to Not Supported.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-137">Suporte</span><span class="sxs-lookup"><span data-stu-id="e1366-137">Refer support</span></span></p></td>
<td><p><span data-ttu-id="e1366-138">Enable3pccRefer</span><span class="sxs-lookup"><span data-stu-id="e1366-138">Enable3pccRefer</span></span></p>
<p><span data-ttu-id="e1366-139">EnableReferSupport</span><span class="sxs-lookup"><span data-stu-id="e1366-139">EnableReferSupport</span></span></p></td>
<td><p><span data-ttu-id="e1366-140">Se definido como <strong>Habilitar endio ao gateway</strong>, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="e1366-140">If set to <strong>Enable sending refer to the gateway</strong>, indicates that the trunk supports receiving Refer requests from the Mediation Server.</span></span></p>
<p><span data-ttu-id="e1366-141">Se definido como <strong>Habilitar refer usando controle de chamada terceirizado</strong>, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host.</span><span class="sxs-lookup"><span data-stu-id="e1366-141">If set to <strong>Enable refer using third-party call control</strong>, indicates that the 3pcc protocol can be used to allow transferred calls to bypass the hosted site.</span></span> <span data-ttu-id="e1366-142">o 3pcc também é conhecido &quot;como controle de terceiros&quot; e ocorre quando um terceiro é usado para conectar um par de chamadores (por exemplo, um operador fazendo uma chamada da pessoa a a pessoa B).</span><span class="sxs-lookup"><span data-stu-id="e1366-142">3pcc is also known as &quot;third party control,&quot; and occurs when a third-party is used to connect a pair of callers (for example, an operator placing a call from person A to person B).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-143">Habilitar bypass de mídia</span><span class="sxs-lookup"><span data-stu-id="e1366-143">Enable media bypass</span></span></p></td>
<td><p><span data-ttu-id="e1366-144">EnableBypass</span><span class="sxs-lookup"><span data-stu-id="e1366-144">EnableBypass</span></span></p></td>
<td><p><span data-ttu-id="e1366-p107">Selecione a opção <strong>Habilitar bypass de mídia</strong> se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-p107">Indicates whether media bypass is enabled for this trunk. Media bypass can only be enabled if <strong>Centralized media processing</strong> is also enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-147">Processamento centralizado de mídia</span><span class="sxs-lookup"><span data-stu-id="e1366-147">Centralized media processing</span></span></p></td>
<td><p><span data-ttu-id="e1366-148">ConcentratedTopology</span><span class="sxs-lookup"><span data-stu-id="e1366-148">ConcentratedTopology</span></span></p></td>
<td><p><span data-ttu-id="e1366-p108">Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)</span><span class="sxs-lookup"><span data-stu-id="e1366-p108">Indicates whether there is a well-known media termination point. (An example of a well-known media termination point would be a PSTN gateway where the media termination has the same IP as the signaling termination.)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-151">Habilitar RTP com trava</span><span class="sxs-lookup"><span data-stu-id="e1366-151">Enable RTP latching</span></span></p></td>
<td><p><span data-ttu-id="e1366-152">EnableRTPLatching</span><span class="sxs-lookup"><span data-stu-id="e1366-152">EnableRTPLatching</span></span></p></td>
<td><p><span data-ttu-id="e1366-p109">Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.</span><span class="sxs-lookup"><span data-stu-id="e1366-p109">Indicates whether or not the SIP trunks support RTP latching. RTP latching is a technology that enables RTP/RTCP connectivity through a NAT (network address translator) device or firewall.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-155">Habilitar histórico de encaminhamento de chamada</span><span class="sxs-lookup"><span data-stu-id="e1366-155">Enable forward call history</span></span></p></td>
<td><p><span data-ttu-id="e1366-156">ForwardCallHistory</span><span class="sxs-lookup"><span data-stu-id="e1366-156">ForwardCallHistory</span></span></p></td>
<td><p><span data-ttu-id="e1366-157">Indica se as informações de histórico de chamada serão encaminhadas pelo tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-157">Indicates whether call history information will be forwarded through the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-158">Habilitar dados de encaminhamento P-Asserted-Identity</span><span class="sxs-lookup"><span data-stu-id="e1366-158">Enable forward P-Asserted-Identity data</span></span></p></td>
<td><p><span data-ttu-id="e1366-159">ForwardPAI</span><span class="sxs-lookup"><span data-stu-id="e1366-159">ForwardPAI</span></span></p></td>
<td><p><span data-ttu-id="e1366-p110">Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.</span><span class="sxs-lookup"><span data-stu-id="e1366-p110">Indicates whether the P-Asserted-Identity (PAI) header will be forwarded along with the call. The PAI header provides a way to verify the identity of the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-162">Habilitar timer de failover do roteamento de saída</span><span class="sxs-lookup"><span data-stu-id="e1366-162">Enable outbound routing failover timer</span></span></p></td>
<td><p><span data-ttu-id="e1366-163">EnableFastFailoverTimer</span><span class="sxs-lookup"><span data-stu-id="e1366-163">EnableFastFailoverTimer</span></span></p></td>
<td><p><span data-ttu-id="e1366-p111">Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.</span><span class="sxs-lookup"><span data-stu-id="e1366-p111">Indicates whether outbound calls that are not answered by the gateway within 10 seconds will be routed to the next available trunk; if there are no additional trunks then the call will automatically be dropped. In an organization with slow networks and gateway responses, that could potentially result in calls being dropped unnecessarily.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-166">Uso associado de PSTNsages</span><span class="sxs-lookup"><span data-stu-id="e1366-166">Associated PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="e1366-167">PSTNUsages</span><span class="sxs-lookup"><span data-stu-id="e1366-167">PSTNUsages</span></span></p></td>
<td><p><span data-ttu-id="e1366-168">Coleção de usos de PSTN atribuídos ao tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-168">Collection of PSTN usages assigned to the trunk.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-169">Número convertido para testar</span><span class="sxs-lookup"><span data-stu-id="e1366-169">Translated number to test</span></span></p></td>
<td><p><span data-ttu-id="e1366-170">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e1366-170">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1366-171">Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-171">Phone number that can be used to do an ad hoc test of the trunk configuration settings.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-172">Regras de conversão associadas</span><span class="sxs-lookup"><span data-stu-id="e1366-172">Associated translation rules</span></span></p></td>
<td><p><span data-ttu-id="e1366-173">OutboundTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="e1366-173">OutboundTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="e1366-174">Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).</span><span class="sxs-lookup"><span data-stu-id="e1366-174">Collection of phone number translation rules that apply to calls handled by Outbound Routing (calls routed to PBX or PSTN destinations).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-175">Regras de conversão do número chamado</span><span class="sxs-lookup"><span data-stu-id="e1366-175">Called number translation rules</span></span></p></td>
<td><p><span data-ttu-id="e1366-176">OutboundCallingNumberTranslationRulesList</span><span class="sxs-lookup"><span data-stu-id="e1366-176">OutboundCallingNumberTranslationRulesList</span></span></p></td>
<td><p><span data-ttu-id="e1366-177">Coleção de regras de conversão do número de chamada de saída atribuído ao tronco.</span><span class="sxs-lookup"><span data-stu-id="e1366-177">Collection of outbound calling number translation rules assigned to the trunk.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-178">Número de telefone a ser de testado.</span><span class="sxs-lookup"><span data-stu-id="e1366-178">Phone number to test</span></span></p></td>
<td><p><span data-ttu-id="e1366-179">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e1366-179">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1366-180">Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.</span><span class="sxs-lookup"><span data-stu-id="e1366-180">Phone number that can be used to do an ad hoc test of the translation rules.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1366-181">Número de chamada</span><span class="sxs-lookup"><span data-stu-id="e1366-181">Calling number</span></span></p></td>
<td><p><span data-ttu-id="e1366-182">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e1366-182">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1366-183">Indica que o número de telefone a ser testado é o número do chamador.</span><span class="sxs-lookup"><span data-stu-id="e1366-183">Indicates that the phone number to test is the phone number of the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1366-184">Número chamado</span><span class="sxs-lookup"><span data-stu-id="e1366-184">Called number</span></span></p></td>
<td><p><span data-ttu-id="e1366-185">Não disponível</span><span class="sxs-lookup"><span data-stu-id="e1366-185">N/A</span></span></p></td>
<td><p><span data-ttu-id="e1366-186">Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.</span><span class="sxs-lookup"><span data-stu-id="e1366-186">Indicates that the phone number to test is the phone number of the person being called.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="e1366-187">Os cmdlets do Lync Server CsTrunkConfiguration suportam propriedades adicionais não mostradas no painel de controle do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e1366-187">The Lync Server CsTrunkConfiguration cmdlets support additional properties not shown in Lync Server Control Panel.</span></span> <span data-ttu-id="e1366-188">Para obter mais informações, consulte o tópico de ajuda para o cmdlet <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">set-CsTrunkConfiguration</A> .</span><span class="sxs-lookup"><span data-stu-id="e1366-188">For more information, see the help topic for the <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration">Set-CsTrunkConfiguration</A> cmdlet.</span></span>



</div>

<div>

## <a name="to-modify-sip-trunk-configuration-settings-by-using-lync-server-control-panel"></a><span data-ttu-id="e1366-189">Para modificar as definições de configuração do tronco SIP usando o painel de controle do Lync Server</span><span class="sxs-lookup"><span data-stu-id="e1366-189">To modify SIP trunk configuration settings by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="e1366-190">No painel de controle do Lync Server, clique em **Roteamento de voz**e em **configuração de tronco**.</span><span class="sxs-lookup"><span data-stu-id="e1366-190">In Lync Server Control Panel, click **Voice Routing**, and then click **Trunk Configuration**.</span></span>

2.  <span data-ttu-id="e1366-p113">Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e1366-p113">On the **Trunk Configuration** tab, double-click the trunk configuration settings to be modified. Note that you can only edit one collection of settings at a time. If you would like to make the same changes on multiple collections, use Windows PowerShell instead.</span></span>

3.  <span data-ttu-id="e1366-194">Na caixa de diálogo **Editar configuração do tronco** , faça as seleções apropriadas e clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1366-194">In the **Edit Trunk Configuration** dialog, make the appropriate selections and then click **OK**.</span></span>

4.  <span data-ttu-id="e1366-p114">A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.</span><span class="sxs-lookup"><span data-stu-id="e1366-p114">The **State** property for the collection will be updated to **Uncommitted**. To commit the changes, and to delete the collection, click **Commit** and then click **Commit All**.</span></span>

5.  <span data-ttu-id="e1366-197">Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1366-197">In the **Uncommitted Voice Configuration Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="e1366-198">Na caixa de diálogo **Painel de Controle do Microsoft Lync Server 2013**, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1366-198">In the **Microsoft Lync Server 2013 Control Panel** dialog box click **OK**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

