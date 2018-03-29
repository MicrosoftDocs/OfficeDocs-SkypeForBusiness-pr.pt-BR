---
title: Lista de tabelas CDR Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: O esquema de banco de dados (CDR) de registro de detalhes de chamada consiste nas tabelas a seguir.
ms.openlocfilehash: 7e224b8170ec078cafaec2fe3cbf4cf9819eba41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tabelas CDR Skype para Business Server 2015
 
O esquema de banco de dados (CDR) de registro de detalhes de chamada consiste nas tabelas a seguir. 
  
## <a name="static-tables"></a>Tabelas estáticas

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela CallPriorities Skype para Business Server 2015](callpriorities.md) <br/> |Armazena a lista de prioridades de chamada possíveis, tais como emergência, urgente, normal, não urgente e muito mais.  <br/> |
|[Tabela ConferenceJoinTimeThresholds no Skype para Business Server 2015](conferencejointimethresholds.md) <br/> |Armazena os limites de classificação utilizados pelo relatório de resumo de tempo de ingresso de conferência.  <br/> |
|[Tabela DeRegisterType Skype para Business Server 2015](deregistertype.md) <br/> |Armazena a lista de possível usuário cancelamento de registro de motivos, como "cliente iniciado," "registro expirou",""Falha de cliente"e muito mais.  <br/> |
|[Tabela mediaList](medialist.md) <br/> |Armazena a lista de tipos de mídia que podem gerar as entradas no banco de dados (por exemplo, mensagens Instantâneas, áudio, vídeo e transferência de arquivos).  <br/> |
|[Tabela PurgeSettings](purgesettings.md) <br/> |Armazena informações que especificam se (e quando) desatualizadas call detail Records, registros serão excluídos automaticamente do banco de dados de CDR.  <br/> |
|[Tabela de funções](roles.md) <br/> |Armazena a lista de possíveis funções de conferência (por exemplo, o participante e apresentador).  <br/> |
|[Tabela SIPResponseMetaData](sipresponsemetadata.md) <br/> |Armazena uma lista de códigos de resposta SIP e a classificação e a definição de cada um desses códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tabelas de suporte

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela ClientVersions Skype para Business Server 2015](clientversions.md) <br/> |Armazena os clientes (ambos os cliente tipo e número de versão) de cada cliente envolvido em uma chamada com informações capturadas neste banco de dados.  <br/> |
|[Tabela ConferenceUris Skype para Business Server 2015](conferenceuris.md) <br/> |Armazena uma lista de ConferenceURIs que são usados na conferência relacionadas a chamadas.  <br/> |
|[Tabela ContentTypes Skype para Business Server 2015](contenttypes.md) <br/> |Armazena uma lista de tipos de conteúdo de protocolo de iniciação de sessão (SIP) que são usados em chamadas ponto a ponto e chamadas em conferência.  <br/> |
|[Tabela de dispositivos no Skype para Business Server 2015](devices.md) <br/> |Armazena uma lista de dispositivos, incluindo o seu fabricante, a versão de hardware e o endereço MAC.  <br/> |
|[Tabela de diálogos no Skype para Business Server 2015](dialogs.md) <br/> |Armazena informações sobre a ID de diálogo para cada sessão no banco de dados.  <br/> |
|[Tabela EdgeServers no Skype para Business Server 2015](edgeservers.md) <br/> |Armazena uma lista de servidores de borda que são usados para chamadas externas.  <br/> |
|[Tabela de gateways no Skype para Business Server 2015](gateways.md) <br/> |Armazena uma lista de Gateways que são usados para Voice, chamadas de protocolo da Internet (VoIP).  <br/> |
|[Tabela HardwareVersions no Skype para Business Server 2015](hardwareversions.md) <br/> |Armazena uma lista das versões de hardware de dispositivos (telefone de mesa).  <br/> |
|[Tabela de fabricantes no Skype para Business Server 2015](manufacturers.md) <br/> |Armazena uma lista de fabricantes de dispositivos (telefone de mesa).  <br/> |
|[Tabela MCUs Skype para Business Server 2015](mcus.md) <br/> |Armazena informações sobre os vários A / V Conferencing Servers e seus URIs.  <br/> |
|[Tabela MediationServers](mediationservers.md) <br/> |Armazena uma lista de servidores de mediação que são usados para chamadas VoIP.  <br/> |
|[Tabela de telefones](phones.md) <br/> |Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou que tiveram seus detalhes chamada gravados.  <br/> |
|[Tabela de pools](pools.md) <br/> |Armazena os nomes do pool no qual IM as mensagens são capturadas.  <br/> |
|[Tabela de servidores](servers.md) <br/> |Armazena o nome dos servidores envolvidos em chamadas.  <br/> |
|[Tabela de locatários](tenants.md) <br/> |Armazena os locatários suportados pelo implantação atual. Há alguns inquilinos interna para usuário corporativo, usuários federados, usuários de conectividade IM públicos e usuários anônimos.  <br/> |
|[Tabela UserAgentDef](useragentdef.md) <br/> |Mapeia identificadores de agente do usuário aos nomes descritivos dos agentes.  <br/> |
|[Tabela de usuários](users.md) <br/> |Armazena o usuário URIs de usuários que tenham participado em sessões gravadas ou arquivadas neste banco de dados.  <br/> |
|[Tabela UserStatistics](userstatistics.md) <br/> |Armazena informações sobre o uso de um usuário individual do sistema.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tabelas específicas para registros de CDR de conferências

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela de conferências em Skype para Business Server 2015](conferences.md) <br/> |Armazena informações sobre todas as conferências que foram arquivadas ou que tiveram seus detalhes gravados, incluindo Conferenceui e hora de início e término.  <br/> |
|[Tabela ConferenceSessionDetails Skype para Business Server 2015](conferencesessiondetails-0.md) <br/> |Armazena informações sobre cada sessão de conferência baseada em SIP, incluindo o início e hora de término, ID de usuário, código de resposta e ID de diagnóstico para cada sessão.  <br/> |
|[Tabela FocusJoinsAndLeaves Skype para Business Server 2015](focusjoinsandleaves.md) <br/> |Armazena informações sobre conferência ingressa e deixar, incluindo a função dos usuários e a versão do cliente.  <br/> |
|[Tabela McuJoinsAndLeaves Skype para Business Server 2015](mcujoinsandleaves.md) <br/> |Armazena informações sobre A / V Conferencing Servers que estão envolvidos em uma conferência e o usuário entram e saem vezes.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabelas para mensagens em conferências de mensagens Instantâneas

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela ConferenceMessageCount Skype para Business Server 2015](conferencemessagecount.md) <br/> |Para cada conferência de mensagem Instantânea, armazena o número de mensagens que foram enviados por cada usuário.  <br/> |
|[Tabela IMReportSummary no Skype para Business Server 2015](imreportsummary.md) <br/> |Fornece um relatório geral sobre a mantidos em uma organização de sessões de mensagens instantâneas.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabelas para sessões ponto a ponto

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela SessionDetails](sessiondetails.md) <br/> |Armazena informações sobre cada sessão ponto a ponto, incluindo o início e hora de término, ID de usuário, código de resposta e contagem de mensagem para cada usuário.  <br/> |
|[Tabela FileTransfers Skype para Business Server 2015](filetransfers-0.md) <br/> |Armazena informações sobre a transferência de arquivos do nome de sessões, incluindo o arquivo e resultam (aceita, rejeitada ou cancelada).  <br/> |
|[Tabela de mídia](media.md) <br/> |Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto a ponto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabela de detalhes das chamadas VoIP

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela VoipDetails](voipdetails-0.md) <br/> |Para cada chamada VoIP/PSTN de duas partes, armazena informações sobre a chamada, por exemplo, o telefone telefone ID de VoIP, gateway usado e quais participantes desconectado. Refere-se à [tabela SessionDetails](sessiondetails.md) para horas de início/término da chamada e o código de resposta. <br/> |
   
