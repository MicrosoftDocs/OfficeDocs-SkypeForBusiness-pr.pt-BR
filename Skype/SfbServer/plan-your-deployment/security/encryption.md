---
title: Criptografia para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: O Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro. Ao conectar o Skype for Business Server a sistemas IPPBX de terceiros ou troncos SIP TLS é opcional, mas altamente recomendado entre o servidor de mediação e o gateway de mídia. Se o TLS for configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que seja confiável para o servidor de mediação.
ms.openlocfilehash: 3aadc51dff7fafe32ea929cdec3d4f2f03ee92fa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296914"
---
# <a name="encryption-for-skype-for-business-server"></a>Criptografia para o Skype for Business Server
 
O Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor necessita do MTLS, independentemente se o tráfego está restrito à rede interna ou se ultrapassa seu perímetro. Ao conectar o Skype for Business Server a sistemas de IPPBX de terceiros ou o SIP Trunks TLS é opcional, mas altamente recomendado entre o servidor de mediação e o gateway de mídia. Se o TLS for configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma autoridade de certificação que seja confiável para o servidor de mediação.
  
> [!NOTE]
> Um comunicado de segurança sobre SSL 3.0 foi publicado em 2014. A desabilitação do SSL 3,0 no Skype for Business Server 2015 é uma opção com suporte. Para saber mais sobre o comunicado de segurança, Confira como [desabilitar o SSL 3,0 no Lync server 2013 e no Skype for Business Server 2015](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/).<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2015 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: **TLS 1,2, tls 1,1, tls 1,0**. O TLS é um aspecto crítico do Skype for Business Server 2015 e, portanto, é necessário para manter um ambiente compatível.<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2019 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: **tls 1,3, tls 1,2**. O TLS é um aspecto crítico do Skype for Business Server 2019 e, portanto, é necessário para manter um ambiente compatível. 
  
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
> Para obter mais informações sobre a configuração de híbrido, consulte [planejar conectividade híbrida](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

O Skype for Business Server e o Microsoft Exchange Server 2016 operam com o suporte a algoritmos padrão do FIPS (Federal Information Processing Standard 140-2) se os sistemas operacionais Windows Server estiverem configurados para usar os algoritmos FIPS 140-2 para a criptografia do sistema . Para implementar o suporte a FIPS, você deve configurar cada servidor que está executando o Skype for Business Server para dar suporte a ele.
  

