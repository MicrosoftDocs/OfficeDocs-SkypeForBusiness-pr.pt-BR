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
ms.openlocfilehash: ec711ad773aeb1b3b426e929b2d87d033f8d8004
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infraestrutura de chave pública do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-13_

O Microsoft Lync Server 2013 depende de certificados para autenticação de servidor e estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. O Windows Server 2012 R2, o Windows Server 2012, o Windows Server 2008 R2, o Windows Server 2008 e o Windows Server 2003 infraestrutura de chave pública (PKI) fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.

Os certificados são IDs digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma autoridade de certificação que é confiável para clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar somente com outros clientes e servidores em uma rede privada, a CA poderá ser uma CA empresarial. Se o servidor interagir com entidades fora da rede privada, uma CA pública poderá ser necessária.

Mesmo que as informações de um certificado sejam válidas, deve haver alguma forma de verificar se o servidor que está apresentando o certificado é realmente o representado pelo certificado. É aqui que a PKI do Windows entra em ação.

Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado retém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar uma parte aleatória das informações e enviá-la ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão poderá ter a certeza de que o servidor retém a chave privada para o certificado e, portanto, é o servidor nomeado no certificado.

<div>


> [!NOTE]  
> Nem todas as CAs públicas estão em conformidade com os requisitos dos certificados do Lync Server 2013. Recomendamos a consulta à lista de fornecedores certificados de CA pública para suas necessidades de certificado público. Para obter detalhes, consulte Unified Communications <A href="https://go.microsoft.com/fwlink/p/?linkid=140898">https://go.microsoft.com/fwlink/p/?LinkId=140898</A>Certificate Partners em.



</div>

<div>

## <a name="crl-distribution-points"></a>Pontos de distribuição de CRL

O Lync Server 2013 requer que todos os certificados de servidor contenham um ou mais pontos de distribuição de CRL (lista de certificados revogados). CDPs (Pontos de distribuição de CRL) são locais a partir dos quais os CRLs podem ser baixados para verificar se o certifico não foi revogado desde que foi emitido e se ainda está dentro do período de validade. Um ponto de distribuição da lista de certificados revogados é especificado nas propriedades do certificado como uma URL e, geralmente, é um HTTP seguro.

</div>

<div>

## <a name="enhanced-key-usage"></a>Uso avançado de chave

O Lync Server 2013 requer que todos os certificados do servidor ofereçam suporte a EKU (uso avançado de chave) para fins de autenticação de servidor. A configuração do campo de EKU para autenticação de servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para o MTLS. É possível ter mais de uma entrada no EKU, o que habilitará o certificado a mais de uma finalidade.

<div>


> [!NOTE]  
> O EKU de Autenticação de Cliente é necessário para conexões MTLS de saída no Live Communications Server 2003 e Live Communications Server 2005, mas ele não é mais obrigatório. No entanto, esse EKU deve estar presente nos Servidores de Borda que se conectam ao AOL por meio da conectividade a redes públicas de mensagens instantâneas.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

