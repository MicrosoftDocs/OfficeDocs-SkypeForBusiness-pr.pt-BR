---
title: Expansor de Configurações de FQDNs de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
ROBOTS: NOINDEX, NOFOLLOW
description: Para editar ou especificar Configurações Externas para os Servidores de Borda, primeiro determine se você usará endereços IP separados para o acesso SIP, o serviço de Borda de Webconferência e o serviço de Borda de Áudio/Vídeo.
ms.openlocfilehash: 4cf7d04ed94a867dcf1e351868cc205aac2439b0
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793809"
---
# <a name="edge-server-fqdns-settings-expander"></a>Expansor de Configurações de FQDNs de Servidor de Borda

Para editar ou especificar **Configurações Externas** para os Servidores de Borda, primeiro determine se você usará endereços IP separados para o acesso SIP, o serviço de Borda de Webconferência e o serviço de Borda de Áudio/Vídeo.

Caso pretenda usar endereços IP separados para cada um, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve ter um registro de host (A) DNS (Domain Name System) correspondente criado para ele.

Para cada serviço externo, especifique um nome de domínio totalmente qualificado (FQDN) e uma porta associada. Por exemplo, para **Acesso SIP**, você poderia usar sip.contoso.com e porta 5061 como porta associada.

> [!IMPORTANT]
> Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele. Por padrão, o SIP está na porta 5061/TLS, o serviço de Borda de Conferência Web está na porta 444/TLS e o serviço de Borda de Conferência A/V está na porta 443/TLS. Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externos, desmarque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você poderá então editar o FQDN de pool e os valores de porta do **Acesso SIP**, se for necessário.

> [!IMPORTANT]
> Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Para obter detalhes sobre como definir e configurar serviços de Borda, consulte [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


