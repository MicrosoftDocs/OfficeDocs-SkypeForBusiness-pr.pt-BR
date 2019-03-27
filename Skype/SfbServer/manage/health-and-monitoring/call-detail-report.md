---
title: Relatório detalhado de chamadas no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38862e35-3fec-41b9-a035-0b301942d446
description: 'Resumo: Saiba mais sobre o Call Detail Report usada no Skype para Business Server.'
ms.openlocfilehash: a0b0836099e1181a25b95bf7adbbe603ef7d5e5f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887649"
---
# <a name="call-detail-report-in-skype-for-business-server"></a>Relatório detalhado de chamadas no Skype para Business Server
 
**Resumo:** Saiba mais sobre o Call Detail Report usada no Skype para Business Server.
  
O Call Detail Report fornece uma descrição detalhada em uma chamada individual; o relatório inclui quase todos os o Quality of Experience métricas e estatísticas coletadas pelo Skype para Business Server, divididos em seções do relatório, como:
  
- Informações da chamada 
    
- Medição do dispositivo e do sinal do chamador
    
- Medição do dispositivo e do sinal de quem é chamado
    
- Evento do cliente do chamador
    
- Evento do cliente de quem é chamado
    
- Fluxo de áudio (do chamador para que é chamado)
    
- Fluxo de vídeo (do chamador para que é chamado)
    
- Fluxo de áudio (de quem é chamado para o chamador)
    
- Fluxo de vídeo (de quem é chamado para o chamador)
    
Lembre-se de que as categorias e métricas de um determinado relatório dependem de duas coisas: o tipo de sessão e o tipo de ponto de extremidade usados na sessão. Por exemplo, uma chamada com apenas áudio não reportará métricas de fluxo de vídeo; isso se deve ao fato de a chamada não ter um fluxo de vídeo. Da mesma forma, é possível ter um relatório que liste estatísticas do chamador, mas não de quem é chamado. Normalmente, isso ocorre quando quem foi chamado não usa um dispositivo compatível com SIP. Os pontos de extremidade são responsáveis por reportar estatísticas no final de uma chamada; no entanto, um telefone celular (que desconhece SIP ou as estatísticas de SIP) não pode reportar esse tipo de informação. Se você ligar para alguém e essa pessoa atender em um telefone celular, você não obterá um relatório desse telefone celular quando a chamada terminar.
  
O Relatório Detalhado de Chamadas é especialmente útil quando você está tentando determinar exatamente porque determinada chamada enfrentou problemas de qualidade de mídia.
  
## <a name="accessing-the-call-detail-report"></a>Acessando o Relatório Detalhado de Chamadas

O Relatório Detalhado de Chamadas pode ser acessado a partir de qualquer um dos seguintes relatórios:
  