> [!NOTE]
> Se um participante em uma chamada é um usuário VoIP ou um servidor de mediação foi envolvido na chamada, será criado um registro nesta tabela. Informações sobre as chamadas de VoIP/VoIP não envolvendo um telefone PSTN (rede) de telefônica comutada pública é capturado na [tabela SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabela para auditoria de chamada E9-1-1

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela de localizações em Skype para Business Server 2015](locations.md) <br/> |Para cada chamada de emergência, por exemplo, uma chamada do Enhanced 9-1-1 (E9-1-1), armazena informações de local sobre a chamada. Refere-se à [tabela SessionDetails](sessiondetails.md) para horas de início/término da chamada e o código de resposta. <br/> |
   
> [!NOTE]
> Esta tabela contém apenas o blob local para a chamada E9-1-1. Refere-se à tabela SessionDetails para obter outras informações detalhadas sobre a chamada. 
  
## <a name="tables-for-troubleshooting"></a>Tabelas para resolução de problemas

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela de aplicativo no Skype para Business Server 2015](application.md) <br/> |Armazena informações sobre vários processos do Skype para Business Server 2015 que estão envolvidos em roteamento e conexões.  <br/> |
|[Tabela CallType Skype para Business Server 2015](calltype.md) <br/> |Armazena informações sobre os tipos de chamada, por exemplo, "áudio", "IM", "áudio e vídeos" e "compartilhamento de aplicativos".  <br/> |
|[Tabela ErrorCategory no Skype para Business Server 2015](errorcategory.md) <br/> |Armazena o nome amigável para cada Skype para a classificação de diagnóstico Business Server 2015.  <br/> |
|[Tabela ErrorDef no Skype para Business Server 2015](errordef.md) <br/> |Armazena informações sobre tipos de erros e suas definições.  <br/> |
|[Tabela ErrorReport Skype para Business Server 2015](errorreport.md) <br/> |Armazena informações sobre os erros que ocorreram.  <br/> |
|[Tabela ProgressReport](progressreport.md) <br/> |Armazena informações sobre os relatórios de progresso das várias etapas envolvidas na Skype para processos de negócios Server 2015.  <br/> |
   
As tabelas na lista a seguir são usadas internamente pelo Skype para Business Server 2015. Seus detalhes não são descritos neste documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabelas para uso interno pelo Lync Server

|**Tabela**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Somente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Somente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Somente para uso interno.  <br/> |
|**Tabela FrontEnd** <br/> |Somente para uso interno.  <br/> |
|**Tabela MSMQProcessing** <br/> |Somente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Somente para uso interno.  <br/> |
|**Tabela syndicators** <br/> |Somente para uso interno.  <br/> |
|**Tabela SyndicatorsTenantMap** <br/> |Somente para uso interno.  <br/> |
|**Tabela de tarefas** <br/> |Somente para uso interno.  <br/> |
|**UserStatistics** <br/> |Somente para uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Somente para uso interno.  <br/> |
|**UsageSummary** <br/> |Somente para uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Somente para uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Somente para uso interno.  <br/> |
|**Fusos horários** <br/> |Somente para uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Somente para uso interno.  <br/> |
|**FailureSummary** <br/> |Somente para uso interno.  <br/> |
|**ServerSummary** <br/> |Somente para uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Somente para uso interno.  <br/> |
   

