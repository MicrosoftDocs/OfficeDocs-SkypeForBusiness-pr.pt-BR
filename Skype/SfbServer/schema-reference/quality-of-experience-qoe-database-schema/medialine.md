---
title: Exibir MediaLine
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: O modo de exibição de MediaLine armazena informações sobre cada linha de mídia no banco de dados. Normalmente, uma sessão de áudio conterá uma linha de mídia de áudio. Um áudio e vídeo (A / V) sessão normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; No entanto, a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 04037bae4b2f04058667d42205a2e0b33abacb4f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894213"
---
# <a name="medialine-view"></a>Exibir MediaLine
 
O modo de exibição de MediaLine armazena informações sobre cada linha de mídia no banco de dados. Normalmente, uma sessão de áudio conterá uma linha de mídia de áudio. Um áudio e vídeo (A / V) sessão normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; No entanto, a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o chamador. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o receptor. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|Segurança  <br/> |tinyint  <br/> |Perfil de segurança em uso. 0 é NONE, 1 é o SRTP, 2 é V1.  <br/> |
|Transporte  <br/> |tinyint  <br/> |Tipo de transporte. 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do chamador. Isso pode ser o endereço de um IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se ou não o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede corporativa. 0 significa que o chamador está fora da rede.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Endereço MAC da interface de rede usada pelo chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do / serviço de borda V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no / serviço de borda V usado pelo chamador.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |Endereço IP do chamador conforme relatado pelo / serviço de borda V. Esse endereço pode ser diferente que o CallerIPAddr se o cliente está localizado, por exemplo, por trás de um NAT.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Descrição da unidade Wifi do chamador.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Versão da unidade Wifi do chamador.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalhes da conexão de rede do chamador. Consulte a [tabela NetworkConnectionDetail](networkconnectiondetail.md) para obter mais informações. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Identificador SSID usado pela conexão WiFi.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador conectou por uma rede privada virtual. 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor. Isso pode ser o endereço de um IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o receptor está dentro da rede corporativa. 1 significa que o receptor está na rede corporativa, 0 significa que o receptor está fora da rede.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Endereço MAC da interface de rede usada pelo receptor.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do / serviço de borda V usado pelo receptor. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no / serviço de borda V usado pelo receptor.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor conforme relatado pelo / serviço de borda V. Esse endereço pode ser diferente que o CalleeIPAddr se o cliente está localizado, por exemplo, por trás de um NAT.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nome do dispositivo de captura do receptor.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do receptor.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do receptor.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do receptor.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Descrição da unidade Wifi do receptor.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Versão da unidade Wifi do receptor.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalhes da conexão de rede do receptor. Consulte a [tabela NetworkConnectionDetail](networkconnectiondetail.md) para obter mais informações. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Identificador SSID usado pela conexão de WiFi do receptor.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o receptor da chamada se conectou por uma rede privada virtual. 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da conversa de banda estreita sessões de áudio (com base em dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Esta é a largura de banda real aplicada ao envio determinado lado fluxo dado várias configurações de política (ativar, API, SDP, servidor de políticas, etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva inferior com base na estimativa de largura de banda. Isto é, basicamente, a largura de banda máxima, que o fluxo de envio pode demorar limites impostos pela estimativa de largura de banda de bloqueio.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Origem do limite de largura de banda que está sendo imposta. Ele descreve onde o limite de largura de banda é proveniente (por exemplo, "Política de servidor", "Ativar o servidor" ou "Modalidade").  <br/> |
|Chamador  <br/> |bit  <br/> |Indica se as métricas do chamador foram recebidas; 1 é Sim, 0 é não.  <br/> |
|Receptor  <br/> |bit  <br/> |Indica se as métricas do receptor da chamada foram recebidas; 1 é Sim, 0 é não.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica se o relatório é para uma parte da chamada ou à chamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica se uma chamada foi classificada como pobre (1) ou uma chamada boa (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica se o usuário chamada se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> |
   

