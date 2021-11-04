---
title: Relatório de Resumo de Qualidade de Mídia no Skype for Business Server
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
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Resumo: saiba mais sobre o Relatório de Resumo de Qualidade de Mídia no Skype for Business Server.'
ms.openlocfilehash: 7dad97de5c763dd578b90559653606911e03c78a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765399"
---
# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de Qualidade de Mídia no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo de Qualidade de Mídia Skype for Business Server.
  
O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:
  
- Chamadas ponto a ponto da UC (como um Skype for Business para Skype for Business chamada)
    
- Sessões de Conferência de UC
    
- Sessões de Conferência PSTN
    
- Chamadas PSTN: Desvio de Mídia
    
- Chamadas PSTN (Não Ignorar): Trecho de UC
    
- Chamadas PSTN (Não Ignorar): Trecho de Gateway
    
- Outros Tipos de Chamada
    
Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias. Sem sair do relatório, você pode expandir cada categoria para ver subcategorias, como chamadas feitas do Office Communicator 2007 R2 para Skype for Business. Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.
  
Em Skype for Business Server Relatório de Resumo de Qualidade de Mídia divide ainda mais os dados em três tipos de chamada: chamadas de áudio, chamadas de vídeo e chamadas de compartilhamento de aplicativos. Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.
  
O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.
  
## <a name="accessing-the-media-quality-summary-report"></a>Como acessar o Relatório de resumo de qualidade de mídia

O Relatório de resumo de qualidade de mídia é acessado a partir da página inicial dos Relatórios de Monitoramento. Você pode detalhar o Relatório de [Lista](call-list-report-0.md) de Chamada em Skype for Business Server clicando em uma das seguintes métricas:
  
- Volume da chamada
    
- Percentual de chamadas ruins
    
Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:
  
- Viagem de ida e volta (ms)
    
- Degradação (MOS)
    
- Perda de pacote
    
- Tremulação (ms)
    
- Taxa de correção oculta
    
- Taxa de correção estendida
    
- Taxa de correção compactada
    
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno vs. acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.
  
**Filtros do Relatório de Resumo de Qualidade de Mídia**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Tipo de acesso** <br/> | Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não VPN <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.
  
**Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de Chamada/Tipo de Ponto de Extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Tempo de resposta (ms)** <br/> |Não  <br/> |Quantidade média (em milissegundos) necessária para um pacote de protocolo de transporte em tempo real (RTP) viajar para outro ponto de extremidade e voltar. Tempos de resposta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Quantidade média de degradação MOS (pontuação média de opinião) experimentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. Em Skype for Business Server um conjunto de algoritmos prevêem como os usuários classificariam uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacotes RTP (a perda de pacotes acontece quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela Internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência da rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda do áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   
**Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de Chamada/Tipo de Ponto de Extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Taxa de bits média (Kbits/s)** <br/> |Não  <br/> |Taxa de bits média (em quilobytes por segundo).  <br/> |
|**% de taxa de bits baixa** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa.  <br/> |
|**Perda de pacote de saída** <br/> |Não  <br/> |Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**% de quadros congelados** <br/> |Não  <br/> |Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.  <br/> |
|**Taxa de quadros média de saída** <br/> |Não  <br/> |Taxa de quadros média para transmissões de saída durante a chamada.  <br/> |
|**Taxa de quadros média de entrada** <br/> |Não  <br/> |Taxa de quadros média para transmissões de entrada durante a chamada.  <br/> |
|**% de taxa de quadros baixa de entrada** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.  <br/> |
|**% de integridade do cliente** <br/> ||Indica o estado relativo do dispositivo do cliente durante a chamada.  <br/> |
   
**Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de Chamada/Tipo de Ponto de Extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Percentual de chamadas ruins** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Unidirecional relativo médio** <br/> |Não  <br/> |Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.  <br/> |
|**Latência média de processamento lado a lado RDP** <br/> |Não  <br/> |A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Uma média alta reflete um atraso maior na experiência de exibição e inclui latência de rede. Um servidor de conferência sobrecarregado pode enfrentar atrasos médios maiores.  <br/> |
|**% total de lado a lado estragado** <br/> |Não  <br/> |A porcentagem total de lado a lado estragados.  <br/> |
   

