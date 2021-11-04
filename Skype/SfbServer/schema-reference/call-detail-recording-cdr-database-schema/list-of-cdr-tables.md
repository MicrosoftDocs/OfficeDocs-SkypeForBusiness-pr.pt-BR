---
title: Lista de tabelas cdr no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: O esquema de banco de dados de registro de detalhes das chamadas (CDR) consiste nas seguintes tabelas.
ms.openlocfilehash: 1e8c76080089005977154c3e23d924a4b98dc6b5
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746657"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tabelas cdr no Skype for Business Server 2015
 
O esquema de banco de dados de registro de detalhes das chamadas (CDR) consiste nas seguintes tabelas. 
  
## <a name="static-tables"></a>Tabelas Estáticas

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela CallPriorities no Skype for Business Server 2015](callpriorities.md) <br/> |Armazena a lista de prioridade de chamadas possíveis, tais como emergência, urgente, normal, não urgente e outras.  <br/> |
|[Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |Armazena os limites de classificação utilizados pelo Relatório de resumo de tempo de participação na conferência.  <br/> |
|[Tabela DeRegisterType no Skype for Business Server 2015](deregistertype.md) <br/> |Armazena a lista de possíveis razões de cancelamento de registro de usuário, como "iniciado por cliente", "registro expirou", "falha de cliente" dentre outros.  <br/> |
|[Tabela MediaList](medialist.md) <br/> |Armazena a lista de tipos de mídia que podem gerar as entradas no banco de dados (por exemplo IM, áudio, vídeo e transferência de arquivos).  <br/> |
|[Tabela PurgeSettings](purgesettings.md) <br/> |Armazena informação que especifica se (e quando) registros de detalhes de chamada desatualizada serão excluídas automaticamente do banco de dados CDR.  <br/> |
|[Tabela Funções](roles.md) <br/> |Armazena a lista de funções de conferência possíveis (por exemplo, participantes e apresentadores).  <br/> |
|[Tabela SIPResponseMetaData](sipresponsemetadata.md) <br/> |Stores a list of SIP response codes and the classification and definition of each of those codes.  <br/> |
   
## <a name="supporting-tables"></a>Tabelas de suporte

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela ClientVersions no Skype for Business Server 2015](clientversions.md) <br/> |Armazena os clientes (tanto o tipo de cliente quanto o número de versão) de cada cliente envolvido em uma chamada com informações capturadas neste banco de dados.  <br/> |
|[Tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) <br/> |Armazena uma lista de ConferenceURIs que são utilizadas em chamadas relacionadas a conferências.  <br/> |
|[Tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) <br/> |Armazena uma lista de tipos de conteúdo SIP (Session Initiation Protocol) que são usadas tanto em chamadas ponto-a-ponto quanto em chamadas de conferência.  <br/> |
|[Tabela Dispositivos no Skype for Business Server 2015](devices.md) <br/> |Armazena uma lista de dispositivos, incluindo a versão de hardware, fabricante e endereço MAC.  <br/> |
|[Tabela caixas de diálogo no Skype for Business Server 2015](dialogs.md) <br/> |Armazena informações sobre o ID de Diálogo para cada sessão no banco de dados.  <br/> |
|[Tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) <br/> |Armazena uma lista de Servidores de Borda  usados para chamadas externas.  <br/> |
|[Tabela Gateways no Skype for Business Server 2015](gateways.md) <br/> |Armazena uma lista de Gateways usados para chamadas VoIP (Voice over Internet Protocol).  <br/> |
|[Tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) <br/> |Armazena uma lista de versões de hardware de dispositivos (telefone de mesa).  <br/> |
|[Tabela fabricantes Skype for Business Server 2015](manufacturers.md) <br/> |Armazena uma lista de fabricantes de dispositivos (telefone de mesa).  <br/> |
|[Tabela Mcus no Skype for Business Server 2015](mcus.md) <br/> |Armazena informações sobre os vários Servidores de Conferência A/V e seus URIs.  <br/> |
|[Tabela MediationServers](mediationservers.md) <br/> |Armazena uma lista de Servidores de Mediação usados para chamadas VoIP.  <br/> |
|[Tabela Phones](phones.md) <br/> |Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou que tiveram os detalhes da chamadas gravados.  <br/> |
|[Tabela Pools](pools.md) <br/> |Armazena os nomes do pool no qual as mensagens de IM são capturadas.  <br/> |
|[Tabela Servidores](servers.md) <br/> |Armazena o nome de servidores envolvidos em chamadas.  <br/> |
|[Tabela tenants](tenants.md) <br/> |Armazena os locatários suportados pela implantação atual. Existem alguns locatários integrados para os usuários Enterprise, Federado, de conectividade de IM público e Anônimos.  <br/> |
|[Tabela UserAgentDef](useragentdef.md) <br/> |Mapas identificadores de agente de usuário para os nomes descritivos do agente.  <br/> |
|[Tabela Usuários](users.md) <br/> |Armazena o os URIs de usuários que tenham participado em sessões gravadas ou arquivadas neste banco de dados.  <br/> |
|[Tabela UserStatistics](userstatistics.md) <br/> |Armazena informações sobre o uso do sistema por um usuário individual.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tabelas Específicas para Registros de CDR de Conferências

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela de conferências no Skype for Business Server 2015](conferences.md) <br/> |Armazena informações sobre todas as conferências que foram arquivadas ou que tiveram seus detalhes gravados, incluindo ConferenceUI e hora de início e término.  <br/> |
|[Tabela ConferenceSessionDetails Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |Armazena informações sobre todas as sessões de conferência baseada em SIP, incluindo hora de início e término, ID de usuário, código de resposta e ID de diagnóstico para cada sessão.  <br/> |
|[Tabela FocusJoinsAndLeaves no Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |Armazena informações sobre junções e folhas de conferência, incluindo a função dos usuários e a versão do cliente.  <br/> |
|[Tabela McuJoinsAndLeaves no Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |Armazena informações sobre os Servidores de Conferência A/V que estão envolvidos em uma conferência e os horários de ingresso e saída de usuário.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabelas para Mensagens em Conferências IM

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela ConferenceMessageCount no Skype for Business Server 2015](conferencemessagecount.md) <br/> |Armazena, para cada conferência IM, o número de mensagem que foram enviadas por cada usuário.  <br/> |
|[Tabela IMReportSummary no Skype for Business Server 2015](imreportsummary.md) <br/> |Provides an overall report on the instant messaging sessions held in an organization.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabelas para Sessões Ponto-a-Ponto

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela SessionDetails](sessiondetails.md) <br/> |Armazena informações sobre cada sessão ponto-a-ponto, incluindo horário de início e término, ID de usuário, código de resposta e a contagem de mensagem para cada usuário.  <br/> |
|[Tabela FileTransfers no Skype for Business Server 2015](filetransfers-0.md) <br/> |Armazena informações sobre sessões de transferência de arquivo, incluindo nome de arquivo e resultado (aceita, rejeitada ou cancelada).  <br/> |
|[Tabela de mídia](media.md) <br/> |Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto-a-ponto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabela para Detalhes de Chamadas VoIP

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela VoipDetails](voipdetails-0.md) <br/> |Armazena, para cada chamada VoIP/PSTN de duas partes, informações sobre a chamada, tais como ID de telefone do telefone VoIP, gateway usado e qual parte desconectou. Refere-se à tabela [SessionDetails para](sessiondetails.md) horários de início/término de chamada e código de resposta. <br/> |
   
