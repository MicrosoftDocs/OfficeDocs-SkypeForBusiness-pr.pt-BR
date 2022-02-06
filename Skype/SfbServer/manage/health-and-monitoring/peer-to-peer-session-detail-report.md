---
title: Relatório de detalhes de sessão ponto a ponto no Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 6be1d676-68f7-4a53-a72a-de73296c5571
description: 'Resumo: saiba mais sobre o Relatório de Detalhes de Sessão Ponto a Ponto no Skype for Business Server.'
---

# <a name="peer-to-peer-session-detail-report-in-skype-for-business-server"></a>Relatório de detalhes de sessão ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Detalhes de Sessão Ponto a Ponto no Skype for Business Server.
  
O Relatório Detalhado de Sessão Ponto a Ponto retorna informações detalhadas sobre uma sessão ponto a ponto. Por exemplo, se você selecionar uma sessão de mensagens instantâneas, o relatório informará o número de mensagens enviadas por cada um dos dois usuários na seção.
  
## <a name="accessing-the-peer-to-peer-session-detail-report"></a>Acessando o Relatório Detalhado de Sessão Ponto a Ponto

O Relatório Detalhado de Sessão Ponto a Ponto pode ser acessado a partir de qualquer um dos relatórios a seguir (todos os quais podem ser acessados a partir da home page Relatórios de Monitoramento):
  
- Relatório de Inventário de Telefones IP
    
- Relatório de Atividades do Usuário
    
- Relatório de Controle de Admissão de Chamadas
    
- Relatório de Lista de Falhas 
    
No Relatório de Detalhes de Sessão Ponto [a](diagnostic-report.md) Ponto, você pode acessar o Relatório de Diagnóstico em Skype for Business Server clicando na métrica Relatório de Diagnóstico (Detalhes). Você também pode acessar o Relatório das Principais Falhas clicando em uma destas duas métricas:
  
- Resposta
    
- ID de diagnóstico
    
## <a name="making-the-best-use-of-the-peer-to-peer-session-detail-report"></a>Usando o Relatório Detalhado de Sessão Ponto a Ponto da melhor maneira possível

O Relatório Detalhado de Sessão Ponto a Ponto inclui um grande número de métricas, muitas das quais os administradores de sistemas podem desconhecer. Muitas vezes, porém, você pode exibir uma dica de ferramenta que oferece uma breve descrição da métrica. Para isso, basta manter o cursor do mouse sobre o rótulo da métrica.
  
Observe que as métricas mostradas em determinado relatório dependerão do tipo de sessão ponto a ponto selecionada. Uma sessão de áudio/vídeo mostrará um conjunto de métricas diferente de uma sessão de mensagens instantâneas.
  
Você também pode manter o cursor do mouse sobre as métricas Código de resposta e ID de diagnóstico para obter uma descrição desses valores:
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o relatório de Detalhes de Sessão Ponto a Ponto.
  
## <a name="session-information-metrics"></a>Métricas de informações da sessão

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão.
  
**Métricas de informações da sessão**

|**Name**|**Descrição**|
|:-----|:-----|
|**FQDN do pool** <br/> |Nome de domínio totalmente qualificado (FQDN) do pool de Registradores ou Servidor de Borda envolvido na sessão.  <br/> |
|**Hora do convite** <br/> |Data e hora em que o convite de sessão foi originalmente enviado.  <br/> |
|**Hora da resposta** <br/> |Data e hora em que a aceitação do convite foi recebida.  <br/> |
|**Do usuário** <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Do agente usuário** <br/> |Software usado pelo ponto de extremidade do usuário que iniciou a sessão.  <br/> |
|**É Usuário interno de origem** <br/> |Indica se o usuário que iniciou a sessão estava conectado à rede interna.  <br/> |
|**É Usuário de origem integrado ao telefone de mesa** <br/> |Indica se o ponto de extremidade usado pelo usuário que iniciou a sessão está integrado ao seu telefone de mesa.  <br/> |
|**Prioridade da Sessão** <br/> |Prioridade atribuída à sessão. As prioridades válidas são: Desconhecida; Não Urgente; Normal; Urgente; e Emergência.  <br/> |
|**Código de resposta** <br/> |Código de resposta SIP enviado quando a sessão falhou.  <br/> |
|**Front-End**. <br/> |Nome do Servidor Front-End usado na conferência.  <br/> |
|**Hora da captura** <br/> |Data e hora em que a sessão de informações foi gravada.  <br/> |
|**Hora final** <br/> |Data e hora em que a sessão foi encerrada.  <br/> |
|**Para o usuário** <br/> |Endereço SIP do usuário que foi convidado para a sessão.  <br/> |
|**Para o agente do usuário** <br/> |Software usado pelo ponto de extremidade do usuário que foi convidado para a sessão.  <br/> |
|**É Usuário interno de destino** <br/> |Indica se o usuário que foi convidado para a sessão estava conectado à rede interna.  <br/> |
|**É Usuário de destino integrado ao telefone de mesa** <br/> |Indica se o ponto de extremidade usado pelo usuário que foi convidado para a sessão está integrado ao seu telefone de mesa.  <br/> |
|**É sessão repetida** <br/> |Indica se a sessão é uma tentativa para repetir uma sessão que falhou anteriormente.  <br/> |
|**ID de diagnóstico** <br/> |Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros. Mantenha o mouse sobre o número de identificação para exibir informações adicionais sobre essa identificação.  <br/> |
   
## <a name="metrics-for-modalities"></a>Métricas para modalidades

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada sessão de modalidade.
  
**Métricas para modalidades**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Modalidades** <br/> |Não  <br/> |Modalidades usadas na sessão. Por exemplo, mensagens instantâneas ou transferência de arquivo.  <br/> |
|**Mensagens do usuário de origem** <br/> |Não  <br/> |Número de mensagens enviadas pelo usuário que iniciou a sessão.  <br/> |
|**Mensagens do usuário de destino** <br/> |Não  <br/> |Número de mensagens enviadas pelo usuário que foi convidado para a sessão.  <br/> |
   
## <a name="metrics-for-diagnostic-reports"></a>Métricas para relatórios de diagnóstico

A tabela a seguir lista as informações fornecidas no relatório de Detalhes de Sessão Ponto a Ponto para cada relatório de diagnóstico.
  
**Métricas para relatórios de diagnóstico**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Ver os detalhes** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o Relatório de Diagnóstico da sessão.  <br/> |
|**Hora do relatório** <br/> |Não  <br/> |Data e hora em que o relatório foi gravado.  <br/> |
|**Solicitação** <br/> |Não  <br/> |Tipo de solicitação SIP. Por exemplo, INVITE ou BYE.  <br/> |
|**ID de diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (no formato de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que frequentemente oferece informações úteis para resolução de erros.  <br/> |
|**Tipo de conteúdo** <br/> |Não  <br/> |Tipo de conteúdo de mídia usado na conferência. Por exemplo, um tipo de conteúdo comum é Application/sdp. O protocolo SDP  é um protocolo padrão de Internet usado para comunicados de sessão, convites de sessão e outras formas de início de sessão multimídia.  <br/> |
|**Relatado por** <br/> |Não  <br/> |Computador (isso é, o cliente ou servidor) que relatou o problema.  <br/> |
   

