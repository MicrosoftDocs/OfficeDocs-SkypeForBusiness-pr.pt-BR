---
title: 'Lync Server 2013: criptografia'
description: 'Lync Server 2013: criptografia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Encryption for Lync Server 2013
ms:assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481135(v=OCS.15)
ms:contentKeyID: 59893874
ms.date: 09/14/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab2c46af16cfdbb9a01631777e65219acb2ceb2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575647"
---
# <a name="encryption-for-lync-server-2013"></a><span data-ttu-id="9e54b-103">Criptografia para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e54b-103">Encryption for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e54b-104">_**Última modificação do tópico:** 2017-09-14_</span><span class="sxs-lookup"><span data-stu-id="9e54b-104">_**Topic Last Modified:** 2017-09-14_</span></span>

<span data-ttu-id="9e54b-105">O Microsoft Lync Server 2013 usa TLS e MTLS para criptografar mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="9e54b-105">Microsoft Lync Server 2013 uses TLS and MTLS to encrypt instant messages.</span></span> <span data-ttu-id="9e54b-106">Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego ter sido confinado na rede interna ou cruzar o perímetro da rede interna.</span><span class="sxs-lookup"><span data-stu-id="9e54b-106">All server-to-server traffic requires MTLS, regardless of whether the traffic is confined to the internal network or crosses the internal network perimeter.</span></span> <span data-ttu-id="9e54b-107">O TLS é opcional, mas é altamente recomendável entre o servidor de mediação e o gateway de mídia.</span><span class="sxs-lookup"><span data-stu-id="9e54b-107">TLS is optional but strongly recommended between the Mediation Server and media gateway.</span></span> <span data-ttu-id="9e54b-108">Se o TLS estiver configurado nesse link, MTLS será necessário.</span><span class="sxs-lookup"><span data-stu-id="9e54b-108">If TLS is configured on this link, MTLS is required.</span></span> <span data-ttu-id="9e54b-109">Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que é confiável para o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9e54b-109">Therefore, the gateway must be configured with a certificate from a CA that is trusted by the Mediation Server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e54b-110">Um comunicado de segurança sobre SSL 3,0 foi publicado no 2014.</span><span class="sxs-lookup"><span data-stu-id="9e54b-110">A security advisory regarding SSL 3.0 was published in 2014.</span></span> <span data-ttu-id="9e54b-111">A desabilitação do SSL 3,0 no Lync Server 2013 é uma opção com suporte.</span><span class="sxs-lookup"><span data-stu-id="9e54b-111">Disabling SSL 3.0 in Lync Server 2013 is a supported option.</span></span> <span data-ttu-id="9e54b-112">Para saber mais sobre o comunicado de segurança, consulte <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A> .</span><span class="sxs-lookup"><span data-stu-id="9e54b-112">To learn more about the security advisory, see <A class=uri href="https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/">https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/</A>.</span></span>



</div>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="9e54b-114">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="9e54b-114">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="9e54b-115">Para garantir que o protocolo criptográfico mais forte seja usado, o Lync Server 2013 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: <strong>TLS 1,2</strong> , <strong>TLS 1,1</strong>, <strong>TLS 1,0</strong>.</span><span class="sxs-lookup"><span data-stu-id="9e54b-115">To ensure the strongest cryptographic protocol is used, Lync Server 2013 will offer TLS encryption protocols in the following order to clients: <strong>TLS 1.2</strong> , <strong>TLS 1.1</strong>, <strong>TLS 1.0</strong>.</span></span> <span data-ttu-id="9e54b-116">O TLS é um aspecto crítico do Lync Server 2013 e, portanto, é necessário para manter um ambiente com suporte.</span><span class="sxs-lookup"><span data-stu-id="9e54b-116">TLS is a critical aspect of Lync Server 2013 and thus it is required in order to maintain a supported environment.</span></span></td>
</tr>
</tbody>
</table>


</div>

<span data-ttu-id="9e54b-p104">Os requisitos do tráfego de cliente para cliente depende de o tráfego atravessar ou não o firewall corporativo interno. O tráfego estritamente interno pode usar o TLS (as mensagens instantâneas são criptografadas) ou o TCP (as mensagens instantâneas não são criptografadas).</span><span class="sxs-lookup"><span data-stu-id="9e54b-p104">Requirements for client-to-client traffic depend on whether that traffic crosses the internal corporate firewall. Strictly internal traffic can use either TLS, in which case the instant message is encrypted, or TCP, in which case it is not.</span></span>

