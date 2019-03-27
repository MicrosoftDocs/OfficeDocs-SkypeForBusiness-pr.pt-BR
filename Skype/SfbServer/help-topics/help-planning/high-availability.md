---
title: High Availability (Planning Tool)
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/8/2016
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.plan.HighAvailability
- ms.lync.plan.HighAvailability
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14a897b3-2406-46c7-b08f-490085b3d048
description: O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server 2015 se baseia em redundância de servidor por meio do pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
ms.openlocfilehash: 50cc5f371e4964555aae2a7f50ce3d1431f4f10c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874022"
---
# <a name="high-availability-planning-tool"></a>High Availability (Planning Tool)
 
O esquema principal de alta disponibilidade para a maioria das funções de servidor em Skype para Business Server 2015 se baseia em redundância de servidor por meio do pool. Se um servidor que estiver executando uma determinada função do servidor falhar, os outros servidores no pool que executam a mesma função assumirão a carga desse servidor.
  
Skype para Business Server 2015 requer pelo menos dois servidores Front-End para habilitar a alta disponibilidade. A ferramenta de planejamento usa os seguintes critérios para determinar se ele adicionará servidores adicionais para dar suporte à alta disponibilidade:
  
- Se a implantação contiver dois ou mais servidores Front-End, a ferramenta de planejamento não adiciona um servidor adicional.
    
- Se a implantação contiver um servidor de borda, um servidor adicional é adicionado. 
    
- Se a implantação contiver Chat persistente, a ferramenta de planejamento irá adicionar um servidor extra, mas não aumentar o número de pool. Por exemplo, se a implantação já contiver quatro servidores, a ferramenta de planejamento irá sugerir adicionando um servidor adicional (para um total de cinco servidores) mas manterá um único pool. 
    
A ferramenta de planejamento também adiciona um banco de dados do SQL de espelho para todos os bancos de dados. Por exemplo, se houver um banco de dados do servidor SQL Front-End, a ferramenta de planejamento irá adicionar outro banco de dados como o banco de dados de espelho para que este e nomeie-o como o "banco de dados SQL de espelho de Front-End.
  
Para obter mais detalhes sobre como preparar seu ambiente para alta disponibilidade, consulte [Planejar a alta disponibilidade e recuperação de desastres em Skype para Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).
  

