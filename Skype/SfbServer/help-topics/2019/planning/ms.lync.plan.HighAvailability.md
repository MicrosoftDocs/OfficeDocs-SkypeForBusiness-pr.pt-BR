---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
ROBOTS: NOINDEX, NOFOLLOW
description: O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor via pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
ms.openlocfilehash: 2a3327bcf5b17df7bc6eb4880a9966764786560d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281584"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
O principal esquema de alta disponibilidade para a maioria das funções de servidor no Skype for Business Server baseia-se na redundância do servidor via pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
  
O Skype for Business Server exige pelo menos dois servidores front end para permitir alta disponibilidade. A ferramenta de planejamento usará os seguintes critérios para determinar se ele adicionará servidores extras para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais servidores front-end, a ferramenta de planejamento não adicionará um servidor extra.
    
- Se a implantação contiver o servidor de borda, um servidor adicional será adicionado. 
    
- Se a implantação contiver chats persistentes, a ferramenta de planejamento adicionará um servidor extra, mas não aumentará o número do pool. Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir a adição de um servidor adicional (para um total de cinco servidores), mas manterá um único pool. 

    > [!NOTE] 
    > O chat persistente está disponível no Skype for Business Server 2015, mas não é mais compatível com o Skype for Business Server 2019. A mesma funcionalidade está disponível no Microsoft Teams. Para obter mais informações, consulte [atualização do Skype for Business para o Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/journey-skypeforbusiness-teams). Se você precisar usar chats persistentes, suas opções serão migrar usuários que exigem essa funcionalidade para o Microsoft Teams ou continuar usando o Skype for Business Server 2015. 

    
A ferramenta de planejamento também adiciona um banco de dados espelho do SQL a todos os bancos de dados. Por exemplo, se houver um banco de dados de front-end do SQL Server, a ferramenta de planejamento adicionará o outro banco de dados como o banco de dados espelho para este e o nomeará como o banco de dados do SQL espelho do front-end.
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [planejar a alta disponibilidade e a recuperação de desastres no Skype for Business Server](../../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

