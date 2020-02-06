---
title: Lista de tabelas QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: O esquema de banco de dados consiste nas tabelas a seguir.
ms.openlocfilehash: 6c82585195befda13ebb14215e72a59341fac1d3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41808999"
---
# <a name="list-of-qoe-tables"></a>Lista de tabelas QoE
 
O esquema de banco de dados consiste nas tabelas a seguir. 
  
**Tabelas de suporte**

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com o compartilhamento de aplicativos.  <br/> |
|[Tabela CodecDescription](codecdescription.md) <br/> |Mapeia identificadores de codec exclusivos para o codec correspondente.  <br/> |
|[Tabela IPAddress](ipaddress.md) <br/> |Mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.  <br/> |
|[Tabela NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mapeia tipos de conexão de rede para os identificadores de conexão de rede usados em outro lugar no banco de dados de qualidade da experiência.  <br/> |
|[Tabela PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Armazena informações que especificam se (e quando) registros de qualidade de experiência desatualizados serão excluídos automaticamente do banco de dados de QoE.  <br/> |
|[Tabela de TraceRoute](traceroute.md) <br/> |Armazena informações de roteamento para chamadas.  <br/> |
|[Tabela UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mapeia identificadores de agente de usuário para os nomes descritivos do agente.  <br/> |
|[Tabela VideoMetricsThreshold](videometricsthreshold.md) <br/> |Armazena valores satisfatórios e satisfatórios para as métricas de qualidade da experiência usadas com chamadas com vídeo.  <br/> |
|[Tabela UserAgent](useragent.md) <br/> |Armazena cadeias de caracteres de UA (protocolo de início de sessão) do SIP e tipos de UA usados em sessões de áudio e vídeo.  <br/> |
|[Tabela User](user-0.md) <br/> |Armazena URIs de usuário, conferência e telefone usados em sessões de áudio e vídeo.  <br/> |
|[Tabela Endpoint](endpoint.md) <br/> |Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.  <br/> |
|[Tabela Pool](pool.md) <br/> |Armazena os nomes dos pools aos quais os dados de métricas pertencem.  <br/> |
|[Tabela Device](device.md) <br/> |Armazena dispositivos de captura e renderiza dispositivos que são usados em chamadas de áudio/vídeo.  <br/> |
|[Tabela DeviceDriver](devicedriver.md) <br/> |Armazena o driver para o dispositivo de captura e o dispositivo de renderização que são usados em chamadas de áudio/vídeo.  <br/> |
|[Tabela Conference](conference.md) <br/> |Armazena URIs de conferência para cenários de conferência ou caixa de diálogo para outros cenários.  <br/> |
|[Tabela SessionCorrelation](sessioncorrelation.md) <br/> |Armazena CorrelationId para chamadas PSTN.  <br/> |
|[Tabela PayloadDescription](payloaddescription.md) <br/> |Armazena o codec usado em chamadas de áudio/vídeo.  <br/> |
|[Tabela AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Armazena a fonte de largura de banda usada em chamadas de áudio/vídeo.  <br/> |
|[Tabela MacAddress](macaddress.md) <br/> |Armazena o endereço MAC dos pontos de extremidade que participam de sessões de áudio e vídeo.  <br/> |
|[Tabela Dialog](dialog.md) <br/> |Armazena a ID da caixa de diálogo de sessões de áudio e vídeo.  <br/> |
|[Tabela de regiões](region.md) <br/> |Armazena a região de rede definida na configuração NCS.  <br/> |
|[Tabela UserSite](usersite.md) <br/> |Armazena o site de rede definido na configuração NCS.  <br/> |
|[Tabela Subnet](subnet.md) <br/> |Armazena a sub-rede definida na configuração NCS.  <br/> |
|[Tabela MonitoredRegionLink](monitoredregionlink.md) <br/> |Armazena o link de região definido na configuração NCS.  <br/> |
|[Tabela MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Armazena os links de sites de rede definidos na configuração NCS.  <br/> |
|[Tabela EndpointSubnet](endpointsubnet.md) <br/> |Armazena a sub-rede do ponto de extremidade que participa de uma sessão de áudio e vídeo.  <br/> |
|[Tabela Server](server.md) <br/> |Armazena o FQDN ou endereço IP do servidor ao qual a mídia vai.  <br/> |
   
**Tabelas para dados de métricas**

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingStream](appsharingstream.md) <br/> |Armazena métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos. Métricas de qualidade de experiência para os fluxos de rede usados para compartilhamento de aplicativos.  <br/> |
|[Tabela Session](session.md) <br/> |Armazena informações gerais sobre uma sessão de áudio ou de áudio/vídeo. Uma sessão é definida como uma caixa de diálogo de áudio ou vídeo SIP entre dois pontos de extremidade.  <br/> |
|[Tabela MediaLine](medialine-0.md) <br/> |Armazena informações sobre cada linha de mídia em uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo. Geralmente, uma única linha de mídia terá dois fluxos, áudio ou vídeo.  <br/> |
|[Tabela AudioStream](audiostream.md) <br/> |Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioSignal](audiosignal.md) <br/> |Armazena métricas de qualidade de mídia de áudio na linha de mídia. Isso inclui as métricas de cancelamento de eco acústico (AEC) e controle automático de ganho (AGC).  <br/> |
|[Tabela VideoStream](videostream.md) <br/> |Armazena as métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioClientEvent](audioclientevent.md) <br/> |Armazena métricas de qualidade da mídia de áudio coletadas do evento do cliente.  <br/> |
|[Tabela VideoClientEvent](videoclientevent.md) <br/> |Armazena as métricas de qualidade da mídia de vídeo coletadas do evento do cliente.  <br/> |
|**Tabela DiagnosticData** <br/> |Armazena dados de diagnóstico que são somente para uso interno.  <br/> |
   
**Tabelas para dados de resumo**

|**Tabela**|**Descrição**|
|:-----|:-----|
|**Tabela ServerSummary** <br/> |Armazena dados de resumo para os servidores, esses dados são usados apenas para relatórios de qualidade da experiência (QoE).  <br/> |
|**Tabela do usersummary** <br/> |Armazena dados de resumo para os usuários, esses dados são usados somente para relatórios de QoE.  <br/> |
|**Tabela CallTypeSummary** <br/> |Armazenar dados de resumo para tipos de chamadas, esses dados são usados somente para relatórios de QoE.  <br/> |
   
**Tabelas para uso interno pelo Monitoring Server**

|**Tabela**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Somente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Somente para uso interno.  <br/> |
|**Tabela de front-end** <br/> |Somente para uso interno.  <br/> |
|**Tabela de tarefas** <br/> |Somente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Somente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Somente para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Somente para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Somente para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Somente para uso interno.  <br/> |
|**Fusos horários** <br/> |Somente para uso interno.  <br/> |
|**Tabela CallSummary** <br/> |Somente para uso interno.  <br/> |
|**Tabela DeviceCallSumary** <br/> |Somente para uso interno.  <br/> |
|**Tabela de locatários** <br/> |Somente para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
   

