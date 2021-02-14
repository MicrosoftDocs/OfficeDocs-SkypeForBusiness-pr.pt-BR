---
title: Verificar a federação e o acesso remoto para usuários externos
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
description: Depois de fazer a transição da rota de federação para o Servidor de Borda do Skype for Business Server 2019, você deve realizar alguns testes funcionais para verificar se a federação funciona conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751663"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar a federação e o acesso remoto para usuários externos

Depois de fazer a transição da rota de federação para o Servidor de Borda do Skype for Business Server 2019, você deve realizar alguns testes funcionais para verificar se a federação funciona conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e o acesso externo

- Usuários de pelo menos um domínio federado, um usuário interno no Skype for Business Server 2019 e um usuário na instalação herdada. Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.
    
- Os usuários de cada provedor de serviços públicos de mensagens im que sua organização suporta (e para os quais o provisionamento foi concluído) se comunicam com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Um usuário hospedado na instalação herdada usando o acesso de usuário remoto (registro em log i nto Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Testar a IM, presença, A/V e compartilhamento de área de trabalho.
    
- Um usuário hospedado no Skype for Business Server 2019 usando o acesso de usuário remoto (entrando no Skype for Business Server 2019 de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Testar a IM, presença, A/V e compartilhamento de área de trabalho.
    

