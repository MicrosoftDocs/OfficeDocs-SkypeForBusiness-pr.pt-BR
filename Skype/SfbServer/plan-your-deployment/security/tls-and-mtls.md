---
title: TLS e MTLS para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações na rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.
ms.openlocfilehash: fe8619dd499388472612c67ddf1801a027ed1e5d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296844"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS para o Skype for Business Server
 
Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações na rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.
  
O TLS permite que os usuários, por meio do software cliente, autentiquem os servidores do Skype for Business Server aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável. Nesse contexto, a Secure Sockets Layer (SSL), conforme utilizada com serviços os Web, pode ser associada ao protocolo baseado em TLS.
  
Conexões de servidor para servidor baseiam-se em MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável. Os certificados comprovam a identidade de cada servidor ao outro. Nas implantações do Skype for Business Server, os certificados emitidos pela CA corporativa que estão durante o período de validade e não revogados pela CA de emissão são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um Domínio Directory confia na CA da empresa nesse domínio. Em cenários federados, a AC emissora deve ser confiável por ambos os parceiros federados. Cada parceiro pode usar uma AC diferente, se desejado, contanto que a AC também seja considerada confiável pelo outro parceiro. Essa confiança é realizada com facilidade pelos servidores de borda com o certificado da autoridade de certificação raiz do parceiro nas CAs raiz confiáveis, ou por meio de uma autoridade de certificação de terceiros que é confiável para ambas as partes.
  
O TLS e MTLS ajudam a evitar a espionagem e ataques a intermediários. Em um ataque man-in-Middle, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor sem o conhecimento de ambas as partes. Especificação de servidores confiáveis do TLS e do Skype for Business Server (somente aqueles especificados no construtor de topologia) reduzem o risco de um ataque man-in-the Middle parcialmente na camada do aplicativo usando a criptografia ponto a ponto coordenada usando a chave pública a criptografia entre os dois pontos de extremidade e um invasor precisa ter um certificado válido e confiável com a chave privada correspondente e emitida para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. Em última análise, entretanto, você deve cumprir as práticas recomendadas de segurança em sua infraestrutura de rede (no caso de um DNS corporativo). O Skype for Business Server pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e os catálogos globais são confiáveis, mas o DNS fornece um nível de segurança contra ataques de seqüestro de DNS impedindo que o servidor de um invasor responda êxito em uma solicitação para o nome falso.
  

