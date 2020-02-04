---
title: 'Lync Server 2013: Configurar políticas para controle de acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control remote user access
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d8542e7d64198cb83df58885b9240e07066288d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurar políticas para controle de acesso de usuário remoto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-18_

Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários remotos podem colaborar com usuários internos do Lync Server. Para controlar o acesso do usuário remoto, você pode configurar políticas nos níveis global, de site e de usuário. Políticas de site substituem a política global e as políticas de usuário substituem políticas globais e do site. Para obter detalhes sobre os tipos de diretivas que você pode configurar, consulte [Gerenciamento de Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

<div>


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso do usuário remoto, mesmo se você não tiver habilitado o acesso de usuário remoto para a sua organização. No entanto, as políticas que você configura são efetivadas apenas quando você tem acesso de usuário remoto habilitado para sua organização. Para obter detalhes sobre como habilitar o acesso do usuário remoto, consulte <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar ou desabilitar a conectividade de mensagens de chat pública e de Federação no Lync Server 2013</A>. Além disso, se você especificar uma política de usuário para controlar o acesso do usuário remoto, a política se aplicará somente aos usuários habilitados para o Lync Server e configurados para usar a política. Para obter detalhes sobre como especificar os usuários que podem entrar no Lync Server de locais remotos, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</A>.



</div>

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso do usuário remoto.

<div>


> [!NOTE]  
> Este procedimento descreve como configurar uma política somente para permitir comunicações com usuários remotos, mas cada política que você configura para dar suporte ao acesso de usuário remoto também pode configurar o acesso de usuário federado e acesso de usuário público. Para obter detalhes sobre como configurar políticas para dar suporte a usuários federados, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013</A>. Para obter detalhes sobre como configurar políticas para dar suporte a usuários públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">criar ou editar provedores federados SIP públicos no Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuários remotos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso de usuário remoto, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnableRemoteUsers** para uma política de usuário que permita comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para a política, marque a caixa de seleção **habilitar comunicações com usuários remotos** .
    
      - Para desabilitar o acesso de usuário remoto para a política, desmarque a caixa de seleção **habilitar comunicações com usuários remotos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte ao acesso de usuários remotos em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) na documentação de implantação ou documentação de operações.

Se esta for uma política de usuário, você também deverá aplicar a política aos usuários para os quais você deseja poder se conectar remotamente. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) na documentação de implantação ou documentação de operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

