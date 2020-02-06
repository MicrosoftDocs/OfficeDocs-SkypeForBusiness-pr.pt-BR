---
title: Relatório de lista de chamadas no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
description: 'Resumo: Saiba mais sobre o relatório de lista de chamadas usado no Skype for Business Server.'
ms.openlocfilehash: 3013dcce34804c7afb4c0d1ca7a211f8decf56ed
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818112"
---
# <a name="call-list-report-in-skype-for-business-server"></a>Relatório de lista de chamadas no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de lista de chamadas usado no Skype for Business Server.
  
O Relatório de Lista de Chamadas fornece métricas de QoE (qualidade da experiência) para chamadas individuais feitas e recebidas em sua organização. Observe que as métricas reais relatadas dependem de como você acessa o relatório de Lista de Chamadas. Por exemplo, se você abrir o relatório do [relatório de dispositivos no Skype for Business Server](device-report.md), verá métricas como as métricas a seguir, que também são relatadas no relatório do dispositivo:
  
- Microfone do chamador
    
- Alto-falante do chamador
    
- Microfone do receptor
    
- Alto-falante do receptor
    
- Tempo de troca da taxa de voz 
    
No entanto, se você abrir o relatório de lista de chamadas no [relatório de localização no Skype for Business Server](location-report.md), não verá nenhuma dessas métricas; em vez disso, você verá métricas como estas:
  
- Ida e volta (ms)
    
- Degradação (MOS)
    
- Perda de pacote
    
- Tremulação (ms)
    
Há métricas relatadas no Relatório de Local. Entretanto, a partir do Relatório de Lista de Chamadas, é sempre possível clicar na métrica Detalhe para fornecer informações completas de QoE de qualquer chamada.
  
## <a name="accessing-the-call-list-report"></a>Como acessar o Relatório de Lista de Chamadas

O Relatório de Lista de Chamadas pode ser acessado de qualquer um dos seguintes relatórios:
  
- O [relatório de localização no Skype for Business Server](location-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)
    
- O [relatório do dispositivo no Skype for Business Server](device-report.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)
    
- O [relatório de Resumo de qualidade da mídia no Skype for Business Server](summary.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)
    
- O [relatório de desempenho do servidor no Skype for Business Server](server-performance.md) (clicando no volume da chamada ou na métrica de porcentagem baixa de chamada)
    
No relatório de lista de chamadas, você pode acessar o [relatório de detalhes de chamadas no Skype for Business Server](call-detail-report.md) clicando na métrica de detalhes.
  
## <a name="making-the-best-use-of-the-call-list-report"></a>Como usar melhor o Relatório de Lista de Chamada

Se não conseguir se lembrar o que algumas das métricas do Relatório de Lista de Chamada (como o Tempo de troca da taxa de voz) realmente medem, coloque o mouse sobre o rótulo da métrica; uma dica de ferramenta aparecerá fornecendo uma breve descrição da métrica.
  
## <a name="filters"></a>Filtros

Nenhum. Não é possível filtrar o Relatório de Lista de Chamadas.
  
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações detalhadas fornecidas no Relatório de Lista de Chamadas para cada chamada.
  
**Métricas do Relatório de Lista de Chamadas**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Detalhes** <br/> |Não  <br/> |Ao clicar neste item, o relatório exibe informações adicionais sobre a chamada.  <br/> |
|**Chamador** <br/> |Sim  <br/> |Endereço SIP da pessoa que iniciou a chamada.  <br/> |
|**Receptor** <br/> |Sim  <br/> |Endereço SIP da pessoa que recebeu a chamada.  <br/> |
|**Hora inicial** <br/> |Sim  <br/> |Data e horário em que a chamada teve início.  <br/> |
|**Hora de término** <br/> |Sim  <br/> |Data e horário em que a chamada terminou.  <br/> |
|**Agente do usuário do chamador** <br/> |Sim  <br/> |Software usado pelo ponto de extremidade da pessoa que iniciou a chamada.  <br/> |
|**Agente do usuário do receptor** <br/> |Sim  <br/> |Software usado pelo ponto de extremidade da pessoa que recebeu a chamada.  <br/> |
|**Ida e volta (ms)** <br/> |Sim  <br/> |Quantidade média de (em milissegundos) exigida para que um pacote RTP (protocolo de transporte em tempo real) viaje até outra extremidade e retorne. Tempos de viagem de ida e volta de 100 milissegundos ou menos são considerados de qualidade aceitável.  <br/> Os valores altos de ida e volta pode ser causados por roteamento de chamada internacional, um erro de configuração de roteamento ou um servidor de mídia sobrecarregado. Tempos de ida e volta altos resultam em dificuldades com conversas de áudio em tempo real e bidirecionais.  <br/> |
|**Degradação (MOS)** <br/> |Sim  <br/> |Quantidade média da degradação MOS (pontuação média de opinião) enfrentada durante uma chamada. Os valores de degradação variam de um baixo de 0,0 a um alto de 5,0. Um valor de 0,5 ou menos representa degradação aceitável. As pontuações médias de opinião costumava ser calculadas a partir da classificação da qualidade de uma chamada em uma escala de 1 a 5, feita pelos dos usuários. No Skype for Business Server, um conjunto de algoritmos prevê como os usuários teriam classificado uma chamada.  <br/> Os valores de degradação altos podem ser causados por congestão, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia ou ponto de extremidade sobrecarregado. A alta degradação resulta em perda ou distorção de áudio.  <br/> |
|**Perda de pacote** <br/> |Sim  <br/> |Taxa média de perda de pacote RTP. (A perda de pacote ocorre quando os pacotes RTP, um protocolo usado para transmissão de áudio e vídeo pela Internet, não conseguem chegar aos seus destinos.) Taxas de perda altas normalmente são causadas por congestionamento, falta de largura de banda, congestionamento ou interferência sem fio ou um servidor de mídia sobrecarregado. A perda de pacote normalmente resulta em perda ou distorção de áudio.  <br/> |
|**Tremulação** <br/> |Sim  <br/> |Tremulação média detectada entre chegadas de pacote RTP. (Tremulação é uma medição de quanto uma chamada treme.) Valores altos de tremulação são normalmente causados por congestionamento ou por um servidor de mídia sobrecarregado e resultam em perda ou distorção de áudio.  <br/> |
|**Taxa de correção oculta** <br/> |Sim  <br/> |Taxa média de amostras de áudio ocultas para o número total de amostras. (Uma amostra de áudio oculta é uma técnica usada para suavizar a transição abrupta que normalmente seria causada por pacotes de rede descartados.) Valores altos indicam níveis consideráveis de perda de ocultação aplicada causada por perda de pacote ou tremulação e resulta na perda ou distorção de áudio.  <br/> |
|**Taxa de correção estendida** <br/> |Sim  <br/> |Taxa média de amostras de áudio estendidas para o número total de amostras. (Áudio estendido é o áudio que foi expandido a fim de ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos indicam níveis significativos de extensão de amostra causada por tremulação e resultam em um som robótico ou distorcido.  <br/> |
|**Taxa de correção compactada** <br/> |Sim  <br/> |Taxa média de amostras de áudio compactadas para o número total de amostras. (Áudio compactado é o áudio que foi compactado para ajudar a manter a qualidade da chamada quando um pacote de rede descartado é detectado.) Valores altos podem indicar níveis consideráveis de compactação de amostra causada por tremulação e resultam em um som acelerado ou distorcido.  <br/> |
|**Conectividade** <br/> |Sim  <br/> | Tipo de link de comunicação sem fio. Normalmente é um dos seguintes: <br/>  Retransmissão <br/>  Direto <br/> |
   

