---
title: Requisitos mínimos de rede do aplicativo de reuniões do Skype
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumo: informações para organizações que não usam o Office 365 e precisam acessar reuniões hospedadas por organizações que fazem.'
ms.openlocfilehash: 162d05f9786f02258afa080e630c85d4b513db4e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42033185"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do aplicativo de reuniões do Skype
 
**Resumo:**  Informações para organizações que não usam o Office 365 e precisam acessar reuniões hospedadas por organizações que fazem isso. Este artigo não se destina aos usuários desses aplicativos.
  
Para permitir que os usuários usem o aplicativo reuniões do Skype para participar de reuniões hospedados no Skype for Business Online, os administradores de rede de organizações que não usam o Office 365 devem se tornar disponíveis os FQDNs, IPs e portas mencionados abaixo.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para conectividade do aplicativo de reuniões do Skype

As informações listadas aqui são um subconjunto de [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), o que oferece mais profundidade e sempre será a mais atualizada.
                    
 
|App |FQDNs de destino  |Endereços IP  |Portas  |
|---|---------|---------|---------|
|**Aplicativo de Reuniões do Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Broadcast<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*. s-microsoft.com<br/>        |   Esses endereços IP são atualizados com frequência.  Confira os intervalos de [IP do Skype for Business](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , bem como os [intervalos de IP do Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Esses endereços IP são atualizados com frequência.  Confira os intervalos de [IP do Skype for Business](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , bem como os [intervalos de IP do Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Plano para clientes de reuniões (aplicativo Web e aplicativos de reuniões)](meetings-clients.md)

[Implantar clientes para download da Web no Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo de reuniões do Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
