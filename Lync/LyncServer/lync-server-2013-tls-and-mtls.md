---
title: 'Lync Server 2013: TLS e MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06938cfb6c37a84de5256feb6e4b370eb36f3702
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="9b8d6-102">TLS e MTLS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9b8d6-102">TLS and MTLS for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9b8d6-103">_**Tópico da última modificação:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="9b8d6-103">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="9b8d6-104">Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-104">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="9b8d6-105">O Microsoft Lync Server 2013 usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações na rede sejam criptografadas.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-105">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="9b8d6-106">Todas as comunicações SIP entre servidores ocorrem no MTLS.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-106">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="9b8d6-107">As comunicações SIP entre o cliente e o servidor ocorrem no TLS.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-107">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="9b8d6-108">O TLS permite que os usuários, por meio do software cliente, autentiquem os servidores do Lync Server 2013 aos quais se conectam.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-108">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="9b8d6-109">Em uma conexão TLS, o cliente solicita um certificado válido do servidor.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-109">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="9b8d6-110">Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-110">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="9b8d6-111">Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-111">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="9b8d6-112">A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-112">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="9b8d6-113">Nesse contexto, a Secure Sockets Layer (SSL), conforme utilizada com serviços os Web, pode ser associada ao protocolo baseado em TLS.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-113">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="9b8d6-114">Conexões de servidor para servidor baseiam-se em MTLS para autenticação mútua.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-114">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="9b8d6-115">Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-115">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="9b8d6-116">Os certificados comprovam a identidade de cada servidor ao outro.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-116">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="9b8d6-117">Nas implantações do Lync Server 2013, os certificados emitidos pela CA corporativa que estão durante o período de validade e não revogados pela CA de emissão são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um domínio do Active Directory confiar na CA corporativa nesse domínio.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-117">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="9b8d6-118">Em cenários federados, a AC emissora deve ser confiável por ambos os parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-118">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="9b8d6-119">Cada parceiro pode usar uma AC diferente, se desejado, contanto que a AC também seja considerada confiável pelo outro parceiro.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-119">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="9b8d6-120">Essa confiabilidade é mais facilmente assegurada pelos Servidores de Borda que possuem o certificado da AC raiz dos parceiros em suas ACs raiz confiáveis ou pelo uso de uma AC de terceiro que seja considerada confiável pelas duas partes.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-120">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="9b8d6-121">O TLS e MTLS ajudam a evitar a espionagem e ataques a intermediários.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-121">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="9b8d6-122">Em um ataque a intermediários, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor, sem o conhecimento das partes.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-122">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="9b8d6-123">A especificação do TLS e do Lync Server 2013 de servidores confiáveis (somente aqueles especificados no construtor de topologia) reduzem o risco de um ataque man-in-the Middle parcialmente na camada do aplicativo usando a criptografia ponto a ponto coordenada usando a criptografia de chave pública entre os dois pontos de extremidade, e um invasor precisa ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-123">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="9b8d6-124">Em última análise, entretanto, você deve cumprir as práticas recomendadas de segurança em sua infraestrutura de rede (no caso de um DNS corporativo).</span><span class="sxs-lookup"><span data-stu-id="9b8d6-124">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="9b8d6-125">O Lync Server 2013 pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e os catálogos globais são confiáveis, mas o DNS fornece um nível de segurança contra ataques de seqüestro de DNS impedindo que o servidor de um invasor responda com êxito a um solicitação ao nome falso.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-125">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="9b8d6-126">A figura a seguir mostra em alto nível como o Lync Server 2013 usa a MTLS para criar uma rede de servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="9b8d6-126">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="9b8d6-127">**Conexões confiáveis em uma rede do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="9b8d6-127">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="9b8d6-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="9b8d6-128">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

