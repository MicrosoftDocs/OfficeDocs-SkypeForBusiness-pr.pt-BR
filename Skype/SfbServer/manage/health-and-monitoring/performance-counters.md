---
title: Contadores de desempenho de mobilidade no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Resumo: Saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores executando o API de Web de comunicações unificadas (UCWA) e o Skype para serviço de mobilidade do Business Server Mcx.'
ms.openlocfilehash: 4d55dab133b7006f8a239560efb084fd2c61b917
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197650"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contadores de desempenho de mobilidade no Skype para Business Server
 
**Resumo:** Saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores executando o API de Web de comunicações unificadas (UCWA) e o Skype para serviço de mobilidade do Business Server Mcx.
  
As tabelas a seguir listam os nomes e descrições dos contadores de desempenho que você pode usar para monitorar servidores executando o API de Web de comunicações unificadas (UCWA) e o Skype para serviço de mobilidade do Business Server Mcx. 
  
O nome da categoria dos contadores na tabela UCWA é **LS:WEB - UCWA**.
  
O nome da categoria para os contadores na tabela do Serviço de Mobilidade Mcx é **LS:WEB – Mobile Communication Service**.

> [!NOTE]
> Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.
  
## <a name="performance-counters-for-ucwa"></a>Contadores de desempenho para UCWA

