---
title: Processo de migração
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
description: O procedimento de migração recomendado e suportado para Skype for Business Server 2019 é a migração lado a lado. Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.
ms.openlocfilehash: e1d89dc2081918d87f73cd3c6908fff0c388e6700d00af6dcd72161a2ccc9ece
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303405"
---
# <a name="migration-process"></a>Processo de migração

O procedimento de migração recomendado e suportado para Skype for Business Server 2019 é a migração lado a lado. Este tópico descreve porquê você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.
  
## <a name="side-by-side-migration"></a>Migração lado a lado

Em praticamente cada migração, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, você implanta um novo servidor com o Skype for Business Server 2019 juntamente com um servidor correspondente que está executando uma versão anterior e transfere operações para o novo servidor. Se for necessário reverter para a versão anterior, você só terá que mudar as operações de volta para os servidores originais. Lembre-se de que nessa situação, quaisquer novas reuniões agendadas com os clientes atualizados não funcionarão e também seria necessário fazer o downgrade dos clientes.
  
## <a name="coexistence-testing"></a>Teste de coexistência

Depois de ter implantado o Skype for Business Server 2019 em paralelo com a versão anterior, a implantação representa um estado de teste de coexistência do Skype for Business Server 2019 e da versão anterior. Durante este estado, é importante testar e garantir que os serviços estejam iniciados, que cada site possa ser administrado e que os clientes possam se comunicar com usuários atuais e herdados. Antes da migração de todos os usuários, é muito importante entender o estado de cada implantação e garantir que cada uma delas esteja funcional e funcionando adequadamente. Normalmente, a fase de teste de coexistência existe durante o teste piloto do Skype for Business Server 2019. Os usuários herdados são movidos para o Skype for Business Server 2019 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estão funcionando corretamente. Após o teste piloto, os usuários e aplicativos são movidos para a versão de produção do Skype for Business Server 2019, e os pools e aplicativos herdado da versão anterior são retirados.
  
