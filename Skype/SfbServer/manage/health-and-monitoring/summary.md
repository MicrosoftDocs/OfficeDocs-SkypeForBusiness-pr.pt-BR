---
title: Media Quality relatório de resumo no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
description: 'Resumo: Saiba mais sobre o Media Quality relatório de resumo no Skype para Business Server.'
ms.openlocfilehash: dfe59d4c115f8396625979cf7c7dc88ac4f52ee5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874525"
---
# <a name="media-quality-summary-report-in-skype-for-business-server"></a>Media Quality relatório de resumo no Skype para Business Server
 
**Resumo:** Saiba mais sobre o Media Quality relatório de resumo no Skype para Business Server.
  
O Relatório de resumo de qualidade de mídia é talvez a melhor maneira de analisar a qualidade das chamadas em sua organização: este relatório fornece métricas de chamada para Qualidade de Serviço (QoS) divididas nas seguintes categorias:
  
- Chamadas ponto a ponto de UC (por exemplo, um Skype for Business para Skype para chamada de negócios)
    
- Sessões de Conferência de UC
    
- Sessões de Conferência PSTN
    
- Chamadas PSTN: Desvio de Mídia
    
- Chamadas PSTN (Não Ignorar): Trecho de UC
    
- Chamadas PSTN (Não Ignorar): Trecho de Gateway
    
- Outros Tipos de Chamada
    
Ao abrir pela primeira vez o relatório, você verá informações resumidas para cada uma das categorias. Sem deixar o relatório, você pode expandir cada categoria a ser analisado subcategorias como chamadas feitas a partir do Office Communicator 2007 R2 para Skype para negócios. Por sua vez, você pode ver os detalhes de cada chamada feita dentro dessa subcategoria.
  
No Skype para Business Server o relatório de resumo de qualidade de mídia ainda mais divide os dados em três tipos de chamada: chamadas de áudio, vídeo e chamadas de compartilhamento de aplicativos. Cada tipo de chamada tem sua própria seção no relatório, e seu próprio conjunto de métricas de chamadas.
  
O Relatório de resumo de qualidade de mídia também permite aplicar filtros que permitem comparar a qualidade de chamada de chamadas com fio em relação a chamadas sem fio, chamadas internas x chamadas externas e chamadas VPN x chamadas não VPN.
  
## <a name="accessing-the-media-quality-summary-report"></a>Como acessar o Relatório de resumo de qualidade de mídia

O Relatório de resumo de qualidade de mídia é acessado na página inicial dos Relatórios de Monitoramento. Você pode analisar o [Call List Report no Skype para Business Server](call-list-report-0.md) clicando em uma das seguintes métricas:
  
- Volume da chamada
    
- Porcentagem de chamadas ruins
    
Além disso, você pode acessar o Relatório de distribuição de métricas de qualidade de mídia clicando em uma das seguintes métricas de chamada de áudio:
  
- Ida e volta (ms)
    
- Degradação (MOS)
    
- Perda de pacote
    
- Tremulação (ms)
    
- Taxa de correção oculta
    
- Taxa de correção estendida
    
- Taxa de correção compactada
    
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Qualidade de Mídia permite filtrar os dados retornados por informações como tipo de acesso (ou seja, acesso interno x acesso externo) ou por conexão de rede com fio/sem fio. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Qualidade de Mídia.
  
**Filtros do Relatório de Resumo de Qualidade de Mídia**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Tipo de acesso** <br/> | Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não-VPN <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Qualidade de Mídia.
  
**Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de áudio**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de chamada/Tipo de ponto de extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Porcentagem de chamada inválida** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Não  <br/> |Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.  <br/> |
|**Degradação (MOS)** <br/> |Não  <br/> |Quantidade média da degradação MOS enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários. No Skype para Business Server um conjunto de algoritmos prever como usuários classificou uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Não  <br/> |Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacotes RTP. (Tremulação é uma medida de quanto uma chamada treme.) Os valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Não  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Não  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Não  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   
**Métricas do Relatório de Resumo de Qualidade de Mídia: Resumo da chamada de vídeo**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de chamada/Tipo de ponto de extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Porcentagem de chamada inválida** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Taxa de bits média (Kbits/s)** <br/> |Não  <br/> |Taxa de bits média (em quilobytes por segundo).  <br/> |
|**Taxa de bits baixa %** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa.  <br/> |
|**Perda de pacote de saída** <br/> |Não  <br/> |Perda de pacotes do Protocolo de transporte em tempo real (RTP) para pacotes enviados. (A perda de pacotes ocorre quando pacotes RTP, um protocolo usado para transmitir áudio e vídeo pela internet, falha ao tentar alcançar seu destino). Altas taxas de perda geralmente são causadas por congestionamento, insuficiência da largura de banda, congestionamento ou interferência na rede sem fio ou um servidor de mídia sobrecarregado. A perda de pacotes normalmente resulta em distorção ou perda de áudio.  <br/> |
|**% de quadros congelados** <br/> |Não  <br/> |Porcentagem de quadros "congelados". Em um quadro congelado, o vídeo não avança enquanto a parte de áudio da chamada prossegue.  <br/> |
|**Taxa de quadros média de saída** <br/> |Não  <br/> |Taxa de quadros média para transmissões de saída durante a chamada.  <br/> |
|**Taxa de quadros média de entrada** <br/> |Não  <br/> |Taxa de quadros média para transmissões de entrada durante a chamada.  <br/> |
|**% de taxa de quadros baixa de entrada** <br/> |Não  <br/> |Porcentagem da chamada onde a taxa de bits foi baixa para vídeo de entrada.  <br/> |
|**% de integridade do cliente** <br/> ||Indica o estado relativo do dispositivo do cliente durante a chamada.  <br/> |
   
**Métricas do Relatório de resumo de qualidade de mídia: Resumo de chamada de compartilhamento de aplicativos**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de chamada/Tipo de ponto de extremidade** <br/> |Não  <br/> | Ao clicar neste item, o relatório mostra informações detalhadas sobre chamadas baseadas no tipo escolhido. Tipos de chamada incluem: <br/>  Chamadas Ponto a Ponto de UC <br/>  Sessões de Conferência de UC <br/>  Sessões de Conferência PSTN <br/>  Chamadas PSTN: Desvio de Mídia <br/>  Chamadas PSTN (Não Ignorar): Trecho de UC <br/>  Chamadas PSTN (Não Ignorar): Trecho de Gateway <br/>  Outros Tipos de Chamada <br/> |
|**Volume da chamada** <br/> |Não  <br/> |Número total de chamadas por tipo de chamada.  <br/> |
|**Porcentagem de chamada inválida** <br/> |Não  <br/> |Número total de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada em que no mínimo uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).  <br/> |
|**Volume de chamadas (chamadas sem fio)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão sem fio.  <br/> |
|**Volume de chamadas (chamadas VPN)** <br/> |Não  <br/> |Número total de chamadas que usaram uma conexão VPN.  <br/> |
|**Volume de chamadas (chamadas externas)** <br/> |Não  <br/> |Número de chamadas que usaram uma conexão externa (ou seja, uma conexão fora da rede interna).  <br/> |
|**Tremulação (ms)** <br/> |Não  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Unidirecional relativo médio** <br/> |Não  <br/> |Atraso unidirecional relativo médio entre dois pontos de extremidade de mídia. Esta é uma medida de latência de salto único.  <br/> |
|**Latência média de processamento lado a lado RDP** <br/> |Não  <br/> |A latência média de processamento lado a lado RDP no Servidor de Conferência AS durante a sessão de visualização. Uma média alta reflete um atraso maior na experiência de visualização e inclui latência de rede. Um servidor de conferência sobrecarregado pode sofrer médias maiores de atrasos.  <br/> |
|**% total de lado a lado estragado** <br/> |Não  <br/> |A porcentagem total de lado a lado estragados.  <br/> |
   

