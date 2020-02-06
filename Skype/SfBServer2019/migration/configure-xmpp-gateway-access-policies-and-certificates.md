---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
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
description: 'A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP). Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:'
ms.openlocfilehash: 8182153bf3633b2392969f5870a7d5b96471d4fb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813759"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway de XMPP

A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP). Uma configuração do XMPP permite que os usuários acessem os usuários de domínio do XMPP:
  
- Mensagem instantânea e presença-pessoa somente para pessoa
    
- Criação de contatos federados do XMPP no cliente Skype for Business
    
Quando você configura políticas para dar suporte a XMPP parceiros federados, as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas (IM) do protocolo de início de sessão (IM) ou domínios do SIP federado. Você configura um parceiro federado do XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem. Depois que as políticas estiverem em vigor, você precisará configurar os certificados de gateway do XMPP. 
  
> [!NOTE]
> A funcionalidade do XMPP foi preterida no Skype for Business Server 2019, mas pode continuar em um servidor herdado em coexistência com o Skype for Business Server 2019. Verifique se você já implantou o servidor herdado (Skype for Business Server 2015/Lync Server 2013) XMPP o gateway e configurou as políticas de acesso para permitir aos usuários do gateway herdado do XMPP. Para obter detalhes, consulte [migrando a Federação do XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar uma política de acesso externo para permitir que os usuários do gateway herdado XMPP

1. Abra o painel de controle herdado do Skype for Business Server.
    
2. Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **política de acesso externo**.
    
3. Clique em **Novo** e em **Política do usuário**.
    
4. Digite um nome para a política de usuário de acesso externo.
    
5. Forneça uma descrição para a política de usuário de acesso externo.
    
6. Selecione **habilitar comunicações com usuários federados**.
    
7. Selecione **habilitar comunicações com usuários federados do XMPP**.
    
8. Clique em **confirmar** para salvar as alterações no site ou na política de usuário. 
    

