---
title: Relatório de Tendências de Localização no Skype for Business Server
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
ms.assetid: 61e2db3c-9f10-4411-8e7e-c6950faf8533
description: 'Resumo: saiba mais sobre o Relatório de Tendências de Localização Skype for Business Server.'
---

# <a name="location-trend-report-in-skype-for-business-server"></a>Relatório de Tendências de Localização no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Tendências de Localização Skype for Business Server.
  
O Relatório de Tendências de Local fornece informações sobre as tendências de qualidade de chamada para locais de rede.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Tendências de Local permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno x acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Tendências de Local. 
  
**Filtros do Relatório de Tendências de Local**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanal (é possível exibir no máximo 12 semanas) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/8/2012 e a data de término 28/9/2011, os dados serão exibidos para os dias de 7/8/2012 12:00 AM a 7/9/2012 12:00 AM (ou seja, um total de 31 dias de dados). <br/> |
|**Tipo de acesso** <br/> | Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não VPN <br/> |
   