<span data-ttu-id="9e54b-119">A tabela a seguir resume os requisitos de protocolo de cada tipo de tráfego.</span><span class="sxs-lookup"><span data-stu-id="9e54b-119">The following table summarizes the protocol requirements for each type of traffic.</span></span>

### <a name="traffic-protection"></a><span data-ttu-id="9e54b-120">Proteção de tráfego</span><span class="sxs-lookup"><span data-stu-id="9e54b-120">Traffic Protection</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9e54b-121">Tipo de tráfego</span><span class="sxs-lookup"><span data-stu-id="9e54b-121">Traffic type</span></span></th>
<th><span data-ttu-id="9e54b-122">Protegido por</span><span class="sxs-lookup"><span data-stu-id="9e54b-122">Protected by</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9e54b-123">Servidor para servidor</span><span class="sxs-lookup"><span data-stu-id="9e54b-123">Server-to-server</span></span></p></td>
<td><p><span data-ttu-id="9e54b-124">MTLS</span><span class="sxs-lookup"><span data-stu-id="9e54b-124">MTLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e54b-125">Cliente para servidor</span><span class="sxs-lookup"><span data-stu-id="9e54b-125">Client-to-server</span></span></p></td>
<td><p><span data-ttu-id="9e54b-126">TLS</span><span class="sxs-lookup"><span data-stu-id="9e54b-126">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e54b-127">Sistema de mensagens instantâneas e presença</span><span class="sxs-lookup"><span data-stu-id="9e54b-127">Instant messaging and presence</span></span></p></td>
<td><p><span data-ttu-id="9e54b-128">TLS (se configurado para TLS)</span><span class="sxs-lookup"><span data-stu-id="9e54b-128">TLS (if configured for TLS)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e54b-129">Compartilhamento de área de trabalho, áudio e vídeo da mídia</span><span class="sxs-lookup"><span data-stu-id="9e54b-129">Audio and video and desktop sharing of media</span></span></p></td>
<td><p><span data-ttu-id="9e54b-130">SRTP</span><span class="sxs-lookup"><span data-stu-id="9e54b-130">SRTP</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e54b-131">Compartilhamento de área de trabalho (sinalização)</span><span class="sxs-lookup"><span data-stu-id="9e54b-131">Desktop sharing (signaling)</span></span></p></td>
<td><p><span data-ttu-id="9e54b-132">TLS</span><span class="sxs-lookup"><span data-stu-id="9e54b-132">TLS</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9e54b-133">Webconferência</span><span class="sxs-lookup"><span data-stu-id="9e54b-133">Web conferencing</span></span></p></td>
<td><p><span data-ttu-id="9e54b-134">TLS</span><span class="sxs-lookup"><span data-stu-id="9e54b-134">TLS</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9e54b-135">Download do conteúdo das reuniões, download do catálogo de endereços, expansão de grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="9e54b-135">Meeting content download, address book download, distribution group expansion</span></span></p></td>
<td><p><span data-ttu-id="9e54b-136">HTTPS</span><span class="sxs-lookup"><span data-stu-id="9e54b-136">HTTPS</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="media-encryption"></a><span data-ttu-id="9e54b-137">Criptografia da mídia</span><span class="sxs-lookup"><span data-stu-id="9e54b-137">Media Encryption</span></span>

