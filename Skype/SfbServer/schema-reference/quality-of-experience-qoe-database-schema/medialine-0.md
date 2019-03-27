---
title: Tabela MediaLine
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa uma única linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Um áudio e vídeo (A / V) sessão geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado.
ms.openlocfilehash: 11c309091211ce0bc480fa032e0f1dbbbbf533cd
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896067"
---
# <a name="medialine-table"></a>Tabela MediaLine
 
Cada registro representa uma única linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Um áudio e vídeo (A / V) sessão geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de sessão](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de sessão](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |0 é áudio principal, 1 é o vídeo principal e 2 é vídeo panorâmico, 3 é o compartilhamento de aplicativo/área de trabalho, 16 é o vídeo com base em compartilhamento de tela (VbSS). Esse rótulo deve ser exclusivo dentro de uma única sessão.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Essa coluna está presente, mas não utilizado no Microsoft Lync Server 2013. Informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descrito em sinalizadores de bits. Para obter detalhes, consulte a *Qualidade da experiência do Monitoring Server especificação de protocolo* , disponível para download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Mesmo como CallerIceWarningFlags, mas no lado do receptor. Para obter detalhes, consulte a *Qualidade da experiência do Monitoring Server especificação de protocolo* , disponível para download. <br/> |
|**Segurança** <br/> |tinyint  <br/> | <br/> |O perfil de segurança em uso. 0 é NONE, 1 é o SRTP, 2 é V1.  <br/> |
|**Transporte** <br/> |tinyint  <br/> | <br/> |0 é UDP, 1 é TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP do chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Porta usada pelo chamador. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Externa <br/> |A sub-rede do chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa que o chamador está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Externa  <br/> |Endereço de mac do chamador, referenciado da [tabela MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP do / serviço de borda V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Porta usada no serviço de borda de V pelo chamador /.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Externa  <br/> |Usado pelo chamador do dispositivo de captura. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Externa  <br/> |Usada pelo chamador do dispositivo de renderização. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Driver de dispositivo de captura do chamador, referenciado na [DeviceDriver table](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Externa  <br/> |Driver de dispositivo de renderização do chamador, referenciado na [DeviceDriver table](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica como o chamador se conectou à rede. Valores são obtidos da [tabela NetworkConnectionDetail](networkconnectiondetail.md). Valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão de Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Externa  <br/> |BSSID do chamador se wireless é usado. Referência na [MacAddress table](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||Link do chamador. 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||A velocidade de link de rede, em bps, para o ponto de extremidade do chamador.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP do receptor da chamada. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Porta usada pelo receptor da chamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Externa  <br/> |Subrede do receptor. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa que o receptor da chamada está dentro da rede corporativa, 0 significa que o receptor da chamada está fora da rede.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Externa  <br/> |Endereço Mac do receptor da chamada. Referenciado da [tabela MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP do serviço de borda V usada pelo receptor da chamada. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Porta usada no serviço de borda de V pelo receptor da chamada /.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |externa  <br/> |Usado pelo receptor da chamada do dispositivo de captura. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Externa  <br/> |Usado pelo receptor da chamada do dispositivo de renderização. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Externa  <br/> |Driver de dispositivo de captura do receptor da chamada. Referenciado na [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Externa  <br/> |Driver de dispositivo de renderização do receptor da chamada. Referenciado na [DeviceDriver table](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externa  <br/> |Indica como o receptor da chamada conectada à rede. Valores são obtidos da [tabela NetworkConnectionDetail](networkconnectiondetail.md). Valores típicos são 0 para uma conexão com fio ' 1 para uma conexão WiFi; e 3 para uma conexão de Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Externa  <br/> |BSSID do receptor se wireless é usado. Referência na [MacAddress table](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |Link do receptor da chamada; 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |A velocidade de link de rede, em bps, para o ponto de extremidade do receptor da chamada.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS da conversa de banda estreita sessões de áudio (com base em dois fluxos de áudio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Esta é a largura de banda real aplicada ao envio determinado lado fluxo dado várias configurações de política (ativar, API, SDP, servidor de políticas e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva inferior com base na estimativa de largura de banda. Isto é, basicamente, a largura de banda máxima, que o fluxo de envio pode demorar limites impostos pela estimativa de largura de banda de bloqueio.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Isso representa a origem do limite de largura de banda que está sendo imposta. Ele descreve onde o limite de largura de banda é proveniente ("Política de servidor", "Ativar o servidor", "Modalidade" e assim por diante). Referenciado da [tabela AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Chamador** <br/> |bit  <br/> | <br/> |Indica se as métricas do chamador foram recebidas; 1 é Sim, um valor nulo é nenhum.  <br/> |
|**Receptor** <br/> |bit  <br/> | <br/> |Indica se as métricas do receptor da chamada foram recebidas; 1 é Sim, um valor nulo é nenhum.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica se o relatório é para uma parte da sessão ou da sessão inteira.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica se uma chamada foi classificada como pobre (valor de 1) ou uma chamada boa (0).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP reflexivo do usuário que fez a chamada. Em organizações que usam NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versão para o driver WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Externa  <br/> |Endereço IP reflexivo do usuário que recebeu a chamada. Em organizações que usam NAT (conversão de endereço de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Externa  <br/> |Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Externa  <br/> |Número de versão para o driver WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

