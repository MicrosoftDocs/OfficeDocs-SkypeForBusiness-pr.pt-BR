---
title: Plano para alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 'Resumo: Leia este tópico para saber como planejar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.'
ms.openlocfilehash: 08b025b09acc4b4db5f26ae67761412a96c0339c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815739"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Plano para alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015
 
**Resumo:** Leia este tópico para saber como planejar a alta disponibilidade e a recuperação de desastres para o servidor de chat persistente no Skype for Business Server 2015.
  
A alta disponibilidade e a recuperação de desastres para servidor de chat persistente exigem recursos adicionais além do que normalmente é necessário para operação completa. 
  
> [!NOTE]
> O uso de Grupos de Disponibilidade AlwaysOn do SQL não tem suporte com bancos de dados de Servidor de Chat Persistente. 

> [!NOTE] 
> O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [introdução à atualização do Microsoft Teams](/microsoftteams/upgrade-start-here). Se você precisar usar chats persistentes, suas opções serão migrar os usuários que exigem essa funcionalidade para o Microsoft Teams ou para continuar usando o Skype for Business Server 2015. 
  
## <a name="resource-requirements"></a>Requisitos de recursos

Antes de configurar o servidor de chat persistente para alta disponibilidade e recuperação de desastres, certifique-se de ter os seguintes recursos adicionais. 
  
- Uma instância de banco de dados dedicada localizada no mesmo Data Center físico no qual o front-end de página inicial do serviço de servidor de chat persistente está localizado. Esse banco de dados funcionará como o espelho do SQL Server para o banco de dados de chat persistente principal. Opcionalmente, designe um SQL Server adicional para atuar como a testemunha de espelhamento se desejar um failover automatizado para o banco de dados espelho.
    
- Uma instância de banco de dados dedicada localizada no outro data center físico. Este banco de dados funcionará como o banco de dados secundário de envio de logs do SQL Server para o banco de dados no centro de dados principal.
    
- Uma instância de banco de dados dedicada para servir como o espelho do SQL Server para o banco de dados secundário. Opcionalmente, designe um SQL Server adicional para o servidor como testemunha de espelhamento. Ambos devem estar localizados no mesmo data center físico que o banco de dados secundário.
    
- Se a conformidade com o servidor de chat persistente estiver habilitada, serão necessárias outras três instâncias de banco de dados dedicados. Sua distribuição é a mesma que a que foi descrita anteriormente para o banco de dados de chat persistente. Embora seja possível que o banco de dados de conformidade compartilhe a mesma instância do SQL Server que o banco de dados de chat persistente, instâncias autônomas para alta disponibilidade e recuperação de desastres são recomendadas.
    
- Um compartilhamento de arquivos deve ser criado e designado para os logs de transação de envio de logs do SQL Server. Todos os SQL Servers nos dois data centers que executam bancos de dados de chat persistente devem ter acesso de leitura/gravação a este compartilhamento de arquivos. Esse compartilhamento não está definido como parte de uma função FileStore.
    
- Um compartilhamento de arquivo no servidor de banco de dados secundário para atuar como a pasta de destino dos logs de transação do SQL Server que são copiados do compartilhamento de arquivos do servidor primário.
    
## <a name="disaster-recovery-and-high-availability-solutions"></a>Soluções de recuperação de desastre e alta disponibilidade

O Skype for Business Server oferece suporte a vários modos de alta disponibilidade para seus servidores back-end, incluindo o espelhamento de banco de dados. Para obter mais informações, veja [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md). 
  
A solução de recuperação de desastres para servidor de chat persistente descrito neste tópico foi criada em um pool de servidores de chat persistentes ampliados. Não há requisitos para uma VLAN (rede local virtual) ampliada. Ao esticar um pool de servidores de chat persistente, você configura um pool na topologia logicamente, mas coloca fisicamente os servidores no pool em dois data centers diferentes. Configure o espelhamento do SQL Server para o banco de dados do mesmo modo e implante o banco de dados e o espelho no mesmo data center. Você deve configurar um banco de dados de backup no data center secundário (com um espelho opcional para fornecer alta disponibilidade durante a recuperação de desastre). Esse é o banco de dados de backup usado para failover durante a recuperação de desastre. 
  
