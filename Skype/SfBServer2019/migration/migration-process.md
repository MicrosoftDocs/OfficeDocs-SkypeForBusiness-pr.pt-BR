---
title: Processo de migração
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: O procedimento de migração recomendado e compatível com o Skype for Business Server 2019 é migração lado a lado. Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.
ms.openlocfilehash: 6ef8a70aa436663b7ff88723800375eeef620b6d
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237776"
---
# <a name="migration-process"></a>Processo de migração

O procedimento de migração recomendado e compatível com o Skype for Business Server 2019 é migração lado a lado. Este tópico descreve porque você deve usar a migração lado a lado e também inclui informações sobre testes de coexistência.
  
## <a name="side-by-side-migration"></a>Migração lado a lado

Em quase todas as migrações, você deve usar o caminho de migração lado a lado. Em uma migração lado a lado, implante um novo servidor com o Skype for Business Server 2019 juntamente com um servidor correspondente que esteja executando uma versão anterior e transfira as operações para o novo servidor. Se for necessário reverter para a versão anterior, você só terá que mudar as operações de volta para os servidores originais. Lembre-se de que, nesta situação, todas as novas reuniões agendadas com clientes atualizados não funcionarão, e os clientes também precisariam ser rebaixados.
  
## <a name="coexistence-testing"></a>Teste de coexistência

Após a implantação do Skype for Business Server 2019 paralelamente à versão anterior, a implantação representa um estado de teste de coexistência do Skype for Business Server 2019 e a versão anterior. Nesse estado, é importante testar e garantir que os serviços sejam iniciados, que cada site pode ser administrado, e os clientes podem se comunicar com os usuários atuais e herdados. Antes da migração de todos os usuários, é muito importante que você compreenda o estado de cada implantação e certifique-se de que cada implantação está funcional e funcionando corretamente. Geralmente, a fase de teste de coexistência existe durante o teste piloto do Skype for Business Server 2019. Os usuários herdados são movidos para o Skype for Business Server 2019 por um período de tempo para garantir que a compatibilidade e os recursos e funções do aplicativo estejam funcionando corretamente. Após o teste piloto, os usuários e os aplicativos são movidos para a versão de produção do Skype for Business Server 2019, e os pools herdados e os aplicativos da versão anterior são desativados.
  
