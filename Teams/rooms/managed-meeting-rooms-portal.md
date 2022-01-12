---
title: Salas do Microsoft Teams Portal
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.reviewer: dstrome
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Forneça uma visão da saúde de suas salas de reunião.
f1keywords: ''
ms.openlocfilehash: db8f6125bda335dfab2f9208fcfd8ab0f192e4e7
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767446"
---
# <a name="microsoft-managed-meeting-rooms-portal"></a>Portal de Salas de Reunião Gerenciadas da Microsoft

## <a name="overview"></a>Visão Geral

O Portal de Salas de Reunião Gerenciadas ("Portal de Salas") fornece uma visão da saúde de suas salas de reunião. Uma visão do cliente deste portal é para sua visibilidade e comentários e para facilitar suas ferramentas/práticas de monitoramento existentes.

O escopo do monitoramento é

- Exibição de incidentes
  - Principais problemas que afetam suas salas
  - Ações necessárias para restaurar salas com status ável
  - Problemas que estão sendo investigados pela Microsoft
- Exibição de Microsoft Teams de sala
  - Instantâneo de status no nível Salas do Microsoft Teams (MTR) do dispositivo
  - Histórico e detalhes básicos para cada dispositivo

**Exibição de Microsoft Teams de sala**

- Instantâneo de status no nível Salas do Microsoft Teams (MTR) do dispositivo
- Histórico e detalhes básicos para cada dispositivo

