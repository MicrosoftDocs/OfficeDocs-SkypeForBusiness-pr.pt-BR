---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários remotos'
description: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários remotos.'
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
ms.openlocfilehash: 6408747cfbbc5e7dff8fd198c0de162f49fc5ff2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548707"
---
# <a name="configure-policies-to-control-remote-user-access-in-lync-server-2013"></a>Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-18_

Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com usuários internos do Lync Server. Para controlar o acesso de usuários remotos, você pode configurar políticas no nível global, de site e de usuário. As políticas de site substituem a política global e as políticas de usuário substituem as políticas globais e do site. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md). As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

<div>


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário remoto, mesmo que você não tenha habilitado o acesso de usuário remoto para sua organização. No entanto, as políticas que você configurou estão em vigor somente quando você tem acesso de usuário remoto habilitado para sua organização. Para obter detalhes sobre como habilitar o acesso de usuário remoto, consulte <A href="lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md">habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013</A>. Além disso, se você especificar uma política de usuário para controlar o acesso de usuário remoto, a política será aplicada somente aos usuários habilitados para o Lync Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários que podem entrar no Lync Server a partir de locais remotos, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013</A>.



</div>

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso de usuários remotos.

<div>


> [!NOTE]  
> Este procedimento descreve como configurar uma política somente para habilitar comunicações com usuários remotos, mas cada política configurada para dar suporte ao acesso de usuário remoto também pode configurar o acesso de usuário federado e o acesso de usuário público. Para obter detalhes sobre como configurar políticas para dar suporte a usuários federados, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure Policies to Control Federated User Access in Lync Server 2013</A>. Para obter detalhes sobre como configurar políticas para dar suporte a usuários públicos, consulte <A href="lync-server-2013-create-or-edit-public-sip-federated-providers.md">create or Edit Public SIP Federated Providers in Lync Server 2013</A>.



</div>

<div>

## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuários remotos

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:
    
      - Para configurar a política global para oferecer suporte ao acesso de usuários remotos, clique na política global, clique em **Editar**e em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.
    
      - Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica o que a política de usuário abrange (por exemplo, **EnableRemoteUsers** para uma política de usuário que permite comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para a política, marque a caixa de seleção **habilitar comunicações com usuários remotos** .
    
      - Para desabilitar o acesso de usuário remoto para a política, desmarque a caixa de seleção **habilitar comunicações com usuários remotos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte para o acesso de usuários remotos em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) na documentação de implantação ou na documentação operações.

Se esta for uma política de usuário, você também deverá aplicar a política aos usuários que você deseja que se conectem remotamente. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md) na documentação de implantação ou na documentação de operações.

</div>

</div>

<span> </span>

</div>

</div>

</div>

