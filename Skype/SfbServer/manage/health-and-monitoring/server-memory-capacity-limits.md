---
title: Monitorar os limites de capacidade de memória do servidor Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 1697ea71-6fcf-480d-b4e9-cd79f94d247e
description: 'Resumo: saiba como monitorar os limites de capacidade de memória do servidor Skype for Business Server.'
---

# <a name="monitor-for-server-memory-capacity-limits-in-skype-for-business-server"></a>Monitorar os limites de capacidade de memória do servidor Skype for Business Server
 
**Resumo:** Saiba como monitorar os limites de capacidade de memória do servidor Skype for Business Server.
  
> [!CAUTION]
> As informações neste tópico que se referem ao Planejamento de Capacidade pertencem apenas aos clientes do Lync 2010 Mobile e ao Serviço de Mobilidade (Mcx). O Planejamento de Capacidade para a UCWA (Unified Communications Web API), usada pelos clientes do Lync 2013 Mobile, é fornecido pela Ferramenta de Planejamento do Lync Server 2013. 

> [!NOTE]
> O suporte ao MCX (Mobility Service) para clientes móveis herdado não está mais disponível no Skype for Business Server 2019. Todos os clientes Skype for Business móveis atuais já usam a UCWA (Unified Communications Web API) para dar suporte a mensagens instantâneas (IM), presença e contatos. Os usuários com clientes herdamentos usando MCX precisarão atualizar para um cliente atual.
  
Dois contadores de desempenho de mobilidade podem ajudá-lo a determinar seu uso atual e ajudá-lo a planejar a capacidade do Serviço de Mobilidade Skype for Business Server (Mcx), bem como monitorar o uso de memória para o UCWA. Para o UCWA, a categoria de contador **é LS:WEB - UCWA**. Para o Serviço de Mobilidade (Mcx), os contadores estão na categoria **LS:WEB - Serviço de Comunicação Móvel**. Os contadores a monitorar são:
  
- **Contagem de Sessão Ativa com Assinaturas** de Presença Ativa, que é o número atual de pontos de extremidade registrados por meio do UCWA ou do Mobility Service (Mcx) que possuem assinaturas de presença ativa (número de usuários móveis sempre conectados)
    
- **Contagem de sessão ativa no** momento, que é o número atual de pontos de extremidade registrados por meio do UCWA ou do Serviço de Mobilidade
    
Se a diferença entre Contagem de Sessão Ativa atual com **Assinaturas** de Presença Ativa  e Contagem de Sessão Ativa atual for pequena ao longo do tempo, isso significa que a maioria dos usuários de dispositivo móvel tem um dispositivo sempre conectado, como um dispositivo móvel Android ou Nokia (somente para Mcx). Os dispositivos UCWA sempre conectados incluem dispositivos Apple e Android executando clientes do Lync 2013 Mobile). Se a Contagem **de Sessão Ativa** atual for muito maior do que a Contagem de Sessões Atualmente Ativas com **Assinaturas** de Presença Ativa, isso indica que mais usuários estão usando um dispositivo de ponto de extremidade em segundo plano, como um dispositivo apple iOS ou um Windows Phone em Mcx. (Windows Phone é o único cliente Lync 2013 Mobile que se registrará como este).
  
Você deve definir um limite na Contagem de Sessões Atualmente Ativas com **Assinaturas** de Presença  Ativa e contadores de desempenho da Contagem de Sessões Atualmente Ativas com base no uso esperado, nos resultados de planejamento de capacidade e no monitoramento contínuo do Serviço de Mobilidade e de outros contadores do Servidor Front-End. Os limites definidos devem permitir que você avalie a capacidade do servidor e ative alertas quando a capacidade for excedida.
  
Para determinar os limites apropriados, você precisa primeiro determinar quanta memória está disponível no Servidor Front-End para o Serviço de Mobilidade. Monitore os contadores para determinar quando você precisa planejar a capacidade extra, de acordo com a seguinte fórmula:
  
Memória total usada pelo Mcx Mobility Service (MB) = 164 + (400 + 134) / 1024 * Contagem atual de sessão ativa com **assinaturas** de presença ativa + 400 / 1024 *** (** -  Contagem atual de sessão ativa contagem simultânea de sessão com **assinaturas** de presença ativa)
  
> [!IMPORTANT]
> A Calculadora de Capacidade do Microsoft Lync Server 2010 é uma planilha pré-populada com todas as fórmulas que permitem que um planejador determine quais serão os requisitos para os servidores Skype for Business, incluindo CPU, memória e disco rígido. Você pode [baixar a planilha e um documento associado](https://go.microsoft.com/fwlink/p/?LinkID=212657). 
  
O Servidor Front-End precisa de memória disponível suficiente para dar suporte ao Serviço de Mobilidade em situações de failover. Você pode monitorar a memória disponível atual no Servidor Front-End usando o contador **Mbytes Memory\Available** ou usando a equação mencionada anteriormente para planejar a quantidade de memória que você espera que o Serviço de Mobilidade use.
  
Se a quantidade de memória disponível no Servidor Front-End for inferior a 1.500 MB ao planejar o número esperado de usuários de mobilidade, você precisará adicionar mais hardware para dar suporte ao Serviço de Mobilidade. Para obter mais detalhes, [consulte Monitor mobility for performance in Skype for Business Server](monitor-mobility-performance.md) na documentação Operações.
  
## <a name="see-also"></a>Confira também

[Monitorar mobilidade para desempenho em Skype for Business Server](monitor-mobility-performance.md)
