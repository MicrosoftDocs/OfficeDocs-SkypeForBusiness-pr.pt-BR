---
title: Criptografia para Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego estar confinado à rede interna ou cruzar o perímetro de rede interno. Ao conectar Skype for Business Server a sistemas IPPBX de terceiros ou troncos SIP TLS é opcional, mas altamente recomendado entre o Servidor de Mediação e o gateway de mídia. Se o TLS estiver configurado neste link, MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma AC confiável pelo Servidor de Mediação.
ms.openlocfilehash: 3ee649f62e2855f959b2ee9fdc25bdb2d77fa6e9
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849714"
---
# <a name="encryption-for-skype-for-business-server"></a>Criptografia para Skype for Business Server
 
Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego estar confinado à rede interna ou cruzar o perímetro de rede interno. Ao conectar Skype for Business Server a sistemas IPPBX de terceiros ou troncos SIP TLS é opcional, mas altamente recomendado entre o Servidor de Mediação e o gateway de mídia. Se o TLS estiver configurado neste link, MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma AC confiável pelo Servidor de Mediação.
  
> [!NOTE]
> Um aviso de segurança sobre o SSL 3.0 foi publicado em 2014. Desabilitar o SSL 3.0 no Skype for Business Server 2015 é uma opção suportada. Para saber mais sobre a consultoria de segurança, consulte [Desabilitando o SSL 3.0 no Lync Server 2013 e Skype for Business Server 2015](/archive/blogs/uclobby/disabling-ssl-3-0-in-lync-server-2013).<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2015 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: **TLS 1.2 , TLS 1.1, TLS 1.0**. O TLS é um aspecto crítico do Skype for Business Server 2015 e, portanto, é necessário para manter um ambiente com suporte.<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2019 oferecerá protocolos de criptografia TLS na seguinte ordem para clientes: **TLS 1.3, TLS 1.2**. O TLS é um aspecto crítico do Skype for Business Server 2019 e, portanto, é necessário para manter um ambiente com suporte. 
  
A tabela a seguir resume os requisitos de protocolo de cada tipo de tráfego. 
  
**Proteção de tráfego**

|**Tipo de tráfego**|**Protegido por**|
|:-----|:-----|
|Servidor para servidor  <br/> |MTLS  <br/> |
|Cliente para servidor  <br/> |TLS  <br/> |
|Sistema de mensagens instantâneas e presença  <br/> |TLS  <br/> |
|Compartilhamento de área de trabalho, áudio e vídeo da mídia  <br/> |SRTP  <br/> |
|Compartilhamento de área de trabalho (sinalização)  <br/> |TLS  <br/> |
|Webconferência  <br/> |TLS  <br/> |
|Download do conteúdo das reuniões, download do catálogo de endereços, expansão de grupos de distribuição  <br/> |HTTPS  <br/> |
   
## <a name="media-encryption"></a>Criptografia da mídia

O tráfego de mídia é criptografado usando SRTP, um perfil de protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataque de repetição para o tráfego RTP. Além disso, a mídia que flui em ambas as direções entre o servidor de mediação e seu próximo nó interno também é criptografada usando o SRTP. A mídia que flui em ambas as direções entre o Servidor de Mediação e um gateway de mídia é opcionalmente criptografada e recomendada. O Servidor de Mediação pode oferecer suporte à criptografia para o gateway de mídia, mas o gateway deve oferecer suporte ao MTLS e ao armazenamento de um certificado.
  
> [!NOTE]
> Para obter mais informações sobre a configuração híbrida, consulte [Plan hybrid connectivity](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json).
  
## <a name="fips"></a>FIPS

Skype for Business Server e Microsoft Exchange Server 2016 operam com suporte para algoritmos FIPS (Federal Information Processing Standard) 140-2 se os sistemas operacionais do Windows Server estão configurados para usar os algoritmos FIPS 140-2 para criptografia do sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor executando Skype for Business Server para dar suporte a ele.
