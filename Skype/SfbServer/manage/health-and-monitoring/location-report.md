---
title: Relatório de localização no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb2f1551-1e21-4f13-a39d-91f5f9010ccf
description: 'Resumo: Saiba mais sobre o relatório de localização no Skype para Business Server.'
ms.openlocfilehash: 61e9ab93189a9bf8597e879b5996761d5d937195
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20977469"
---
# <a name="location-report-in-skype-for-business-server"></a>Relatório de localização no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de localização no Skype para Business Server.
  
O Relatório de Localização oferece informações sobre as métricas de qualidade de chamada agrupadas pelo local de rede (isto é, pela subrede). Se seus usuários enfrentarem problemas com suas chamadas, este relatório pode ajudar você a determinar se estes problemas são amplos ou estão confinados a um determinado segmento da rede.
  
## <a name="accessing-the-location-report"></a>Acessando o Relatório de Localização

O Relatório de Localização é acessado na página inicial de Relatórios de Monitoramento. É possível detalhar o Relatório de Lista de Chamadas clicando em uma das seguintes métricas:
  
- Volume da chamada
    
- Porcentagem de chamadas ruins
    
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Locais permite que você filtre coisas como o local onde a chamada foi originada ou se a chamada ocorreu em uma conexão com ou sem fio. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Locais.
  
**Filtros do Relatório de Locais**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Local do chamador** <br/> |Sub-rede IP do usuário que fez a chamada. É possível selecionar somente **[Tudo]** para indicar todas as sub-redes.<br/> |
|**Local do computador chamado** <br/> |Sub-rede IP do usuário que recebeu a chamada. É possível selecionar somente **[Tudo]** para indicar todas as sub-redes.<br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não-VPN <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Locais.
  
**Métricas do Relatório de Locais**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Sub-rede do chamador** <br/> |Não  <br/> |Sub-rede IP do usuário que fez a chamada.  <br/> |
|**Sub-rede do computador chamado** <br/> |Não  <br/> |Sub-rede IP do usuário que recebeu a chamada.  <br/> |
|**Volume da chamada** <br/> |Sim  <br/> |Número total de chamadas realizadas.  <br/> |
|**Porcentagem de chamadas ruins** <br/> |Sim  <br/> |Percentual de chamadas classificadas como ruins. Uma chamada ruim é qualquer chamada da qual pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada que experimentou tremulação excessiva).  <br/> |
|**Viagem de ida e volta (ms)** <br/> |Sim  <br/> |Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.  <br/> |
|**Degradação (MOS)** <br/> |Sim  <br/> |Quantidade média da degradação da pontuação média de opinião (MOS, mean opinion score) enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. Historicamente, pontuações de opções médias foram calculadas com usuários classificando a qualidade de uma chamada em uma escala de 1 a 5. No Skype para Business Server, um conjunto de algoritmos prever como usuários classificou uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Sim  <br/> |Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**Tremulação** <br/> |Sim  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Sim  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Sim  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Sim  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
   

