---
title: Exibição MediaLine
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: O MediaLine View armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio normalmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: cf360f06fa293dc75c33caa2a10ac761ae156e91
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858118"
---
# <a name="medialine-view"></a>Exibição MediaLine
 
O MediaLine View armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio normalmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**detalhes**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo do ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits para o chamador. Para detalhes, consulte a Especificação do Protocolo de Servidor do Monitoramento da Qualidade da Experiência.  <br/> |
|Segurança  <br/> |tinyint  <br/> |Perfil de segurança em uso. 0 é NONE (nenhum), 1 é SRTP, 2 é V1.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte. 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está ou não dentro da rede da organização. 1 significa que o chamador está dentro da rede corporativa, 0 significa que está fora.  <br/> |
|CallerMacAddress  <br/> |varchar(256)  <br/> |Endereço MAC da interface de rede usada pelo chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de Borda de A/V usado pelo chamador.  <br/> |
|CallerReflexiveIPAddr  <br/> |var(50)  <br/> |O endereço IP do chamador conforme relatado pelo serviço de Borda A/V. Este endereço pode ser diferente do endereço na coluna CallerIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver de dispositivo de renderização do chamador.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar(256  <br/> |Descrição do driver Wifi do chamador.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar(256)  <br/> |Versão do driver Wifi do chamador.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalhes da conexão de rede do chamador. Consulte a [tabela NetworkConnectionDetail para](networkconnectiondetail.md) obter mais informações. <br/> |
|CallerBssid  <br/> |varchar(256)  <br/> |Identificador SSID usado pela conexão WiFi do chamador.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor da chamada. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o receptor da chamada está dentro da rede corporativa. 1 significa que o receptor está dentro da rede corporativa, 0 significa que está fora.  <br/> |
|CalleeMacAddress  <br/> |varchar(256)  <br/> |Endereço MAC da interface de rede usada pelo receptor da chamada.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do serviço de Borda de A/V usado pelo receptor da chamada. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de Borda de A/V usado pelo receptor da chamada.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var(50)  <br/> |O endereço IP do chamador conforme relatado pelo serviço de Borda A/V. Este endereço pode ser diferente do endereço na coluna CalleeIPAddr se o cliente estiver localizado atrás de uma NAT, por exemplo.  <br/> |
|CalleeCaptureDev  <br/> |var(50)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar(256)  <br/> |Descrição do driver Wifi do destinatário.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar(256  <br/> |Versão do driver Wifi do destinatário.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar(256)  <br/> |Detalhes da conexão de rede do chamador. Consulte a [tabela NetworkConnectionDetail para](networkconnectiondetail.md) obter mais informações. <br/> |
|CalleeBssid  <br/> |varchar(256)  <br/> |Identificador de Conjunto de Serviços Básico usado pela conexão WiFi do chamador.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o receptor da chamada se conectou por uma rede virtual privada. 1 é rede virtual privada (VPN), 0 é não-VPN.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Esta é a largura de banda real aplicada a um dado fluxo de envio, considerando várias configurações de política (TURN, API, SDP, Servidor de Políticas, etc.). Não deve ser confundida com a largura de banda real porque pode haver uma largura de banda real menor com base na estimativa da largura de banda. Esta é basicamente a largura de banda máxima que o fluxo de envio pode usar, salvo limites impostos pela estimativa da largura de banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar(256)  <br/> |Origem da capacidade da largura de banda imposta. Ele descreve de onde vem o limite de largura de banda (por exemplo, "Servidor de Política", "SERVIDOR TURN" ou "Modalidade").  <br/> |
|Chamador  <br/> |bit  <br/> |Indica se as métricas do chamador foram recebidas; 1 é sim, 0 é não.  <br/> |
|Chamador  <br/> |bit  <br/> |Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, 0 é não.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica se o relatório refere-se a uma parte da chamada ou à chamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica se uma chamada foi classificada como ruim (1) ou boa (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica se o chamador se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica se o usuário receptor da chamada se conectou à rede usando o protocolo ICE (Internet Connectivity Establishment).  <br/> |
   

