---
title: Criptografia do Skype para Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype para Business Server usa o TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro. Quando a conexão Skype para Business Server a 3º sistemas IPPBX de terceiros ou troncos SIP TLS é opcional, mas altamente recomendado entre o servidor de mediação e o gateway de mídia. Se o TLS for configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação confiável pelo servidor de mediação.
ms.openlocfilehash: e4a58cf10d268dedadb34556206e1c7227d4fdf5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879206"
---
# <a name="encryption-for-skype-for-business-server"></a>Criptografia do Skype para Business Server
 
Skype para Business Server usa o TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro. Quando a conexão Skype para Business Server a sistemas IPPBX de terceiros ou troncos SIP TLS é opcional, mas altamente recomendado entre o servidor de mediação e o gateway de mídia. Se o TLS for configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação confiável pelo servidor de mediação.
  
> [!NOTE]
> Um comunicado de segurança sobre SSL 3.0 foi publicado em 2014. Desabilitar o SSL 3.0 no Skype para Business Server 2015 é uma opção suportada. Para saber mais sobre o aviso de segurança, consulte [desativando o SSL 3.0 no Lync Server 2013 e Skype para Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte é usado, Skype para Business Server 2015 oferecerá protocolos de criptografia TLS na seguinte ordem aos clientes: **1.2 TLS, TLS 1.1, TLS 1.0**. O TLS é um aspecto crítico do Skype para Business Server 2015 e, portanto, ela é necessário para manter um ambiente com suporte.<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte é usado, Skype para Business Server 2019 oferecerá protocolos de criptografia TLS na seguinte ordem aos clientes: **1.3 TLS, TLS 1.2**. O TLS é um aspecto crítico do Skype para Business Server 2019 e, portanto, ela é necessário para manter um ambiente com suporte. 
  
A seguinte tabela resume os requisitos de protocolo para cada tipo de tráfego. 
  
**Proteção de Tráfego**

|**Tipo de Tráfego**|**Protegido por**|
|:-----|:-----|
|Servidor para Servidor  <br/> |MTLS  <br/> |
|Cliente para Servidor  <br/> |TLS  <br/> |
|Mensagens instantâneas e presença  <br/> |TLS  <br/> |
|Compartilhamento de mídia de áudio, vídeo e de área de trabalho  <br/> |SRTP  <br/> |
|Compartilhamento de área de trabalho (sinalização)  <br/> |TLS  <br/> |
|Webconferência  <br/> |TLS  <br/> |
|Download de conteúdo de reunião, download do catálogo de endereços, expansão de grupo de distribuição  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Criptografia de mídia

O tráfego de mídia é criptografado usando SRTP (Secure RTP), um perfil do protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataques de repetição para o tráfego RTP. Além disso, a mídia que flui em ambas as direções entre o Servidor de Mediação e seu próximo salto interno também é criptografada usando SRTP. A mídia que flui em ambas as direções entre o Servidor de Mediação e um gateway de mídia é criptografada opcionalmente e recomendada. O Servidor de Mediação pode dar suporte à criptografia para o gateway de mídia, mas o gateway deve dar suporte a MTLS e ao armazenamento de um certificado.
  
> [!NOTE]
> Para obter mais informações sobre a configuração híbrida, consulte [Planejar a conectividade híbrida](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype para Business Server e Microsoft Exchange Server 2016 operar com suporte a algoritmos Federal Information Processing Standard (FIPS) 140-2, se os sistemas operacionais Windows Server estiverem configurados para usar o FIPS 140-2 algoritmos para criptografia do sistema . Para implementar o suporte FIPS, você deve configurar cada servidor que executa o Skype para Business Server oferecer suporte a ele.
  