- [Location Report no Skype para Business Server (local-report.md) (clicando na métrica de porcentagem de chamadas ruins ou o volume de chamadas)
    
- O [Media Quality Summary Report no Skype para Business Server (summary.md) (clicando no volume de chamada ou na medida percentual de chamadas ruins)
    
- O [Relatório de comparação de qualidade de mídia no Skype para Business Server](comparison.md) (por clicando no [Call List Report no Skype para Business Server](call-list-report-0.md) e, em seguida, clicando na métrica detalhe).
    
- O [Server Performance Report no Skype para Business Server](server-performance.md) (clicando no volume de chamada ou na medida percentual de chamadas ruins)
    
- O [Call List Report no Skype para Business Server](call-list-report-0.md) (clicando na métrica detalhe)
    
Dentro do relatório de detalhes das chamadas você pode acessar o [Relatório de dispositivo no Skype para Business Server](device-report.md) clicando em uma das seguintes métricas:
  
- Dispositivo de captura
    
- Dispositivos de renderização
    
Também é possível acessar o Relatório de Tendências de Qualidade de Mídia clicando na métrica Servidor de borda de áudio/vídeo.
  
## <a name="making-the-best-use-of-the-call-detail-report"></a>Fazendo o melhor uso do Relatório Detalhado de Chamadas

O Relatório Detalhado de Chamadas normalmente contém 250 métricas diferentes, inclusive itens como Descompasso do carimbo de data/hora do microfone, Tempo de SNR baixo e Extremidade próxima ao tempo de eco. Se não conseguir se lembrar o que exatamente todas essas métricas avaliam, tente pousar o mouse sobre o rótulo da métrica; na maioria das vezes, uma dica de ferramenta será exibida descrevendo a métrica.
  
Se tiver problemas para localizar uma métrica, digite parte do nome da métrica na caixa de pesquisa e clique em **Localizar**. Por exemplo, se não puder localizar a métrica Tempo de SNR baixo, digite SNR na caixa de pesquisa e clique em **Localizar**.
  
Observe que o relatório rastreia apenas as informações sobre uma chamada. A chamada em si não é gravada.
  
## <a name="filters"></a>Filtros

Nenhum. Você não pode filtrar o Relatório Detalhado de Chamadas.
  
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório Detalhado de Chamadas para cada chamada.
  
**Métricas do Relatório Detalhado de Chamadas**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**PAI do chamador** <br/> |Não  <br/> |O P-Asserted-Identity do usuário que iniciou a chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.  <br/> |
|**URI do chamador** <br/> |Não  <br/> |Endereço SIP do usuário que iniciou a chamada.  <br/> |
|**Ponto de extremidade do chamador** <br/> |Não  <br/> |Dispositivo usado para efetuar a chamada.  <br/> |
|**Agente do usuário do chamador** <br/> |Não  <br/> |Software usado no dispositivo que fez a chamada.  <br/> |
|**Início da chamada** <br/> |Não  <br/> |Data e hora em que a chamada foi iniciada.  <br/> |
|**Chamada de desvio do Servidor de Mediação** <br/> |Não  <br/> |Indica se a chamada conectou a um gateway de voz PSTN ou IP-PBX qualificado sem passar pelo Servidor de Mediação.  <br/> |
|**OS do chamador** <br/> |Não  <br/> |Sistema operacional do computador do chamador.  <br/> |
|**CPU do chamador** <br/> |Não  <br/> |CPU instalado no computador do usuário que iniciou a chamada.  <br/> |
|**Número de core do CPU do chamador** <br/> |Não  <br/> |Número do processador no computador usado pela pessoa que iniciou a chamada.  <br/> |
|**Velocidade de CPU do chamador** <br/> |Não  <br/> |Velocidade de relógio do CPU do computador usado pela pessoa que iniciou a chamada.  <br/> |
|**Virtualização de CPU do chamador** <br/> |Não  <br/> |Virtualização (se houver) no computador usado pela pessoa que iniciou a chamada.  <br/> |
|**PAI do receptor da chamada** <br/> |Não  <br/> |O P-Asserted-Identity do usuário convidado a entrar na chamada. Essa identidade é usada para transportar a identidade comprovada de um usuário dentro de uma rede confiável.  <br/> |
|**URI do receptor da chamada** <br/> |Não  <br/> |Endereço SIP do usuário que foi chamado.  <br/> |
|**Ponto de extremidade do receptor da chamada** <br/> |Não  <br/> |Dispositivo usado para receber a chamada.  <br/> |
|**Agente do usuário do receptor** <br/> |Não  <br/> |Software usado no dispositivo que recebeu a chamada.  <br/> |
|**Duração** <br/> |Não  <br/> |Tempo da chamada.  <br/> |
|**Sinalizador de aviso do desvio de mídia** <br/> |Não  <br/> |Aviso emitido quando o Servidor de Mediação foi desviado.  <br/> |
|**OS do receptor da chamada** <br/> |Não  <br/> |Sistema operacional do computador do usuário que foi chamado.  <br/> |
|**CPU do receptor da chamada** <br/> |Não  <br/> |CPU instalado no computador do usuário que foi chamado.  <br/> |
|**Número de core do receptor da chamada** <br/> |Não  <br/> |Número do processador no computador usado pela pessoa que foi chamada.  <br/> |
|**Velocidade de CPU do receptor da chamada** <br/> |Não  <br/> |Velocidade de relógio do CPU do computador usado pela pessoa que foi chamada.  <br/> |
|**Virtualização de CPU do receptor da chamada** <br/> |Não  <br/> |Virtualização (se houver) no computador usado pela pessoa que foi chamada.  <br/> |
   

