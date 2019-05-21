---
title: Sub-relatório de resumo ponto a ponto no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Resumo: Saiba mais sobre o sub-relatório de Resumo de P2P no Skype for Business Server.'
ms.openlocfilehash: 5238e910896a6af956285235d7e1234fe17fe005
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279911"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Sub-relatório de resumo ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o sub-relatório de resumo ponto a ponto no Skype for Business Server.
  
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
   

