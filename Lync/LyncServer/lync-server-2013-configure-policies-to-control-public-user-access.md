---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários públicos'
description: 'Lync Server 2013: configurar políticas para controlar o acesso de usuários públicos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d44437cc288d1515784af8c635f4b28902c4fa1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548727"
---
# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurar políticas para controlar o acesso de usuários públicos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-10-07_

A conectividade de mensagens instantâneas (IM) pública permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviço de IM públicos, incluindo a rede do Windows Live de serviços de Internet, Yahoo \! e AOL. Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários públicos podem colaborar com usuários internos do Lync Server. A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração de sua implantação e dos usuários. Também depende do provisionamento do serviço no provedor de IM público. Para obter informações sobre como provisionar sua implantação para usar os provedores públicos, consulte o guia "Public IM Connectivity Provisioning Guide for Microsoft Lync Server, Office Communications Server e Live Communications Server": [https://go.microsoft.com/fwlink/?LinkId=269821](https://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de IM pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a se federar com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim de vida de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">support for Public Instant Messenger Connectivity in Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário por mês, necessária para o Lync Server ou o Office Communications Server federar-se com o Yahoo! Instantânea. A capacidade da Microsoft de fornecer esse serviço tem sido contingente o suporte da Yahoo!, o contrato subjacente para o qual está se enrolando para baixo.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma poderosa ferramenta para a conexão entre organizações e pessoas em todo o mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada à lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com IM e voz.</P></LI></UL>



</div>

Para acessar o site de provisionamento da conectividade de IM pública do Microsoft Lync Server, use o seguinte link: [https://go.microsoft.com/fwlink/p/?linkId=212638](https://go.microsoft.com/fwlink/p/?linkid=212638)

Para controlar o acesso do usuário público, é possível configurar políticas no nível global, site e de usuário. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Configurando o suporte para acesso de usuário externo no Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) na documentação de implantação ou na documentação de planejamento. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

No caso de convites de IM, a resposta depende do software cliente. A solicitação é aceita a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas de cliente **Permitir** e **Bloquear** do usuário). Além disso, os convites de IM podem ser bloqueados se um usuário optar por bloquear toda IM de usuários que não estão na lista **Permitir**.

<div>


> [!NOTE]  
> É possível configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a federação para sua organização. No entanto, as políticas configuradas entram em vigor somente quando a federação está habilitada para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou na documentação operações. Além disso, se você especificar uma política de usuário para controlar o acesso de usuário público, a política será aplicada somente aos usuários habilitados para o Lync Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários públicos que podem entrar no Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync server 2013</A> na documentação de implantação ou na documentação de operações.



</div>

Use o procedimento a seguir para configurar uma política para suportar o acesso de usuários de um ou mais provedores de IM público.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar uma política de acesso externo para suportar o acesso de usuário público

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, execute uma das seguintes ações:
    
      - Para configurar a política global a fim de suportar o acesso de usuário público, clique na política global, em **Editar** e clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **Novo** e clique em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **Novo** e clique em **Política de Usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o que a política de usuário cobre (por exemplo, **EnablePublicUsers** para uma política de usuário que permite comunicações para usuários públicos).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar** e clique em **Mostrar detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuários públicos à política, marque a caixa de seleção **Habilitar comunicações com usuários públicos**.
    
      - Para desabilitar o acesso de usuários públicos à política, desmarque a caixa de seleção **Habilitar comunicações com usuários públicos**.

7.  Clique em **Confirmar**.

Para habilitar o acesso do usuário público, você também deve habilitar o suporte para federação em sua organização. Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Se for uma política de usuário, também será necessário aplicar a política aos usuários públicos para os quais você deseja permitir a colaboração com usuários públicos. Para obter detalhes, consulte [atribuir políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou editar provedores federados SIP públicos no Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Gerenciar provedores federados SIP para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

