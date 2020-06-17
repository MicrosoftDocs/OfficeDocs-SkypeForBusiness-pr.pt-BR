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
description: Se você implantou o servidor de arquivamento e o Monitoring Server no seu ambiente herdado, pode implantar esses servidores no seu ambiente do Skype for Business Server 2019 após migrar seus pools de front-end. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.
ms.openlocfilehash: 595c92e23b0872571f75c140f86b5c437c7d8129
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752663"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

Se você implantou o servidor de arquivamento e o Monitoring Server no seu ambiente herdado, pode implantar esses servidores no seu ambiente do Skype for Business Server 2019 após migrar seus pools de front-end. No entanto, se a funcionalidade de arquivamento e monitoramento for crítica para sua organização, você deverá adicionar arquivamento e monitoramento ao seu pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração. 
  
Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:
  
- Os dados de arquivamento e de monitoramento não são movidos para a implantação do Skype for Business Server 2019. Os dados que você fez backup antes de encerrar o ambiente herdado serão seu histórico de atividades no ambiente herdado.
    
- A versão herdada do servidor de arquivamento e do Monitoring Server só pode ser associada a um pool de front-ends herdado. No Skype for Business Server 2019, o arquivamento e o monitoramento não são mais funções de servidor, mas os serviços integrados ao pool de front-ends do Skype for Business Server 2019.
    
- Durante o tempo em que suas implantações herdadas do Skype for Business Server 2019 coexistem, a versão herdada do servidor de arquivamento e do Monitoring Server coleta dados para usuários hospedados em pools herdados. Arquivamento e monitoramento no Skype for Business Server 2019 coletar dados para usuários hospedados no Skype for Business Server 2019 pools.
    
    > [!NOTE]
    > Durante a fase de migração quando você ainda estiver usando seu servidor de borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do servidor de arquivamento continua a coletar dados para usuários hospedados em pools herdados e arquivamento no Skype for Business Server 2019 coleta dados para usuários hospedados no Skype for Business Server 2019 pools. 
  
- Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o arquivamento e o monitoramento no Skype for Business Server 2019, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.
    

