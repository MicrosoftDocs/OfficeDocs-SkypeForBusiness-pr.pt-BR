---
title: Expansor de Configurações de Gateway PSTN
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 56f26a4113841b7563e42180aa51a80eedb2f859
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823721"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="18f48-103">Expansor de Configurações de Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="18f48-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="18f48-104">Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="18f48-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="18f48-105">FQDN ou Endereço IP do Gateway é uma entrada necessária e define o **Nome de domínio totalmente qualificado (FQDN)** do gateway PSTN, conforme definido por um registro (A) do host DNS (Domain Name System), uma entrada de arquivo HOSTS estática ou pelo endereço IP do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="18f48-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="18f48-p101">O Protocolo de Transporte SIP pode ser TCP (Transmission Control Protocol) ou TLS (Transport Layer Security). TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber o que seu gateway suporta. O padrão é TLS, e deve ser considerado a seleção mais segura, se o gateway suportar TLS.</span><span class="sxs-lookup"><span data-stu-id="18f48-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="18f48-110">Selecione se deseja habilitar IPv4 e IPv6 para o gateway.</span><span class="sxs-lookup"><span data-stu-id="18f48-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="18f48-p102">O **Endereço IP de mídia alternativo** é uma definição para o Servidor de Mediação para o qual o gateway PSTN implantado tem um endereço IP diferente para tráfego de mídia com relação ao endereço IP padrão configurado, que é normalmente dedicado ao tráfego SIP. Se você definir esse parâmetro, o gateway PSTN suportará uma interface de rede diferente ou caminho para mídia diferente. Se esse endereço for deixado em branco, o gateway PSTN não suportará o caminho alternativo para mídia.</span><span class="sxs-lookup"><span data-stu-id="18f48-p102">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic. If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media. If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

