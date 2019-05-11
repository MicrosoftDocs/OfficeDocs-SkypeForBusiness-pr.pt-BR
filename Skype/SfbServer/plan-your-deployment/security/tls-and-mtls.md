---
title: TLS e MTLS para Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. Skype para Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.
ms.openlocfilehash: 995eb0b29e07d9224b2c7fa989eb96154267ac8f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929116"
---
# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS para Skype para Business Server
 
Os protocolos Transport Layer Security (TLS) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. Skype para Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações nessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem no MTLS. As comunicações SIP entre o cliente e o servidor ocorrem no TLS.
  
O TLS permite que os usuários, por meio do seu software cliente autenticar o Skype para servidores Business Server ao qual se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ser emitido por uma AC considerada confiável pelo cliente, e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usa a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem utilizadas na comunicação, assim, apenas o proprietário original do certificado pode utilizar sua chave privada para descriptografar os conteúdos de comunicação. A conexão resultante é confiável e, a partir desse momento, não será desafiada por nenhum outro servidor ou cliente confiável. Nesse contexto, a Secure Sockets Layer (SSL), conforme utilizada com serviços os Web, pode ser associada ao protocolo baseado em TLS.
  
Conexões de servidor para servidor baseiam-se em MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que cria a mensagem e o servidor que a recebe trocam certificados mutuamente a partir de uma AC confiável. Os certificados comprovam a identidade de cada servidor ao outro. No Skype para implantações de servidor de negócios, os certificados emitidos pela autoridade de certificação corporativa e que estão durante sua validade não e período revogada pela autoridade de certificação emissora são automaticamente considerados válidos por todos os servidores e clientes internos porque todos os membros de um ativo Domínio de diretório confiar a autoridade de certificação corporativa nesse domínio. Em cenários federados, a AC emissora deve ser confiável por ambos os parceiros federados. Cada parceiro pode usar uma AC diferente, se desejado, contanto que a AC também seja considerada confiável pelo outro parceiro. Esta confiança é mais facilmente realizada pelos servidores de borda, tendo o certificado de autoridade de certificação raiz do parceiro em sua autoridades de certificação de raiz confiável, ou pelo uso de uma autoridade de certificação de terceiros que é confiável por ambas as partes.
  
O TLS e MTLS ajudam a evitar a espionagem e ataques a intermediários. Em um ataque man-in-the-middle, o invasor roteia novamente as comunicações entre duas entidades de rede através do computador do invasor sem o conhecimento da outra parte. TLS e Skype para especificação Business Server de servidores confiáveis (apenas aqueles especificados no construtor de topologia) reduzem o risco de um ataque intermediário de man-in-the parcialmente na camada de aplicativo usando a criptografia de ponta a ponta coordenada usando a chave pública criptografia entre os dois pontos de extremidade e um invasor teria que ter um certificado válido e confiável com a chave privada correspondente e emitida para o nome do serviço ao qual o cliente está se comunicando para descriptografar a comunicação. Em última análise, entretanto, você deve cumprir as práticas recomendadas de segurança em sua infraestrutura de rede (no caso de um DNS corporativo). Skype para Business Server pressupõe que o servidor DNS é confiável da mesma forma que os controladores de domínio e catálogos globais são confiáveis, mas DNS fornecem um nível de proteção contra ataques DNS, impedindo que o servidor do invasor respondendo com êxito a uma solicitação para o nome falsificado.
  

