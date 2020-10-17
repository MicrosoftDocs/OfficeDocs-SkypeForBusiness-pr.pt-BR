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
ms.openlocfilehash: 7cee633f877a34dcf2ec0fd0b98891c62faf0bad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512408"
---
# <a name="public-key-infrastructure-for-lync-server-2013"></a><span data-ttu-id="8c039-102">Infraestrutura de chave pública do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8c039-102">Public Key Infrastructure for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8c039-103">_**Última modificação do tópico:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="8c039-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="8c039-104">O Microsoft Lync Server 2013 depende de certificados para autenticação de servidor e estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor.</span><span class="sxs-lookup"><span data-stu-id="8c039-104">Microsoft Lync Server 2013 relies on certificates for server authentication and to establish a chain of trust between clients and servers and among the different server roles.</span></span> <span data-ttu-id="8c039-105">O Windows Server 2012 R2, o Windows Server 2012, o Windows Server 2008 R2, o Windows Server 2008 e o Windows Server 2003 infraestrutura de chave pública (PKI) fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.</span><span class="sxs-lookup"><span data-stu-id="8c039-105">The Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008, and Windows Server 2003 Public Key Infrastructure (PKI) provides the infrastructure for establishing and validating this chain of trust.</span></span>

<span data-ttu-id="8c039-106">Os certificados são IDs digitais.</span><span class="sxs-lookup"><span data-stu-id="8c039-106">Certificates are digital IDs.</span></span> <span data-ttu-id="8c039-107">Eles identificam um servidor por nome e especificam suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="8c039-107">They identify a server by name and specify its properties.</span></span> <span data-ttu-id="8c039-108">Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma autoridade de certificação que é confiável para clientes ou outros servidores que se conectam ao servidor.</span><span class="sxs-lookup"><span data-stu-id="8c039-108">To ensure that the information on a certificate is valid, the certificate must be issued by a CA that is trusted by clients or other servers that connect to the server.</span></span> <span data-ttu-id="8c039-109">Se o servidor se conectar somente com outros clientes e servidores em uma rede privada, a CA poderá ser uma CA empresarial.</span><span class="sxs-lookup"><span data-stu-id="8c039-109">If the server connects only with other clients and servers on a private network, the CA can be an enterprise CA.</span></span> <span data-ttu-id="8c039-110">Se o servidor interagir com entidades fora da rede privada, uma CA pública poderá ser necessária.</span><span class="sxs-lookup"><span data-stu-id="8c039-110">If the server interacts with entities outside the private network, a public CA might be required.</span></span>

<span data-ttu-id="8c039-p103">Mesmo que as informações de um certificado sejam válidas, deve haver alguma forma de verificar se o servidor que está apresentando o certificado é realmente o representado pelo certificado. É aqui que a PKI do Windows entra em ação.</span><span class="sxs-lookup"><span data-stu-id="8c039-p103">Even if the information on the certificate is valid, there must be some way to verify that the server presenting the certificate is actually the one represented by the certificate. This is where the Windows PKI comes in.</span></span>

<span data-ttu-id="8c039-p104">Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado retém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar uma parte aleatória das informações e enviá-la ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão poderá ter a certeza de que o servidor retém a chave privada para o certificado e, portanto, é o servidor nomeado no certificado.</span><span class="sxs-lookup"><span data-stu-id="8c039-p104">Each certificate is linked to a public key. The server named on the certificate holds a corresponding private key that only it knows. A connecting client or server uses the public key to encrypt a random piece of information and sends it to the server. If the server decrypts the information and returns it as plain text, the connecting entity can be sure that the server holds the private key to the certificate and therefore is the server named on the certificate.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c039-117">Nem todas as CAs públicas estão em conformidade com os requisitos dos certificados do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8c039-117">Not all public CAs comply with the requirements of Lync Server 2013 certificates.</span></span> <span data-ttu-id="8c039-118">Recomendamos a consulta à lista de fornecedores certificados de CA pública para suas necessidades de certificado público.</span><span class="sxs-lookup"><span data-stu-id="8c039-118">We recommend that you refer to the listing of certified Public CA vendors for your public certificate needs.</span></span> <span data-ttu-id="8c039-119">Para obter detalhes, consulte Unified Communications Certificate Partners em <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A> .</span><span class="sxs-lookup"><span data-stu-id="8c039-119">For details, see Unified Communications Certificate Partners at <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>.</span></span>