<span data-ttu-id="9e54b-138">O tráfego de mídia é criptografado usando SRTP, um perfil de protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataque de repetição para o tráfego RTP.</span><span class="sxs-lookup"><span data-stu-id="9e54b-138">Media traffic is encrypted using Secure RTP (SRTP), a profile of Real-Time Transport Protocol (RTP) that provides confidentiality, authentication, and replay attack protection to RTP traffic.</span></span> <span data-ttu-id="9e54b-139">Além disso, a mídia que flui em ambas as direções entre o servidor de mediação e seu próximo nó interno também é criptografada usando o SRTP.</span><span class="sxs-lookup"><span data-stu-id="9e54b-139">In addition, media flowing in both directions between the Mediation Server and its internal next hop is also encrypted using SRTP.</span></span> <span data-ttu-id="9e54b-140">O fluxo de mídia em ambas as direções entre o servidor de mediação e um gateway de mídia não é criptografado por padrão.</span><span class="sxs-lookup"><span data-stu-id="9e54b-140">Media flowing in both directions between the Mediation Server and a media gateway is not encrypted by default.</span></span> <span data-ttu-id="9e54b-141">O Servidor de Mediação pode oferecer suporte à criptografia para o gateway de mídia, mas o gateway deve oferecer suporte ao MTLS e ao armazenamento de um certificado.</span><span class="sxs-lookup"><span data-stu-id="9e54b-141">The Mediation Server can support encryption to the media gateway, but the gateway must support MTLS and storage of a certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9e54b-142">Áudio/vídeo (A/V) é compatível com a nova versão do Windows Live Messenger.</span><span class="sxs-lookup"><span data-stu-id="9e54b-142">Audio/Video (A/V) is supported with the new version of Windows Live Messenger.</span></span> <span data-ttu-id="9e54b-143">Se você estiver implementando uma federação A/V com Windows Live Messenger, também deverá modificar o nível de criptografia do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e54b-143">If you are implementing A/V federation with Windows Live Messenger, you must also modify the Lync Server encryption level.</span></span> <span data-ttu-id="9e54b-144">Por padrão, o nível de criptografia é Obrigatório.</span><span class="sxs-lookup"><span data-stu-id="9e54b-144">By default, the encryption level is Required.</span></span> <span data-ttu-id="9e54b-145">Você deve alterar essa configuração para suportado usando o Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9e54b-145">You must change this setting to Supported by using the Lync Server Management Shell.</span></span> <span data-ttu-id="9e54b-146">Para obter mais informações, consulte <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A> na documentação de implantação.</span><span class="sxs-lookup"><span data-stu-id="9e54b-146">For more information, see <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="9e54b-147">O tráfego de mídia de áudio e vídeo não é criptografado entre os clientes do Microsoft Lync 2013 e do Windows Live.</span><span class="sxs-lookup"><span data-stu-id="9e54b-147">Audio and video media traffic is not encrypted between Microsoft Lync 2013 and Windows Live clients.</span></span>

</div>

<div>

## <a name="fips"></a><span data-ttu-id="9e54b-148">FIPS</span><span class="sxs-lookup"><span data-stu-id="9e54b-148">FIPS</span></span>

<span data-ttu-id="9e54b-149">O Lync Server 2013 e o Microsoft Exchange Server 2013 operam com suporte para algoritmos normativos FIPS (Federal Information Processing Standard 140-2) se os sistemas operacionais Windows Server estiverem configurados para usar os algoritmos FIPS 140-2 para criptografia de sistema.</span><span class="sxs-lookup"><span data-stu-id="9e54b-149">Lync Server 2013 and Microsoft Exchange Server 2013 operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="9e54b-150">Para implementar o suporte a FIPS, você deve configurar cada servidor executando o Lync Server 2013 para dar suporte a ele.</span><span class="sxs-lookup"><span data-stu-id="9e54b-150">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="9e54b-151">Para obter detalhes sobre o uso de algoritmos compatíveis com FIPS e sobre como implementar o suporte a FIPS, consulte o artigo 811833 da base de dados de conhecimento da Microsoft, os efeitos da habilitação da configuração de segurança "criptografia de sistema: usar algoritmos compatíveis com FIPS para criptografia, hash e assinatura" no Windows XP e em versões posteriores do Windows em [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="9e54b-151">For details about the use of FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, The effects of enabling the “System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing" security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="9e54b-152">Para obter detalhes sobre o suporte a FIPS 140-2 e limitações no Exchange 2010, consulte Exchange 2010 SP1 e suporte para algoritmos compatíveis com FIPS em [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="9e54b-152">For details about FIPS 140-2 support and limitations in Exchange 2010, see Exchange 2010 SP1 and Support for FIPS Compliant Algorithms at [https://go.microsoft.com/fwlink/p/?LinkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

