---
title: 'Lync Server 2013: TLS e MTLS'
description: 'Lync Server 2013: TLS e MTLS.'
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
ms.openlocfilehash: a0ccee47e635435dd5f0d5eae03711c0cd5e517b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541787"
---
# <a name="tls-and-mtls-for-lync-server-2013"></a><span data-ttu-id="f7102-103">TLS e MTLS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f7102-103">TLS and MTLS for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7102-104">_**Última modificação do tópico:** 2013-11-07_</span><span class="sxs-lookup"><span data-stu-id="f7102-104">_**Topic Last Modified:** 2013-11-07_</span></span>

<span data-ttu-id="f7102-105">Os protocolos de segurança de camada de transporte (TLS) e de protocolo MTLS fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet.</span><span class="sxs-lookup"><span data-stu-id="f7102-105">Transport Layer Security (TLS) and Mutual Transport Layer Security (MTLS) protocols provide encrypted communications and endpoint authentication on the Internet.</span></span> <span data-ttu-id="f7102-106">O Microsoft Lync Server 2013 usa esses dois protocolos para criar a rede de servidores confiáveis e para garantir que todas as comunicações nessa rede sejam criptografadas.</span><span class="sxs-lookup"><span data-stu-id="f7102-106">Microsoft Lync Server 2013 uses these two protocols to create the network of trusted servers and to ensure that all communications over that network are encrypted.</span></span> <span data-ttu-id="f7102-107">Todas as comunicações SIP entre servidores ocorrem através de MTLS.</span><span class="sxs-lookup"><span data-stu-id="f7102-107">All SIP communications between servers occur over MTLS.</span></span> <span data-ttu-id="f7102-108">Comunicações SIP de cliente para servidor ocorrem em TLS.</span><span class="sxs-lookup"><span data-stu-id="f7102-108">SIP communications from client to server occur over TLS.</span></span>

<span data-ttu-id="f7102-109">O TLS habilita usuários, através do software cliente, para autenticar os servidores do Lync Server 2013 aos quais eles se conectam.</span><span class="sxs-lookup"><span data-stu-id="f7102-109">TLS enables users, through their client software, to authenticate the Lync Server 2013 servers to which they connect.</span></span> <span data-ttu-id="f7102-110">Em uma conexão TLS, o cliente solicita um certificado válido do servidor.</span><span class="sxs-lookup"><span data-stu-id="f7102-110">On a TLS connection, the client requests a valid certificate from the server.</span></span> <span data-ttu-id="f7102-111">Para ser válido, o certificado deve ter sido emitido por uma autoridade de certificação que também é confiável pelo cliente e o nome DNS do servidor deve corresponder ao nome DNS no certificado.</span><span class="sxs-lookup"><span data-stu-id="f7102-111">To be valid, the certificate must have been issued by a CA that is also trusted by the client and the DNS name of the server must match the DNS name on the certificate.</span></span> <span data-ttu-id="f7102-112">Se o certificado for válido, o cliente usará a chave pública no certificado para criptografar as chaves de criptografia simétrica a serem usadas para a comunicação, de modo que somente o proprietário original do certificado possa usar sua chave privada para descriptografar o conteúdo da comunicação.</span><span class="sxs-lookup"><span data-stu-id="f7102-112">If the certificate is valid, the client uses the public key in the certificate to encrypt the symmetric encryption keys to be used for the communication, so only the original owner of the certificate can use its private key to decrypt the contents of the communication.</span></span> <span data-ttu-id="f7102-113">A conexão resultante é confiável e, a partir desse ponto, não é desafiada por outros clientes ou servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f7102-113">The resulting connection is trusted and from that point is not challenged by other trusted servers or clients.</span></span> <span data-ttu-id="f7102-114">Dentro desse contexto, o SSL (Secure Sockets Layer) conforme usado com os serviços Web pode ser associado como baseado em TLS.</span><span class="sxs-lookup"><span data-stu-id="f7102-114">Within this context, Secure Sockets Layer (SSL) as used with Web services can be associated as TLS-based.</span></span>