> [!Important]
> Revise [**Atribuir usuários à função Administrador**](enrolling-mtrp-managed-service.md#assign-users-to-the-managed-service-administrator-role) de Serviços Gerenciados e certifique-se de que o acesso ao portal seja limitado com base nas suas necessidades de negócios.

## <a name="terminology"></a>Terminologia

Aqui estão os termos usados com frequência no portal.

|Termo |Significado |
| :- | :- |
|**Software de Monitoramento** |Agente de monitoramento implantado em cada um dos dispositivos Microsoft Teams Room. |
|**Aplicativo** |Microsoft Teams aplicativo de sistema de sala (independentemente de usar Skype for Business ou Microsoft Teams como o serviço de colaboração. |
|**Sala/Dispositivo** |O dispositivo Microsoft Teams sistema de sala certificado. |
|**Não monitorado** | O software de monitoramento da Microsoft implantado como parte dos serviços gerenciados não é capaz de se conectar aos serviços de nuvem. Não estamos recebendo telemetria sobre o dispositivo. |
|<p>**Healthy /** </p><p>**Insalubridade** </p>|Anormalidades no dispositivo/periférico. |
|**Suprimido** |Se um dispositivo é conhecido por estar em manutenção e seus alertas devem ser ignorados, o dispositivo pode ser suprimido deliberadamente. |
|**Integração** |O estado de um dispositivo de sala enquanto ele está sendo adicionado à instalação, mas não está pronto como uma sala com suporte regular. |
|**Incidente** |Um problema que afeta as experiências de reunião de usuários finais que precisam de ação. |
|**Configurada inconfigurada** |A configuração detectada não é correta/comumente usada. |
|**Tíquete de suporte** |Identificador de controle interno da Microsoft que rastreia todas as comunicações/ações relacionadas a um incidente. |

## <a name="incidents-view"></a>Exibição incidentes

Esta exibição é uma visão geral da guia Incidentes no Portal de Salas Gerenciadas. Esta página é a home page padrão do portal.

### <a name="top-level-summary"></a>Resumo de nível superior 
O resumo de nível superior mostra rapidamente os problemas que afetam suas salas, o que você precisa fazer e o que a Microsoft está fazendo sobre eles:

![Captura de tela mostrando resumo de problemas de nível superior](../media/rooms-monitor-001new.png)

|# |Explicação |
| :- | :- |
|1 |Tipos de incidentes que afetam suas salas |
|2 |**AÇÃO DE NECESSIDADE**: itens que exigem que sua intervenção seja resolvida. |
|3 |**ATRIBUÍDO À MICROSOFT**: itens atualmente investigados pela equipe da Microsoft. |
|4 |**INVESTIGAÇÃO PENDENTE**: itens na fila a serem investigados pela equipe da Microsoft. |

Os incidentes devem estar em um dos três estados:

- **Ação de necessidade**: atribuída a você para ação
- **Atribuído à Microsoft**: Atribuído à Microsoft para a próxima ação
- **Investigação Pendente**: em investigação para próximas etapas

### <a name="reviewing-incidents"></a>Revisão de incidentes

A imagem a seguir lista todos os incidentes que estão atualmente ativos em suas salas. Os que são atribuídos a você estão na *parte superior–* é isso que você precisa ver para as próximas etapas. Além disso, os atribuídos à Microsoft ou à investigação pendente têm detalhes que você pode usar para intervir.

Clicar em qualquer um dos itens com status "**Ação Necessidades**" mostra detalhes adicionais sobre o incidente.

## <a name="types-of-incidents"></a>Tipos de incidentes

Os incidentes são classificados em dois tipos de gravidade ampla:

- **Importante**: incidentes que provavelmente estão causando problemas em reuniões e devem ser priorizados.
- **Aviso** – Incidentes que são notificações para planejar ações de manutenção. Se isso não for feito, com o tempo as salas provavelmente chegarão a um problema. Os avisos destinam-se a dar tempo para planejar e orquestrar o suporte.

Um aviso pode fazer a transição para "**Importante**" se não for atendido por um tempo.

## <a name="health-status-of-device-and-incidents"></a>Status de saúde do dispositivo e incidentes

Incidentes que são classificados como **"Importantes"** na gravidade afetarão o status de saúde de um dispositivo. Se houver pelo menos um incidente de **Severidade = "Importante"** associado a um dispositivo, ele será classificado como **_um dispositivo não_** al.

Incidentes classificados como **gravidade "Aviso"** não afetam o status de saúde relatado em um dispositivo. No entanto, se um dispositivo tiver incidentes de nível de aviso associados a ele, ele será mostrado com o status de saúde do dispositivo da seguinte forma.

![Captura de tela mostrando o status de saúde de uma sala](../media/rooms-monitor-004.jpg)

A seguir estão alguns dos tipos de incidentes que você pode ver e as explicações para cada tipo. Para cada tipo, a ação associada ao incidente será mais específica, dependendo do problema.

**Tabela 1: Incidentes com gravidade "importante"**

|Tipo |Explicação |
| :- | :- |
|**Display** |A exibição conectada ao dispositivo não parece saudável.|
|**Microfone de conferência, alto-falante de conferência** |Os dispositivos de áudio (microfone/alto-falante) parecem estar mal configurados. |
|**Câmera** |A câmera conectada ao dispositivo não parece estar bem. |
|**Ingestão HDMI** |HdMI Ingest não está íntegre. |
|**Entrar** (Exchange) |Microsoft Teams aplicativo de sala acessa informações de calendário Exchange e qualquer problema com o sucesso de entrada será relatado com um incidente de entrada. |
|**Entrar** (Teams) |Microsoft Teams o aplicativo room entra no dispositivo e a falha na entrada será relatada com esse incidente (se o cliente estiver usando Teams). |
|**Entrar** (Skype for Business) |Microsoft Teams o aplicativo room entra no dispositivo e a falha ao entrar será relatada com esse incidente (se o cliente estiver usando Skype for Business) |
|**Sensor de proximidade** |Microsoft Teams aplicativo de sala convida os participantes a ingressarem em uma reunião se eles estão próximos. Falhas neste recurso serão relatadas sob este incidente. |

**Tabela 2: Incidentes com gravidade "Aviso"**

|Tipo |Explicação |
| :- | :- |
|**Versão do aplicativo** |A versão do Microsoft Teams Aplicativo de Sala em execução no dispositivo não é atual. Versões antigas são causas conhecidas para problemas experimentados pelos usuários. |
|**Versão do sistema operacional.** |A versão do Windows operacional em execução na sala de reunião não é mais recomendada. |
|**Rede** |Isso será removido como um tipo de aviso no curto prazo devido ao trabalho adicional necessário após a avaliação. |

## <a name="responding-to-incidents"></a>Respondendo a incidentes

Os incidentes se enquadram em três categorias: Precisa de Ação, Investigação Pendente ou Atribuído à Microsoft.

### <a name="needs-action-incidents"></a>Incidentes "Precisa de Ação"

Incidentes com status definido como **"Ação de Necessidades"** são atribuídos a você para tomar uma ação corretiva.

Cada incidente desse tipo terá um campo de ação com uma ação recomendada da Microsoft da seguinte forma:

![Captura de tela mostrando a ação de incidente recomendada](../media/rooms-monitor-005.jpg)

- Se você tiver tomado a ação, poderá responder ao incidente com suas anotações na caixa Responder, em seguida, escolha "Atribuir à Microsoft" antes de postar.
- Também é possível que a notificação seja incorreta com base na revisão. Nesse caso, forneça esse feedback e atribua de volta à Microsoft.
- Por fim, se você quiser adicionar um comentário para fornecer contexto adicional para sua própria equipe ou para a equipe da Microsoft, poste a mensagem sem acioná-la "Atribuir à Microsoft".

>[!NOTE]
>Sua ação corretiva pode resolver o problema e o monitoramento de Salas Gerenciadas limpa esse incidente da sua lista. Na situação acima, talvez você não tenha a chance de resolver o problema e atribuí-lo de volta à Microsoft. Esse problema será abordado em uma versão futura.

### <a name="pending-investigation-incidents"></a>Incidentes de "Investigação Pendente"

Para os incidentes em investigação, o campo de descrição contém informações sobre o incidente, causas típicas e resoluções que podem ser úteis para resolver determinados problemas para que você possa agir sem atraso.

### <a name="assigned-to-microsoft-incidents"></a>Incidentes "Atribuídos à Microsoft"

Para os incidentes atribuídos à Microsoft, o campo "Ação" conterá breves detalhes sobre etapas corretivas planejadas ou progredidas. Essas etapas podem precisar de colaboração com sua equipe e a colaboração estendida será feita por email/chamadas, conforme necessário. Depois que esses problemas são resolvidos, eles desaparecem do portal e, no futuro, haverá histórico para acompanhar esses incidentes e sua resolução.

![Captura de tela mostrando etapas corretivas do MS](../media/rooms-monitor-006.jpg)

## <a name="rooms-view"></a>Exibição de Salas

Cada dispositivo é um proxy para uma sala e seus periféricos conectados. Um dispositivo saudável representa uma sala saudável e um dispositivo não saudável representa uma sala provavelmente causando problemas durante as reuniões. Além da exibição Incidentes, o Portal de Salas Gerenciadas também fornece uma visão geral da saúde da sala e ajuda você a solucionar problemas de detalhes do dispositivo e a entender falhas repetidas com o histórico de incidentes.

![Captura de tela mostrando a visão geral de saúde de uma sala](../media/rooms-monitor-007.jpg)

**Healthy, Unhealthy, Disconnected** O painel superior no modo de exibição Salas fornece um instantâneo rápido de quantos de seus dispositivos estão em um bom estado("Saudável"), quantos são afetados por problemas ("Não Íveis"), quantos não estão fornecendo telemetria ("Desconectado") e quantos dispositivos são suprimidos do alerta (como uma substituição). As salas são monitoradas para a saúde usando critérios e heurísticas em evolução. O objetivo é refletir a realidade da experiência do usuário na sala com a maior precisão possível e torná-la a ação.

**Salas saudáveis / não salubres:**

Dispositivos/periféricos que não têm nenhum incidente de gravidade "Importante" estão a atender aos critérios atuais de saúde são marcados como saudáveis. No entanto, isso não implica que haja uma paralisação de sala para cada dispositivo não aldo no portal. A descrição e a parte de ação do incidente contém detalhes mais específicos sobre o problema e o impacto potencial na experiência do usuário.

**Dispositivo desconectado:**

O agente de monitoramento da Microsoft implantado como parte do piloto de Salas Gerenciadas é desconectado dos serviços de nuvem de Sala Gerenciada. Não estamos recebendo telemetria sobre a sala e não temos o status de saúde mais recente. Isso pode acontecer devido a problemas de rede, alterações na política de firewall ou se houver alterações feitas na imagem do dispositivo.

## <a name="room-detail-status-and-changes"></a>Detalhes da Sala: Status e Alterações

**Detalhes da Sala: Status** A guia *Status* do dispositivo fornece uma exibição consolidada do status de um dispositivo, todos os problemas ativos para o dispositivo, as ações necessárias para resolvê-los ou que estão em andamento. A guia Status também contém a divisão de diferentes componentes de saúde do dispositivo na *guia Incidentes.* Se um dispositivo for desconectado, os detalhes de Status não estarão disponíveis.

![Captura de tela mostrando exibição de status consolidada](../media/rooms-monitor-008.png)

**Mostrar todos os sinais:** Para exibir todos os sinais contidos em uma categoria de sinal, habilita o botão Mostrar todos os sinais de alternância. As setas de expansão aparecerão ao lado de títulos de categoria que podem ser clicados em para expandir o exibição de accordion.

![Captura de tela mostrando sinais dentro de uma categoria](../media/rooms-monitor-009.png)

**Tíquete supressão/desuppresso** Quando uma sala está inscrita, você está indicando que deseja receber notificações para alterações na telemetria da sala. Há ocasiões em que um determinado dispositivo ou periférico está em um estado conhecido em que você não deseja tíquetes ou notificações geradas. Usando a funcionalidade suprimir tíquete, silenciará qualquer notificação sobre esse sinal específico. Quando você estiver pronto para o serviço monitorar e notificá-lo sobre esse sinal, basta descompactar o sinal individual.

![Captura de tela mostrando os tíquetes suprimidos da sala](../media/rooms-monitor-010.png)

**Expansão da categoria de tíquete ativo** Em cada categoria de tíquete, qualquer tíquete resolvido ativo ou mais recente será exibido juntamente com a gravidade e quando o tíquete foi atualizado pela última vez. Clicando na seta de expansão, todos os tíquetes aparecerão com um link ativo para as informações do tíquete.

Expansão da Categoria de Tíquete Ativo: em cada categoria de tíquete, qualquer tíquete resolvido ativo ou mais recente será exibido juntamente com a gravidade e quando o tíquete foi atualizado pela última vez. Clicando na seta de expansão, todos os tíquetes aparecerão com um link ativo para as informações do tíquete.

![Captura de tela mostrando categoria de tíquete resolvido](../media/rooms-monitor-011.png)

## <a name="active-ticket-overview"></a>Tíquete Ativo: Visão geral

Cada incidente criado identifica o problema detectado e a ação corretiva que precisa ser tomada para restaurar a sala em um estado corretamente. O tíquete gerado transmitirá a visão geral do incidente com todas as mensagens geradas pela AI de serviços gerenciados, bem como a equipe de engenharia de serviço da Microsoft que está investigando o problema. Todos os anexos coletados para solução de problemas de incidentes serão listados. A guia Histórico fornece as datas em que os problemas foram identificados.

![Captura de tela mostrando visão geral do tíquete ativo](../media/rooms-monitor-012.png)

Tíquete Ativo: Mensagens A interface do usuário de mensagens é a principal ferramenta de comunicação para interagir com os engenheiros de serviço da Microsoft que trabalham para correção do problema identificado. É importante confirmar as comunicações da Microsoft para garantir que estamos fornecendo o melhor serviço possível. Se você tiver tomado as ações recomendadas, responda a esse incidente com suas anotações na caixa Responder e atribua de volta à Microsoft clicando em "Atribuir à Microsoft" antes de postar.
Também é possível que a notificação seja incorreta com base na revisão. Nesse caso, forneça esse feedback e atribua de volta à Microsoft.
Por fim, se você quiser adicionar um comentário para fornecer contexto adicional para sua própria equipe ou para a equipe da Microsoft, basta postar a mensagem sem acioná-la "Atribuir à Microsoft

![Captura de tela mostrando mensagens de tíquete ativo](../media/rooms-monitor-013.png)


Tíquete Ativo: Anexos Há ocasiões em que os engenheiros de serviço da Microsoft precisam de informações adicionais para aumentar a investigação do problema. A guia anexo oferece a capacidade de carregar imagens, vídeos ou logs solicitados.

![Captura de tela mostrando anexações de tíquete ativo](../media/rooms-monitor-014.png)

Tíquete Ativo: Histórico Cada sinal de sala tem apenas um número de tíquete atribuído a ele de propósito. Um dispositivo de sala ou periférico persiste em uma sala e pode ter problemas ao longo do tempo. Mantendo essas informações em uma ID de tíquete exclusiva específica, todas as informações históricas são mantidas e podem ser analisadas para padrões de comportamento. A interface do usuário histórico fornece uma exibição de todas as ações de tíquetes criadas e resolvidas para esse sinal.

![Captura de tela mostrando o histórico de tíquetes ativos](../media/rooms-monitor-015.png)

Perguntas frequentes Como os tíquetes dinâmicos afetam a mim e às operações de minhas salas?  
Os clientes verão a criação de tíquetes e correções mais inteligentes que se expandem além de apenas um tíquete de sinal binário. Por exemplo, pode haver até três exibições em um Sala de Reunião (Display 1, Display 2 & exibição do painel de toque MTR). No entanto, há apenas 1 (um) sinal de exibição que é saudável ou não saudável. Com os novos tíquetes dinâmicos, agora podemos gerar tíquetes exclusivos para cada sinal de exibição.
