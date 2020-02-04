---
title: 'Lync Server 2013: infraestrutura de chave pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b205699e9efd896a157654f5c1fb200e34087fc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724621"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="60385-102">Infraestrutura de chave pública do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60385-102">Public Key Infrastructure for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60385-103">_**Tópico da última modificação:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="60385-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="60385-104">O Microsoft Lync Server 2013 depende de certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="60385-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="60385-105">O Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003 infraestrutura de chave pública (PKI) fornece a infraestrutura para o estabelecimento e a validação da cadeia de confiança.</span><span class="sxs-lookup"><span data-stu-id="60385-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="60385-p102">Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma AC confiável pelos clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar apenas com outros clientes e servidores de rede privada, a AC pode ser uma AC corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.</span><span class="sxs-lookup"><span data-stu-id="60385-p102">Certificates are digital IDs. They identify a server by name and specify its properties. To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server. If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA. If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="60385-p103">Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.</span><span class="sxs-lookup"><span data-stu-id="60385-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="60385-p104">Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado</span><span class="sxs-lookup"><span data-stu-id="60385-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60385-117">Nem todas as CAs públicas estão em conformidade com os requisitos dos certificados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60385-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="60385-118">Recomendamos que consulte a lista de fornecedores certificados de AC pública para suas necessidades de certificados públicos.</span><span class="sxs-lookup"><span data-stu-id="60385-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="60385-119">Para obter detalhes, consulte parceiros de certificado de <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>comunicação unificada em.</span><span class="sxs-lookup"><span data-stu-id="60385-119">For details, see Unified Communications Certificate Partners at <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="60385-120">Pontos de distribuição das listas de certificados revogados (CRLs)</span><span class="sxs-lookup"><span data-stu-id="60385-120">CRL Distribution Points</span></span>

<span data-ttu-id="60385-121">O Lync Server 2013 requer que todos os certificados do servidor contenham um ou mais pontos de distribuição da lista de certificados revogados (CRL).</span><span class="sxs-lookup"><span data-stu-id="60385-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="60385-122">Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade.</span><span class="sxs-lookup"><span data-stu-id="60385-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="60385-123">Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura.</span><span class="sxs-lookup"><span data-stu-id="60385-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="60385-124">Uso avançado da chave</span><span class="sxs-lookup"><span data-stu-id="60385-124">Enhanced Key Usage</span></span>

<span data-ttu-id="60385-125">O Lync Server 2013 requer que todos os certificados do servidor ofereçam suporte ao uso avançado de chave (EKU) para a finalidade da autenticação do servidor.</span><span class="sxs-lookup"><span data-stu-id="60385-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="60385-126">A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores.</span><span class="sxs-lookup"><span data-stu-id="60385-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="60385-127">Esse EKU é essencial para MTLS.</span><span class="sxs-lookup"><span data-stu-id="60385-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="60385-128">É possível ter mais de uma entrada no EKU, permitindo o uso do certificado para mais de uma finalidade.</span><span class="sxs-lookup"><span data-stu-id="60385-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="60385-129">A EKU de autenticação de cliente é necessária para conexões MTLS de saída do Live Communications Server 2003 e do Live Communications Server 2005, mas não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="60385-129">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required.</span></span> <span data-ttu-id="60385-130">No entanto, esse EKU deve estar presente em servidores de borda que se conectam à AOL por meio de conectividade de mensagens de chat públicas.</span><span class="sxs-lookup"><span data-stu-id="60385-130">However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

