---
title: Lista de tabelas CDR no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: O esquema de banco de dados de registro de detalhes de chamadas (CDR) consiste nas tabelas a seguir.
ms.openlocfilehash: a8d36d75f629b41c535de99c0b9aef42770ba573
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296150"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Lista de tabelas CDR no Skype for Business Server 2015
 
O esquema de banco de dados de registro de detalhes de chamadas (CDR) consiste nas tabelas a seguir. 
  
## <a name="static-tables"></a>Tabelas estáticas

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela CallPriorities no Skype for Business Server 2015](callpriorities.md) <br/> |Armazena a lista de prioridades de chamadas possíveis, como emergência, urgente, normal, não urgente e muito mais.  <br/> |
|[Tabela ConferenceJoinTimeThresholds no Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |Armazena os limites de classificação usados pelo relatório de Resumo de tempo de ingresso em conferência.  <br/> |
|[Tabela canregistertype no Skype for Business Server 2015](deregistertype.md) <br/> |Armazena a lista de possíveis motivos de cancelamento de usuário, como "iniciado pelo cliente", "registro expirado", "falha do cliente" e muito mais.  <br/> |
|[Tabela MediaList](medialist.md) <br/> |Armazena a lista de tipos de mídia que podem gerar entradas no banco de dados (por exemplo, mensagens instantâneas, áudio, vídeo e transferência de arquivos).  <br/> |
|[Tabela PurgeSettings](purgesettings.md) <br/> |Armazena informações que especificam se (e quando) registros de detalhes de chamadas desatualizadas serão automaticamente excluídos do banco de dados CDR.  <br/> |
|[Tabela Roles](roles.md) <br/> |Armazena a lista de possíveis funções de conferência (por exemplo, participante e apresentador).  <br/> |
|[Tabela SIPResponseMetaData](sipresponsemetadata.md) <br/> |Armazena uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos.  <br/> |
   
## <a name="supporting-tables"></a>Tabelas de suporte

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela ClientVersions no Skype for Business Server 2015](clientversions.md) <br/> |Armazena os clientes (o tipo de cliente e o número da versão) de cada cliente envolvido em uma chamada com informações capturadas nesse banco de dados.  <br/> |
|[Tabela ConferenceUris no Skype for Business Server 2015](conferenceuris.md) <br/> |Armazena uma lista de ConferenceURIs que são usadas em chamadas relacionadas à conferência.  <br/> |
|[Tabela ContentTypes no Skype for Business Server 2015](contenttypes.md) <br/> |Armazena uma lista de tipos de conteúdo de protocolo SIP que são usados em chamadas ponto a ponto e em chamadas em conferência.  <br/> |
|[Tabela de dispositivos no Skype for Business Server 2015](devices.md) <br/> |Armazena uma lista de dispositivos, incluindo o fabricante, a versão de hardware e o endereço MAC.  <br/> |
|[Tabela de caixas de diálogo no Skype for Business Server 2015](dialogs.md) <br/> |Armazena informações sobre a ID da caixa de diálogo para cada sessão do banco de dados.  <br/> |
|[Tabela EdgeServers no Skype for Business Server 2015](edgeservers.md) <br/> |Armazena uma lista de servidores de borda que são usados para chamadas externas.  <br/> |
|[Tabela gateways no Skype for Business Server 2015](gateways.md) <br/> |Armazena uma lista de gateways que são usados para chamadas de protocolo de voz por Internet (VoIP).  <br/> |
|[Tabela HardwareVersions no Skype for Business Server 2015](hardwareversions.md) <br/> |Armazena uma lista de versões de hardware de dispositivos (telefone de mesa).  <br/> |
|[Tabela fabricantes no Skype for Business Server 2015](manufacturers.md) <br/> |Armazena uma lista de fabricantes de dispositivos (telefone de mesa).  <br/> |
|[Tabela MCUs no Skype for Business Server 2015](mcus.md) <br/> |Armazena informações sobre os vários servidores de conferência A/V e seus URIs.  <br/> |
|[Tabela MediationServers](mediationservers.md) <br/> |Armazena uma lista de servidores de mediação que são usados para chamadas VoIP.  <br/> |
|[Tabela Phones](phones.md) <br/> |Armazena todos os números de telefone usados em chamadas VoIP que foram arquivadas ou cujos detalhes da chamada foram registrados.  <br/> |
|[Tabela Pools](pools.md) <br/> |Armazena os nomes do pool no qual as mensagens INSTANTÂNEAs são capturadas.  <br/> |
|[Tabela de servidores](servers.md) <br/> |Armazena o nome dos servidores envolvidos nas chamadas.  <br/> |
|[Tabela Tenants](tenants.md) <br/> |Armazena os locatários compatíveis com a implantação atual. Há alguns locatários de compilação para usuários corporativos, usuários federados, usuários de conectividade de mensagens de chat públicas e usuários anônimos.  <br/> |
|[Tabela UserAgentDef](useragentdef.md) <br/> |Mapeia identificadores de agente de usuário para os nomes descritivos do agente.  <br/> |
|[Tabela Users](users.md) <br/> |Armazena o usuário URIs de usuários que participaram de sessões registradas ou arquivadas neste banco de dados.  <br/> |
|[Tabela userstatistics](userstatistics.md) <br/> |Armazena informações sobre o uso de um usuário individual do sistema.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tabelas específicas para registros de CDR em conferência

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela de conferências no Skype for Business Server 2015](conferences.md) <br/> |Armazena informações sobre todas as conferências que foram arquivadas ou cujos detalhes foram registrados, incluindo ConferenceURI e hora de início e de término.  <br/> |
|[Tabela ConferenceSessionDetails no Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |Armazena informações sobre cada sessão de conferência baseada em SIP, incluindo hora de início e de término, ID de usuário, código de resposta e identificação de diagnóstico para cada sessão.  <br/> |
|[Tabela FocusJoinsAndLeaves no Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |Armazena informações sobre junções e folhas de conferência, incluindo a função do usuário e a versão do cliente.  <br/> |
|[Tabela McuJoinsAndLeaves no Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |Armazena informações sobre os servidores de conferência A/V envolvidos em uma conferência e o usuário ingressa e sai do tempo.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabelas de mensagens em conferências de mensagens INSTANTÂNEAs

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela ConferenceMessageCount no Skype for Business Server 2015](conferencemessagecount.md) <br/> |Para cada conferência de mensagem instantânea, armazena o número de mensagens enviadas por cada usuário.  <br/> |
|[Tabela IMReportSummary no Skype for Business Server 2015](imreportsummary.md) <br/> |Fornece um relatório geral sobre as sessões de mensagens instantâneas contidas em uma organização.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabelas para sessões ponto a ponto

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela SessionDetails](sessiondetails.md) <br/> |Armazena informações sobre cada sessão ponto a ponto, incluindo a hora de início e de término, a ID de usuário, o código de resposta e a contagem de mensagens para cada usuário.  <br/> |
|[Tabela de transferências de fileno Skype for Business Server 2015](filetransfers-0.md) <br/> |Armazena informações sobre sessões de transferência de arquivos, incluindo o resultado e o resultado (aceito, rejeitado ou cancelado).  <br/> |
|[Tabela Media](media.md) <br/> |Armazena informações sobre os diferentes tipos de mídia envolvidos em sessões ponto a ponto.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabela para detalhes da chamada VoIP

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela VoipDetails](voipdetails-0.md) <br/> |Para cada chamada VoIP/PSTN de dois participantes, armazena informações sobre a chamada, como a ID do telefone de VoIP, o gateway usado e a parte desconectada. Refere-se à [tabela SessionDetails](sessiondetails.md) para horas de início/término de chamada e código de resposta. <br/> |
   
