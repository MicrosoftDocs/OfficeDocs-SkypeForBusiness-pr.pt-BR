---
title: Contadores de desempenho de mobilidade Skype for Business Server
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
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 'Resumo: saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores executando a UCWA (Unified Communications Web API) e o serviço de mobilidade Skype for Business Server Mcx.'
ms.openlocfilehash: e89ffdb590a7028bd1fa9a9594b6ba0bcce9be11
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60827574"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Contadores de desempenho de mobilidade Skype for Business Server
 
**Resumo:** Saiba mais sobre os contadores de desempenho que você pode usar para monitorar servidores executando a UCWA (Unified Communications Web API) e o serviço de mobilidade Skype for Business Server Mcx.
  
As tabelas a seguir listam os nomes e descrições dos contadores de desempenho que você pode usar para monitorar servidores executando a UCWA (Unified Communications Web API) e o serviço de mobilidade Skype for Business Server Mcx. 
  
O nome da categoria para os contadores na tabela UCWA é **LS:WEB - UCWA**.
  
O nome da categoria para os contadores na tabela Mcx Mobility Service é **LS:WEB - Serviço de Comunicação Móvel**.

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
## <a name="performance-counters-for-ucwa"></a>Contadores de desempenho para UCWA

|Contador|Descrição|
|:-----|:-----|
|Contagem ativa de aplicativos  <br/> |O número atual de aplicativos  <br/> |
|Contagem de modalidades de compartilhamento de aplicativos ativos  <br/> |O número atual da modalidade de Compartilhamento de Aplicativos  <br/> |
|Contagem de modalidades de áudio ativas  <br/> |O número atual da modalidade Audio  <br/> |
|Contagem de Modalidades de Colaboração de Dados Ativos  <br/> |O número atual de modalidade de Colaboração de Dados  <br/> |
|Fotos do Active Directory Obter Latência (ms)  <br/> |Este contador mostra o tempo médio (em milissegundos) para recuperar uma foto do active directory  <br/> |
|Contagem de Modalidades de Mensagens Ativas  <br/> |O número atual da modalidade Messaging  <br/> |
|Contagem ativa de modalidade de vídeo panorâmico  <br/> |O número atual da modalidade vídeo panorâmico  <br/> |
|Active Pending Get Count  <br/> |O número de obtém pendentes atualmente ativos; conexões de longa duração com o servidor  <br/> |
|Contagem ativa de sessão  <br/> |O número atual de pontos de extremidade registrados no UCWA por aplicativo e total  <br/> |
|Contagem de instâncias do usuário ativo  <br/> |O número atual de instâncias do usuário  <br/> |
|Instâncias de usuário ativas sem aplicativo  <br/> |O número atual de instâncias do usuário sem aplicativo  <br/> |
|Contagem de modalidades de vídeo ativas  <br/> |O número atual da modalidade Video  <br/> |
|Solicitações de criação de aplicativo recebidas/segundo  <br/> |A taxa por segundo de solicitações de criação de aplicativo recebidas  <br/> |
|AS MCU Join Failures  <br/> |O número de falhas de junção do AS MCU  <br/> |
|Falhas de junção do AV MCU  <br/> |O número de falhas de junção do AV MCU  <br/> |
|Tempo médio de inicialização do aplicativo (ms)  <br/> |O tempo médio de inicialização do aplicativo em Milissegundos  <br/> |
|Tempo médio de vida da sessão (ms)  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Falhas de junção de MCU de dados  <br/> |O número de falhas de junção de mcu de dados  <br/> |
|Exchange Latência de Pesquisa de Contato (ms)  <br/> |Este contador mostra o tempo médio (em milissegundos) para pesquisar contato no Exchange  <br/> |
|Exchange Hd Photo Get Latency (ms)  <br/> |Esse contador mostra o tempo médio (em milissegundos) para recuperar uma foto do Exchange  <br/> |
|Respostas HTTP 4xx/Segundo  <br/> |A taxa por segundo de respostas com código HTTP 4xx  <br/> |
|Respostas HTTP 5xx/Segundo  <br/> |A taxa por segundo de respostas com código HTTP 5xx  <br/> |
|Falhas de junção do MCU de IM  <br/> |O número de falhas de junção de IM MCU  <br/> |
|Número de falhas de foto do Active Directory  <br/> |O número total de falhas para recuperar fotos do Active Directory  <br/> |
|Número de falhas na Pesquisa de Contatos  <br/> |O número total de falhas para pesquisar contatos em Exchange  <br/> |
|Número de falhas de desserialização  <br/> |O número total de falhas de desserialização  <br/> |
|Número de falhas de hd photo get  <br/> |O número total de falhas para recuperar fotos HD de Exchange  <br/> |
|Sobre o máximo de assinaturas por aplicativo  <br/> |O número de solicitações de assinatura acima do máximo permitido por aplicativo  <br/> |
|Sobre o máximo de assinaturas por lote  <br/> |O número de solicitações de assinatura acima do máximo permitido por lote  <br/> |
|Falhas de assinatura de presença  <br/> |O número de falhas para assinar presença  <br/> |
|Registrando falhas de ponto de extremidade  <br/> |O número de falhas para registrar pontos de extremidade  <br/> |
|Solicitações recebidas/segundo  <br/> |A taxa de solicitações recebidas por segundo  <br/> |
|Solicitações bem-sucedidas/segundo  <br/> |A taxa por segundo de solicitações bem-sucedidas (códigos de resposta HTTP 2xx/3xx)  <br/> |
|Criar solicitações de aplicativo com êxito/segundo  <br/> |A taxa por segundo de solicitações de criação de aplicativos bem-sucedidas  <br/> |
|Contagem de tempo de espera pendente  <br/> |O número de pendentes obtém esse tempo de espera  <br/> |
|Total de solicitações de criação de aplicativo recebidas  <br/> |O número total de solicitações de criação de aplicativo recebidas desde que o serviço foi iniciado  <br/> |
|Total de respostas HTTP 4xx  <br/> |O número total de respostas HTTP 4xxx  <br/> |
|Total de respostas HTTP 5xx  <br/> |O número total de respostas HTTP 5xxx  <br/> |
|Total de Solicitações Recebidas no Canal de Comando  <br/> |O número total de solicitações recebidas no canal do comando  <br/> |
|Total de solicitações bem-sucedidas  <br/> |O número total de solicitações que foram bem-sucedidas  <br/> |
|Total de sessões iniciadas  <br/> |O número total de sessões iniciadas desde que o serviço foi iniciado  <br/> |
|Total de sessões encerradas devido ao tempo de ocioso  <br/> |O número total de sessões encerradas devido ao tempo limite de usuário ocioso  <br/> |
|Total de aplicativos com aceleração  <br/> |O número de aplicativos com aceleração  <br/> |
   
**Contadores de desempenho do Mcx Mobility Service**

|**Contador**|**Descrição**|
|:-----|:-----|
|Tempo média de vida de uma sessão em milissegundos  <br/> |O tempo médio de vida de uma sessão em milissegundos  <br/> |
|Assinaturas atuais de notificação por push  <br/> |O número atual de assinaturas de notificação por push. Esse número, em conjunto com a Contagem de Sessão Ativa No Momento, representa o subconjunto de sessões ativas atualmente registradas para dispositivos Windows Mobile ou iPhone.  <br/> |
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
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
