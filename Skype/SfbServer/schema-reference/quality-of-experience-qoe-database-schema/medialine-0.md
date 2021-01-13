---
title: Tabela MediaLine
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
description: Cada registro representa uma linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o Gallery View for usado.
ms.openlocfilehash: 99a54fe7a4ee4e91506069873c98d423b9069f06
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802761"
---
# <a name="medialine-table"></a>Tabela MediaLine
 
Cada registro representa uma linha de mídia. (Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo, embora a sessão possa conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o Gallery View for usado.
  
|**Coluna**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [Session](session.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [Session](session.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |0 é áudio principal, 1 é vídeo principal e 2 é vídeo panorâmico, 3 é Compartilhamento de Aplicativo/Área de Trabalho, 16 é Compartilhamento de Tela Baseado em Vídeo (VbSS). Esse rótulo deve ser exclusivo em uma única sessão.  <br/> |
|**ConnectivityIce** <br/> |tinyint  <br/> | <br/> |Esta coluna está presente, mas não é usada no Microsoft Lync Server 2013. Informações sobre a conectividade usada para uma linha de mídia são capturadas nas colunas CallerConnectivityICE e CalleeConnectivityICE.  <br/> |
|**CallerIceWarningFlags** <br/> |int  <br/> | <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits. Para obter detalhes, consulte a  *Especificação de*  Protocolo do Servidor de Monitoramento de Qualidade da Experiência, disponível para download. <br/> |
|**CalleeIceWarningFlags** <br/> |int  <br/> | <br/> |Mesmo que CallerIceWarningFlags, mas no lado do chamado. Para obter detalhes, consulte a  *Especificação de*  Protocolo do Servidor de Monitoramento de Qualidade da Experiência, disponível para download. <br/> |
|**Segurança** <br/> |tinyint  <br/> | <br/> |O perfil de segurança em uso. 0 é NONE (nenhum), 1 é SRTP, 2 é V1.  <br/> |
|**Transport** <br/> |tinyint  <br/> | <br/> |0 é UDP, 1 é TCP.  <br/> |
|**CallerIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP do chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CallerPort** <br/> |int  <br/> | <br/> | Porta usada pelo chamador. <br/> |
|**CallerSubnet** <br/> |int  <br/> | Externo <br/> |A sub-rede do chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CallerInside** <br/> |bit  <br/> | <br/> |1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.  <br/> |
|**CallerMacAddress** <br/> |int  <br/> |Externo  <br/> |Endereço mac do chamador, referenciado na [tabela MacAddress](macaddress.md).  <br/> |
|**CallerRelayIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CallerRelayPort** <br/> |int  <br/> | <br/> |Porta usada no serviço de Borda A/V pelo chamador.  <br/> |
|**CallerCaptureDev** <br/> |int  <br/> |Externo  <br/> |Dispositivo de captura usado pelo chamador. Referenciado na tabela [Device](device.md).  <br/> |
|**CallerRenderDev** <br/> |int  <br/> |Externo  <br/> |Dispositivo de renderização usado pelo chamador. Referenciado na tabela [Device](device.md).  <br/> |
|**CallerCaptureDevDriver** <br/> |int  <br/> |Externo  <br/> |Driver para o dispositivo de captura do chamador, referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CallerRenderDevDriver** <br/> |int  <br/> |Externo  <br/> |Driver para o dispositivo de renderização do chamador, referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CallerNetworkConnectionType** <br/> |tinyint  <br/> |Externo  <br/> |Indica como o chamador se conectou à rede. Os valores são obtidos da [tabela NetworkConnectionDetail](networkconnectiondetail.md). Os valores típicos são 0 para uma conexão com fio' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.  <br/> |
|**CallerBssid** <br/> |int  <br/> |Externo  <br/> |BSSID do chamador se for usado sem fio. Referenciado da [tabela MacAddress](macaddress.md).  <br/> |
|**CallerVPN** <br/> |bit  <br/> ||O link do chamador. 1 é para rede virtual privada (VPN), 0 é para não-VPN.  <br/> |
|**CallerLinkSpeed** <br/> |decimal(18,0)  <br/> ||A velocidade do link de rede, em bps, para o ponto de extremidade do chamador.  <br/> |
|**CalleeIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP do receptor da chamada. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CalleePort** <br/> |bit  <br/> ||Porta usada pelo receptor da chamada.  <br/> |
|**CalleeSubnet** <br/> |int  <br/> |Externo  <br/> |Sub-rede do destinatário da chamada. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CalleeInside** <br/> |bit  <br/> | <br/> |1 significa que o receptor de chamada está dentro da rede corporativa, 0 significa que o receptor de chamada está fora da rede.  <br/> |
|**CalleeMacAddress** <br/> |int  <br/> |Externo  <br/> |Endereço mac do destinatário da chamada. Referenciado na tabela [MacAddress](macaddress.md).  <br/> |
|**CalleeRelayIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP do serviço de Borda A/V usado pelo receptor de chamada. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|**CalleeRelayPort** <br/> |int  <br/> | <br/> |Porta usada no Serviço de Borda A/V pelo receptor de chamada.  <br/> |
|**CalleeCaptureDev** <br/> |int  <br/> |externo  <br/> |Dispositivo de captura usado pelo receptor de chamada. Referenciado na tabela [Device](device.md).  <br/> |
|**CalleeRenderDev** <br/> |int  <br/> |Externo  <br/> |Dispositivo de renderização usado pelo receptor de chamada. Referenciado na tabela [Device](device.md).  <br/> |
|**CalleeCaptureDevDriver** <br/> |int  <br/> |Externo  <br/> |Driver para o dispositivo de captura do receptor da chamada. Referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CalleeRenderDevDriver** <br/> |varchar(256)  <br/> |Externo  <br/> |Driver para o dispositivo de renderização do receptor da chamada. Referenciado na [tabela DeviceDriver](devicedriver.md).  <br/> |
|**CalleeNetworkConnectionType** <br/> |tinyint  <br/> |Externo  <br/> |Indica como o chamado se conectou à rede. Os valores são obtidos da [tabela NetworkConnectionDetail](networkconnectiondetail.md). Os valores típicos são 0 para uma conexão com fio' 1 para uma conexão WiFi; e 3 para uma conexão Ethernet.  <br/> |
|**CalleeBssid** <br/> |int  <br/> |Externo  <br/> |BSSID do destinatário da chamada se for usado sem fio. Referenciado da [tabela MacAddress](macaddress.md).  <br/> |
|**CalleeVPN** <br/> |bit  <br/> | <br/> |O link do receptor da chamada; 1 é VPN (rede virtual privada), 0 é não VPN.  <br/> |
|**CalleeLinkSpeed** <br/> |decimal(18,0)  <br/> | <br/> |A velocidade do link de rede, em bps, para o ponto de extremidade do receptor da chamada.  <br/> |
|**ConversationalMOS** <br/> |decimal(3,2)  <br/> | <br/> |MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|**AppliedBandwidthLimit** <br/> |int  <br/> ||Essa é a largura de banda real aplicada ao fluxo de envio determinado, considerando várias configurações de política (TURN, API, SDP, Servidor de Políticas e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda. Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.  <br/> |
|**AppliedBandwidthSourceKey** <br/> |smallint  <br/> ||Essa é a origem do cap de largura de banda que está sendo imposto. Ele descreve de onde vem o limite de largura de banda ("Servidor de Política", "Servidor TURN", "Modalidade" e assim por diante). Referenciado da [tabela AppliedBandwidthSource](appliedbandwidthsource.md).  <br/> |
|**Caller** <br/> |bit  <br/> | <br/> |Indica se métricas do chamador foram recebidas; 1 é sim, um valor nulo é não.  <br/> |
|**Destinatário da chamada** <br/> |bit  <br/> | <br/> |Indica se métricas do receptor da chamada foram recebidas; 1 é sim, um valor nulo é não.  <br/> |
|**MidCallReport** <br/> |bit  <br/> ||Indica se o relatório é para uma parte da sessão ou para a sessão completa.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||Indica se uma chamada foi classificada como uma chamada ruim (valor 1) ou como uma boa chamada (0).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerConnectivityICE** <br/> |tinyInt  <br/> ||Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeConnectivityICE** <br/> |tinyint  <br/> ||Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerReflexiveLocalIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP reflexivo do usuário que fez a chamada. Em organizações que usam NAT (conversão de endereços de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverDevicesDesc** <br/> |int  <br/> |Externo  <br/> |Descrição do dispositivo para o driver WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CallerWiFiDriverVersion** <br/> |int  <br/> |Externo  <br/> |Número da versão do driver de WiFi empregado pelo usuário que fez a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleReflexiveLocalIPAddr** <br/> |int  <br/> |Externo  <br/> |Endereço IP reflexivo do usuário que recebeu a chamada. Em organizações que usam NAT (conversão de endereços de rede), o endereço IP reflexivo é o endereço IP do servidor proxy.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverDevicesDesc** <br/> |int  <br/> |Externo  <br/> |Descrição do dispositivo para o driver de WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**CalleeWiFiDriverVersion** <br/> |int  <br/> |Externo  <br/> |Número da versão do driver de WiFi empregado pelo usuário que recebeu a chamada.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