> [!NOTE]
> Se um participante de uma chamada for um usuário de VoIP ou se um servidor de mediação estiver envolvido na chamada, um registro será criado nessa tabela. As informações sobre chamadas VoIP/VoIP que não envolvem um telefone PSTN (rede telefônica pública comutada) são capturadas na [tabela SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabela para auditoria de chamada E9-1-1

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela locais no Skype for Business Server 2015](locations.md) <br/> |Para cada chamada de emergência, como uma chamada Enhanced 9-1-1 (E9-1-1), armazena informações de localização sobre a chamada. Refere-se à [tabela SessionDetails](sessiondetails.md) para horas de início/término de chamada e código de resposta. <br/> |
   
> [!NOTE]
> Esta tabela contém apenas o blob de localização para a chamada E9-1-1. Refere-se à tabela SessionDetails para obter outras informações detalhadas sobre a chamada. 
  
## <a name="tables-for-troubleshooting"></a>Tabelas para solução de problemas

|**Tabela**|**Descrição**|
|:-----|:-----|
|[Tabela de aplicativos no Skype for Business Server 2015](application.md) <br/> |Armazena informações sobre vários processos no Skype for Business Server 2015 envolvidos em roteamento e conexões.  <br/> |
|[Tabela CallType no Skype for Business Server 2015](calltype.md) <br/> |Armazena informações sobre tipos de chamada, como "áudio", "mensagens instantâneas", "áudio e vídeo" e "compartilhamento de aplicativos".  <br/> |
|[Tabela ErrorCategory no Skype for Business Server 2015](errorcategory.md) <br/> |Armazena o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015.  <br/> |
|[Tabela ErrorDef no Skype for Business Server 2015](errordef.md) <br/> |Armazena informações sobre tipos de erros e suas definições.  <br/> |
|[Tabela ErrorReport no Skype for Business Server 2015](errorreport.md) <br/> |Armazena informações sobre erros ocorridos.  <br/> |
|[Tabela ProgressReport](progressreport.md) <br/> |Armazena informações sobre os relatórios de progresso de várias etapas envolvidas nos processos do Skype for Business Server 2015.  <br/> |
   
As tabelas na lista a seguir são usadas internamente pelo Skype for Business Server 2015. Seus detalhes não estão descritos neste documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabelas para uso interno pelo Lync Server

|**Tabela**|**Descrição**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Somente para uso interno.  <br/> |
|**DbConfigInt** <br/> |Somente para uso interno.  <br/> |
|**DbErrorMessage** <br/> |Somente para uso interno.  <br/> |
|**Tabela de front-end** <br/> |Somente para uso interno.  <br/> |
|**Tabela MSMQProcessing** <br/> |Somente para uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Somente para uso interno.  <br/> |
|**Tabela de sindicadores** <br/> |Somente para uso interno.  <br/> |
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
   

