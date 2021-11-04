---
title: Sub-relatório de resumo P2P no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
description: 'Resumo: saiba mais sobre o Sub-relatório resumo P2P no Skype for Business Server.'
ms.openlocfilehash: 14472ee8ede0e05d56f026561dfd8884c3d6c152
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774851"
---
# <a name="p2p-summary-subreport-in-skype-for-business-server"></a>Sub-relatório de resumo P2P no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Sub-relatório resumo P2P no Skype for Business Server.
  
O Sub-relatório resumo P2P fornece uma exibição geral de suas sessões de comunicação ponto a ponto com falha.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. A tabela a seguir lista os filtros que você pode usar com o Sub-relatório resumo P2P.
  
**Filtros de sub-relatório de resumo P2P**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre correm do domingo até sábado.  <br/> |
|**Pool** <br/> |FQDN do pool do Registrador ou Servidor de Borda. É possível selecionar um pool individual ou clicar em **[Todos]** para exibir os dados de todos os pools. Esta lista suspensa é preenchida automaticamente para você com base nos registros do banco de dados.<br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Sub-relatório resumo P2P.
  
**Métricas de sub-relatório de resumo P2P**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.  <br/> |
|**Taxa de falha** <br/> |Não  <br/> |Percentual de sessões ponto a ponto que falharam.  <br/> |
|**Sessões por Modalidade** <br/> |Não  <br/> |Número total de sessões agrupadas por modalidade (por exemplo, mensagens instantâneas).  <br/> |
|**Taxa de falha por modalidade** <br/> |Não  <br/> |Número total de sessões com falha agrupadas por modalidade (por exemplo, mensagens instantâneas).  <br/> |
   

