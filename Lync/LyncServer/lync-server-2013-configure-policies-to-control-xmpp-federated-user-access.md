---
title: 'Lync Server 2013: configurar políticas para controlar o acesso de usuário federado do XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control XMPP federated user access
ms:assetid: 0fe0ff75-e52a-4e3e-923a-64f6412ac4e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552446(v=OCS.15)
ms:contentKeyID: 48679557
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1ef7679270410df9c7a6ae6f1fa22858bf7a0b53
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035253"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurar políticas para controlar o acesso de usuário federado do XMPP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Esta é uma documentação preliminar e está sujeita a alterações. Tópicos em branco são incluídos como espaços reservados.

Ao configurar políticas para oferecer suporte a parceiros federados do protocolo XMPP, as políticas aplicam-se a usuários dos domínios XMPP federados, mas não a usuários de provedores de serviços de mensagens instantâneas (IM) do protocolo SIP (por exemplo, Windows Live), ou domínios SIP federados. Configure um **Parceiro Federado XMPP** para cada domínio XMPP federado para os quais deseja permitir que seus usuários adicionem contatos e se comuniquem. Políticas de parceiros federados XMPP estão disponíveis somente em um único escopo, e embora não sejam definidas como políticas globais, agem como uma. Para definir uma política global, de site ou de usuário para Parceiros Federados XMPP, configure o escopo da política primeiro criando e configurando a Política de Acesso Externo para o escopo necessário. Para obter detalhes sobre os tipos de políticas que você pode configurar para acesso externo e Federação, consulte [Managing Federation and external Access to Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação operações.

<div>


> [!NOTE]  
> Todas as políticas de <STRONG>Federação de Acesso Externo</STRONG> são aplicadas através de provisionamento em banda. As políticas que se aplicam ao usuário, pertencem a um site ou são globais no escopo são comunicadas ao cliente durante o login. Você pode configurar políticas para controlar o acesso de parceiros federados XMPP, mesmo se não tiver habilitado a federação XMPP para a sua organização. No entanto, as políticas configuradas produzem efeito somente quando você tem a federação de parceiros XMPP implantada, habilitada e configurada para a sua organização. Para obter detalhes sobre como implantar e configurar a Federação de parceiros do XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configuring SIP Federation, XMPP Federation and Public Instant Messaging in Lync Server 2013</A> na documentação de implantação. Além disso, se você especificar uma política de usuário na política de acesso externo para controlar parceiros federados do XMPP, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Para editar uma política global para parceiros federados XMPP

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e clique em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, faça o seguinte para a política global:

5.  Clique na política global, clique em **Editar** e em Exibir detalhes.

6.  Forneça uma descrição para a política global (opcional).

7.  Selecione **Habilitar comunicações com usuários federados**.

8.  Selecione **Habilitar comunicações com usuários federados XMPP**.

9.  Clique em **Confirmar** para salvar suas alterações na política global.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Para criar uma política de site ou de usuário para parceiros federados XMPP

1.  Clique em **Novo** e em **Política de site** ou **Política de usuário**. Em **Selecionar um Site**, clique no site apropriado na lista e clique em **OK**.

2.  Forneça uma descrição para a política de site (opcional).

3.  Na política de site ou de usuário, selecione **Habilitar comunicações com usuários federados**.

4.  Selecione **Habilitar comunicações com usuários federados XMPP**.

5.  Clique em **Confirmar** para salvar suas alterações na política de site ou de usuário.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Para editar uma política existente para parceiros federados XMPP

1.  Para alterar uma política existente, selecione a política desejada na lista, clique em **Editar** e em **Exibir detalhes**.

2.  Altere ou atualize a descrição da política (opcional).

3.  Marque ou desmarque a opção **Habilitar comunicações com usuários federados**.

4.  Marque ou desmarque a opção **Habilitar comunicações com usuários federados XMPP**.

5.  Clique em **Confirmar** para salvar suas alterações na política.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para editar uma política existente para parceiros federados XMPP usando o Windows PowerShell

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Um comando de exemplo que definirá a política global para acesso de usuário federado como true (Enabled) e o acesso de domínio XMPP como true (Enabled):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Para criar uma política de site ou de usuário para parceiros federados XMPP usando o Windows PowerShell

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Um comando de exemplo que definirá uma política de site para o site Redmond para o acesso de usuários federados como habilitado e acesso ao domínio XMPP como habilitado:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para excluir uma política existente para parceiros federados XMPP usando o Windows PowerShell

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Um comando de exemplo que excluirá uma política de usuário:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Um comando de exemplo que redefinirá a política global para a configuração padrão:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Confira também


[Atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gerenciar parceiros federados do XMPP no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

