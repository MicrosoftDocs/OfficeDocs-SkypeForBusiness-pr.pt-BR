---
title: Requisitos mínimos de rede do Aplicativo Skype Meetings
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumo: informações para organizações que não usam o Office 365 e precisam acessar reuniões hospedadas por organizações que o fazem.'
ms.openlocfilehash: 1017c81fc3432fbd409077b89809d725b2b0e2cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277479"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do Aplicativo Skype Meetings
 
**Resumo:**  Informações para organizações que não usam o Office 365 e precisam acessar reuniões hospedadas por organizações que o fazem. Este artigo não se destina aos usuários desses aplicativos.
  
Para permitir que os usuários usem o aplicativo reuniões do Skype para participar de reuniões hospedadas no Skype for Business Online, os administradores de rede de organizações que não usam o Office 365 devem ter a lista branca ou os FQDNs, IPs e portas mencionados abaixo.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos de conectividade do Aplicativo Skype Meetings

As informações listadas aqui são um subconjunto de [URLs e intervalos de endereços IP do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), que proporcionam mais profundidade e sempre serão as mais atualizadas.
                    
 
|AppV |FQDNs de destino  |Endereços IP  |Portas  |
|---|---------|---------|---------|
|**Aplicativo Reuniões do Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*Transmit<span></span>. officeapps.Live.com <br/>\*PowerPoint<span></span>. officeapps.Live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Esses endereços IP são atualizados com frequência.  Veja os [intervalos de IP do Skype for Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e os [intervalos de IP do Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Microsoft Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Esses endereços IP são atualizados com frequência.  Veja os [intervalos de IP do Skype for Business](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) e os [intervalos de IP do Office Online](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Plano para clientes de reuniões (aplicativo Web e aplicativo reuniões)](meetings-clients.md)

[Implantar clientes para download da Web no Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
