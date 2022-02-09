---
title: Alta disponibilidade (Ferramenta de Planejamento)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor Skype for Business Server se baseia na redundância do servidor por meio do pool. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
ms.openlocfilehash: 0d19099e156b5c67bb443cb0ca81566d3771e465
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411224"
---
# <a name="high-availability-planning-tool"></a>Alta disponibilidade (Ferramenta de Planejamento)
 
O principal esquema de alta disponibilidade para a maioria das funções de servidor Skype for Business Server se baseia na redundância do servidor por meio do pool. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
  
Skype for Business Server requer pelo menos dois Servidores Front-End para habilitar a alta disponibilidade. A Ferramenta de Planejamento usa os critérios a seguir para determinar se adicionará servidores extras para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais Servidores Front-End, a Ferramenta de Planejamento não adicionará um servidor extra.
    
- Se a implantação contiver o Servidor de Borda, um servidor adicional será adicionado. 
    
- Se a implantação contiver Chat Persistente, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool. Por exemplo, se a implantação já contiver quatro servidores, a Ferramenta de Planejamento sugerirá adicionar um servidor adicional (para um total de cinco servidores), mas manterá um único pool. 

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, [consulte Skype for Business para Microsoft Teams atualização](/MicrosoftTeams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

    
A Ferramenta de Planejamento também adiciona um banco de dados SQL espelho para todos os bancos de dados. Por exemplo, se houver um banco de dados de SQL Server front-end, a Ferramenta de Planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o nomeará como o "banco de dados de espelho de front-end SQL.
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Plan for high availability and disaster recovery in Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
