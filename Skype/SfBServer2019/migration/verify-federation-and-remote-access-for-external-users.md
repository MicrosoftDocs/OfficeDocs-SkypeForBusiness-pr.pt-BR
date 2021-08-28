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
ms.localizationpriority: medium
description: Depois de fazer a transição da rota de federação para o servidor de borda Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a federação está funcionando conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.
ms.openlocfilehash: ef6e41242462f218ab96db94dd8a2b5df1b388bb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58592955"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar a federação e o acesso remoto para usuários externos

Depois de fazer a transição da rota de federação para o servidor de borda Skype for Business Server 2019, você deve executar alguns testes funcionais para verificar se a federação está funcionando conforme o esperado. Os testes de acesso do usuários externo devem incluir qualquer tipo de usuário externo suportado pela sua organização, incluindo qualquer um ou todos os seguintes.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar conectividade de usuários externos e acesso externo

- Usuários de pelo menos um domínio federado, um usuário interno no Skype for Business Server 2019 e um usuário na instalação herdada. Teste as mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.
    
- Os usuários de cada provedor de serviço de IM público que sua organização oferece suporte (e para o qual o provisionamento foi concluído) comunicam-se com um usuário no Skype for Business Server 2019 e um usuário na instalação herdado. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Um usuário hospedado na instalação herdada usando o acesso de usuário remoto (log i nto Lync Server/Skype for Business de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Testar a IM, presença, A/V e compartilhamento de área de trabalho.
    
- Um usuário hospedado no Skype for Business Server 2019 usando o acesso de usuário remoto (entrar no Skype for Business Server 2019 de fora da intranet, mas sem VPN) com um usuário no Skype for Business Server 2019 e um usuário na instalação herdada. Testar a IM, presença, A/V e compartilhamento de área de trabalho.
    

