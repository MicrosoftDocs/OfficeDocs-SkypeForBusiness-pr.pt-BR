---
title: Expansor de Configurações de Gateway PSTN
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
description: 'Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:'
ms.openlocfilehash: b13580053783ae6b6934fa40e93b493280fd6d3c
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="pstn-gateway-settings-expander"></a>Expansor de Configurações de Gateway PSTN
 
Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:
  
O FQDN do gateway ou Endereço IP é uma entrada necessária e define o **Nome de domínio totalmente qualificado (FQDN)** do gateway PSTN, conforme definido por um registro (A) do host DNS (Sistema de Nomes de Domínio), uma entrada de arquivo HOSTS estática ou pelo endereço IP do gateway PSTN.
  
O Protocolo de Transporte SIP pode ser um protocolo TCP ou um protocolo TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber qual é compatível com o seu gateway. O padrão é TLS, portanto, se o gateway tiver suporte para TLS, esta deve ser a escolha mais segura.
  
Selecione se deseja habilitar IPv4 e IPv6 para o gateway.
  
O **endereço IP de mídia alternativa** é uma definição para o servidor de mediação para o qual o gateway PSTN implantado tem um endereço IP diferente para o tráfego de mídia que o endereço IP configurado padrão, que geralmente é dedicado para o tráfego SIP. Se você definir esse parâmetro, o gateway PSTN incluirá suporte a uma interface de rede ou caminho de mídia diferente. Se esse endereço for deixado em branco, o gateway PSTN não incluirá suporte para o caminho alternativo de mídia.
  

