---
title: Expansor de Configurações FQDNs de Servidor de Borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeFqdnsSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e4e9445-0147-4dd6-84f0-b41de142b332
description: Para editar ou especificar configurações externas para os servidores de borda, primeiro você deve determinar se usará endereços IP separados para o acesso do protocolo SIP, o serviço de borda de Webconferência e o serviço de borda de áudio/vídeo.
ms.openlocfilehash: f04cdcb16678825d9ab7cc4696c4e649676587b2
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218212"
---
# <a name="edge-server-fqdns-settings-expander"></a>Expansor de Configurações FQDNs de Servidor de Borda

Para editar ou especificar **configurações externas** para os servidores de borda, primeiro você deve determinar se usará endereços IP separados para o acesso do protocolo SIP, o serviço de borda de Webconferência e o serviço de borda de áudio/vídeo.

Caso você pretenda usar endereços IP separados para cada um, marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V**. Cada serviço deve possuir um registro de hospedeiro (A) DNS (Domain Name System) correspondente criado para ele.

Para cada serviço externamente focado, especifique um FQDN (nome de domínio totalmente qualificado) e uma porta associada. Por exemplo, para   **Acesso SIP **, você poderia usar sip.contoso.com com uma porta 5061 associada.

> [!IMPORTANT]
> Caso você selecione FQDNs separados para cada um dos serviços externamente focados, cada serviço deve ter um valor de porta único associado a ele. Por padrão, o SIP está na porta 5061/TLS, o serviço de Borda de Conferência Web está na porta 444/TLS e o serviço de Borda de Conferência A/V está na porta 443/TLS. Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Caso você determine que sua organização utilizará um único endereço IP e FQDN para os serviços externamente focados, limpe a caixa de seleção  **Habilitar FQDN e endereço IP separados para webconferência e A/V **. Você então pode editar o pool FQDN de  **Acesso SIP ** e valores de porta, se necessário.

> [!IMPORTANT]
> Se você alterar alguma destas configurações, incluindo usar endereços IP ou FQDN ou portas separadas, você deve atualizar todos os outros serviços que dependerão dos valores configurados inicialmente.

Para obter detalhes sobre como definir e configurar as definições para os serviços de borda, consulte [define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx).


