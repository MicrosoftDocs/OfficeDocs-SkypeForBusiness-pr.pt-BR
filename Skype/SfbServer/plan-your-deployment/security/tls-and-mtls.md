---
title: TLS e MTLS para Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Os protocolos TLS e MTLS (Mutual Transport Layer Security) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem em MTLS. As comunicações SIP de cliente para servidor ocorrem por TLS.
ms.openlocfilehash: 7acc75ef35a9fe9c3f155ca31f06ac38df371e37
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832011"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS para Skype for Business Server
 
Os protocolos TLS e MTLS (Mutual Transport Layer Security) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. O Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem em MTLS. As comunicações SIP de cliente para servidor ocorrem por TLS.
  
O TLS permite que os usuários, por meio de seu software cliente, autentiem os servidores do Skype for Business Server aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ter sido emitido por uma CA que também é confiável para o cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usará a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem usadas para a comunicação, para que somente o proprietário original do certificado possa usar sua chave privada para descriptografar o conteúdo da comunicação. A conexão resultante é confiável e a partir desse ponto não é desafiada por outros servidores ou clientes confiáveis. Nesse contexto, o SSL (Secure Sockets Layer) conforme usado com serviços Web pode ser associado com base em TLS.
  
As conexões de servidor para servidor dependem do MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que origina uma mensagem e o servidor que a recebe trocam certificados de uma CA mutuamente confiável. Os certificados comprovam a identidade de cada servidor para o outro. Nas implantações do Skype for Business Server, os certificados emitidos pela AC corporativa que estão durante o período de validade e não foram revogados pela CA emissor são automaticamente considerados válidos por todos os clientes e servidores internos porque todos os membros de um domínio do Active Directory confiam na AC Corporativa nesse domínio. Em cenários federados, a CA de emissão deve ser confiável por ambos os parceiros federados. Cada parceiro pode usar uma CA diferente, se desejado, desde que essa AC também seja confiável para o outro parceiro. Essa confiança é mais facilmente realizada pelos Servidores de Borda que têm o certificado de AC raiz do parceiro em suas CAs raiz confiáveis ou pelo uso de uma CA de terceiros que seja confiável para ambas as partes.
  
O TLS e o MTLS ajudam a evitar ataques de espionagem e man-in-the-middle. Em um ataque man-in-the-middle, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor sem o conhecimento de nenhuma das partes. A especificação do TLS e do Skype for Business Server de servidores confiáveis (somente aqueles especificados no Construtor de Topologias) reduz o risco de um ataque man-in-the-middle parcialmente na camada do aplicativo usando criptografia de ponta a ponta coordenada usando a criptografia de Chave Pública entre os dois pontos de extremidade, e um invasor teria que ter um certificado válido e confiável com a chave privada correspondente e emitido para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. Por fim, no entanto, você deve seguir as práticas recomendadas de segurança com sua infraestrutura de rede (neste caso, DNS corporativo). O Skype for Business Server pressupo que o servidor DNS é confiável da mesma forma que os controladores de domínio e catálogos globais são confiáveis, mas o DNS fornece um nível de proteção contra ataques de invasor de DNS, impedindo que o servidor do invasor responde com êxito a uma solicitação para o nome falso.
  

