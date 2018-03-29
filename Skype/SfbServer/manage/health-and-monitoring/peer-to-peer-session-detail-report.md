---
title: Relatório de Detalhes de Sessão Ponto a Ponto no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Resumo: Saiba mais sobre o relatório de detalhes de sessão ponto a ponto no Skype para Business Server 2015.'
ms.openlocfilehash: 454a31449ceff109ac81bd266f1ef7c21f7c0afd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server-2015"></a>Relatório de Detalhes de Sessão Ponto a Ponto no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o relatório de detalhes de sessão ponto a ponto no Skype para Business Server 2015.
  
O Relatório Detalhado de Sessão Ponto a Ponto retorna informações detalhadas sobre uma sessão ponto a ponto. Por exemplo, se você selecionar uma sessão de mensagens instantâneas, o relatório informará o número de mensagens enviadas por cada um dos dois usuários na seção.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Acessando o Relatório Detalhado de Sessão Ponto a Ponto

O Relatório Detalhado de Sessão Ponto a Ponto pode ser acessado a partir de qualquer um dos relatórios a seguir (todos os quais podem ser acessados a partir da home page Relatórios de Monitoramento):
  
- Relatório de Inventário de Telefones IP
    
- Relatório de Atividades do Usuário
    
- Relatório de Controle de Admissão de Chamadas
    
- Relatório de lista de falhas 
    
De dentro do relatório de detalhes de sessão ponto a ponto você pode acessar o [Relatório de diagnóstico no Skype para Business Server 2015](diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhes). Você também pode acessar o Relatório das Principais Falhas clicando em uma destas duas métricas:
  
- Resposta
    
- ID do Diagnóstico
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Usando o Relatório Detalhado de Sessão Ponto a Ponto da melhor maneira possível

O Relatório Detalhado de Sessão Ponto a Ponto inclui um grande número de métricas, muitas das quais os administradores de sistemas podem desconhecer. Muitas vezes, porém, você pode exibir uma dica de ferramenta que oferece uma breve descrição da métrica. Para isso, basta manter o cursor do mouse sobre o rótulo da métrica.
  
Observe que as métricas mostradas em determinado relatório dependerão do tipo de sessão ponto a ponto selecionada. Uma sessão de áudio/vídeo mostrará um conjunto de métricas diferente de uma sessão de mensagens instantâneas.
  
Você também pode manter o cursor do mouse sobre as métricas Código de resposta e ID de diagnóstico para obter uma descrição desses valores:
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o relatório de Detalhes de Sessão Ponto a Ponto.
  
## <a name="session-information-metrics"></a>Métricas de informações da sessão

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão.
  
**Métricas de informação da sessão**

|**Nome**|**Descrição**|
|:-----|:-----|
|**FQDN do pool** <br/> |Nome de domínio totalmente qualificado (FQDN) do pool de Registradores ou Servidor de Borda envolvido na sessão.  <br/> |
|**Hora do convite** <br/> |Data e hora em que o convite de sessão foi originalmente enviado.  <br/> |
|**Hora da resposta** <br/> |Data e hora de recebimento da aceitação do convite.  <br/> |
|**Usuário "De"** <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Agente do usuário "De"** <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**É usuário "De" interno** <br/> |Indica se o usuário que iniciou a sessão estava conectado à rede interna.  <br/> |
|**É usuário "De" integrado com telefone de mesa** <br/> |Indica se o ponto de extremidade usado pelo usuário que iniciou a sessão está integrado ao seu telefone de mesa.  <br/> |
|**Prioridade da Sessão** <br/> |Prioridade atribuída à sessão. As prioridades válidas são: Desconhecida; Não Urgente; Normal; Urgente; e Emergência.  <br/> |
|**Código da resposta** <br/> |Código da resposta SIP enviado quando a sessão falhou.  <br/> |
|**Front-End** <br/> |Nome do Servidor Front-End usado na conferência.  <br/> |
|**Hora da captura** <br/> |Data e hora em que a sessão de informações foi gravada.  <br/> |
|**Hora final** <br/> |Data e hora em que a sessão foi encerrada.  <br/> |
|**Usuário "Para"** <br/> |Endereço SIP do usuário convidado para a sessão.  <br/> |
|**Agente do usuário "Para"** <br/> |Software usado pelo ponto de extremidade do usuário que foi convidado para a sessão.  <br/> |
|**É usuário "Para" interno** <br/> |Indica se o usuário que foi convidado para a sessão estava conectado à rede interna.  <br/> |
|**É usuário "Para" integrado com telefone de mesa** <br/> |Indica se o ponto de extremidade usado pelo usuário que foi convidado para a sessão está integrado ao seu telefone de mesa.  <br/> |
|**É sessão repetida** <br/> |Indica se a sessão é uma tentativa para repetir uma sessão que falhou anteriormente.  <br/> |
|**ID do Diagnóstico** <br/> |Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros. Mantenha o mouse sobre o número de identificação para exibir informações adicionais sobre essa identificação.  <br/> |
   
## <a name="metrics-for-modalities"></a>Métricas para modalidades

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão de modalidade.
  
**Métricas para modalidades**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Modalidades** <br/> |Não  <br/> |Modalidades usadas na sessão. Por exemplo, mensagens instantâneas ou transferência de arquivo.  <br/> |
|**Mensagens do usuário "De"** <br/> |Não  <br/> |Número de mensagens enviadas pelo usuário que iniciou a sessão.  <br/> |
|**Mensagens do usuário "Para"** <br/> |Não  <br/> |Número de mensagens enviadas pelo usuário que foi convidado para a sessão.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Métricas para relatórios de diagnóstico

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada relatório de diagnóstico.
  
**Métricas para relatórios de diagnóstico**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Detalhe** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o Relatório de Diagnóstico da sessão.  <br/> |
|**Hora do relatório** <br/> |Não  <br/> |Data e hora do registro do relatório.  <br/> |
|**Solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP. Por exemplo, INVITE ou BYE.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas.  <br/> |
|**Tipo de conteúdo** <br/> |Não  <br/> |Tipo de conteúdo de mídia usado na conferência. Por exemplo, um tipo de conteúdo comum é Application/sdp. O protocolo SDP é um protocolo padrão de Internet usado para comunicados de sessão, convites de sessão e outras formas de início de sessão multimídia.  <br/> |
|**Relatado por** <br/> |Não  <br/> |Computador (isso é, o cliente ou servidor) que relatou o problema.  <br/> |
   

