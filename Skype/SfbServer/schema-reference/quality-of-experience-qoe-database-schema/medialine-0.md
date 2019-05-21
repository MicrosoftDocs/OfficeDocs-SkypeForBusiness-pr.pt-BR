---
title: Tabela MediaLine
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa uma linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.
ms.openlocfilehash: f9ededade35e5654a89b68343f44094f4319ae70
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294891"
---
# <a name="medialine-table"></a>Tabela MediaLine
 
Cada registro representa uma linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de sessão](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de sessão](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |0 é o áudio principal, 1 é o vídeo principal e 2 é o vídeo panorâmico, 3 é o compartilhamento de aplicativos/desktops, 16 é o compartilhamento de tela baseado em vídeo (VbSS). Esse rótulo deve ser exclusivo em uma única sessão.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013. Informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits. Para obter detalhes, consulte a *especificação de protocolo de servidor do monitoramento de qualidade de experiência* , disponível para download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Mesmo que CallerIceWarningFlags, mas no lado do chamador. Para obter detalhes, consulte a *especificação de protocolo de servidor do monitoramento de qualidade de experiência* , disponível para download. <br/> |
|**Segurança** <br/> |tinyint  <br/> | <br/> |O perfil de segurança em uso. 0 é nenhum, 1 é SRTP; 2 é v1.  <br/> |
|**SMTP** <br/> |tinyint  <br/> | <br/> |0 é UDP; 1 é TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP do chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Porta usada pelo chamador. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Exterior <br/> |A sub-rede do chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Exterior  <br/> |Endereço MAC do chamador, referenciado na [tabela MACAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Porta usada no serviço de borda A/V pelo chamador.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Exterior  <br/> |Dispositivo de captura usado pelo chamador. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Exterior  <br/> |Processar o dispositivo usado pelo chamador. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Exterior  <br/> |Driver para o dispositivo de captura do chamador, referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Exterior  <br/> |Driver para o dispositivo de renderização do chamador, referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Exterior  <br/> |Indica como o chamador está conectado à rede. Os valores são obtidos na [tabela NetworkConnectionDetail](networkconnectiondetail.md). Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Exterior  <br/> |BSSID do chamador se for usada uma conexão sem fio. Referenciado da [tabela MACAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||O link do chamador. 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal (18, 0)  <br/> ||A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP do receptor da chamada. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Porta usada pelo receptor da chamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Exterior  <br/> |Sub-rede do chamado. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa que o receptor da chamada está dentro da rede corporativa, 0 significa que o receptor da chamada está fora da rede.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Exterior  <br/> |Endereço MAC do chamador. Referenciado na [tabela MACAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP do serviço de borda A/V usado pelo receptor de chamadas. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Porta usada no serviço de borda a/V pelo receptor da chamada.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |exterior  <br/> |Dispositivo de captura usado pelo receptor de chamadas. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Exterior  <br/> |Processar o dispositivo usado pelo receptor da chamada. Referenciado da [tabela de dispositivos](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Exterior  <br/> |Driver para o dispositivo de captura do receptor da chamada. Referenciado pela [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar (256)  <br/> |Exterior  <br/> |Driver para o dispositivo de renderização do receptor da chamada. Referenciado pela [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Exterior  <br/> |Indica como o chamador está conectado à rede. Os valores são obtidos na [tabela NetworkConnectionDetail](networkconnectiondetail.md). Os valores típicos são 0 para uma conexão com fio ' 1 para conexão WiFi; e 3 para uma conexão Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Exterior  <br/> |BSSID do chamador se for usada uma conexão sem fio. Referenciado da [tabela MACAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |O link do receptor da chamada; 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal (18, 0)  <br/> | <br/> |A velocidade do link de rede, em bps, para o ponto de extremidade do receptor da chamada.  <br/> |
|**ConversationalMOS** <br/> |decimal (3; 2)  <br/> | <br/> |O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Esta é a largura de banda real aplicada ao fluxo de envios do lado fornecido com várias configurações de política (ativar, API, SDP, servidor de política e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Essa é a origem do limite de largura de banda que está sendo imposto. Ele descreve onde o limite de largura de banda é proveniente de ("servidor de políticas", "Ativar servidor", "Janelarestritaidade" e assim por diante). Referenciado da [tabela AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Chamador** <br/> |bit  <br/> | <br/> |Indica se as métricas do autor foram recebidas; 1 é sim, um valor nulo é não.  <br/> |
|**Receptor** <br/> |bit  <br/> | <br/> |Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, um valor nulo é não.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica se o relatório é para uma parte da sessão ou para a sessão completa.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou uma boa chamada (0).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP reflexivo do usuário que fez a chamada. Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Exterior  <br/> |Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Exterior  <br/> |Número da versão do driver WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Exterior  <br/> |Endereço IP reflexivo do usuário que recebeu a chamada. Em organizações que usam NAT (Network Address Translation), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Exterior  <br/> |Descrição do dispositivo para o driver WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Exterior  <br/> |Número da versão do driver WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

