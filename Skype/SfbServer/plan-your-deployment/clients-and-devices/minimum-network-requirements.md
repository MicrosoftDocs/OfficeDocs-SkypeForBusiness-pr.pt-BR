---
title: Requisitos mínimos de rede do Aplicativo Skype Meetings
ms.author: v-cichur
author: cichur
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
description: 'Resumo: informações para organizações que não usam o Microsoft 365 ou o Office 365 e precisam acessar reuniões hospedadas por organizações que usam.'
ms.openlocfilehash: d5e6b838ceddb4ea1195694eb0ad11a1d029a1bb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816301"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do Aplicativo Skype Meetings
 
**Resumo:**  Informações para organizações que não usam o Microsoft 365 ou o Office 365 e precisam acessar reuniões hospedadas por organizações que usam. Este artigo não se destina aos usuários desses aplicativos.
  
Para permitir que os usuários usem o Aplicativo Reuniões do Skype para participar de reuniões hospedadas no Skype for Business Online, os administradores de rede de organizações que não usam o Microsoft 365 ou o Office 365 devem permitir ou disponibilizar os FQDNs, IPs e portas mencionados abaixo.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para conectividade do aplicativo Reuniões do Skype

As informações listadas aqui são um subconjunto de URLs e intervalos de endereços IP do [Office 365,](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)que fornece mais profundidade e sempre será o mais atualizado.
                    
 
|App |FQDNs de destino  |Endereços IP  |Portas  |
|---|---------|---------|---------|
|**Aplicativo de Reuniões do Skype** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Esses endereços IP são atualizados com frequência.  Ver [intervalos de IP do Skype for Business,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) bem como [intervalos de IP do Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Esses endereços IP são atualizados com frequência.  Ver [intervalos de IP do Skype for Business,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) bem como [intervalos de IP do Office](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Planejar-se para clientes de reuniões (aplicativo Web App e Reuniões)](meetings-clients.md)

[Implantar clientes para download da Web no Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo Reuniões do Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
