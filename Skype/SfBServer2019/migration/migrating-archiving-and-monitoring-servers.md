---
title: Migrando servidores de arquivamento e monitoramento
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente herdado, poderá implantar esses servidores no ambiente do Skype for Business Server 2019 depois de migrar seus pools front-ends. No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração.
ms.openlocfilehash: 94a3d21b9b76d18f63fdf7db53144b1d51deb53c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298194"
---
# <a name="migrating-archiving-and-monitoring-servers"></a>Migrando servidores de arquivamento e monitoramento

Se você implantou o servidor de arquivamento e monitorando o servidor em seu ambiente herdado, poderá implantar esses servidores no ambiente do Skype for Business Server 2019 depois de migrar seus pools front-ends. No entanto, se a funcionalidade de arquivamento e monitoramento for essencial para sua organização, você deverá adicionar arquivamento e monitoramento ao pool piloto do Skype for Business Server 2019 antes de migrar para que a funcionalidade esteja disponível durante o processo de migração. 
  
Se você quiser a funcionalidade de arquivamento e monitoramento durante o processo de migração, tenha em mente as seguintes considerações:
  
- O arquivamento de dados e monitoramento de dados não são movidos para a implantação do Skype for Business Server 2019. Os dados que você reproduz antes de descomissionar o ambiente herdado serão o seu histórico de atividades no ambiente herdado.
    
- A versão herdada do servidor de arquivamento e do Monitoring Server somente pode ser associada a um pool de front-end herdado. No Skype for Business Server 2019, o arquivamento e o monitoramento não são mais funções do servidor, mas serviços integrados ao pool de front-end do Skype for Business Server 2019.
    
- Durante o tempo em que suas implantações do 2019 e do Skype for Business Server existentes coexistem, a versão herdada do servidor de arquivamento e monitoração coleta dados para os usuários hospedados em pools herdados. O arquivamento e o monitoramento no Skype for Business Server 2019 coletam dados para usuários hospedados no Skype for Business Server 2019 pools.
    
    > [!NOTE]
    > Durante a fase de migração, quando você ainda estiver usando o seu servidor de borda herdado com o novo pool piloto do Skype for Business Server 2019, a versão herdada do servidor de arquivamento continua a coletar dados para os usuários hospedados em pools herdados e arquivamento no Skype for Business O servidor 2019 coleta dados para usuários hospedados no Skype for Business Server 2019 pools. 
  
- Se você usar uma solução de arquivamento e monitoramento de terceiros em conjunto com o arquivamento e o monitoramento no Skype for Business Server 2019, consulte o fornecedor sobre quando e como você precisa integrar a solução de terceiros com o Skype for Business Server 2019.
    

