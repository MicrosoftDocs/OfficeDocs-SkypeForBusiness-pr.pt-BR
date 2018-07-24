---
title: Relatório de controle de admissão de chamadas no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea4b0c9f-7f93-4b8a-b901-01e1636c44fb
description: 'Resumo: Saiba mais sobre os relatórios de controle de admissão chamada usada no Skype para Business Server.'
ms.openlocfilehash: c3828eb890ed8f70c41bc669785278f9be017893
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21011243"
---
# <a name="call-admission-control-report-in-skype-for-business-server"></a>Relatório de controle de admissão de chamadas no Skype para Business Server
 
**Resumo:** Saiba mais sobre os relatórios de controle de admissão chamada usada no Skype para Business Server.
  
O Relatório de Controle de Admissão de Chamadas fornece informações sobre sessões de conferência e ponto a ponto que eram conduzidas sob restrições impostas pelo Controle de Admissão de Chamadas. O Controle de Admissão de Chamadas fornece uma maneira para que os administradores permitam (ou não) sessões de comunicação baseadas em limites de largura de banda. Por exemplo, os administradores podem criar políticas que imponham um limite na quantidade de banda disponível para chamadas de voz e vídeo. Caso o limite de banda seja alcançado, novas chamadas de voz ou vídeo não poderão ser feitas até que uma das chamadas atuais termine e libere os recursos de rede necessários.
  
## <a name="accessing-the-call-admission-control-report"></a>Acessando o Relatório de Controle de Admissão de Chamadas

O Relatório de Controle de Admissão de Chamadas é acessado através da página de Relatórios de Monitoramento. A partir do Relatório de Controle de Admissão de Chamadas você pode buscar mais detalhes em um dos seguintes relatórios:
  
- Relatório de detalhes de conferência - para acessar este relatório, clique na métrica detalhes em uma sessão de conferência. 
    
- -A-ponto sessão detalhe relatório - para acessar este relatório, clique na métrica detalhes para uma sessão ponto a ponto.
    
## <a name="making-the-best-use-of-the-call-admission-control-report"></a>Como usar o Relatório de Controle de Admissão de Chamadas da melhor maneira possível

Para obter uma lista de chamadas que falharam por causa de largura de banda insuficiente, selecione Chamadas rejeitadas devido ao controle de admissão de chamadas, na lista suspensa Categoria da chamada. A maioria das chamadas retornadas provavelmente terá a ID de diagnóstico 5:
  
Largura de banda insuficiente para estabelecer sessão. Tente reencaminhamento por PSTN.
  
Isso indica que as limitações do Controle de Admissão de Chamadas estavam impedindo a chamada de ser efetuada na rede VoIP.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Controle de Admissão de Chamadas permite que você filtre as chamadas de acordo com o usuário que iniciou a chamada ou com o usuário que está sendo chamado. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Controle de Admissão de Chamadas.
  
**Filtros do Relatório de Controle de Admissão de Chamadas**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início da seguinte forma:  <br/> 17/7/12015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final da seguinte forma:  <br/> 17/7/12015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do Pool de registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Tipo de atividade** <br/> | Tipo de atividade. Selecione uma das seguintes atividades: <br/>  [Todos] <br/>  Ponto a Ponto <br/>  Conferência <br/> |
|**Categoria da chamada** <br/> | Indica o motivo de o CAC ter sido usado para a chamada. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Chamada rejeitada devido ao controle de admissão de chamadas <br/>  Chamadas roteadas novamente por PSTN devido ao controle de admissão de chamadas <br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para sessões ponto a ponto (ou seja, sessões que envolvem apenas dois participantes).
  
**Métricas para sessões ponto a ponto**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Detalhe** <br/> |Não  <br/> |Quando você clica nesse item, o relatório mostra o Relatório Detalhado de Sessão Ponto a Ponto para a sessão especificada.  <br/> |
|**De usuário** <br/> |Sim  <br/> |Endereço SIP do usuário que iniciou a sessão.  <br/> |
|**Para usuário** <br/> |Sim  <br/> |Endereço SIP do usuário convidado para ingressar na sessão.  <br/> |
|**Modalidades** <br/> |Sim  <br/> |Modalidades de comunicação (como áudio e vídeo) usadas durante a sessão.  <br/> |
|**Hora do convite** <br/> |Sim  <br/> |Data e hora de envio do convite inicial da sessão para o usuário remetente.  <br/> |
|**Hora da resposta** <br/> |Sim  <br/> |Data e hora de recebimento da aceitação do convite.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora de encerramento da sessão.  <br/> |
|**ID do Diagnóstico** <br/> |Sim  <br/> |Identificador exclusivo (na forma de cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para solucionar erros. Os cabeçalhos Diagnóstico são opcionais (é possível ter sessões SIP que não os incluem), e as IDs de diagnóstico são relatadas somente para as sessões com algum tipo de problema.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para sessões de conferência (ou seja, sessões que envolvem três ou mais participantes).
  
**Métricas para sessões de conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**URI de conferência** <br/> |Sim  <br/> |Identificador exclusivo para a conferência. Quando você clica nesse item, o relatório mostra os participantes individuais da conferência.  <br/> |
|**Organizador** <br/> |Sim  <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Pool** <br/> |Sim  <br/> |Servidor de Borda usado na conferência.  <br/> |
|**Hora de início** <br/> |Sim  <br/> |Data e hora de início da sessão.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e hora em que a conferência terminou.  <br/> |
   
## <a name="metrics-for-individual-conference-participants"></a>Métricas para participantes individuais da conferência

A tabela a seguir lista as informações fornecidas no Relatório de Controle de Admissão de Chamadas para participantes individuais da conferência.
  
**Métricas para participantes individuais da conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Função** <br/> |Não  <br/> |Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.  <br/> |
|**Participante** <br/> |Não  <br/> |Endereço SIP do participante de conferência.  <br/> |
|**Conectividade** <br/> |Não  <br/> |Conectividade de rede (normalmente Interna ou Externa) para o participante.  <br/> |
|**Modalidade** <br/> |Não  <br/> |Tipo de conferência (por exemplo, conferência de A/V).  <br/> |
|**Hora de ingresso** <br/> |Não  <br/> |Data e hora de ingresso do participante na conferência.  <br/> |
|**Hora da saída** <br/> |Não  <br/> |Data e hora de saída do participante da conferência.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de um cabeçalho de diagnóstico-ms) anexado a uma mensagem SIP que fornece informações úteis sobre os erros de solução de problemas. Os cabeçalhos diagnósticos são opcionais (é possível ter sessões SIP que não os incluem), e os IDs diagnósticos são relatados somente para as sessões com algum tipo de problema.  <br/> |
   

