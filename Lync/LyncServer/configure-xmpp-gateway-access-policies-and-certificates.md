---
title: Configurar políticas e certificados de acesso ao gateway de XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: d7353d6bfdd4c045d9d592ababf92f2aaaec2365
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754469"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configurar políticas e certificados de acesso ao gateway de XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - IM e Presença – apenas pessoa para pessoa

  - Criação de contatos federados XMPP no cliente Lync

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

<div>


> [!NOTE]  
> Para começar a migração de Gateway XMPP, você precisa implantar o Gateway XMPP do Lync Server 2013 e configurar as políticas de acesso para habilitar usuários para o gateway do Lync Server 2013 XMPP. Todos os usuários devem ser movidos para a implantação do Lync Server 2013 antes de executar estas etapas. Para obter detalhes, consulte <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurar uma Política de acesso externo para habilitar usuários para o Gateway XMPP do Lync Server 2013

1.  Abra o Painel de Controle do Lync Server.

2.  Na barra de navegação esquerda, clique em **Acesso externo e Federação** e em **Política de acesso externo**.

3.  Clique em **Novo** e em **Política do usuário**.

4.  Insira um nome para a política de usuário de acesso externo.

5.  Ofereça uma descrição para a política do usuário de acesso externo.

6.  Selecione **Habilitar comunicações com usuários federados**.

7.  Selecione **Habilitar comunicações com usuários federados XMPP**.

8.  Clique em **Confirmar** para salvar suas alterações na política de usuário ou local.

</div>

</div>

<span> </span>

</div>

</div>

</div>

