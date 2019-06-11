---
title: 'Lync Server 2013: criptografia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 01c989213b050bdb536e95a8a42e8f7b35292eaf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829233"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="f255c-102">Criptografia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f255c-102">Encryption for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f255c-103">_**Tópico da última modificação:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="f255c-103">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="f255c-104">O Microsoft Lync Server 2013 usa TLS e MTLS para criptografar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="f255c-104">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="f255c-105">Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="f255c-105">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="f255c-106">O TLS é opcional, mas altamente recomendável entre o servidor de mediação e o gateway de mídia.</span><span class="sxs-lookup"><span data-stu-id="f255c-106">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="f255c-107">Se o TLS for configurado neste link, o MTLS será necessário.</span><span class="sxs-lookup"><span data-stu-id="f255c-107">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="f255c-108">Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que seja confiável para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="f255c-108">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f255c-109">Um comunicado de segurança sobre SSL 3.0 foi publicado em 2014.</span><span class="sxs-lookup"><span data-stu-id="f255c-109">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="f255c-110">A desabilitação do SSL 3,0 no Lync Server 2013 é uma opção com suporte.</span><span class="sxs-lookup"><span data-stu-id="f255c-110">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="f255c-111">Para saber mais sobre o comunicado de segurança, <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>consulte.</span><span class="sxs-lookup"><span data-stu-id="f255c-111">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="f255c-113">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="f255c-113">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="f255c-114">Para garantir que o protocolo criptográfico mais forte seja usado, o Lync Server 2013 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="f255c-114">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="f255c-115">O TLS é um aspecto crítico do Lync Server 2013 e, portanto, é necessário para manter um ambiente compatível.</span><span class="sxs-lookup"><span data-stu-id="f255c-115">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="f255c-116">Os requisitos para tráfego de cliente para cliente dependem do fato de o tráfego cruzar o firewall corporativo interno.</span><span class="sxs-lookup"><span data-stu-id="f255c-116">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall.</span></span> <span data-ttu-id="f255c-117">O tráfego interno estrito pode usar o TLS, caso em que a mensagem instantânea está criptografada, ou TCP, e, nesse caso, não é.</span><span class="sxs-lookup"><span data-stu-id="f255c-117">Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="f255c-118">A seguinte tabela resume os requisitos de protocolo para cada tipo de tráfego.</span><span class="sxs-lookup"><span data-stu-id="f255c-118">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="f255c-119">Proteção de Tráfego</span><span class="sxs-lookup"><span data-stu-id="f255c-119">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f255c-120">Tipo de Tráfego</span><span class="sxs-lookup"><span data-stu-id="f255c-120">Traffic type</span></span></th>
<th><span data-ttu-id="f255c-121">Protegido por</span><span class="sxs-lookup"><span data-stu-id="f255c-121">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f255c-122">Servidor para Servidor</span><span class="sxs-lookup"><span data-stu-id="f255c-122">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="f255c-123">MTLS</span><span class="sxs-lookup"><span data-stu-id="f255c-123">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f255c-124">Cliente para Servidor</span><span class="sxs-lookup"><span data-stu-id="f255c-124">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="f255c-125">TLS</span><span class="sxs-lookup"><span data-stu-id="f255c-125">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f255c-126">Mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="f255c-126">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="f255c-127">TLS (se configurado para TLS)</span><span class="sxs-lookup"><span data-stu-id="f255c-127">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f255c-128">Compartilhamento de mídia de áudio, vídeo e de área de trabalho</span><span class="sxs-lookup"><span data-stu-id="f255c-128">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="f255c-129">SRTP</span><span class="sxs-lookup"><span data-stu-id="f255c-129">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f255c-130">Compartilhamento de área de trabalho (sinalização)</span><span class="sxs-lookup"><span data-stu-id="f255c-130">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="f255c-131">TLS</span><span class="sxs-lookup"><span data-stu-id="f255c-131">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f255c-132">Webconferência</span><span class="sxs-lookup"><span data-stu-id="f255c-132">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="f255c-133">TLS</span><span class="sxs-lookup"><span data-stu-id="f255c-133">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f255c-134">Download de conteúdo de reunião, download do catálogo de endereços, expansão de grupo de distribuição</span><span class="sxs-lookup"><span data-stu-id="f255c-134">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="f255c-135">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f255c-135">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="f255c-136">Criptografia de mídia</span><span class="sxs-lookup"><span data-stu-id="f255c-136">Media Encryption</span></span>

<span data-ttu-id="f255c-137">O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP.</span><span class="sxs-lookup"><span data-stu-id="f255c-137">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="f255c-138">Além disso, a mídia que flui em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografada usando SRTP.</span><span class="sxs-lookup"><span data-stu-id="f255c-138">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="f255c-139">A mídia flui em ambas as direções entre o servidor de mediação e um gateway de mídia não é criptografada por padrão.</span><span class="sxs-lookup"><span data-stu-id="f255c-139">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="f255c-140">O Servidor de Mediação pode dar suporte à criptografia para o gateway de mídia, mas o gateway deve dar suporte a MTLS e ao armazenamento de um certificado.</span><span class="sxs-lookup"><span data-stu-id="f255c-140">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f255c-141">Áudio/vídeo (A/V) é compatível com a nova versão do Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="f255c-141">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="f255c-142">Se você estiver implementando a Federação de A/V com o Windows Live Messenger, também deverá modificar o nível de criptografia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f255c-142">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="f255c-143">Por padrão, o nível de criptografia é Exigido.</span><span class="sxs-lookup"><span data-stu-id="f255c-143">By default, the encryption level is Required.</span></span> <span data-ttu-id="f255c-144">Você deve alterar essa configuração para com suporte usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f255c-144">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="f255c-145">Para obter mais informações, consulte Implantando o <A href="lync-server-2013-deploying-external-user-access.md">acesso de usuários externos no Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="f255c-145">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="f255c-146">O tráfego de mídia de áudio e vídeo não é criptografado entre clientes do Microsoft Lync 2013 e do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="f255c-146">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="f255c-147">FIPS</span><span class="sxs-lookup"><span data-stu-id="f255c-147">FIPS</span></span>

<span data-ttu-id="f255c-148">O Lync Server 2013 e o Microsoft Exchange Server 2013 operam com suporte para algoritmos de 140-2 padrão FIPS (Federal Information Processing Standard) se os sistemas operacionais Windows Server estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia do sistema.</span><span class="sxs-lookup"><span data-stu-id="f255c-148">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="f255c-149">Para implementar o suporte a FIPS, você deve configurar cada servidor que está executando o Lync Server 2013 para dar suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="f255c-149">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="f255c-150">Para obter detalhes sobre o uso de algoritmos compatíveis com FIPS e sobre como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento Microsoft, os efeitos de habilitar a segurança "criptografia do sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e assinatura" configuração no Windows XP e em versões posteriores do Windows [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)em.</span><span class="sxs-lookup"><span data-stu-id="f255c-150">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="f255c-151">Para obter detalhes sobre o suporte e as limitações do FIPS 140-2 no Exchange 2010, consulte Exchange 2010 SP1 e suporte para [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335)algoritmos compatíveis com FIPS em.</span><span class="sxs-lookup"><span data-stu-id="f255c-151">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

