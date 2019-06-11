---
title: 'Lync Server 2013: Configurar políticas para controlar o acesso de usuário público'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure policies to control public user access
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e259082aa73d4354e8e4aa93eb7a0cc8d7ed7a6e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836356"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-public-user-access-in-lync-server-2013"></a>Configurar políticas para controlar o acesso de usuário público no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-10-07_

A conectividade de mensagens instantâneas públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores de serviços públicos de mensagens instantâneas, incluindo a rede do Windows Live dos serviços de Internet, o Yahoo\!e o AOL. Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários públicos podem colaborar com usuários internos do Lync Server. A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração da sua implantação e dos usuários. Ele também depende do provisionamento do serviço no provedor público de IM. Para obter informações sobre como provisionar sua implantação para usar os provedores públicos, consulte o guia "guia de provisionamento de conectividade pública de IM para Microsoft Lync Server, Office Communications Server e Live Communications Server":[http://go.microsoft.com/fwlink/?LinkId=269821](http://go.microsoft.com/fwlink/?linkid=269821)

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partir de 1º de setembro de 2012, a licença de assinatura de usuário da conectividade de mensagem de chat pública do Microsoft Lync ("PIC USL") não está mais disponível para compra de contratos novos ou de renovação. Os clientes com licenças ativas poderão continuar a federar-se com o Yahoo! Messenger até a data de encerramento do serviço. Uma data de fim da vida útil de junho de 2014 para AOL e Yahoo! foi anunciado. Para obter detalhes, consulte <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">suporte para conectividade de mensagens instantâneas públicas no Lync Server 2013</A>.</P>
> <LI>
> <P>O PIC USL é uma licença de assinatura por usuário por mês necessária para o Lync Server ou o Office Communications Server se federar com o Yahoo! Spam. A capacidade da Microsoft de oferecer esse serviço por meio do suporte do Yahoo!, o contrato subjacente para o qual está prestes a ser enrolado.</P>
> <LI>
> <P>Mais do que nunca, o Lync é uma ferramenta poderosa para a conexão entre organizações e pessoas ao redor do mundo. A Federação com o Windows Live Messenger não requer licenças de usuário/dispositivo adicionais além da CAL padrão do Lync. A Federação do Skype será adicionada a essa lista, permitindo que os usuários do Lync atinjam centenas de milhões de pessoas com mensagens instantâneas e voz.</P></LI></UL>



</div>

Para acessar o site de configuração de conectividade de mensagens instantâneas públicas do Microsoft Lync Server, use o seguinte link:[http://go.microsoft.com/fwlink/p/?linkId=212638](http://go.microsoft.com/fwlink/p/?linkid=212638)

Para controlar o acesso do usuário público, você pode configurar políticas nos níveis global, de site e de usuário. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte Configurando o [suporte para acesso de usuários externos no Lync Server 2013](lync-server-2013-configuring-support-for-external-user-access.md) na documentação de implantação ou documentação de planejamento. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

No caso de convites por mensagem instantânea, a resposta depende do software cliente. A solicitação é aceita, a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas **permitir** e **Bloquear** do cliente do usuário). Além disso, os convites de mensagem instantânea podem ser bloqueados se um usuário optar por bloquear todas as mensagens instantâneas de usuários que não estão na sua lista de **permissões** .

<div>


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a Federação para sua organização. No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou documentação de operações. Além disso, se você especificar uma política de usuário para controlar o acesso ao usuário público, a política se aplicará somente aos usuários habilitados para o Lync Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários públicos que podem entrar no Lync Server, consulte <A href="lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md">atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync server 2013</A> na documentação de implantação ou documentação de operações.



</div>

Use o procedimento a seguir para configurar uma política para dar suporte ao acesso por usuários de um ou mais provedores de mensagens de chat públicos.

<div>

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuários públicos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso a usuários públicos, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnablePublicUsers** para uma política de usuário que permita comunicações para usuários públicos).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário público para a política, marque a caixa de seleção **habilitar comunicações com usuários públicos** .
    
      - Para desabilitar o acesso de usuário público para a política, desmarque a caixa de seleção **habilitar comunicações com usuários públicos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário público, você também deve habilitar o suporte para Federação em sua organização. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

Se esta for uma política de usuário, você também deverá aplicar a política a usuários públicos que você deseja que possam colaborar com usuários públicos. Para obter detalhes, consulte [atribuindo políticas por usuário no Lync Server 2013](lync-server-2013-assigning-per-user-policies.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar ou editar fornecedores SIP públicos federados no Lync Server 2013](lync-server-2013-create-or-edit-public-sip-federated-providers.md)  


[Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

