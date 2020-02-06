---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: 7f27fa853c8af2ba5e97835ad1e0dd893c9128e0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812679"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar o acesso remoto e de federação para usuários externos

Após a transição da rota de Federação para o servidor de borda do Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Os testes de acesso de usuário externo devem incluir cada tipo de usuário externo compatível com a sua organização, incluindo qualquer um ou todos os itens a seguir.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e acesso externo

- Usuários de pelo menos um domínio federado, um usuário interno do Skype for Business Server 2019 e um usuário na instalação herdada. Testar mensagens instantâneas (IM), presença, áudio/vídeo (A/V) e compartilhamento da área de trabalho.
    
- Os usuários de cada provedor de serviço de mensagens de chat público compatível com a sua organização (e para a qual o provisionamento foi concluído) se comunicando com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Um usuário hospedado na instalação herdada usando o acesso de usuário remoto (registro em log eu sou Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.
    
- Um usuário hospedado no Skype for Business Server 2019 usando acesso de usuário remoto (conectando-se ao Skype for Business Server 2019 de fora da intranet, mas sem VPN), com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Teste mensagens instantâneas, presença, A/V e compartilhamento de área de trabalho.
    

