---
title: 'Lync Server 2013: TLS e MTLS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TLS and MTLS for Lync Server 2013
ms:assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481133(v=OCS.15)
ms:contentKeyID: 59893873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 066612f08c61ad1df342b4f2dd9b61ff5a5cc286
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS e MTLS para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-07_

Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Microsoft Lync Server 2013 usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações na rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.

O TLS permite que os usuários, por meio do software cliente, autentiquem os servidores do Lync Server 2013 aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável. Nesse contexto, a Secure Sockets Layer (SSL), conforme utilizada com serviços os Web, pode ser associada ao protocolo baseado em TLS.

Conexões de servidor para servidor baseiam-se em MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável. Os certificados comprovam a identidade de cada servidor ao outro. Nas implantações do Lync Server 2013, os certificados emitidos pela CA corporativa que estão durante o período de validade e não revogados pela CA de emissão são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um domínio do Active Directory confiar na CA corporativa nesse domínio. Em cenários federados, a AC emissora deve ser confiável por ambos os parceiros federados. Cada parceiro pode usar uma AC diferente, se desejado, contanto que a AC também seja considerada confiável pelo outro parceiro. Essa confiabilidade é mais facilmente assegurada pelos Servidores de Borda que possuem o certificado da AC raiz dos parceiros em suas ACs raiz confiáveis ou pelo uso de uma AC de terceiro que seja considerada confiável pelas duas partes.

O TLS e MTLS ajudam a evitar a espionagem e ataques a intermediários. Em um ataque a intermediários, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor, sem o conhecimento das partes. A especificação do TLS e do Lync Server 2013 de servidores confiáveis (somente aqueles especificados no construtor de topologia) reduzem o risco de um ataque man-in-the Middle parcialmente na camada do aplicativo usando a criptografia ponto a ponto coordenada usando a criptografia de chave pública entre os dois pontos de extremidade, e um invasor precisa ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. Em última análise, entretanto, você deve cumprir as práticas recomendadas de segurança em sua infraestrutura de rede (no caso de um DNS corporativo). O Lync Server 2013 pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e os catálogos globais são confiáveis, mas o DNS fornece um nível de segurança contra ataques de seqüestro de DNS impedindo que o servidor de um invasor responda com êxito a um solicitação ao nome falso.

A figura a seguir mostra em alto nível como o Lync Server 2013 usa a MTLS para criar uma rede de servidores confiáveis.

**Conexões confiáveis em uma rede do Lync Server**

![437749da-C372-4f0d-ac72-ccfd5191696b] (images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-C372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

