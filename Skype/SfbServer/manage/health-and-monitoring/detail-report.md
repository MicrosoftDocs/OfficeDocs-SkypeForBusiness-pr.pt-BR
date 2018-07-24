---
title: Relatório de detalhes de conferência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1d61cd81-dcfe-40b4-9a41-a73b038bc216
description: 'Resumo: Saiba mais sobre o relatório de detalhes de conferência usado no Skype para Business Server.'
ms.openlocfilehash: ebccaf35464c54eac6c1b8c5a2febf2ebea02b7e
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971312"
---
# <a name="conference-detail-report-in-skype-for-business-server"></a>Relatório de detalhes de conferência no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de detalhes de conferência usado no Skype para Business Server.
  
O Relatório de Detalhe da Conferência fornece informações detalhadas sobre todos os usuários que participaram de uma conferência. Por exemplo, você pode ver tal informação como a data e hora que um usuário participou da conferência, a data e hora que o usuário saiu da conferência e o agente do usuário do ponto de extremidade que foi usado para conectar o usuário à conferência. Também é possível ver informações da função do usuário em cada conferência (por exemplo, Apresentador ou Participante). Talvez, o mais importante, você pode ver rapidamente quais usuários participaram com sucesso e concluíram a conferência e quais usuários não puderam participar e concluir a conferência.
  
## <a name="accessing-the-conference-detail-report"></a>Acessar o Relatório de Detalhe da Conferência

O Relatório de Detalhe da Conferência pode ser acessado pelos seguintes relatórios:
  
- O [Relatório de controle de admissão chamada no Skype para Business Server](call-admission-control-report.md) (clicando na métrica detalhe de uma conferência)
    
- O [Relatório de lista de falhas no Skype para Business Server](failure-list-report.md) (clicando na métrica conferência)
    
- O [Relatório de atividades do usuário no Skype para Business Server](user-activity-report.md) (clicando na métrica URI de conferência)
    
Do relatório de detalhes de conferência, você pode acessar o [Relatório de diagnóstico no Skype para Business Server](diagnostic-report.md) clicando na métrica relatório de diagnóstico (detalhe).
  
## <a name="filters"></a>Filtros

Nenhum. Você não pode filtrar o Relatório de Detalhe da Conferência.
  
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas na seção Informação da Conferência do Relatório de Detalhe da Conferência.
  
**Métricas de Informação da Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**URI de conferência** <br/> |URI atribuído à conferência. Por exemplo:  <br/> SIP:kmyer@litwareinc.com;GRUU;Opaque=App:conf:Focus:ID:drg2y8v4  <br/> |
|**FQDN do pool** <br/> |Nome de domínio totalmente qualificado do pool do Registrador ou Servidor de Borda envolvido em uma sessão.  <br/> |
|**Hora inicial** <br/> |Data e hora de início da sessão.  <br/> |
|**Organizador** <br/> |Endereço SIP do usuário que organizou a conferência.  <br/> |
|**Hora final** <br/> |Data e hora em que a conferência terminou.  <br/> |
   
A tabela a seguir lista as informações oferecidas na Seção de Participação da Conferência do Relatório de Detalhe da Conferência.
  
**Métricas de Participação da Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**Usuário** <br/> |Endereço SIP do usuário que participou da conferência.  <br/> |
|**Função** <br/> |Função (por exemplo, Apresentador) desempenhada pelo participante da conferência.  <br/> |
|**Conectividade** <br/> |Conectividade de rede (normalmente Interna ou Externa) para o participante.  <br/> |
|**Hora da ingresso** <br/> |Data e hora de ingresso do participante na conferência.  <br/> |
|**Hora da saída** <br/> |Data e hora de saída do participante da conferência.  <br/> |
|**Agente do usuário** <br/> |Identificador do software usado pelo ponto de extremidade do participante.  <br/> |
|**Relatórios de diagnóstico** <br/> |Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.  <br/> |
   
A tabela a seguir lista as informações fornecidas na seção modalidades de conferência do relatório de detalhes de conferência.
  
**Métricas das Modalidades da Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**Usuário** <br/> |Endereço SIP do usuário que participou da conferência.  <br/> |
|**Hora da ingresso** <br/> |Data e hora de ingresso do participante na conferência.  <br/> |
|**Hora da saída** <br/> |Data e hora que um participante deixou a conferência.  <br/> |
|**URI do servidor de conferência** <br/> |URI para o servidor de Conferência usado na conferência.  <br/> |
|**Relatórios de diagnóstico** <br/> |Fornece informações de resolução de problemas e diagnóstico. Incluindo códigos de resposta SIP, cabeçalhos de diagnóstico, hora de ingresso na conferência e IDs de diagnósticos para sessões com falha.  <br/> |
   

