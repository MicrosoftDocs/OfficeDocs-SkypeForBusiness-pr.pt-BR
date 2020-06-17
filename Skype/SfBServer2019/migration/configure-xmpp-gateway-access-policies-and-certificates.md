---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
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
description: 'A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP). Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:'
ms.openlocfilehash: f94cd3bc0a769165f6ffe8ecabea8b7f48a1ff07
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753931"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway de XMPP

A federação XMPP define uma implantação externa baseada no Protocolo de Presença e Mensagem eXtensible (XMPP). Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:
  
- IM e presença-pessoa somente para pessoa
    
- Criação de contatos federados XMPP no cliente Skype for Business
    
Quando você configura políticas para suporte a parceiros federados XMPP, as políticas se aplicam a usuários de domínios federados XMPP, mas não a usuários de provedores de serviço de mensagens instantâneas (IM) ou domínios de SIP federados. Configure um parceiro federado do XMPP para cada domínio federado do XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem com o. Quando as políticas estiverem inseridas, você precisa configurar os certificados de Gateway XMPP. 
  
> [!NOTE]
> A funcionalidade do XMPP foi preterida no Skype for Business Server 2019, mas pode continuar em um servidor herdado em coexistência com o Skype for Business Server 2019. Verifique se você já implantou o servidor herdado (Skype for Business Server 2015/Lync Server 2013) XMPP gateway e configurou as políticas de acesso para habilitar os usuários para o Gateway XMPP herdado. Para obter detalhes, consulte [Migrating XMPP Federation](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar uma política de acesso externo para habilitar usuários para o Gateway XMPP herdado

1. Abra o painel de controle do Skype for Business Server herdado.
    
2. Na barra de navegação esquerda, clique em **Acesso externo e Federação** e em **Política de acesso externo**.
    
3. Clique em **Novo** e em **Política do usuário**.
    
4. Insira um nome para a política de usuário de acesso externo.
    
5. Ofereça uma descrição para a política do usuário de acesso externo.
    
6. Selecione **Habilitar comunicações com usuários federados**.
    
7. Selecione **Habilitar comunicações com usuários federados XMPP**.
    
8. Clique em **Confirmar** para salvar suas alterações na política de usuário ou local. 
    

