---
title: Migrando servidores de arquivamento e monitoramento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Se você implantou o Servidor de Arquivamento e o Monitoring Server em seu ambiente herdado, poderá implantar esses servidores em seu ambiente do Skype for Business Server 2019 depois de migrar seus pools de Front-End. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752663"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

Se você implantou o Servidor de Arquivamento e o Monitoring Server em seu ambiente herdado, poderá implantar esses servidores em seu ambiente do Skype for Business Server 2019 depois de migrar seus pools de Front-End. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração. 
  
Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:
  
- Os dados de arquivamento e monitoramento não são movidos para a implantação do Skype for Business Server 2019. Os dados que você faz o back-up antes de descommissionar o ambiente herddo serão seu histórico de atividades no ambiente herddo.
    
- A versão herdada do Servidor de Arquivamento e do Monitoring Server só pode ser associada a um pool de Front-End herdado. No Skype for Business Server 2019, Arquivamento e Monitoramento não são mais funções de servidor, mas serviços integrados ao pool de front-end do Skype for Business Server 2019.
    
- Durante o tempo em que suas implantações herdadas e do Skype for Business Server 2019 coexistiram, a versão herdada do Servidor de Arquivamento e do Monitoring Server coleta dados para usuários que estão em pools herdados. O Arquivamento e Monitoramento no Skype for Business Server 2019 coletam dados para usuários que estão em pools do Skype for Business Server 2019.
    
    > [!NOTE]
    > Durante a fase de migração quando você ainda estiver usando seu servidor de Borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do Servidor de Arquivamento continua a coletar dados para usuários que estão em pools herdados e arquivamento no Skype for Business Server 2019 coleta dados para usuários que estão no Skype for Business Server 2019. 
  
- Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o Arquivamento e Monitoramento no Skype for Business Server 2019, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.
    

