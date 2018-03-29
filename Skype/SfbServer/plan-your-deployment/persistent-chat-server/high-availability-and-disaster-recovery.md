---
title: Plano para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Resumo: Leia este tópico para saber como planejar para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype Business Server 2015.'
ms.openlocfilehash: 2730d72b47d02772bf2c5c59c819bbe23e8816db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plano para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar para alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype Business Server 2015.
  
Alta disponibilidade e recuperação de desastres para o servidor de Chat persistente exigem recursos adicionais além normalmente, o que é necessário para a operação completa. 
  
> [!NOTE]
> O uso de Grupos de Disponibilidade AlwaysOn do SQL não tem suporte com bancos de dados de Servidor de Chat Persistente. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar o servidor de Chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de que você tenha os seguintes recursos adicionais. 
  
- Uma instância de banco de dados dedicado, localizada no mesmo físico do data center no qual a página inicial do front-end do serviço servidor de Chat persistente está localizado. Esse banco de dados servirá como o espelho do SQL Server para o banco de dados primário do Chat persistente. Opcionalmente, designe um servidor adicional do SQL para servir como testemunha de espelhamento, se quiser failover automático no banco de dados de espelho.
    
- Uma instância de banco de dados dedicada localizada no outro data center físico. Esse banco de dados servirá como o envio de Log do SQL Server banco de dados secundário para o banco de dados no data center principal.
    
- Uma instância de banco de dados dedicado para servir como o espelho do SQL Server para o banco de dados secundário. Opcionalmente, designe um servidor adicional do SQL para servidor como a testemunha de espelhamento. Ambos devem estar localizados no mesmo data center físico que o banco de dados secundário.
    
- Se a conformidade do servidor de Chat persistente estiver habilitada, uma três instâncias de banco de dados dedicado adicionais são necessários. Sua distribuição é os mesmos descritas anteriormente para o banco de dados de Chat persistente. Embora seja possível para o banco de dados de conformidade compartilhar a mesma instância do SQL Server que o banco de dados de Chat persistente, instâncias autônomo para alta disponibilidade e recuperação de desastres são recomendadas.
    
- Um compartilhamento de arquivo deve ser criado e designado para os logs de transação do envio de Log do SQL Server. Todos os SQL Servers em ambos os data centers que executam o Chat persistente bancos de dados deve ter acesso de leitura/gravação para esse compartilhamento de arquivos. Esse compartilhamento não está definido como parte de uma função FileStore.
    
- Um compartilhamento de arquivo no servidor de banco de dados secundário para servir como a pasta de destino para os logs de transações do SQL Server que são copiados do compartilhamento de arquivo do servidor primário.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluções de recuperação de desastre e alta disponibilidade

Skype para Business Server suporta vários modos de alta disponibilidade para seus servidores Back-End, incluindo o espelhamento de banco de dados. Para obter mais informações, consulte o [plano de alta disponibilidade e recuperação de desastres em Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
A solução de recuperação de desastres para o servidor de Chat persistente descrito neste tópico baseia-se em um pool do servidor de Chat persistente ampliado. Não há requisitos para uma VLAN (rede local virtual) ampliada. Por alongamento um pool do servidor de Chat persistente, você configurar um pool na topologia logicamente, mas você coloque os servidores fisicamente no pool em dois diferentes de data centers. Configure o espelhamento do SQL Server para o banco de dados do mesmo modo e implante o banco de dados e o espelho no mesmo data center. Você deve configurar um banco de dados de backup no data center secundário (com um espelho opcional para fornecer alta disponibilidade durante a recuperação de desastre). Esse é o banco de dados de backup usado para failover durante a recuperação de desastre. 
  
Para obter detalhes sobre como configurar a alta disponibilidade e recuperação de desastres para o servidor de Chat persistente, consulte [Configure alta disponibilidade e recuperação de desastres para o servidor de Chat persistente no Skype para Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
As ilustrações a seguintes mostram como o pool do servidor de Chat persistente pode ser configurado em duas topologias de pool ampliadas diferentes:
  
- Pool de servidor de Chat persistente ampliado quando os data centers estão Geo-localizados com alta largura de banda/baixa latência.
    
- Pool de servidor de Chat persistente ampliado quando os data centers estão Geo-localizados com baixa largura de banda/alta latência.
    
A Figura 1 mostra uma topologia ampliada do pool de servidor de Chat persistente onde os data centers estão Geo-localizados com alta largura de banda/baixa latência. Considere as seguintes informações sobre as topologias físicas e lógicas:
  
- A topologia lógica consiste em:
    
  - Um pool de Chat Persistente nos Sites 1 e 2 contendo servidores 1 a 8.
    
  - Um pool de servidor Front-End, um banco de dados de Chat persistente, um banco de dados espelhado, e, opcionalmente, um banco de dados de testemunha (não é mostrado no diagrama) fisicamente residindo no Site 1. 
    
  - Um segundo pool de Servidores Front-End e um banco de dados de backup residindo fisicamente no Site 2.
    
- A topologia física consiste Sites 1 e 2 da seguinte maneira:
    
  - Um pool de Chat Persistente, contendo servidores 1 a 4, dois ativos e dois ociosos no Site 1.
    
  - Um pool de Chat Persistente, contendo servidores 5 a 8, dois ativos e dois ociosos no Site 2.
    
  - Um pool de servidor Front-End, um banco de dados de Chat persistente, um banco de dados espelhado e, opcionalmente, um testemunha banco de dados (não é mostrado no diagrama) no Site 1.
    
  - Um pool de Servidores Front-End e um banco de dados de backup, que é o destino do envio de logs do SQL, no Site 2.
    
**Pool de servidor de Chat persistente ampliado quando os data centers estão Geo-localizados com alta largura de banda/baixa latência**

![Pool Estendido de Chat Persistente com alta largura de banda/baixa latência](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
Figura 2 mostra uma topologia ampliada do pool de servidor de Chat persistente onde os data centers estão Geo-localizados com baixa largura de banda/alta latência.
  
- A topologia lógica consiste em:
    
  - Um pool de Chat Persistente nos Sites 1 e 2 contendo servidores 1 a 8.
    
  - Um pool de servidor Front-End, um banco de dados de Chat persistente, um banco de dados espelhado, e, opcionalmente, um banco de dados de testemunha (não é mostrado no diagrama) fisicamente residindo no Site 1. 
    
  - Um segundo pool de Servidores Front-End e um banco de dados de backup residindo fisicamente no Site 2.
    
- A topologia física consiste Sites 1 e 2 da seguinte maneira:
    
  - Um pool de Chat Persistente, contendo servidores 1 a 4, todos ativos, no Site 1.
    
  - Um pool de Chat Persistente, contendo servidores 5 a 8, todos ociosos, no Site 2.
    
  - Um pool de servidor Front-End, um banco de dados de Chat persistente, um banco de dados espelhado e, opcionalmente, um testemunha banco de dados (não é mostrado no diagrama) no Site 1.
    
  - Um pool de Servidores Front-End e um banco de dados de backup, que é o destino do envio de logs do SQL, no Site 2.
    
**Pool de servidor de Chat persistente ampliado quando os data centers estão Geo-localizados com baixa largura de banda/alta latência**

![Pool Estendido de Chat Persistente com baixa largura de banda/alta latência](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

