---
title: Configurar políticas e certificados de acesso ao gateway XMPP
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
description: 'A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP). Uma configuração XMPP permite que os usuários acessem usuários de domínio XMPP por:'
ms.openlocfilehash: 31d3c2a4b4d16407a30eb755e8b18b3ddf1a1b31c342ed6ff3384bbcef3afbc6
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296018"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway XMPP

A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP). Uma configuração XMPP permite que os usuários acessem usuários de domínio XMPP por:
  
- IM e Presença - somente pessoa para pessoa
    
- Criação de contatos federados XMPP no cliente Skype for Business cliente
    
Quando você configura políticas para suporte a parceiros federados XMPP, as políticas se aplicam aos usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) ou domínios federados SIP. Você configura um parceiro federado XMPP para cada domínio federado XMPP com o que deseja permitir que seus usuários adicionem contatos e se comuniquem. Quando as políticas estiverem inseridas, você precisa configurar os certificados de Gateway XMPP. 
  
> [!NOTE]
> A funcionalidade XMPP é preterida no Skype for Business Server 2019, mas pode ser continuada em um servidor herdado em coexistência com o Skype for Business Server 2019. Certifique-se de que você já implantou o gateway XMPP do servidor herdado (Skype for Business Server 2015 /Lync Server 2013) e configurou as políticas de acesso para habilitar os usuários para o Gateway XMPP herdado. Para obter detalhes, [consulte Migrating XMPP Federation](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar uma Política de Acesso Externo para Habilitar Usuários para Gateway XMPP herdado

1. Abra o painel de controle Skype for Business Server de controle herdado.
    
2. Na barra de navegação esquerda, clique em **Acesso externo e Federação** e em **Política de acesso externo**.
    
3. Clique em **Novo** e em **Política do usuário**.
    
4. Insira um nome para a política de usuário de acesso externo.
    
5. Ofereça uma descrição para a política do usuário de acesso externo.
    
6. Selecione **Habilitar comunicações com usuários federados**.
    
7. Selecione **Habilitar comunicações com usuários federados XMPP**.
    
8. Clique em **Confirmar** para salvar suas alterações na política de usuário ou local. 
    

