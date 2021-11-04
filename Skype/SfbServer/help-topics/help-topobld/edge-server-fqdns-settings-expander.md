---
title: Expansor de Configurações FQDNs de Servidor de Borda
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Para editar ou especificar o Configurações externo para os Servidores de Borda, primeiro você deve determinar se você usará endereços IP separados para acesso SIP (Protocolo de Iniciação de Sessão), o serviço de Borda de WebConferência e o serviço de Borda de Áudio/Vídeo.
ms.openlocfilehash: d9404821e8ab1f11014a05030ea9007ad5150a02
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739247"
---
# <a name="edge-server-fqdns-settings-expander"></a>Expansor de Configurações FQDNs de Servidor de Borda

Para editar  ou especificar o Configurações externo para os Servidores de Borda, primeiro você deve determinar se você usará endereços IP separados para acesso SIP (Session Initiation Protocol), o serviço de Borda de WebConferência e o serviço de Borda de Áudio/Vídeo.

Caso você pretenda usar endereços IP separados para cada um, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve possuir um registro de hospedeiro (A) DNS (Domain Name System) correspondente criado para ele.

Para cada serviço externamente focado, especifique um FQDN (nome de domínio totalmente qualificado) e uma porta associada. Por exemplo, para   **Acesso SIP**, você poderia usar sip.contoso.com com uma porta 5061 associada.

> [!IMPORTANT]
> Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele. Por padrão, o SIP está na porta 5061/TLS, o serviço de Borda de Conferência Web está na porta 444/TLS e o serviço de Borda de Conferência A/V está na porta 443/TLS. Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externamente focados, limpe a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Você então pode editar o pool FQDN de  **Acesso SIP** e valores de porta, se necessário.

> [!IMPORTANT]
> Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Para obter detalhes sobre como definir e configurar as configurações dos serviços de Borda, consulte [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology).