---
title: Relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 025e8ab4-2e64-4a6b-8f52-caf756a5cac3
description: 'Resumo: saiba mais sobre o Relatório de Diagnóstico de Atividade Ponto a Ponto no Skype for Business Server.'
ms.openlocfilehash: c0c568a75cddb8ea9f8165a196ee8cef1e03eaab
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858228"
---
# <a name="peer-to-peer-activity-diagnostic-report-in-skype-for-business-server"></a>Relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Diagnóstico de Atividade Ponto a Ponto no Skype for Business Server.
  
O Relatório de Diagnóstico de Atividades Ponto a Ponto fornece informações sobre o sucesso e falha de suas sessões de comunicação ponto a ponto. Observe que Skype for Business Server diferencia entre diferentes tipos de falha:
  
- **Falha esperada**. Uma falha esperada é normalmente uma falha somente no sentido mais técnico. Por exemplo, vamos supor que você ligue para alguém, mas ele ou ela esteja fora do escritório e não possa atender ao telefone. Como a chamada não foi atendida, ela é considerada tecnicamente uma falha. Por outro lado, essa foi uma falha esperada: Skype for Business Server não espera que você atenda o telefone se não estiver disponível para atender o telefone. Da mesma maneira, uma falha esperada ocorrerá se você tentar enviar uma mensagem instantânea a um usuário que esteja offline, ou conectado apenas a um telefone que não suporta mensagem instantânea.
    
- **Falha inesperada**. Uma falha inesperada é exatamente o que o nome diz: um erro que, baseado nas circunstâncias, você não esperaria que ocorrese. Por exemplo, suponha que você chame alguém e essa pessoa está disponível para atender a chamada; no entanto, quando Skype for Business Server tenta roteá-la para a caixa postal, a chamada falha porque a conectividade com Exchange Unificação de Mensagens foi perdida. Esse é um erro inesperado: você deve esperar que as chamadas sempre sejam roteados para a caixa postal. Como regra geral, falhas inesperadas são verdadeiras falhas: elas são problemas que provavelmente não podem ser corrigidos por meio da educação do usuário ou por medidas parecidas.
    
Observe que talvez as métricas Sucesso, Falha esperada e Falha inesperada não acrescentem à métrica Total de sessões. Por exemplo, na ilustração anterior, temos os seguintes valores:
  
|**Sucessos**|**Falhas esperadas**|**Falhas inesperadas**|**Total de sessões**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Se você adicionar 2024 + 469 + 16 terá um total de 2.509 sessões, ainda assim a coluna Total de sessões mostrará um total de 2.521 sessões. As 12 sessões que "faltam" são sessões que o sistema não pode categorizar como bem-sucedida ou sem sucesso. Às vezes, esse será o caso quando um produto de terceiros introduz um novo código de diagnóstico que não é familiar para Skype for Business Server. Quando isso acontece, as chamadas feitas usando esse produto, e o relatório desse código de diagnóstico, não podem sempre ser categorizados como Sucesso, Falha esperada ou Falha inesperada.
  
## <a name="accessing-the-peer-to-peer-activity-diagnostic-report"></a>Acessando o Relatório de Diagnóstico de Atividades Ponto a Ponto

O Relatório de Diagnóstico de Atividades Ponto a Ponto é acessado a partir da home page dos Relatórios de monitoramento. Você pode acessar o [Relatório de Distribuição](failure-distribution-report.md) de Falhas Skype for Business Server clicando em uma das seguintes métricas:
  
- Volume de falhas inesperadas
    
- Volume de falha esperada
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-diagnostic-report"></a>Fazendo o melhor uso do Relatório de Diagnóstico de Atividades Ponto a Ponto

Há diversas maneiras de usar filtrar o Relatório de Diagnóstico de Atividades Ponto a Ponto, mas, por padrão, essas opções de filtragem ficam ocultas. Para exibir as opções de filtragem disponíveis, clique no botão Mostrar/Ocultar Parâmetros no canto superior direito da janela de relatório. Depois de fazer isso, as opções de filtragem ficarão disponíveis para uso.
  
## <a name="filters"></a>Filtros

Filtros oferecem uma maneira de você retornar um conjunto de dados mais preciso ou visualizar os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Atividade Ponto-a-Ponto permite que você filtre tais coisas como a modalidade de sessão (por exemplo, mensagens instantâneas, transferência de arquivos ou compartilhamento de arquivos). Você pode escolher também como os dados devem ser agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode utilizar com o Relatório de Diagnóstico de Atividade Ponto-a-Ponto.
  
**Filtros de Relatório de Diagnóstico de Atividade Ponto-a-Ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (nome de domínio totalmente qualificado) do pool de Registrador ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para visualizar os dados para todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Modalidade** <br/> | Indica o tipo de atividade de comunicação que ocorreu. Selecione um dos seguintes: <br/>  [Todos] <br/>  Mensagens instantâneas <br/>  Transferência de arquivo <br/>  Compartilhamento de aplicativos <br/>  Áudio <br/>  Vídeo <br/> |
   
## <a name="metrics-per-modality"></a>Medidas (por modalidade)

A tabela a seguir lista as informações oferecidas no Relatório de Diagnóstico de Atividades Ponto-a-Ponto para cada modalidade.
  
**Medidas (por modalidade)**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume de sucesso** <br/> |Não  <br/> |Número total de sessões ponto-a-ponto com êxito.  <br/> |
|**Porcentagem de sucesso** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto completas com problemas significativos. Calculado dividindo o Volume de sucesso pelo Total de sessões.  <br/> |
|**Volume de falha esperado** <br/> |Não  <br/> |Número total de sessões nas quais ocorreu uma "falha esperada".  <br/> Uma falha esperada é uma falha que se espera que aconteça. Por exemplo, se um usuário definiu seu status como Não Incomodar, espera-se que qualquer chamada para este usuário falhe.  <br/> |
|**Percentual de falha esperada** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto que tiveram um erro esperado. Calculado dividindo o Volume de falhas esperada pelo Total de sessões.  <br/> |
|**Volume de falhas inesperadas** <br/> |Não  <br/> |Número total de sessões nas quais ocorreu uma "falha inesperada".  <br/> Uma falha inesperada é uma falha que ocorre no que de outro modo aparenta ser um sistema saudável. Por exemplo, uma chamada não deve ser terminada se o chamador é colocado em espera. Caso isso ocorra, será marcado como uma falha inesperada.  <br/> |
|**Percentual de falha inesperada** <br/> |Não  <br/> |Porcentagem de sessões ponto-a-ponto nas quais um erro inesperado ocorreu. Calculado dividindo o Volume de falhas inesperadas pelo Total de sessões.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.  <br/> |
   

