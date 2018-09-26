---
title: Migrando servidores de arquivamento e monitoramento
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se você implantou o servidor de arquivamento e Monitoring Server no seu ambiente herdado, você pode implantar esses servidores no seu Skype para ambiente de negócios Server 2019 após migrar seus pools de Front-End. Se a funcionalidade de monitoramento e arquivamento são essenciais para sua organização, no entanto, você deve adicionar arquivamento e monitoramento para seu Skype para o pool piloto Business Server 2019 antes de migrar para que a funcionalidade está disponível durante o processo de migração.
ms.openlocfilehash: cd6e3bf7ef04ca7906b707a30211d0c22d22d837
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028751"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

Se você implantou o servidor de arquivamento e Monitoring Server no seu ambiente herdado, você pode implantar esses servidores no seu Skype para ambiente de negócios Server 2019 após migrar seus pools de Front-End. Se a funcionalidade de monitoramento e arquivamento são essenciais para sua organização, no entanto, você deve adicionar arquivamento e monitoramento para seu Skype para o pool piloto Business Server 2019 antes de migrar para que a funcionalidade está disponível durante o processo de migração. 
  
Se você deseja as funcionalidades de arquivamento e monitoração durante o processo de migração, lembre-se das considerações a seguir:
  
- Dados de arquivamento e monitoramento de dados não são movidas para o Skype para implantação Business Server 2019. Os dados de que backup antes de encerrar o ambiente Herdado será seu histórico de atividade no ambiente herdado.
    
- A versão herdada do servidor de arquivamento e Monitoring Server pode ser associada somente um pool de Front-End herdado. No Skype para Business Server 2019, arquivamento e monitoramento não são mais funções de servidor, mas serviços integrados do Skype para pool de negócios 2019 Front-End Server.
    
- Durante o tempo que seu herdado e Skype para implantações de negócios Server 2019 coexistir, a versão herdada do servidor de arquivamento e Monitoring Server colete dados para usuários hospedados em pools herdados. Arquivamento e monitoramento no Skype para Business Server 2019 coletam dados para usuários hospedagem no Skype para Business Server 2019 pools.
    
    > [!NOTE]
    > Durante a fase de migração quando você estiver ainda usando seu servidor de borda herdado com o novo Skype para o servidor de negócios 2019 continua do pool piloto, a versão herdada do servidor de arquivamento para coletar dados para usuários hospedado em pools herdados e arquivamento no Skype para negócios Servidor 2019 reúne dados para usuários hospedagem no Skype para Business Server 2019 pools. 
  
- Se você usar um terceiro de arquivamento e monitoramento de solução em conjunto com o arquivamento e monitoramento no Skype para Business Server 2019, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com Skype para Business Server 2019.
    

