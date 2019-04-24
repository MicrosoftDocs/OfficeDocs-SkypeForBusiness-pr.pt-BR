---
title: Expansor de Configurações de FQDNs de Servidor de Borda
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Para editar ou especificar Configurações Externas para os Servidores de Borda, primeiro determine se você usará endereços IP separados para o acesso SIP, o serviço de Borda de Webconferência e o serviço de Borda de Áudio/Vídeo.
ms.openlocfilehash: bb2872ada60da7edb6905692deb5a893fe3e5427
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32203134"
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


