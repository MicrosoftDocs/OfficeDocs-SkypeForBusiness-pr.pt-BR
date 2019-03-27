---
title: Processo de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O procedimento de migração com suporte e recomendados para Skype para Business Server 2019 é migração lado a lado. Este tópico descreve por que você deve usar a migração lado a lado e também inclui informações sobre teste de coexistência.
ms.openlocfilehash: e14226721cbc09bd1f0ac66b47dbd1710712eb17
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876289"
---
# <a name="migration-process"></a>Processo de migração

O procedimento de migração com suporte e recomendados para Skype para Business Server 2019 é migração lado a lado. Este tópico descreve por que você deve usar a migração lado a lado e também inclui informações sobre teste de coexistência.
  
## <a name="side-by-side-migration"></a>Migração lado a lado

Em quase todas as migração, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, você implantar um novo servidor com Skype para Business Server 2019 junto com um servidor correspondente que está executando uma versão anterior e depois transferir operações para o novo servidor. Se for necessário reverter para a versão anterior, você precisará apenas deslocar as operações de volta para os servidores originais. Lembre-se de que essa situação quaisquer novas reuniões agendadas com clientes atualizados não funcionará, e os clientes também precisam ser reduzido.
  
## <a name="coexistence-testing"></a>Teste de coexistência

Depois que você tiver implantado o Skype para Business Server 2019 em paralelo com a versão anterior, a implantação representa uma coexistência testando o estado do Skype para Business Server 2019 e a versão anterior. Enquanto estiver nesse estado, é importante testar e certifique-se de que os serviços foram iniciados, cada site pode ser administrado e clientes podem se comunicar com usuários herdados e atuais. Antes da migração de todos os usuários, é muito importante que você entenda o estado de cada implantação e certifique-se de que cada implantação está funcionando corretamente. Normalmente, a fase de teste de coexistência existe em todo o teste piloto do Skype para Business Server 2019. Usuários herdados são movidos para Skype para Business Server 2019 por um período de tempo para assegurar que compatibilidade de aplicativos e recursos e funções estão funcionando corretamente. Após os testes piloto, usuários e aplicativos são movidos para a versão de produção do Skype para Business Server 2019 e os pools herdados e aplicativos da versão anterior são descartados.
  
