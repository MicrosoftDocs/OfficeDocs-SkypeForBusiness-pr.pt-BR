---
title: Lista de tabelas QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: O esquema de banco de dados consiste em tabelas a seguir.
ms.openlocfilehash: c3ab045e67f38082910f5a2870d4e8c0c8e595b4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30895898"
---
# <a name="list-of-qoe-tables"></a>Lista de tabelas QoE
 
O esquema de banco de dados consiste em tabelas a seguir. 
  
**Tabelas de suporte**

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Armazena valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com compartilhamento de aplicativos.  <br/> |
|[Tabela CodecDescription](codecdescription.md) <br/> |Mapeia identificadores exclusivos de codec ao codec correspondente.  <br/> |
|[Tabela IPAddress](ipaddress.md) <br/> |Mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência.  <br/> |
|[Tabela NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mapeia os tipos de conexão de rede para os identificadores de conexão de rede usados em outros locais no banco de dados de qualidade da experiência.  <br/> |
|[Tabela PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Armazena informações que especificam se (e quando) desatualizadas Quality of Experience registros serão excluídos automaticamente do banco de dados de QoE.  <br/> |
|[Tabela TraceRoute](traceroute.md) <br/> |Armazena informaçoes de roteamento para chamadas.  <br/> |
|[Tabela UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mapeia identificadores de agente do usuário aos nomes descritivos dos agentes.  <br/> |
|[Tabela VideoMetricsThreshold](videometricsthreshold.md) <br/> |Armazena valores ótimos e aceitáveis para as métricas de qualidade da experiência usadas com chamadas de vídeo.  <br/> |
|[Tabela UserAgent](useragent.md) <br/> |Armazena as cadeias de caracteres do agente de usuário do protocolo de iniciação de sessão (SIP) (UA) e tipos de UA usados em sessões de áudio e vídeos.  <br/> |
|[Tabela User](user-0.md) <br/> |Usuário de repositórios, conferência e URIs de telefone usados em sessões de áudio e vídeos.  <br/> |
|[Tabela Endpoint](endpoint.md) <br/> |Armazena os nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeos.  <br/> |
|[Tabela Pool](pool.md) <br/> |Armazena os nomes de pools aos quais métricas dados pertencem.  <br/> |
|[Tabela Device](device.md) <br/> |Armazena os dispositivos de captura e renderizar dispositivos que são usados em um chamadas de áudio/vídeo.  <br/> |
|[Tabela DeviceDriver](devicedriver.md) <br/> |Armazena o driver para o dispositivo de captura e o dispositivo de renderização que são usados em chamadas de áudio/vídeo.  <br/> |
|[Tabela Conference](conference.md) <br/> |Armazena URIs de conferência para cenários de conferência ou DialogID para outros cenários.  <br/> |
|[Tabela SessionCorrelation](sessioncorrelation.md) <br/> |Armazena CorrelationID para chamadas PSTN.  <br/> |
|[Tabela PayloadDescription](payloaddescription.md) <br/> |Armazena o Codec usado em chamadas de áudio/vídeo.  <br/> |
|[Tabela AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Armazena a fonte de largura de banda usada em chamadas de áudio/vídeo.  <br/> |
|[Tabela MacAddress](macaddress.md) <br/> |Armazena o endereço MAC dos pontos de extremidade que participam de sessões de áudio e vídeos.  <br/> |
|[Tabela Dialog](dialog.md) <br/> |Armazena a ID de diálogo de sessões de áudio e vídeos.  <br/> |
|[Tabela de regiões](region.md) <br/> |Armazena a região de rede definida na configuração NCS.  <br/> |
|[Tabela UserSite](usersite.md) <br/> |Armazena o site de rede definido na configuração NCS.  <br/> |
|[Tabela Subnet](subnet.md) <br/> |Armazena a sub-rede definida na configuração NCS.  <br/> |
|[Tabela MonitoredRegionLink](monitoredregionlink.md) <br/> |Armazena o link de região definido na configuração NCS.  <br/> |
|[Tabela MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Armazena os links de site de rede definidos na configuração NCS.  <br/> |
|[Tabela EndpointSubnet](endpointsubnet.md) <br/> |Armazena a sub-rede do ponto de extremidade participando de uma sessão de áudio e vídeo.  <br/> |
|[Tabela Server](server.md) <br/> |Armazena o endereço IP ou FQDN do servidor que a mídia passa.  <br/> |
   
**Tabelas para dados de métrica**

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingStream](appsharingstream.md) <br/> |Armazena métricas de qualidade da experiência para os fluxos de rede usados para compartilhamento de aplicativos. Qualidade de métricas de experiência para os fluxos de rede usados para compartilhamento de aplicativos.  <br/> |
|[Tabela Session](session.md) <br/> |Armazena informações gerais sobre uma sessão de áudio ou áudio/vídeo. Uma sessão é definida como um diálogo SIP de áudio ou vídeo entre dois pontos de extremidade.  <br/> |
|[Tabela MediaLine](medialine-0.md) <br/> |Armazena informações sobre cada linha de mídia em uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeos. Normalmente, uma linha de mídia único terá dois fluxos, áudio ou vídeos.  <br/> |
|[Tabela AudioStream](audiostream.md) <br/> |Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioSignal](audiosignal.md) <br/> |Armazena métricas de qualidade de mídia de áudio na linha de mídia. Isso inclui o cancelamento de eco acústico (AEC) e métricas de (AGC) do controle de ganho automático.  <br/> |
|[Tabela VideoStream](videostream.md) <br/> |Armazena métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioClientEvent](audioclientevent.md) <br/> |Armazena métricas de qualidade de mídia de áudio coletadas do evento do cliente.  <br/> |
|[Tabela VideoClientEvent](videoclientevent.md) <br/> |Armazena métricas de qualidade de mídia de vídeo coletadas do evento do cliente.  <br/> |
|**Tabela DiagnosticData** <br/> |Armazena dados de diagnóstico que é somente para uso interno.  <br/> |
   
**Tabelas para dados de resumo**

|**Tabela**|**Descrição**|
|:-----|:-----|
|**Tabela ServerSummary** <br/> |Armazena dados de resumo para os servidores, esses dados são usados para Quality of Experience (QoE) apenas para relatório.  <br/> |
|**Tabela UserSummary** <br/> |Armazena dados de resumo para os usuários, esses dados são usados para apenas para relatório de QoE.  <br/> |
|**Tabela CallTypeSummary** <br/> |Armazena dados de resumo para tipos de chamada, esses dados são usados para apenas para relatório de QoE.  <br/> |
   
**Tabelas para uso interno de Monitoring Server**

|**Tabela**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Somente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Somente para uso interno.  <br/> |
|**Tabela FrontEnd** <br/> |Somente para uso interno.  <br/> |
|**Tabela de tarefas** <br/> |Somente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Somente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Somente para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Somente para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Somente para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Somente para uso interno.  <br/> |
|**Fusos horários** <br/> |Somente para uso interno.  <br/> |
|**Tabela CallSummary** <br/> |Somente para uso interno.  <br/> |
|**Tabela DeviceCallSumary** <br/> |Somente para uso interno.  <br/> |
|**Tabela inquilino** <br/> |Somente para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
   

