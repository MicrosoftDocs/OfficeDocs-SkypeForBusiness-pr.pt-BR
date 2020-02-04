---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway de XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-15_

A Federação XMPP define uma implantação externa baseada no protocolo de mensagens extensíveis e presença (XMPP). Uma configuração do XMPP permite que os usuários do Lync acessem usuários de domínio do XMPP:

  - Mensagem instantânea e presença – pessoa para pessoa apenas

  - Criação de contatos federados do XMPP no cliente do Lync

Quando você configura políticas para dar suporte a parceiros federados do protocolo de Unificação de mensagens e de protocolo de presença (XMPP), as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) (por exemplo, Windows Live) ou domínios federados SIP. Você configura um parceiro federado do XMPP para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem. Depois que as políticas estiverem em vigor, você precisará configurar os certificados de gateway do XMPP.

<div>


> [!NOTE]  
> Para começar a migração do Gateway XMPP, você precisa implantar o Gateway XMPP do Lync Server 2013 e configurar políticas de acesso para permitir que os usuários do Lync Server 2013 XMPP gateway. Todos os usuários devem ser movidos para a implantação do Lync Server 2013 antes de executar essas etapas. Para obter detalhes, consulte <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configurar o Gateway XMPP no Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurar uma política de acesso externo para permitir aos usuários do Lync Server 2013 XMPP gateway

1.  Abra o Painel de Controle do Lync Server.

2.  Na barra de navegação à esquerda, clique em **Federação e acesso externo**e, em seguida, clique em **política de acesso externo**.

3.  Clique em **novo** e, em seguida, clique em **política de usuário**.

4.  Digite um nome para a política de usuário de acesso externo.

5.  Forneça uma descrição para a política de usuário de acesso externo.

6.  Selecione **habilitar comunicações com usuários federados**.

7.  Selecione **habilitar comunicações com usuários federados do XMPP**.

8.  Clique em **confirmar** para salvar as alterações no site ou na política de usuário.

</div>

</div>

<span> </span>

</div>

</div>

</div>

