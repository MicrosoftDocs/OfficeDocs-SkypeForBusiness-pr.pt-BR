---
title: Verificar a federação e acesso remoto para usuários externos
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: ce0e2dd6ee7d4fb605f844d7dfb26b3f9d13bf14
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25027232"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar a federação e acesso remoto para usuários externos

Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e acesso externo

- Os usuários de pelo menos um domínio federado, um usuário interno no Skype para Business Server 2019 e um usuário no antigo instalar. Testar mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.
    
- Os usuários de cada provedor de serviços IM públicos que ofereçam suporte à sua empresa (e para o qual o provisionamento esteja concluído) se comunicando com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Instalar de um usuário hospedado no antigo usando o acesso de usuário remoto (log i nPara Lync Server/Skype para negócios de fora da intranet, mas sem VPN) com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado. Teste de IM, presença, A / V e área de trabalho de compartilhamento.
    
- Um usuário hospedado no Skype para Business Server 2019 usando o acesso de usuário remoto (fazer logon no Skype para negócios 2019 de servidor de fora da intranet, mas sem VPN) com um usuário do Skype para Business Server 2019 e um usuário na instalação herdado. Teste de IM, presença, A / V e área de trabalho de compartilhamento.
    