Para obter detalhes sobre como configurar a alta disponibilidade e a recuperação de desastre para o servidor de chat persistente, consulte [Configurar alta disponibilidade e recuperação de desastres para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md). 
  
As figuras a seguir mostram como o pool de servidores de chat persistente pode ser configurado em duas topologias de pool ampliadas diferentes:
  
- Pool de servidores de chat persistentes ampliados quando os data centers estão localizados geográficos com alta largura de banda/baixa latência.
    
- Pool de servidores de chat persistentes ampliados quando os centros de dados estiverem localizados na região de baixa largura de banda/alta latência.
    
A Figura 1 mostra uma topologia de pool de servidores de chat persistente ampliada em que os data centers são localizados geográficos com alta largura de banda/baixa latência. Assuma o seguinte para as topologias lógicas e físicas:
  
- A topologia lógica consiste em:
    
  - Um pool de Chat Persistente nos Sites 1 e 2 contendo servidores 1 a 8.
    
  - Um pool de servidores front-end, um banco de dados de chat persistente, um banco de dados espelhado e, opcionalmente, um banco de dados testemunha (não mostrado no diagrama) residindo fisicamente no site 1. 
    
  - Um segundo pool de Servidores Front-End e um banco de dados de backup residindo fisicamente no Site 2.
    
- A topologia física consiste nos locais 1 e 2, da seguinte maneira:
    
  - Um pool de Chat Persistente, contendo servidores 1 a 4, dois ativos e dois ociosos no Site 1.
    
  - Um pool de Chat Persistente, contendo servidores 5 a 8, dois ativos e dois ociosos no Site 2.
    
  - Um pool de servidores front-end, um banco de dados de chat persistente, um banco de dados espelhado e, opcionalmente, um banco de dados testemunha (não mostrado no diagrama) no site 1.
    
  - Um pool de Servidores Front-End e um banco de dados de backup, que é o destino do envio de logs do SQL, no Site 2.
    
**Pool de servidor de chat persistente ampliado quando os data centers estão localizados geograficamente com alta largura de banda/baixa latência.**

![Chat persistente pool ampliado com largura de banda alta/baixa latência](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
A Figura 2 mostra uma topologia de pool de servidores de chat persistente ampliada em que os data centers são localizados geográficos com largura de banda baixa/alta latência.
  
- A topologia lógica consiste em:
    
  - Um pool de Chat Persistente nos Sites 1 e 2 contendo servidores 1 a 8.
    
  - Um pool de servidores front-end, um banco de dados de chat persistente, um banco de dados espelhado e, opcionalmente, um banco de dados testemunha (não mostrado no diagrama) residindo fisicamente no site 1. 
    
  - Um segundo pool de Servidores Front-End e um banco de dados de backup residindo fisicamente no Site 2.
    
- A topologia física consiste nos locais 1 e 2, da seguinte maneira:
    
  - Um pool de Chat Persistente, contendo servidores 1 a 4, todos ativos, no Site 1.
    
  - Um pool de Chat Persistente, contendo servidores 5 a 8, todos ociosos, no Site 2.
    
  - Um pool de servidores front-end, um banco de dados de chat persistente, um banco de dados espelhado e, opcionalmente, um banco de dados testemunha (não mostrado no diagrama) no site 1.
    
  - Um pool de Servidores Front-End e um banco de dados de backup, que é o destino do envio de logs do SQL, no Site 2.
    
**Pool de servidor de chat persistente ampliado quando os data centers estão localizados geograficamente com baixa largura de banda/alta latência.**

![Chat persistente pool ampliado com largura de banda baixa/alta latência](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

