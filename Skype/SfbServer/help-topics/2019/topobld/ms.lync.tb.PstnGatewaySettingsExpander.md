---
title: Expansor de Configurações de Gateway PSTN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:'
ms.openlocfilehash: c54acc930400f66bb04009a6c40dbcf0a1233100
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822301"
---
# <a name="pstn-gateway-settings-expander"></a>Expansor de Configurações de Gateway PSTN
 
Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:
  
FQDN ou Endereço IP do Gateway é uma entrada necessária e define o **Nome de domínio totalmente qualificado (FQDN)** do gateway PSTN, conforme definido por um registro (A) do host DNS (Domain Name System), uma entrada de arquivo HOSTS estática ou pelo endereço IP do gateway PSTN.
  
O Protocolo de Transporte SIP pode ser TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o que seu gateway suporta. O padrão é TLS, e deve ser considerado a seleção mais segura, se o gateway suportar TLS.
  
Selecione se deseja habilitar IPv4 e IPv6 para o gateway.
  
O **Endereço IP de mídia alternativo** é uma definição para o Servidor de Mediação para o qual o gateway PSTN implantado tem um endereço IP diferente para tráfego de mídia com relação ao endereço IP padrão configurado, que é normalmente dedicado ao tráfego SIP. Se você definir esse parâmetro, o gateway PSTN suportará uma interface de rede diferente ou caminho para mídia diferente. Se esse endereço for deixado em branco, o gateway PSTN não suportará o caminho alternativo para mídia.
  

