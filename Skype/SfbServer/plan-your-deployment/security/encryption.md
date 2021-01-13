---
title: Criptografia para o Skype for Business Server
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
ms.assetid: d18c74a6-385b-407b-98eb-0d525fa38fea
description: O Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego estar confinado à rede interna ou cruzar o perímetro de rede interna. Ao conectar o Skype for Business Server a sistemas IPPBX de terceiros ou troncos SIP, o TLS é opcional, mas altamente recomendado entre o Servidor de Mediação e o gateway de mídia. Se o TLS estiver configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma CA confiável para o Servidor de Mediação.
ms.openlocfilehash: 48af03d7f6aed5b744ad4e0c460622194a87d96e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832201"
---
# <a name="encryption-for-skype-for-business-server"></a>Criptografia para o Skype for Business Server
 
O Skype for Business Server usa TLS e MTLS para criptografar mensagens instantâneas. Todo o tráfego de servidor para servidor requer MTLS, independentemente de o tráfego estar confinado à rede interna ou cruzar o perímetro de rede interna. Ao conectar o Skype for Business Server a sistemas IPPBX de terceiros ou troncos SIP, o TLS é opcional, mas altamente recomendado entre o Servidor de Mediação e o gateway de mídia. Se o TLS estiver configurado neste link, o MTLS será necessário. Portanto, o gateway deve ser configurado com um certificado de uma CA confiável para o Servidor de Mediação.
  
> [!NOTE]
> Um aviso de segurança sobre o SSL 3.0 foi publicado em 2014. Desabilitar o SSL 3.0 no Skype for Business Server 2015 é uma opção com suporte. Para saber mais sobre o aviso de segurança, consulte [Desabilitando o SSL 3.0 no Lync Server 2013 e no Skype for Business Server 2015.](https://blogs.technet.microsoft.com/uclobby/2014/10/22/disabling-ssl-3-0-in-lync-server-2013/)<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2015 oferecerá protocolos de criptografia TLS na seguinte ordem para os clientes: **TLS 1.2 , TLS 1.1, TLS 1.0.** O TLS é um aspecto crítico do Skype for Business Server 2015 e, portanto, é necessário para manter um ambiente com suporte.<br/>
**Observação de segurança:** Para garantir que o protocolo criptográfico mais forte seja usado, o Skype for Business Server 2019 oferecerá protocolos de criptografia TLS na seguinte ordem aos clientes: **TLS 1.3, TLS 1.2**. O TLS é um aspecto crítico do Skype for Business Server 2019 e, portanto, é necessário para manter um ambiente com suporte. 
  
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

O tráfego de mídia é criptografado usando SRTP, um perfil de protocolo RTP que fornece confidencialidade, autenticação e proteção contra ataque de repetição para o tráfego RTP. Além disso, a mídia que flui em ambas as direções entre o servidor de mediação e seu próximo nó interno também é criptografada usando o SRTP. O fluxo de mídia em ambas as direções entre o Servidor de Mediação e um gateway de mídia é opcionalmente criptografado e recomendado. O Servidor de Mediação pode oferecer suporte à criptografia para o gateway de mídia, mas o gateway deve oferecer suporte ao MTLS e ao armazenamento de um certificado.
  
> [!NOTE]
> Para obter mais informações sobre como configurar a configuração híbrida, consulte [Planejar conectividade híbrida.](../../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)
  
## <a name="fips"></a>FIPS

O Skype for Business Server e o Microsoft Exchange Server 2016 operam com suporte para algoritmos FIPS 140-2 fips se os sistemas operacionais Windows Server estão configurados para usar os algoritmos FIPS 140-2 para criptografia do sistema. Para implementar o suporte a FIPS, você deve configurar cada servidor que executa o Skype for Business Server para dar suporte a ele.
  

