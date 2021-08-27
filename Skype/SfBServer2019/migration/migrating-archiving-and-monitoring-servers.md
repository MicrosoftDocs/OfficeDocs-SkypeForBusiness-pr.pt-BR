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
ms.localizationpriority: medium
description: Se você implantou o Servidor de Arquivamento e o Servidor de Monitoramento em seu ambiente herdado, poderá implantar esses servidores em seu ambiente Skype for Business Server 2019 depois de migrar seus pools de Front-End. Se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, no entanto, você deve adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração.
ms.openlocfilehash: a5b839a1eb7d460a57d6adf36901c50479f203ad
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58596165"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

Se você implantou o Servidor de Arquivamento e o Servidor de Monitoramento em seu ambiente herdado, poderá implantar esses servidores em seu ambiente Skype for Business Server 2019 depois de migrar seus pools de Front-End. Se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, no entanto, você deve adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade seja disponibilizada durante o processo de migração. 
  
Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre das considerações a seguir:
  
- Dados de arquivamento e monitoramento não são movidos para a implantação Skype for Business Server 2019. Os dados que você faz o back-up antes da desativação do ambiente herdável serão seu histórico de atividades no ambiente herdável.
    
- A versão herdada do Servidor de Arquivamento e do Servidor de Monitoramento só pode ser associada a um pool de Front-End herdado. No Skype for Business Server 2019, Arquivamento e Monitoramento não são mais funções de servidor, mas serviços integrados ao pool de front-end Skype for Business Server 2019.
    
- Durante o tempo em que suas implantações herdadas e Skype for Business Server 2019 coexistem, a versão herdada do Servidor de Arquivamento e do Servidor de Monitoramento coleta dados para usuários que estão em pools herdados. O arquivamento e o monitoramento no Skype for Business Server 2019 coletam dados para usuários que estão Skype for Business Server pools 2019.
    
    > [!NOTE]
    > Durante a fase de migração quando você ainda está usando seu servidor de Borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do Servidor de Arquivamento continua a coletar dados para usuários que estão em casa em pools herdados e arquivamento no Skype for Business Server 2019 coleta dados para usuários que estão em casa no Skype for Business Server 2019 pools. 
  
- Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o Arquivamento e Monitoramento no Skype for Business Server 2019, consulte seu fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.
    

