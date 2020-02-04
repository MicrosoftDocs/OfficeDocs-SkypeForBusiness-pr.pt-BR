---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server 2015 baseia-se na redundância do servidor via pooling. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
ms.openlocfilehash: 53b98b72c70fcb624ab59fc7bfc3fbffadbd231a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696286"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server 2015 baseia-se na redundância do servidor via pooling. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
  
O Skype for Business Server 2015 exige pelo menos dois servidores front end para permitir alta disponibilidade. A ferramenta de planejamento usará os seguintes critérios para determinar se ele adicionará servidores extras para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais servidores front-end, a ferramenta de planejamento não adicionará um servidor extra.
    
- Se a implantação contiver o servidor de borda, um servidor adicional será adicionado. 
    
- Se a implantação contiver chats persistentes, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool. Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir a adição de um servidor adicional (para um total de cinco servidores), mas manterá um único pool. 
    
A ferramenta de planejamento também adiciona um banco de dados espelho do SQL a todos os bancos de dados. Por exemplo, se houver um banco de dados de front-end do SQL Server, a ferramenta de planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o nomeará como o banco de dados do SQL espelho do front-end.
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

