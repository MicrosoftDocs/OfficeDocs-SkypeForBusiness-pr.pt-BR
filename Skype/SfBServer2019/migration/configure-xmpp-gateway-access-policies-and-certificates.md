---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Federação XMPP define uma implantação externa com base nas mensagens extensível e protocolo de presença (XMPP). Uma configuração de XMPP permite que os usuários acessem usuários de domínio XMPP por:'
ms.openlocfilehash: 65ef8904660eaa75ddd10238a6561ea91b9f7278
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889970"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway de XMPP

Federação XMPP define uma implantação externa com base nas mensagens extensível e protocolo de presença (XMPP). Uma configuração de XMPP permite que os usuários acessem usuários de domínio XMPP por:
  
- IM e presença - apenas entre duas pessoas
    
- Criação de contatos federados XMPP no Skype para o cliente de negócios
    
Quando você configura políticas para suporte de XMPP federados parceiros, as diretivas serão aplicadas aos usuários de domínios XMPP federado, mas não para usuários de protocolo de iniciação de sessão (SIP) serviço (IM) de mensagens instantâneas provedores ou SIP domínios federados. Você configurar um parceiro federado de XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionar contatos e comunique-se com. Depois que as diretivas estão no lugar, você precisa configurar os certificados do Gateway XMPP. 
  
> [!NOTE]
> Funcionalidade XMPP foi preterida no Skype para Business Server 2019, mas pode ser continuada em um servidor herdado em coexistência com o Skype para Business Server 2019. Certificar-se de que você já implantou o servidor herdado (Skype para Business Server 2015 / Lync Server 2013) Gateway XMPP e configurar as políticas de acesso para habilitar usuários para o Gateway de XMPP herdado. Para obter detalhes, consulte [Migrando federação de XMPP](migrating-xmpp-federation.md). 
  
### <a name="configure-an-external-access-policy-to-enable-users-for-legacy-xmpp-gateway"></a>Configurar uma política de acesso externo para habilitar usuários para o Gateway de XMPP herdado

1. Abra o Skype herdado para o painel de controle do servidor de negócios.
    
2. Na barra de navegação à esquerda, clique em **federação e acesso externo**e, em seguida, clique em **Política de acesso externo**.
    
3. Clique em **Novo** e em **Política do usuário**.
    
4. Insira um nome para a política de usuário de acesso externo.
    
5. Forneça uma descrição para a política de usuário de acesso externo.
    
6. Selecione **Habilitar comunicações com usuários federados**.
    
7. Selecione **Habilitar comunicações com XMPP usuários federados**.
    
8. Clique em **Confirmar** para salvar suas alterações na política de site ou usuário. 
    

