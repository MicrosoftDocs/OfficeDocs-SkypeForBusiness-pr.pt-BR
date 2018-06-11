---
title: Requisitos mínimos de rede do Aplicativo Skype Meetings
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 6/4/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumo: Informações para organizações que não usam o Office 365 e precisar acessar reuniões hospedadas por organizações que fazem.'
ms.openlocfilehash: 6005e8ea26b5910769967fa38a9a274428395ee4
ms.sourcegitcommit: 0fa147c33b1d7b5790af8d93339700ab62939430
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/11/2018
ms.locfileid: "19744292"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do Aplicativo Skype Meetings
 
**Resumo:**  Informações para organizações que não usam o Office 365 e precisar acessar reuniões hospedadas por organizações que fazem. Este artigo não se destina os usuários desses aplicativos.
  
Para permitir que os usuários utilizem Skype reuniões App para participar de reuniões hospedadas no Skype para Business Online, administradores de rede das organizações que não usam o Office 365 devem branca ou caso contrário tornar disponível para os FQDNs, IPs e portas mencionadas a seguir.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos de conectividade do Aplicativo Skype Meetings

As informações listadas aqui são um subconjunto dos [intervalos de endereços IP e URLs do Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US), que fornece mais detalhadamente e sempre será o mais atualizadas.
                    
 
|App |FQDNs de destino  |Endereços IP  |Portas  |
|---|---------|---------|---------|
|**Aplicativo de reuniões do Skype** | \*. lync.com <br/>\*. infra.lync.com<br/>\*. pipe.aria.microsoft.com<br/>\*. sfbassets.com<br/>\*. msecnd.net<br/>\*difusão<span></span>. officeapps.live.com <br/>\*PowerPoint<span></span>. officeapps.live.com <br/>\*. office.live.com<br/>\*. cdn.office.net<br/>*.s-microsoft.com<br/>        |   Esses endereços IP são atualizados com frequência.  Consulte [Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , bem como os [Intervalos de IP Online do Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Microsoft Teams**    | \*<span></span>. microsoft.com <br/>\*<span></span>. skype.com | Esses endereços IP são atualizados com frequência.  Consulte [Skype para intervalos de IP de negócios](https://support.office.com/en-us/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) , bem como os [Intervalos de IP Online do Office](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Ver também
<a name="BKMK_Conferencing"> </a>

[Planejar para clientes de reuniões (Web App e reuniões App)](meetings-clients.md)

[Implantar clientes para download da Web no Skype para Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo de reuniões do Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)