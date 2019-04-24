---
title: Subrelatório de resumo P2P no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Resumo: Saiba mais sobre o subrelatório de resumo P2P no Skype para Business Server.'
ms.openlocfilehash: c36102eaa3fbf3dd970176316c11dd366b2a8fca
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32198103"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Subrelatório de resumo P2P no Skype para Business Server
 
**Resumo:** Saiba mais sobre o subrelatório de resumo P2P no Skype para Business Server.
  
O sub-relatório de resumo P2P oferece uma visão geral das sessões de comunicação ponto a ponto que falharam.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o sub-relatório de resumo P2P.
  
**Filtros de sub-relatório de resumo P2P**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Pool** <br/> |O FQDN (nome de domínio totalmente qualificado) do pool Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para ver os dados de todos os pools. Essa lista suspensa é preenchida automaticamente com base nos registros no banco de dados.<br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir apresenta as informações oferecidas no sub-relatório de resumo P2P.
  
**Métricas de sub-relatório de resumo P2P**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.  <br/> |
|**Taxa de falha** <br/> |Não  <br/> |Percentual de sessões ponto a ponto que falharam.  <br/> |
|**Sessões por modalidade** <br/> |Não  <br/> |Número total de sessões agrupadas por modalidade (por exemplo, mensagens instantâneas).  <br/> |
|**Taxa de falha por modalidade** <br/> |Não  <br/> |Número total de sessões que falharam agrupadas por modalidade (por exemplo, mensagens instantâneas).  <br/> |
   

