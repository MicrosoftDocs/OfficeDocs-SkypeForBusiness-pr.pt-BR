---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 4/8/2016
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server 2015 baseia-se na redundância de servidor via pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
ms.openlocfilehash: b50ccf145f1197531fe91218d2e99c8b0739c15c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834741"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server 2015 baseia-se na redundância de servidor via pooling. Se um servidor executando uma certa função de servidor falha, os ouros servidores no pool executando a mesma função assumem a carga daquele servidor.
  
O Skype for Business Server 2015 requer pelo menos dois Servidores Front End para habilitar a alta disponibilidade. A Ferramenta de Planejamento usa os seguintes critérios para determinar se adicionará servidores extras para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais Servidores Front-End, a Ferramenta de Planejamento não adicionará um servidor adicional.
    
- Se a implantação contiver Servidor de Borda, um servidor adicional será adicionado. 
    
- Se a implantação contiver Chat Persistente, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool. Por exemplo, se a implantação já contiver quatro servidores, a Ferramenta de Planejamento sugerirá a adição de um servidor adicional (para um total de cinco servidores), mas manterá um único pool. 
    
A Ferramenta de Planejamento também adiciona um banco de dados SQL espelho para todos os bancos de dados. Por exemplo, se houver um banco de dados do SQL Server front-end, a Ferramenta de Planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o chamará de "Banco de dados SQL espelho front-end."
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Plan for high availability and disaster recovery in Skype for Business Server 2015.](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)
  

