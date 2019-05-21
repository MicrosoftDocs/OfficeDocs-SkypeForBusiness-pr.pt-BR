---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: a07cbfc8596cfd49760af1fcee7df90eca362229
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34292169"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar o acesso remoto e de federação para usuários externos

Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e acesso externo

- Usuários de pelo menos um domínio federado, um usuário interno do Skype for Business Server 2019 e um usuário na instalação herdada. Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.
    
- Os usuários de cada provedor de serviço de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicando com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Um usuário hospedado na instalação herdada usando o acesso de usuário remoto (registro em log eu sou Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.
    
- Um usuário hospedado no Skype for Business Server 2019 usando acesso de usuário remoto (conectando-se ao Skype for Business Server 2019 de fora da intranet, mas sem VPN), com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.
    

