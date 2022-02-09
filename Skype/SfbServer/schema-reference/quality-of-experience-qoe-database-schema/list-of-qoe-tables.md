---
title: Lista de tabelas QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: O esquema de banco de dados consiste nas tabelas a seguir.
ms.openlocfilehash: ac00cc41ede9e9a78e6b9a4d811496f4bc17faed
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62420844"
---
# <a name="list-of-qoe-tables"></a>Lista de tabelas QoE
 
O esquema de banco de dados consiste nas tabelas a seguir. 
  
**Tabelas de suporte**

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com compartilhamento de aplicativo.  <br/> |
|[Tabela CodecDescription](codecdescription.md) <br/> |Mapeia identificadores exclusivos de codec ao codec correspondente.  <br/> |
|[Tabela IPAddress](ipaddress.md) <br/> |Mapeia endereços IP aos identificadores de endereços IP exclusivos usados em outros locais no banco de dados de Qualidade da Experiência.  <br/> |
|[Tabela NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mapeia os tipos de conexão de rede aos identificadores de conexão de rede usados em outros locais no banco de dados de Qualidade da Experiência.  <br/> |
|[Tabela PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Armazena informações que especificam se (e quando) registros de Qualidade da Experiência antigos serão automaticamente deletados do banco de dados de QoE (Qualidade da Experiência).  <br/> |
|[Tabela TraceRoute](traceroute.md) <br/> |Armazena informaçoes de roteamento para chamadas.  <br/> |
|[Tabela UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mapas identificadores de agente de usuário para os nomes descritivos do agente.  <br/> |
|[Tabela VideoMetricsThreshold](videometricsthreshold.md) <br/> |Armazena valores ótimos e aceitáveis para as métricas de Qualidade da Experiência usadas com chamadas de vídeo.  <br/> |
|[Tabela UserAgent](useragent.md) <br/> |Armazena as cadeias de Agente de Usuário (UA) do Protocolo de Iniciação de Sessão (SIP) e tipos de UA usados em sessões de áudio e vídeo.  <br/> |
|[Tabela do usuário](user-0.md) <br/> |Armazena URIs de usuário, de conferência, e de telefone usados em sessões de áudio e vídeo.  <br/> |
|[Tabela de ponto de extremidade](endpoint.md) <br/> |Armazena nomes de computador FQDN de pontos de extremidade que participam de sessões de áudio e vídeo.  <br/> |
|[Tabela pool](pool.md) <br/> |Armazena os nomes de pools às quais os dados de métrica pertencem.  <br/> |
|[Tabela de dispositivos](device.md) <br/> |Armazena os dispositivos de captura e de renderização que são usados em chamadas de áudio/vídeo.  <br/> |
|[Tabela DeviceDriver](devicedriver.md) <br/> |Armazena o driver do dispositivo de captura e de renderização que são usados em chamadas de áudio/vídeo.  <br/> |
|[Tabela de conferências](conference.md) <br/> |Armazena os URIs da conferência para cenários de conferência ou DialogID para outros cenários.  <br/> |
|[Tabela SessionCorrelation](sessioncorrelation.md) <br/> |Armazena CorrelationID para chamadas PSTN.  <br/> |
|[Tabela PayloadDescription](payloaddescription.md) <br/> |Armazena o Codec usado em chamadas de áudio/vídeo.  <br/> |
|[Tabela AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Armazena a origem da largura de banda usada em chamadas de áudio/vídeo.  <br/> |
|[Tabela MacAddress](macaddress.md) <br/> |Armazena o endereço MAC dos pontos de extremidade participantes de sessões de áudio e vídeo.  <br/> |
|[Tabela de diálogo](dialog.md) <br/> |Armazena a ID de Diálogo de sessões de áudio e vídeo.  <br/> |
|[Tabela região](region.md) <br/> |Armazena a região de rede definida na configuração NCS.  <br/> |
|[Tabela UserSite](usersite.md) <br/> |Armazena o site de rede definido na configuração NCS.  <br/> |
|[Tabela sub-rede](subnet.md) <br/> |Armazena a sub-rede definida na configuração NCS.  <br/> |
|[Tabela MonitoredRegionLink](monitoredregionlink.md) <br/> |Armazena o link de região definido na configuração NCS.  <br/> |
|[Tabela MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Armazena os links de site de rede definidos na configuração NCS.  <br/> |
|[Tabela EndpointSubnet](endpointsubnet.md) <br/> |Armazena a sub-rede do ponto de extremidade participando em uma sessão de áudio e vídeo.  <br/> |
|[Tabela de servidor](server.md) <br/> |Armazena o FQDN ou endereço IP do servidor pelo qual a mídia passa.  <br/> |
   
**Tabelas para dados de métrica**

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela AppSharingStream](appsharingstream.md) <br/> |Armazena métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo. Métricas de Qualidade da Experiência para as transmissões de rede usadas para compartilhamento de aplicativo.  <br/> |
|[Tabela de sessão](session.md) <br/> |Armazena informações gerais sobre sessões de áudio ou de áudio/vídeo. Uma sessão é definida como um diálogo SIP de áudio ou vídeo entre dois pontos de extremidade.  <br/> |
|[Tabela MediaLine](medialine-0.md) <br/> |Armazena informações sobre cada linha de mídia de uma sessão. Uma linha de mídia é uma coleção de um ou mais fluxos de áudio e vídeo. Geralmente, uma linha única de mídia terá dois fluxos, áudio ou vídeo.  <br/> |
|[Tabela AudioStream](audiostream.md) <br/> |Armazena métricas de qualidade de mídia de áudio para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioSignal](audiosignal.md) <br/> |Armazena métricas de qualidade de mídia de áudio na linha de mídia. Inclui cancelamento do eco acústico (AEC) e métricas de controle automático de ganho (AGC).  <br/> |
|[Tabela VideoStream](videostream.md) <br/> |Armazena métricas de qualidade de mídia de vídeo para cada fluxo de áudio na linha de mídia.  <br/> |
|[Tabela AudioClientEvent](audioclientevent.md) <br/> |Armazena métricas de qualidade de mídia de áudio coletadas do evento do cliente.  <br/> |
|[Tabela VideoClientEvent](videoclientevent.md) <br/> |Armazena métricas de qualidade de mídia de vídeo coletadas do evento do cliente.  <br/> |
|**Tabela DiagnosticData** <br/> |Armazena dados de diagnóstico apenas para uso interno.  <br/> |
   
**Tabelas para dados de resumo**

|**Table**|**Descrição**|
|:-----|:-----|
|**Tabela ServerSummary** <br/> |Armazena dados de resumo para os servidores, esses dados são usados apenas para relatório de Qualidade de Experiência (QoE).  <br/> |
|**Tabela UserSummary** <br/> |Armazena dados de resumo para os usuários, esses dados são usados apenas para relatório de QoE.  <br/> |
|**Tabela CallTypeSummary** <br/> |Armazena dados de resumo para tipos de chamadas, esses dados são usados apenas para relatório de QoE.  <br/> |
   
**Tabelas para uso interno de Monitoring Server**

|**Table**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Apenas para uso interno.  <br/> |
|**DbConfigInt** <br/> |Apenas para uso interno.  <br/> |
|**Tabela FrontEnd** <br/> |Apenas para uso interno.  <br/> |
|**Tabela Tarefa** <br/> |Apenas para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Apenas para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Apenas para uso interno.  <br/> |
|**MetricsThreshold** <br/> |Apenas para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Apenas para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Apenas para uso interno.  <br/> |
|**TimeZones** <br/> |Somente para uso interno.  <br/> |
|**Tabela CallSummary** <br/> |Somente para uso interno.  <br/> |
|**Tabela DeviceCallSumary** <br/> |Somente para uso interno.  <br/> |
|**Tabela Inquilino** <br/> |Somente para uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Somente para uso interno.  <br/> |
   

