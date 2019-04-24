---
title: Expansor de Configurações de Gateway PSTN
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PstnGatewaySettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0fd103df-150d-4ea8-b522-18dbc50f5061
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:'
ms.openlocfilehash: 45b3945a811a2e9c9b5d1c0cce805c78368c9a70
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201626"
---
# <a name="pstn-gateway-settings-expander"></a><span data-ttu-id="f6722-103">Expansor de Configurações de Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="f6722-103">PSTN Gateway Settings Expander</span></span>
 
<span data-ttu-id="f6722-104">Para editar ou modificar as configurações de um gateway PSTN (Rede Telefônica Pública Comutada), modifique os campos a seguir:</span><span class="sxs-lookup"><span data-stu-id="f6722-104">To edit or modify the settings for a public switched telephone network (PSTN) gateway, modify the following fields:</span></span>
  
<span data-ttu-id="f6722-105">O FQDN do gateway ou Endereço IP é uma entrada necessária e define o **Nome de domínio totalmente qualificado (FQDN)** do gateway PSTN, conforme definido por um registro (A) do host DNS (Sistema de Nomes de Domínio), uma entrada de arquivo HOSTS estática ou pelo endereço IP do gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="f6722-105">Gateway FQDN or IP Address is a required entry and defines wither the **Fully qualified domain name (FQDN)** of the PSTN gateway as defined by a Domain Name System (DNS) host (A) record, a static HOSTS file entry, or by the IP address of the PSTN gateway.</span></span>
  
<span data-ttu-id="f6722-p101">O Protocolo de Transporte SIP pode ser um protocolo TCP ou um protocolo TLS. TLS é o padrão. Consulte a documentação do fornecedor do gateway para saber qual é compatível com o seu gateway. O padrão é TLS, portanto, se o gateway tiver suporte para TLS, esta deve ser a escolha mais segura.</span><span class="sxs-lookup"><span data-stu-id="f6722-p101">The SIP Transport Protocol can either be Transmission Control Protocol (TCP) or Transport Layer Security (TLS). TLS is the default. Refer to the gateway vendor documentation for what you gateway supports. The default is TLS, and should be considered the more secure selection, if the gateway supports TLS.</span></span>
  
<span data-ttu-id="f6722-110">Selecione se deseja habilitar IPv4 e IPv6 para o gateway.</span><span class="sxs-lookup"><span data-stu-id="f6722-110">Select whether to enable IPv4 and IPv6 for the gateway.</span></span>
  
<span data-ttu-id="f6722-111">O **endereço IP de mídia alternativa** é uma definição para o servidor de mediação para o qual o gateway PSTN implantado tem um endereço IP diferente para o tráfego de mídia que o endereço IP configurado padrão, que geralmente é dedicado para o tráfego SIP.</span><span class="sxs-lookup"><span data-stu-id="f6722-111">The **Alternate media IP address** is a definition for the Mediation Server for which the deployed PSTN gateway has a different IP address for media traffic than the default configured IP address, which is typically dedicated for SIP traffic.</span></span> <span data-ttu-id="f6722-112">Se você definir esse parâmetro, o gateway PSTN incluirá suporte a uma interface de rede ou caminho de mídia diferente.</span><span class="sxs-lookup"><span data-stu-id="f6722-112">If you define this parameter, then the PSTN gateway supports a different supports a different network interface or path for media.</span></span> <span data-ttu-id="f6722-113">Se esse endereço for deixado em branco, o gateway PSTN não incluirá suporte para o caminho alternativo de mídia.</span><span class="sxs-lookup"><span data-stu-id="f6722-113">If this address is left blank, then the PSTN gateway does not support the alternate path for media.</span></span>
  

