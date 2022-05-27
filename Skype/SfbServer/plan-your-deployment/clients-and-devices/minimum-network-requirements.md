---
title: Requisitos mínimos de rede do Aplicativo Skype Meetings
ms.author: serdars
author: SerdarSoysal
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
ms.openlocfilehash: bdc3c6a3fba4968dd679a2039064c19786bd4661
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674523"
---
# <a name="skype-meetings-app-minimum-network-requirements"></a>Requisitos mínimos de rede do Aplicativo Skype Meetings

**Resumo:** Informações para organizações que não usam Microsoft 365 ou Office 365 e precisam acessar reuniões hospedadas por organizações que usam. Este artigo não se destina a Office 365 ou Microsoft 365 usuários finais.

Os usuários do Skype de Reuniões em organizações que não usam Microsoft 365 ou Office 365 podem precisar participar de reuniões hospedadas no Skype for Business Online. Para participar dessas reuniões, os administradores de rede precisam permitir os seguintes FQDNs, endereços IP e portas por meio do firewall.

## <a name="requirements-for-skype-meetings-app-connectivity"></a>Requisitos para Skype de aplicativo de reuniões

As informações listadas aqui são um subconjunto das informações [em Office 365 URLs e intervalos de endereços IP](/microsoft-365/enterprise/urls-and-ip-address-ranges). Esse tópico é muito mais detalhado e sempre será atual.

|Aplicativo|FQDNs de destino|Endereços IP|Portas|
|---|---------|---------|---------|
|**Skype de Reuniões**|\*.lync.com <br/>\*.infra.lync.com<br/>\*.pipe.aria.microsoft.com<br/>\*.sfbassets.com<br/>\*.msecnd.net<br/>\*broadcast.officeapps.live.com<span></span> <br/>\*powerpoint.officeapps.live.com<span></span> <br/>\*.office.live.com<br/>\*.cdn.office.net<br/>*.s-microsoft.com<br/>|Esses endereços IP são atualizados com frequência. Consulte [Skype for Business e Microsoft Teams de IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), bem como [Office intervalos de IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 80 & 443<br/>UDP: 3478-3481|
|**Teams**|\*<span></span>.microsoft.com <br/>\*<span></span>.skype.com|Esses endereços IP são atualizados com frequência. Consulte [Skype for Business e Microsoft Teams de IP](/microsoft-365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), bem como [Office intervalos de IP](/microsoft-365/enterprise/urls-and-ip-address-ranges)|TCP: 443 <br/> UDP: 3478-3481|

## <a name="see-also"></a>Confira também
<a name="BKMK_Conferencing"> </a>

[Planejar clientes de Reuniões (Aplicativo Web e Aplicativo de Reuniões)](meetings-clients.md)

[Implantar clientes baixáveis na Web Skype for Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plataformas com suporte para o Skype de Reuniões](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
