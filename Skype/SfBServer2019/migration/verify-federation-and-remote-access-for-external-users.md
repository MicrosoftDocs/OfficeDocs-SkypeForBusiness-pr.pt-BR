---
title: Verificar o acesso remoto e de federação para usuários externos
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231347"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a>Verificar o acesso remoto e de federação para usuários externos

Após a transição da rota de federação para o Skype para o servidor de borda de 2019 Business Server, você deve executar alguns testes funcionais para verificar se a Federação funciona conforme o esperado. Testes de acesso de usuário externo devem incluir a cada tipo de usuário externo que sua organização suporta, incluindo qualquer um ou todos os itens a seguir.
  
### <a name="test-connectivity-of-external-users-and-external-access"></a>Testar a conectividade de usuários externos e acesso externo

- Os usuários de pelo menos um domínio federado, um usuário interno no Skype para Business Server 2019 e um usuário no antigo instalar. Testar mensagens instantâneas (IM), presença, áudio/vídeo (A / V) e o compartilhamento de área de trabalho.
    
- Os usuários de cada provedor de serviços IM públicos que ofereçam suporte à sua empresa (e para o qual o provisionamento esteja concluído) se comunicando com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado. 
    
- Verifique se usuários anônimos podem participar de conferências.
    
- Instalar de um usuário hospedado no antigo usando o acesso de usuário remoto (log i nPara Lync Server/Skype para negócios de fora da intranet, mas sem VPN) com um usuário no Skype para Business Server 2019 e um usuário na instalação herdado. Teste de IM, presença, A / V e área de trabalho de compartilhamento.
    
- Um usuário hospedado no Skype para Business Server 2019 usando o acesso de usuário remoto (fazer logon no Skype para negócios 2019 de servidor de fora da intranet, mas sem VPN) com um usuário do Skype para Business Server 2019 e um usuário na instalação herdado. Teste de IM, presença, A / V e área de trabalho de compartilhamento.
    

