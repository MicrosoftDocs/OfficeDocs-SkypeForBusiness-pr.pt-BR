---
title: TLS e MTLS para Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: b32a5b85-fc82-42dc-a9b2-96400f8cd2b8
description: Os protocolos TLS (Transport Layer Security) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações dessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem por MTLS. As comunicações SIP de cliente para servidor ocorrem por TLS.
---

# <a name="tls-and-mtls-for-skype-for-business-server"></a>TLS e MTLS para Skype for Business Server
 
Os protocolos TLS (Transport Layer Security) e Mutual Transport Layer Security (MTLS) fornecem comunicações criptografadas e autenticação de ponto de extremidade na Internet. Skype for Business Server usa esses dois protocolos para criar a rede de servidores confiáveis e garantir que todas as comunicações dessa rede sejam criptografadas. Todas as comunicações SIP entre servidores ocorrem por MTLS. As comunicações SIP de cliente para servidor ocorrem por TLS.
  
O TLS permite que os usuários, por meio de seu software cliente, autententem os servidores Skype for Business Server aos quais se conectam. Em uma conexão TLS, o cliente solicita um certificado válido do servidor. Para ser válido, o certificado deve ter sido emitido por uma AUTORIDADE que também é confiável pelo cliente e o nome DNS do servidor deve corresponder ao nome DNS no certificado. Se o certificado for válido, o cliente usará a chave pública no certificado para criptografar as chaves de criptografia simétricas a serem usadas para a comunicação, portanto, somente o proprietário original do certificado pode usar sua chave privada para descriptografar o conteúdo da comunicação. A conexão resultante é confiável e, a partir desse ponto, não é desafiada por outros servidores ou clientes confiáveis. Nesse contexto, o SSL (Secure Sockets Layer) como usado com serviços Web pode ser associado como baseado em TLS.
  
As conexões de servidor para servidor dependem de MTLS para autenticação mútua. Em uma conexão MTLS, o servidor que origina uma mensagem e o servidor que a recebe troca certificados de uma CA mutuamente confiável. Os certificados provam a identidade de cada servidor para o outro. Em implantações Skype for Business Server, certificados emitidos pela AC corporativa que estão durante o período de validade e não revogados pela CA de emissão são automaticamente considerados válidos por todos os clientes e servidores internos, pois todos os membros de um domínio do Active Directory confiam na CA Enterprise nesse domínio. Em cenários federados, a AC em emissão deve ser confiável por ambos os parceiros federados. Cada parceiro pode usar uma CA diferente, se desejado, desde que essa AC também seja confiável pelo outro parceiro. Essa confiança é mais facilmente realizada pelos Servidores de Borda que têm o certificado de AC raiz do parceiro em suas CAs raiz confiáveis ou pelo uso de uma AC de terceiros que é confiável por ambas as partes.
  
O TLS e o MTLS ajudam a evitar ataques de escuta e man-in-the-middle. Em um ataque man-in-the-middle, o invasor redireciona as comunicações entre duas entidades de rede por meio do computador do invasor sem o conhecimento de nenhuma das partes. O TLS e Skype for Business Server especificação de servidores confiáveis (somente aqueles especificados no Construtor de Topologias) atenuam o risco de um ataque intermediário parcialmente na camada do aplicativo usando criptografia de ponta a ponta coordenada usando a criptografia de Chave Pública entre os dois pontos de extremidade, e um invasor teria que ter um certificado válido e confiável com a chave privada correspondente e emitido com o nome do  para o qual o cliente está se comunicando para descriptografar a comunicação. Por fim, no entanto, você deve seguir as práticas recomendadas de segurança com sua infraestrutura de rede (nesse caso, DNS corporativo). Skype for Business Server supõe que o servidor DNS seja confiável da mesma forma que os controladores de domínio e catálogos globais são confiáveis, mas o DNS fornece um nível de proteção contra ataques de seqüestro DNS impedindo que o servidor de um invasor respondesse com êxito a uma solicitação ao nome falso.
  

