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
ms.openlocfilehash: 262cd9d165a6656742a15e26513e5e8ea8bf3db7
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42141177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="tls-and-mtls-for-lync-server-2013"></a>TLS e MTLS para o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-07_

Os protocolos de segurança de camada de transporte (TLS) e de protocolo MTLS fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Microsoft Lync Server 2013 usa esses dois protocolos para criar a rede de servidores confiáveis e para garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem através de MTLS. Comunicações SIP de cliente para servidor ocorrem em TLS.

O TLS habilita usuários, através do software cliente, para autenticar os servidores do Lync Server 2013 aos quais eles se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ter sido emitido por uma autoridade de certificação que também é confiável pelo cliente e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usará a chave pública no certificado para criptografar as chaves de criptografia simétrica a serem usadas para a comunicação, de modo que somente o proprietário original do certificado possa usar sua chave privada para descriptografar o conteúdo da comunicação. A conexão resultante é confiável e, a partir desse ponto, não é desafiada por outros clientes ou servidores confiáveis. Dentro desse contexto, o SSL (Secure Sockets Layer) conforme usado com os serviços Web pode ser associado como baseado em TLS.

Conexões de servidor para servidor dependem de MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que originou uma mensagem e o servidor que a recebe certificados de uma AC mutuamente confiável. Os certificados comprovam a identidade de cada servidor para o outro. Nas implantações do Lync Server 2013, os certificados emitidos pela autoridade de certificação corporativa que estão durante seu período de validade e não são revogados pela autoridade de certificação emissora são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um domínio do Active Directory Confie na autoridade de certificação corporativa nesse domínio. Em cenários federados, a CA de emissão deve ser confiável para os parceiros federados. Cada parceiro pode usar uma autoridade de certificação diferente, se desejado, desde que a autoridade de certificação também seja confiável para o outro parceiro. Essa relação de confiança é realizada com facilidade pelos servidores de borda com o certificado de autoridade de certificação raiz do parceiro em suas autoridades de certificação raiz confiáveis ou por meio de uma CA de terceiros que é confiável para ambas as partes.

O TLS e a MTLS ajudam a evitar ataques de espionagem e de interceptação. Em um ataque man-in-the-Middle, o invasor redireciona as comunicações entre duas entidades de rede através do computador do invasor sem o conhecimento de ambas as partes. A especificação TLS e Lync Server 2013 de servidores confiáveis (somente aqueles especificados no construtor de topologias) reduzem o risco de um ataque de interceptação de um homem parcialmente na camada de aplicativo usando a criptografia de ponta a ponta coordenada usando a criptografia de chave pública entre os dois pontos de extremidade, e um invasor precisa ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. No entanto, você deve seguir as práticas recomendadas de segurança com sua infraestrutura de rede (neste caso, o DNS corporativo). O Lync Server 2013 pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e os catálogos globais são confiáveis, mas o DNS fornece um nível de proteção contra ataques de seqüestro de DNS, impedindo que o servidor de um invasor responda com êxito a um solicitação para o nome falsificado.

A figura a seguir mostra em um nível alto como o Lync Server 2013 usa MTLS para criar uma rede de servidores confiáveis.

**Conexões confiáveis em uma rede do Lync Server**

![437749da-c372-4f0d-ac72-ccfd5191696b](images/Dn481133.437749da-c372-4f0d-ac72-ccfd5191696b(OCS.15).jpg "437749da-c372-4f0d-ac72-ccfd5191696b")

</div>

<span> </span>

</div>

</div>

</div>