> [!NOTE]
> Se uma parte em uma chamada é um usuário VoIP ou se um Servidor de Mediação esteve envolvido na chamada, um registro será criado nesta tabela. Informações sobre chamadas VoIP/VoIP que não envolvem um telefone PSTN (rede telefônica pública comutado) são capturadas na tabela [SessionDetails.](sessiondetails.md) 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabela para Auditoria de Chamada E9-1-1

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela Locais no Skype for Business Server 2015](locations.md) <br/> |Armazena, para cada chamada de emergência, tal como uma chamada Enhanced 9-1-1 (E9-1-1), informações locais sobre a chamada. Refere-se à tabela [SessionDetails para](sessiondetails.md) horários de início/término de chamada e código de resposta. <br/> |
   
> [!NOTE]
> Esta tabela contém apenas o blob de local para a chamada E9-1-1. Consulte a tabela SessionDetails para outras informações detalhadas sobre a chamada. 
  
## <a name="tables-for-troubleshooting"></a>Tabelas para Resolução de Problemas

|**Table**|**Descrição**|
|:-----|:-----|
|[Tabela de aplicativos Skype for Business Server 2015](application.md) <br/> |Armazena informações sobre vários processos no Skype for Business Server 2015 que estão envolvidos em roteamento e conexões.  <br/> |
|[Tabela CallType no Skype for Business Server 2015](calltype.md) <br/> |Armazena informações sobre tipos da chamada, como "áudio", "Mensagens Instantâneas", "áudio e vídeo" e "compartilhamento de aplicativos".  <br/> |
|[Tabela ErrorCategory no Skype for Business Server 2015](errorcategory.md) <br/> |Armazena o nome amigável para cada classificação de diagnóstico Skype for Business Server 2015.  <br/> |
|[Tabela ErrorDef no Skype for Business Server 2015](errordef.md) <br/> |Armazena informações sobre tipos de erros e suas definições.  <br/> |
|[Tabela ErrorReport no Skype for Business Server 2015](errorreport.md) <br/> |Armazena informações sobre erros que ocorreram.  <br/> |
|[Tabela ProgressReport](progressreport.md) <br/> |Armazena informações sobre os relatórios de progresso de várias etapas envolvidas nos processos Skype for Business Server 2015.  <br/> |
   
As tabelas na lista a seguir são usadas internamente pelo Skype for Business Server 2015. Seus detalhes não são descritos neste documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabelas para Uso Interno do Lync Server

|**Table**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Apenas para uso interno.  <br/> |
|**DbConfigInt** <br/> |Apenas para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Apenas para uso interno.  <br/> |
|**Tabela FrontEnd** <br/> |Apenas para uso interno.  <br/> |
|**MSMQProcessing Table** <br/> |Apenas para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Apenas para uso interno.  <br/> |
|**Syndicators Table** <br/> |Apenas para uso interno.  <br/> |
|**SyndicatorsTenantMap Table** <br/> |Apenas para uso interno.  <br/> |
|**Tabela Tarefa** <br/> |Apenas para uso interno.  <br/> |
|**UserStatistics** <br/> |Apenas para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Apenas para uso interno.  <br/> |
|**UsageSummary** <br/> |Apenas para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Apenas para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Apenas para uso interno.  <br/> |
|**TimeZones** <br/> |For internal use only.  <br/> |
|**FailureSummary_UQ** <br/> |For internal use only.  <br/> |
|**FailureSummary** <br/> |For internal use only.  <br/> |
|**ServerSummary** <br/> |For internal use only.  <br/> |
|**MsDiagMetaData** <br/> |For internal use only.  <br/> |
   