</div>

<div>

## <a name="crl-distribution-points"></a><span data-ttu-id="8c039-120">Pontos de distribuição de CRL</span><span class="sxs-lookup"><span data-stu-id="8c039-120">CRL Distribution Points</span></span>

<span data-ttu-id="8c039-121">O Lync Server 2013 requer que todos os certificados de servidor contenham um ou mais pontos de distribuição de CRL (lista de certificados revogados).</span><span class="sxs-lookup"><span data-stu-id="8c039-121">Lync Server 2013 requires all server certificates to contain one or more Certificate Revocation List (CRL) distribution points.</span></span> <span data-ttu-id="8c039-122">CDPs (Pontos de distribuição de CRL) são locais a partir dos quais os CRLs podem ser baixados para verificar se o certifico não foi revogado desde que foi emitido e se ainda está dentro do período de validade.</span><span class="sxs-lookup"><span data-stu-id="8c039-122">CRL distribution points (CDPs) are locations from which CRLs can be downloaded for purposes of verifying that the certificate has not been revoked since the time it was issued and the certificate is still within the validity period.</span></span> <span data-ttu-id="8c039-123">Um ponto de distribuição da lista de certificados revogados é especificado nas propriedades do certificado como uma URL e, geralmente, é um HTTP seguro.</span><span class="sxs-lookup"><span data-stu-id="8c039-123">A CRL distribution point is noted in the properties of the certificate as a URL, and is typically secure HTTP.</span></span>

</div>

<div>

## <a name="enhanced-key-usage"></a><span data-ttu-id="8c039-124">Uso avançado de chave</span><span class="sxs-lookup"><span data-stu-id="8c039-124">Enhanced Key Usage</span></span>

<span data-ttu-id="8c039-125">O Lync Server 2013 requer que todos os certificados do servidor ofereçam suporte a EKU (uso avançado de chave) para fins de autenticação de servidor.</span><span class="sxs-lookup"><span data-stu-id="8c039-125">Lync Server 2013 requires all server certificates to support Enhanced Key Usage (EKU) for the purpose of server authentication.</span></span> <span data-ttu-id="8c039-126">A configuração do campo de EKU para autenticação de servidor significa que o certificado é válido para fins de autenticação de servidores.</span><span class="sxs-lookup"><span data-stu-id="8c039-126">Configuring the EKU field for server authentication means that the certificate is valid for the purpose of authenticating servers.</span></span> <span data-ttu-id="8c039-127">Esse EKU é essencial para o MTLS.</span><span class="sxs-lookup"><span data-stu-id="8c039-127">This EKU is essential for MTLS.</span></span> <span data-ttu-id="8c039-128">É possível ter mais de uma entrada no EKU, o que habilitará o certificado a mais de uma finalidade.</span><span class="sxs-lookup"><span data-stu-id="8c039-128">It is possible to have more than one entry in the EKU, enabling the certificate for more than one purpose.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8c039-p108">O EKU de Autenticação de Cliente é necessário para conexões MTLS de saída no Live Communications Server 2003 e Live Communications Server 2005, mas ele não é mais obrigatório. No entanto, esse EKU deve estar presente nos Servidores de Borda que se conectam ao AOL por meio da conectividade a redes públicas de mensagens instantâneas.</span><span class="sxs-lookup"><span data-stu-id="8c039-p108">The Client Authentication EKU is required for outbound MTLS connections from Live Communications Server 2003 and Live Communications Server 2005, but it is no longer required. However, this EKU must be present on Edge Servers that connect to AOL by means of public IM connectivity.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

