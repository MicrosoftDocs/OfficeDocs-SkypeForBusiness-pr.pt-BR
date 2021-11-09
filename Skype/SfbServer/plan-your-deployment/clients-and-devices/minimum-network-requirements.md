---
title: Requisitos mínimos de rede do Aplicativo Skype Meetings
ms.author: v-mahoffman
author: HowlinWolf-92
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 6/4/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d9666787-e72b-41e1-ba37-aec5fb849a10
description: 'Resumo: informações para organizações que não usam Microsoft 365 ou Office 365 e precisam acessar reuniões hospedadas por organizações que usam.'
ms.openlocfilehash: 28373203bd60182bd6065a6e7169e8f9f4908940
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862078"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do Aplicativo Skype Meetings
 
**Resumo:**  Informações para organizações que não usam Microsoft 365 ou Office 365 e precisam acessar reuniões hospedadas por organizações que usam. Este artigo não se destina aos usuários desses aplicativos.
  
Para permitir que os usuários usem o Skype Meetings App para participar de reuniões hospedadas no Skype for Business Online, os administradores de rede de organizações que não usam o Microsoft 365 ou o Office 365 devem permitir ou disponibilizar os FQDNs, IPs e portas mencionados abaixo.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para Skype conectividade do aplicativo reuniões

As informações listadas aqui são um subconjunto de [urls](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)Office 365 e intervalos de endereços IP , que fornece mais profundidade e sempre será o mais atualizado.
                    
 
|Aplicativo |FQDNs de destino  |Endereços IP  |Portas  |
|---|---------|---------|---------|
|**Aplicativo de Reuniões do Skype** | \*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast <span></span> .officeapps.live.com <br/>\*powerpoint <span></span> .officeapps.live.com <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>        |   Esses endereços IP são atualizados com frequência.  Consulte [Skype for Business de IP,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) bem como [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)         |TCP: 80 &amp; 443<br/>UDP: 3478-3481<br/>
|**Teams**    | \*<span></span>.microsoft.com <br/>\*<span></span>.skype.com | Esses endereços IP são atualizados com frequência.  Consulte [Skype for Business de IP,](https://support.office.com/article/office-365-urls-and-ip-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#bkmk_sfb_ip) bem como [Office IP Ranges](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;amp;rs=en-US&amp;amp;ad=US)      |TCP: 443 <br/> UDP: 3478-3481

## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Planejar os clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](meetings-clients.md)

[Implantar clientes baixáveis da Web em Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o aplicativo Skype Reuniões](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