|Contador|Descrição|
|:-----|:-----|
|Contagem de aplicativos ativos  <br/> |O número atual de aplicativos  <br/> |
|Contagem da modalidade de compartilhamento do aplicativo ativa  <br/> |O número atual da modalidade de compartilhamento do aplicativo  <br/> |
|Contagem da modalidade de áudio ativa  <br/> |O número atual da modalidade de áudio  <br/> |
|Contagem da modalidade de colaboração de dados ativa  <br/> |O número atual da modalidade de colaboração de dados  <br/> |
|Latência para baixar fotos do diretório ativo (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para obter uma foto do diretório ativo  <br/> |
|Contagem da modalidade de tráfego de mensagens ativa  <br/> |O número atual da modalidade de tráfego de mensagens  <br/> |
|Contagem da modalidade de vídeo panorâmico ativa  <br/> |O número atual da modalidade de vídeo panorâmico  <br/> |
|Contagem de downloads pendentes ativos  <br/> |O número de downloads pendentes atualmente ativos; conexões de longa duração com o servidor  <br/> |
|Contagem de sessões ativas  <br/> |O número atual de pontos de extremidade registrados no UCWA por aplicativo e no total  <br/> |
|Contagem de instâncias de usuário ativas  <br/> |O número atual de instâncias de usuário ativas  <br/> |
|Instâncias de usuário ativas sem aplicativo  <br/> |O número atual de instâncias de usuário sem aplicativo  <br/> |
|Contagem da modalidade de vídeo ativa  <br/> |O número atual da modalidade de vídeo  <br/> |
|Solicitações de criação de aplicativo recebidas por segundo  <br/> |A taxa de solicitações de criação de aplicativo recebidas por segundo  <br/> |
|Falhas de entrada em MCU de AS  <br/> |O número de falhas de entrada em MCU de AS  <br/> |
|Falhas de entrada em MCU de AV  <br/> |O número de falhas de entrada em MCU de AV  <br/> |
|Tempo médio para inicialização do aplicativo (ms)  <br/> |O tempo médio para inicialização do aplicativo em milissegundos  <br/> |
|Tempo médio de duração por sessão (ms)  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Falhas de entrada em MCU de dados  <br/> |O número de falhas de entrada em MCU de dados  <br/> |
|Latência para pesquisa de contatos no Exchange (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para se pesquisar contatos no Exchange  <br/> |
|Latência para baixar fotos em HD no Exchange (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para se baixar uma foto no Exchange  <br/> |
|Respostas/segundo do HTTP 4xx  <br/> |A taxa de respostas por segundo com o código HTTP 4xx  <br/> |
|Respostas/segundo do HTTP 5xx  <br/> |A taxa de respostas por segundo com o código HTTP 5xx  <br/> |
|Falhas de entrada em MCU de IM  <br/> |O número de falhas de entrada em MCU de IM  <br/> |
|Número de falhas ao baixar fotos do Active Directory  <br/> |O número total de falhas ao baixar fotos do Active Directory  <br/> |
|Número de falhas ao pesquisar contatos  <br/> |O número total de falhas ao pesquisar contatos no Exchange  <br/> |
|Número de falhas de desserialização  <br/> |O número total de falhas de desserialização  <br/> |
|Número de falhas de Get HD foto  <br/> |O número total de falhas ao baixar fotos em HD do Exchange  <br/> |
|Excesso de inscrições por aplicativo  <br/> |O número de solicitações de inscrição além do máximo permitido por aplicativo  <br/> |
|Excesso de inscrições por lote  <br/> |O número de solicitações de inscrição além do máximo permitido por lote  <br/> |
|Falhas de inscrição de presença  <br/> |O número de falhas ao realizar inscrições de presença  <br/> |
|Falhas ao se registrar pontos de extremidade  <br/> |O número de falhas ao se registrar pontos de extremidade  <br/> |
|Solicitações recebidas/segundo  <br/> |A taxa de solicitações recebidas por segundo  <br/> |
|Solicitações bem-sucedidas/segundo  <br/> |A taxa por segundo de solicitações bem-sucedidas (códigos de resposta HTTP 2xx/3xx)  <br/> |
|Solicitações de criação de aplicativo bem-sucedidas/segundo  <br/> |A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo  <br/> |
|Contagem de downloads pendentes com tempo limite ultrapassado  <br/> |O número de downloads pendentes que ultrapassaram o tempo limite  <br/> |
|Total de solicitações de criação de aplicativo recebidas  <br/> |O número total de solicitações de criação de aplicativo recebidas desde que o serviço foi iniciado  <br/> |
|Total de respostas de HTTP 4xx  <br/> |O número total de respostas de HTTP 4xx  <br/> |
|Total de respostas de HTTP 5xx  <br/> |O número total de respostas de HTTP 5xx  <br/> |
|Total de solicitações recebidas no Canal de Comando  <br/> |O número total de solicitações recebidas no canal do comando  <br/> |
|Total de solicitações bem-sucedidas  <br/> |O número total de solicitações que tiveram êxito  <br/> |
|Total de sessões iniciadas  <br/> |O número total de sessões iniciadas desde a inicialização do serviço  <br/> |
|Total de sessões encerradas devido ao tempo limite de ociosidade  <br/> |O número total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |
|Total de aplicativos limitados  <br/> |O número de aplicativos limitados  <br/> |
   
**Contadores de desempenho para Mobility Service (Mcx)**

|**Contador**|**Descrição**|
|:-----|:-----|
|Tempo médio de vida de uma sessão em milissegundos  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Assinaturas atuais de notificação por push  <br/> |O número atual de assinaturas de notificação por push. Esse número, em conjunto com a Contagem de sessões atualmente ativas, representam o subconjunto de sessões atualmente ativas registradas para dispositivos Windows Mobile ou iPhone.  <br/> |
|Contagem de polls de tempo limite de rede ativos no momento  <br/> |O número de pools de rede que ultrapassaram o tempo limite  <br/> |
|Contagem de pools ativos no momento  <br/> |O número de polls atualmente ativos (conexões de longa duração com o servidor)  <br/> |
|Contagem de sessão ativa no momento  <br/> |Número atual de pontos de extremidade registrados no Mobility Service  <br/> |
|Contagem de sessão ativa no momento com assinaturas de presença ativa  <br/> |O número de sessões ativas no momento com assinaturas de presença ativa  <br/> |
|Solicitações de notificação por push sem êxito/segundo  <br/> |A taxa de notificações por push sem êxito por segundo  <br/> |
|Solicitações de notificação por push bem-sucedidas/segundo  <br/> |A taxa de notificações por push bem-sucedidas por segundo  <br/> |
|Solicitações de notificação por push limitadas/segundo  <br/> |A taxa de notificações por push limitadas por segundo  <br/> |
|Solicitações de notificação por push/segundo  <br/> |A taxa de notificações por push enviadas por segundo  <br/> |
|Solicitações sem êxito/segundo  <br/> |A taxa de solicitações sem êxito por segundo  <br/> |
|Solicitações recebidas/segundo  <br/> |A taxa de solicitações recebidas por segundo  <br/> |
|Solicitações rejeitadas/segundo  <br/> |A taxa de solicitações receitadas por segundo  <br/> |
|Solicitações bem-sucedidas/segundo  <br/> |A taxa de solicitações bem-sucedidas por segundo  <br/> |
|Solicitações de início de sessão bem-sucedidas/segundo  <br/> |A taxa de solicitações de Obter localização bem-sucedidas por segundo. As solicitações de início de uma sessão consomem grande parte do CPU no servidor. A carga de pico suportada é de 12/segundo. A sustentabilidade depende de outras cargas no servidor. Iniciar uma sessão normalmente significa um logon de um usuário que ficou desconectado durante um período extenso de tempo.  <br/> |
|Total de chamadas de voz de entrada recusadas  <br/> |O número total de chamadas de voz de entrada recusadas  <br/> |
|Total de chamadas de voz de entrada sem êxito  <br/> |O número total de chamadas de voz de entrada que não tiveram êxito  <br/> |
|Total de chamadas de voz de saída sem êxito  <br/> |O número total de chamadas de voz de saída que não tiveram êxito  <br/> |
|Número total de sessões encerradas pelo usuário  <br/> |O número total de sessões encerradas por usuários  <br/> |
|Total de solicitações de notificação por push  <br/> |O número total de solicitações de notificação por push  <br/> |
|Total de solicitações de notificação por push em êxito  <br/> |O número total de solicitações de notificação por push que não tiveram êxito  <br/> |
|Total de solicitações de notificação por push bem-sucedidas  <br/> |O número total de solicitações de notificação por push bem-sucedidas  <br/> |
|Total de solicitações de notificação por push limitadas  <br/> |O número total de solicitações de notificação por push limitadas  <br/> |
|Total de solicitações sem êxito  <br/> |O número total de solicitações que não tiveram êxito  <br/> |
|Total de solicitações recebidas no Canal de Comando  <br/> |O número total de solicitações recebidas no canal do comando  <br/> |
|Total de solicitações rejeitadas  <br/> |O número total de solicitações rejeitadas  <br/> |
|Total de solicitações bem-sucedidas  <br/> |O número total de solicitações feitas ao Mobility Service que tiveram êxito  <br/> |
|Contagem total de sessões iniciadas  <br/> |O número total de sessões iniciadas desde a inicialização do Mobility Service  <br/> |
|Total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |O número total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |
|Total de chamadas de voz de entrada bem-sucedidas  <br/> |O número total de chamadas de voz de entrada que tiveram êxito  <br/> |
|Total de chamadas de voz de saída bem-sucedidas  <br/> |O número total de chamadas de voz de saída que tiveram êxito  <br/> |
   
> [!NOTE]
> Suporte MCX (serviço de mobilidade) para clientes móveis herdados não está mais disponível no Skype para Business Server 2019. Todos os Skype atual para clientes móveis do Business já use Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Usuários com clientes herdados usando MCX serão necessário atualizar para um cliente atual.
