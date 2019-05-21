---
title: Modo de exibição de mídia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
description: O modo de exibição de mídia armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 03b86aa6e954c61a40a28e1d2c2a0194b581849e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294863"
---
# <a name="medialine-view"></a>Modo de exibição de mídia
 
O modo de exibição de mídia armazena informações sobre cada linha de mídia no banco de dados. Uma sessão de áudio geralmente contém uma linha de mídia de áudio. Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**os**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|Segurança  <br/> |tinyint  <br/> |Perfil de segurança em uso. 0 é nenhum, 1 é SRTP; 2 é v1.  <br/> |
|SMTP  <br/> |tinyint  <br/> |Tipo de transporte. 0 é UDP; 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede da empresa. 0 significa que o chamador está fora da rede.  <br/> |
|CallerMacAddress  <br/> |varchar (256)  <br/> |Endereço MAC da interface de rede usada pelo chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de borda A/V usado pelo chamador.  <br/> |
|CallerReflexiveIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador reportado pelo serviço de borda A/V. Esse endereço pode ser diferente de CallerIPAddr se o cliente estiver localizado atrás de um NAT por exemplo.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |O nome do driver de dispositivo de renderização do chamador.  <br/> |
|CallerWifiDriverDeviceDesc  <br/> |varchar (256  <br/> |Descrição do driver WiFi do chamador.  <br/> |
|CallerWifiDriverVersion  <br/> |varchar (256)  <br/> |Versão do driver WiFi do chamador.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalhes da conexão de rede do chamador. Consulte a [tabela NetworkConnectionDetail](networkconnectiondetail.md) para obter mais informações. <br/> |
|CallerBssid  <br/> |varchar (256)  <br/> |Identificador do conjunto de serviços básico usado pela conexão WiFi de chamadores.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador está conectado por meio de uma rede virtual privada. 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se a chamada está dentro da rede corporativa. 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeMacAddress  <br/> |varchar (256)  <br/> |Endereço MAC da interface de rede usada pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de borda A/V usado pelo chamador.  <br/> |
|CalleeReflexiveIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador reportado pelo serviço de borda A/V. Esse endereço pode ser diferente de CalleeIPAddr se o cliente estiver localizado atrás de um NAT por exemplo.  <br/> |
|CalleeCaptureDev  <br/> |var (50)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do Calle.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Chame o nome do driver do dispositivo de processamento do recurso.  <br/> |
|CalleeWifiDriverDeviceDesc  <br/> |varchar (256)  <br/> |Descrição do driver WiFi do Calle.  <br/> |
|CalleeWifiDriverVersion  <br/> |varchar (256  <br/> |Versão do driver WiFi do Calle.  <br/> |
|CalleeNetworkConnectionDetail  <br/> |varchar (256)  <br/> |Detalhes da conexão de rede do Calle. Consulte a [tabela NetworkConnectionDetail](networkconnectiondetail.md) para obter mais informações. <br/> |
|CalleeBssid  <br/> |varchar (256)  <br/> |Identificador do conjunto de serviços básico usado pela conexão WiFi do chamador.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o chamador está conectado por meio de uma rede virtual privada. 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|ConversationalMOS  <br/> |decimal (3; 2)  <br/> |O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Esta é a largura de banda real aplicada ao fluxo de envios do lado fornecido com várias configurações de política (ativar, API, SDP, servidor de política etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.  <br/> |
|AppliedBandwidthSource  <br/> |varchar (256)  <br/> |Fonte do limite de largura de banda imposto. Ele descreve para onde o limite de largura de banda é proveniente (por exemplo, "servidor de políticas", "Ativar servidor" ou "modalidade").  <br/> |
|Chamador  <br/> |bit  <br/> |Indica se as métricas do autor foram recebidas; 1 é sim, 0 é não.  <br/> |
|Receptor  <br/> |bit  <br/> |Indica se as métricas do receptor da chamada foram recebidas; 1 é sim, 0 é não.  <br/> |
|MidCallReport  <br/> |bit  <br/> |Indica se o relatório é para uma parte da chamada ou para a chamada completa.  <br/> |
|ClassifiedPoorCall  <br/> |bit  <br/> |Indica se uma chamada foi classificada como uma chamada deficiente (1) ou uma boa chamada (0).  <br/> |
|CallerConnectivityICE  <br/> |tinyint  <br/> |Indica se o chamador está conectado à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).  <br/> |
|CalleeConnectivityICE  <br/> |tinyint  <br/> |Indica se o usuário chamou conexão à rede usando o protocolo ICE (estabelecimento de conectividade com a Internet).  <br/> |
   

