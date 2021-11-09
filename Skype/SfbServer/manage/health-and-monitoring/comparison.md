---
title: Relatório de Comparação de Qualidade de Mídia Skype for Business Server
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
ms.assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
description: 'Resumo: saiba mais sobre o Relatório de Comparação de Qualidade de Mídia Skype for Business Server.'
ms.openlocfilehash: 8c492e75e124b7529e229ddc353bf89b3830fb93
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847264"
---
# <a name="media-quality-comparison-report-in-skype-for-business-server"></a>Relatório de Comparação de Qualidade de Mídia Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Comparação de Qualidade de Mídia Skype for Business Server.
  
O Relatório de Comparação de Qualidade da Mídia permite você comparar os valores de qualidade da chamada para diferentes tipos de chamadas de áudio (por exemplo, chamadas realizadas através de uma rede sem fio contra chamadas realizadas em uma conexão com fio).
  
## <a name="accessing-the-media-quality-comparison-report"></a>Acessando o Relatório de Comparação de Qualidade da Mídia

O Relatório de Comparação de Qualidade da Mídia é acessado na página inicial de Relatórios de Monitoramento. 
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais detalhado ou exibir os dados retornados em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Comparação de Qualidade da Mídia.
  
**Filtros do Relatório de Comparação de Qualidade da Mídia**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Chamadas** <br/> | Tipo de chamada a ser usada como o item de comparação principal. Os valores permitidos são: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  Não VPN <br/>  Com fio <br/>  Sem fio <br/>  Externa e com fio <br/>  Externa e sem fio <br/>  Externa e VPN <br/>  Externa e não-VPN <br/>  Interna e com fio <br/>  Interna e sem fio <br/> |
|**Comparar com chamadas** <br/> | Tipo de chamada a ser usada como o item de comparação secundária. Os valores permitidos são: <br/>  [Todos] <br/>  Externo <br/>  Interno <br/>  VPN <br/>  Não VPN <br/>  Com fio <br/>  Sem fio <br/>  Externa e com fio <br/>  Externa e sem fio <br/>  Externa e VPN <br/>  Externa e não-VPN <br/>  Interna e com fio <br/>  Interna e sem fio <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Comparação de Qualidade da Mídia.
  
**Métricas do Relatório de Comparação de Qualidade da Mídia**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Quantidade média de degradação de MOS (pontuação média de opinião) experimentado durante uma chamada. Os valores de degradação podem variar de um baixo de 0,0 a uma alta de 5,0; um valor de 0,5 ou menos representa degradação aceitável. Historicamente, as pontuações médias de opinião foram calculadas fazendo com que os usuários taxam a qualidade de uma chamada em uma escala de 1 a 5. Skype for Business Server usa um conjunto de algoritmos para prever como os usuários classificariam uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |O número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Não  <br/> |Quantidade média de (em milissegundos) exigida para que um pacote de Protocolo de Transporte em Tempo Real viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 200 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Altos valores de tempo de resposta podem ser causados por roteamento de chamadas internacionais, configuração incorreta de um roteamento ou um servidor de mídia sobrecarregado. Tempos de resposta altos resultam em dificuldades para conversas de áudio bidirecionais e em tempo real.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacotes de Protocolo de Transporte em Tempo Real (RTP). (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   

