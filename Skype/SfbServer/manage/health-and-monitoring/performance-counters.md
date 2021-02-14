---
title: Contadores de desempenho de mobilidade no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Resumo: saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores que executam a Unified Communications Web API (UCWA) e o Serviço de Mobilidade Mcx do Skype for Business Server.'
ms.openlocfilehash: d711ada11cee9cb12a5cde25cab583f8b174ac50
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814401"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contadores de desempenho de mobilidade no Skype for Business Server
 
**Resumo:** Saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores que executam a Unified Communications Web API (UCWA) e o Serviço de Mobilidade Mcx do Skype for Business Server.
  
As tabelas a seguir listam os nomes e descrições dos contadores de desempenho que você pode usar para monitorar servidores que executam a Unified Communications Web API (UCWA) e o Serviço de Mobilidade Mcx do Skype for Business Server. 
  
O nome da categoria para os contadores na tabela UCWA é **LS:WEB - UCWA**.
  
O nome da categoria para os contadores na tabela Mcx Mobility Service é **LS:WEB - Mobile Communication Service**.

> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
  
## <a name="performance-counters-for-ucwa"></a>Contadores de desempenho para UCWA

|Contador|Descrição|
|:-----|:-----|
|Contagem de aplicativos ativos  <br/> |O número atual de aplicativos  <br/> |
|Contagem de modalidades de compartilhamento de aplicativos ativos  <br/> |O número atual da modalidade de Compartilhamento de Aplicativos  <br/> |
|Contagem de modalidades de áudio ativas  <br/> |O número atual de modalidade de áudio  <br/> |
|Contagem de modalidades de colaboração de dados ativos  <br/> |O número atual da modalidade de Colaboração de Dados  <br/> |
|Latência de Obter Fotos do Active Directory (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Active Directory  <br/> |
|Contagem de modalidades de mensagens ativas  <br/> |O número atual de modalidade de mensagens  <br/> |
|Contagem ativa da modalidade de vídeo panorâmico  <br/> |O número atual da modalidade de Vídeo Panorâmico  <br/> |
|Contagem de get pendentes ativos  <br/> |O número de obtém pendentes ativos no momento; conexões de longa duração com o servidor  <br/> |
|Contagem de sessão ativa  <br/> |O número atual de pontos de extremidade registrados no UCWA por aplicativo e no total  <br/> |
|Contagem de instâncias de usuário ativas  <br/> |O número atual de instâncias de usuário  <br/> |
|Instâncias de usuário ativas sem aplicativo  <br/> |O número atual de instâncias de usuário sem aplicativo  <br/> |
|Contagem da modalidade de vídeo ativa  <br/> |O número atual da modalidade de vídeo  <br/> |
|Solicitações de criação de aplicativo recebidas/segundo  <br/> |A taxa de solicitações de criação de aplicativo recebidas por segundo  <br/> |
|Falhas de ingressar em MCU de AS  <br/> |O número de falhas de junção DE AS MCU  <br/> |
|Falhas de entrada em MCU de AV  <br/> |O número de falhas de entrada em MCU de AV  <br/> |
|Tempo Médio de Inicialização do Aplicativo (ms)  <br/> |O tempo médio de inicialização do aplicativo em milissegundos  <br/> |
|Tempo médio de vida da sessão (ms)  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Falhas de junção de MCU de dados  <br/> |O número de falhas de junção de MCU de dados  <br/> |
|Latência da Pesquisa de Contatos do Exchange (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para pesquisar contato no Exchange  <br/> |
|Latência de Get de Fotos HD do Exchange (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Exchange  <br/> |
|Respostas HTTP 4xx/Segundo  <br/> |A taxa de respostas por segundo com código HTTP 4xx  <br/> |
|Respostas HTTP 5xx/Segundo  <br/> |A taxa de respostas por segundo com código HTTP 5xx  <br/> |
|Falhas de junção de MCU de IM  <br/> |O número de falhas de junção de MCU de IM  <br/> |
|Número de falhas de obter fotos do Active Directory  <br/> |O número total de falhas para recuperar fotos do Active Directory  <br/> |
|Número de falhas de Pesquisa de Contato  <br/> |O número total de falhas na pesquisa de contatos no Exchange  <br/> |
|Número de falhas de desserialização  <br/> |O número total de falhas de desserialização  <br/> |
|Número de falhas ao obter fotos HD  <br/> |O número total de falhas para recuperar fotos EM HD do Exchange  <br/> |
|Acima do máximo de assinaturas por aplicativo  <br/> |O número de solicitações de Assinatura acima do máximo permitido por aplicativo  <br/> |
|Acima do máximo de assinaturas por lote  <br/> |O número de solicitações de Assinatura acima do máximo permitido por lote  <br/> |
|Falhas de Assinatura de Presença  <br/> |O número de falhas na assinatura da presença  <br/> |
|Registrando falhas de ponto de extremidade  <br/> |O número de falhas ao registrar pontos de extremidade  <br/> |
|Solicitações recebidas/segundo  <br/> |A taxa de solicitações recebidas por segundo  <br/> |
|Solicitações bem-sucedidas/segundo  <br/> |A taxa de solicitações bem-sucedidas por segundo (códigos de resposta HTTP 2xx/3xx)  <br/> |
|Solicitações de criação de aplicativo bem-sucedidas/segundo  <br/> |A taxa de solicitações de criação de aplicativo bem-sucedidas por segundo  <br/> |
|Contagem de get pendentes com tempo out  <br/> |O número de pendentes obtém o tempo gasto  <br/> |
|Total de solicitações de criação de aplicativo recebidas  <br/> |O número total de solicitações de criação de aplicativo recebidas desde que o serviço foi iniciado  <br/> |
|Total de respostas HTTP 4xx  <br/> |O número total de respostas HTTP 4xx  <br/> |
|Total de respostas HTTP 5xx  <br/> |O número total de respostas HTTP 5xx  <br/> |
|Total de solicitações recebidas no canal de comando  <br/> |O número total de solicitações recebidas no canal do comando  <br/> |
|Total de solicitações bem-sucedidas  <br/> |O número total de solicitações bem-sucedidas  <br/> |
|Total de sessões iniciadas  <br/> |O número total de sessões iniciadas desde que o serviço foi iniciado  <br/> |
|Total de sessões encerradas devido ao tempo de ociosidade  <br/> |O número total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |
|Total de aplicativos com aceleração  <br/> |O número de aplicativos aceleradores  <br/> |
   
**Contadores de desempenho para o Mcx Mobility Service**

|**Contador**|**Descrição**|
|:-----|:-----|
|Tempo média de vida de uma sessão em milissegundos  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Assinaturas atuais de notificação por push  <br/> |O número atual de assinaturas de notificação por push. Esse número, em conjunto com a Contagem atual de sessão ativa, representa o subconjunto de sessões atualmente ativas registradas para dispositivos Windows Mobile ou iPhone.  <br/> |
|Contagem de polls de tempo limite de rede ativos no momento  <br/> |O número de pools de rede que ultrapassaram o tempo limite  <br/> |
|Contagem de pools ativos no momento  <br/> |O número de polls atualmente ativos (conexões de longa duração com o servidor)  <br/> |
|Contagem de sessão ativa no momento  <br/> |Número atual de pontos de extremidade registrados no Serviço de Mobilidade  <br/> |
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
|Total de solicitações bem-sucedidas  <br/> |O número total de solicitações feitas ao Serviço de Mobilidade que tiveram êxito  <br/> |
|Contagem total de sessões iniciadas  <br/> |O número total de sessões iniciadas desde a inicialização do Serviço de Mobilidade  <br/> |
|Total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |O número total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |
|Total de chamadas de voz de entrada bem-sucedidas  <br/> |O número total de chamadas de voz de entrada que tiveram êxito  <br/> |
|Total de chamadas de voz de saída bem-sucedidas  <br/> |O número total de chamadas de voz de saída que tiveram êxito  <br/> |
   
> [!NOTE]
> O suporte a MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes móveis atuais do Skype for Business já usam o Unified Communications Web API (UCWA) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herddos usando MCX precisarão atualizar para um cliente atual.
