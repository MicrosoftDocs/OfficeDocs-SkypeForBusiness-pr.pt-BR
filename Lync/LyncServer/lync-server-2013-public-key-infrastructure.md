---
title: 'Lync Server 2013: infraestrutura de chave pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Public Key Infrastructure for Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59893870
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0fb79340b29ab4bfa6942d2b2cb62483c79b4ce9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823739"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="public-key-infrastructure-for-lync-server-2013"></a>Infraestrutura de chave pública do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-13_

O Microsoft Lync Server 2013 depende de certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. O Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 e Windows Server 2003 infraestrutura de chave pública (PKI) fornece a infraestrutura para o estabelecimento e a validação da cadeia de confiança.

Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma AC confiável pelos clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar apenas com outros clientes e servidores de rede privada, a AC pode ser uma AC corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.

Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.

Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado

<div>


> [!NOTE]  
> Nem todas as CAs públicas estão em conformidade com os requisitos dos certificados do Lync Server 2013. Recomendamos que consulte a lista de fornecedores certificados de AC pública para suas necessidades de certificados públicos. Para obter detalhes, consulte parceiros de certificado de <A href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</A>comunicação unificada em.



</div>

<div>

## <a name="crl-distribution-points"></a>Pontos de distribuição das listas de certificados revogados (CRLs)

O Lync Server 2013 requer que todos os certificados do servidor contenham um ou mais pontos de distribuição da lista de certificados revogados (CRL). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura.

</div>

<div>

## <a name="enhanced-key-usage"></a>Uso avançado da chave

O Lync Server 2013 requer que todos os certificados do servidor ofereçam suporte ao uso avançado de chave (EKU) para a finalidade da autenticação do servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS. É possível ter mais de uma entrada no EKU, permitindo o uso do certificado para mais de uma finalidade.

<div>


> [!NOTE]  
> A EKU de autenticação de cliente é necessária para conexões MTLS de saída do Live Communications Server 2003 e do Live Communications Server 2005, mas não é mais necessário. No entanto, esse EKU deve estar presente em servidores de borda que se conectam à AOL por meio de conectividade de mensagens de chat públicas.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