<span data-ttu-id="f7102-115">Conexões de servidor para servidor dependem de MTLS para autenticação mútua.</span><span class="sxs-lookup"><span data-stu-id="f7102-115">Server-to-server connections rely on MTLS for mutual authentication.</span></span> <span data-ttu-id="f7102-116">Em uma conexão MTLS, o servidor que originou uma mensagem e o servidor que a recebe certificados de uma AC mutuamente confiável.</span><span class="sxs-lookup"><span data-stu-id="f7102-116">On an MTLS connection, the server originating a message and the server receiving it exchange certificates from a mutually trusted CA.</span></span> <span data-ttu-id="f7102-117">Os certificados comprovam a identidade de cada servidor para o outro.</span><span class="sxs-lookup"><span data-stu-id="f7102-117">The certificates prove the identity of each server to the other.</span></span> <span data-ttu-id="f7102-118">Nas implantações do Lync Server 2013, os certificados emitidos pela autoridade de certificação corporativa que estão durante seu período de validade e não são revogados pela autoridade de certificação emissora são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um domínio do Active Directory confiam na autoridade de certificação corporativa desse domínio.</span><span class="sxs-lookup"><span data-stu-id="f7102-118">In Lync Server 2013 deployments, certificates issued by the enterprise CA that are during their validity period and not revoked by the issuing CA are automatically considered valid by all internal clients and servers because all members of an Active Directory domain trust the Enterprise CA in that domain.</span></span> <span data-ttu-id="f7102-119">Em cenários federados, a CA de emissão deve ser confiável para os parceiros federados.</span><span class="sxs-lookup"><span data-stu-id="f7102-119">In federated scenarios, the issuing CA must be trusted by both federated partners.</span></span> <span data-ttu-id="f7102-120">Cada parceiro pode usar uma autoridade de certificação diferente, se desejado, desde que a autoridade de certificação também seja confiável para o outro parceiro.</span><span class="sxs-lookup"><span data-stu-id="f7102-120">Each partner can use a different CA, if desired, so long as that CA is also trusted by the other partner.</span></span> <span data-ttu-id="f7102-121">Essa relação de confiança é realizada com facilidade pelos servidores de borda com o certificado de autoridade de certificação raiz do parceiro em suas autoridades de certificação raiz confiáveis ou por meio de uma CA de terceiros que é confiável para ambas as partes.</span><span class="sxs-lookup"><span data-stu-id="f7102-121">This trust is most easily accomplished by the Edge Servers having the partner’s root CA certificate in their trusted root CAs, or by use of a third-party CA that is trusted by both parties.</span></span>

<span data-ttu-id="f7102-122">O TLS e a MTLS ajudam a evitar ataques de espionagem e de interceptação.</span><span class="sxs-lookup"><span data-stu-id="f7102-122">TLS and MTLS help prevent both eavesdropping and man-in-the middle attacks.</span></span> <span data-ttu-id="f7102-123">Em um ataque man-in-the-Middle, o invasor redireciona as comunicações entre duas entidades de rede através do computador do invasor sem o conhecimento de ambas as partes.</span><span class="sxs-lookup"><span data-stu-id="f7102-123">In a man-in-the-middle attack, the attacker reroutes communications between two network entities through the attacker’s computer without the knowledge of either party.</span></span> <span data-ttu-id="f7102-124">A especificação TLS e Lync Server 2013 de servidores confiáveis (somente aqueles especificados no construtor de topologias) reduzem o risco de um ataque man-in-the-Middle parcialmente na camada de aplicativo usando a criptografia de ponta a ponta coordenada usando a criptografia de chave pública entre os dois pontos de extremidade, e um invasor precisa ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço para o qual o cliente está se comunicando para descriptografar a comunicação.</span><span class="sxs-lookup"><span data-stu-id="f7102-124">TLS and Lync Server 2013 specification of trusted servers (only those specified in Topology Builder) mitigate the risk of a man-in-the middle attack partially on the application layer by using end-to-end encryption coordinated using the Public Key cryptography between the two endpoints, and an attacker would have to have a valid and trusted certificate with the corresponding private key and issued to the name of the service to which the client is communicating to decrypt the communication.</span></span> <span data-ttu-id="f7102-125">No entanto, você deve seguir as práticas recomendadas de segurança com sua infraestrutura de rede (neste caso, o DNS corporativo).</span><span class="sxs-lookup"><span data-stu-id="f7102-125">Ultimately, however, you must follow best security practices with your networking infrastructure (in this case corporate DNS).</span></span> <span data-ttu-id="f7102-126">O Lync Server 2013 pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e catálogos globais são confiáveis, mas o DNS fornece um nível de proteção contra ataques de seqüestro de DNS, impedindo que o servidor de um invasor responda com êxito a uma solicitação para o nome falsificado.</span><span class="sxs-lookup"><span data-stu-id="f7102-126">Lync Server 2013 assumes that the DNS server is trusted in the same way that domain controllers and global catalogs are trusted, but DNS does provide a level of safeguard against DNS hijack attacks by preventing an attacker’s server from responding successfully to a request to the spoofed name.</span></span>

<span data-ttu-id="f7102-127">A figura a seguir mostra em um nível alto como o Lync Server 2013 usa MTLS para criar uma rede de servidores confiáveis.</span><span class="sxs-lookup"><span data-stu-id="f7102-127">The following figure shows at a high level how Lync Server 2013 uses MTLS to create a network of trusted servers.</span></span>

<span data-ttu-id="f7102-128">**Conexões confiáveis em uma rede do Lync Server**</span><span class="sxs-lookup"><span data-stu-id="f7102-128">**Trusted connections in a Lync Server network**</span></span>

<span data-ttu-id="f7102-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span><span class="sxs-lookup"><span data-stu-id="f7102-129">![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

