---
title: Expansor de Configurações de Gateway PSTN
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:'
ms.openlocfilehash: 10669d4355acc8d2ea1a8546275116660c1ac7a7
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216582"
---
# <a name="pstn-gateway-settings-expander"></a>Expansor de Configurações de Gateway PSTN
 
Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:
  
FQDN ou Endereço IP do Gateway é uma entrada necessária e define o **Nome de domínio totalmente qualificado (FQDN)** do gateway PSTN, conforme definido por um registro (A) do host DNS (Domain Name System), uma entrada de arquivo HOSTS estática ou pelo endereço IP do gateway PSTN.
  
O Protocolo de Transporte SIP pode ser TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o que seu gateway suporta. O padrão é TLS, e deve ser considerado a seleção mais segura, se o gateway suportar TLS.
  
Selecione se deseja habilitar IPv4 e IPv6 para o gateway.
  
O **Endereço IP de mídia alternativo** é uma definição para o Servidor de Mediação para o qual o gateway PSTN implantado tem um endereço IP diferente para tráfego de mídia com relação ao endereço IP padrão configurado, que é normalmente dedicado ao tráfego SIP. Se você definir esse parâmetro, o gateway PSTN suportará uma interface de rede diferente ou caminho para mídia diferente. Se esse endereço for deixado em branco, o gateway PSTN não suportará o caminho alternativo para mídia.
  

