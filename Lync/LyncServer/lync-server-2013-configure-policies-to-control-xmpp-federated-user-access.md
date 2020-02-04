---
title: 'Lync Server 2013: Configurar políticas para controlar o acesso de usuário federado'
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
ms.openlocfilehash: cc79a915d0735f87c0852dff0ba4228b1e391fd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730021"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-xmpp-federated-user-access-in-lync-server-2013"></a>Configurar políticas para controlar o acesso de usuário federado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Esta documentação é preliminar e está sujeita a alterações. Os tópicos em branco são incluídos como espaços reservados.

Quando você configura políticas para dar suporte a parceiros federados do protocolo de Unificação de mensagens e de protocolo de presença (XMPP), as políticas se aplicam a usuários de domínios federados XMPP, mas não aos usuários de provedores de serviços de mensagens instantâneas SIP (protocolo de iniciação de sessão) (por exemplo, Windows Live) ou domínios federados SIP. Você configura um **parceiro federado do XMPP** para cada domínio federado XMPP que você deseja permitir que os usuários adicionem contatos e se comuniquem. As políticas de parceiros federados do XMPP só estão disponíveis em um único escopo, embora não seja definida como uma política global, atua como uma política global. Para definir uma política global, de site ou de usuário para parceiros de Federação do XMPP, configure o escopo da política primeiro criando e configurando a política de acesso externo para o escopo que você precisa. Para obter detalhes sobre os tipos de políticas que você pode configurar para acesso externo e Federação, consulte [Gerenciando a Federação e acesso externo ao Lync Server 2013](lync-server-2013-managing-federation-and-external-access-to-lync-server-2013.md) na documentação de operações.

<div>


> [!NOTE]  
> Todas as políticas <STRONG>de acesso externo e agrupamento</STRONG> são aplicadas por meio do provisionamento em banda. As políticas que se aplicam ao usuário, pertencem a um site ou são globais em escopo são comunicadas ao cliente durante o logon. Você pode configurar políticas para controlar o acesso do parceiro federado do XMPP, mesmo se você não tiver habilitado a Federação do XMPP para a sua organização. No entanto, as políticas que você configura entram em vigor apenas quando você tem a Federação de parceiro do XMPP implantada, habilitada e configurada para sua organização. Para obter detalhes sobre como implantar e configurar a Federação de parceiro do XMPP, consulte <A href="lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md">Configurando Federação SIP, agrupamento XMPP e mensagens instantâneas públicas no Lync Server 2013</A> na documentação de implantação. Além disso, se você especificar uma política de usuário na política de acesso externo para controlar os parceiros federados do XMPP, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.



</div>

<div>

## <a name="to-edit-a-global-policy-for-xmpp-federated-partners"></a>Para editar uma política global para parceiros federados XMPP

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , faça o seguinte para a política global:

5.  Clique na política global, clique em **Editar**e, em seguida, clique em mostrar detalhes.

6.  Forneça uma descrição para a política global (opcional).

7.  Selecione **habilitar comunicações com usuários federados**.

8.  Selecione **habilitar comunicações com usuários federados do XMPP**.

9.  Clique em **confirmar** para salvar as alterações na política global.

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners"></a>Para criar uma política de site ou de usuário para parceiros federados XMPP

1.  Clique em **novo**e, em seguida, clique em política do **site** ou **política do usuário**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.

2.  Forneça uma descrição para a política de site (opcional).

3.  Na política do site ou do usuário, selecione **habilitar comunicações com usuários federados**.

4.  Selecione **habilitar comunicações com usuários federados do XMPP**.

5.  Clique em **confirmar** para salvar as alterações no site ou na política de usuário.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners"></a>Para editar uma política existente para parceiros federados XMPP

1.  Para alterar uma política existente, selecione a política apropriada na lista, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

2.  Altere ou atualize a descrição da política (opcional).

3.  Marque ou desmarque **habilitar comunicações com usuários federados**.

4.  Marque ou desmarque **habilitar comunicações com usuários federados do XMPP**.

5.  Clique em **confirmar** para salvar as alterações na política.

</div>

<div>

## <a name="to-edit-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para editar uma política existente para parceiros federados do XMPP usando o Windows PowerShell

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Um exemplo de comando que define a política global para acesso de usuário federado a true (Enabled) e o acesso de domínio XMPP para true (Enabled):
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-create-a-site-or-user-policy-for-xmpp-federated-partners-using-windows-powershell"></a>Para criar uma política de site ou de usuário para parceiros federados do XMPP usando o Windows PowerShell

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        New-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false>
    
    Um exemplo de comando que definirá uma política de site para o site Redmond para acesso de usuário federado ao acesso de domínio habilitado e XMPP como habilitado:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true

</div>

<div>

## <a name="to-delete-an-existing-policy-for-xmpp-federated-partners-by-using-windows-powershell"></a>Para excluir uma política existente para parceiros federados do XMPP usando o Windows PowerShell

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>
    
    Um exemplo de comando que excluirá uma política de usuário:
    
        Remove-CsExternalAccessPolicy -Identity EAPUserPolicySetXMPP

4.  Um exemplo de comando que irá redefinir a política global para padrões:
    
        Remove-CsExternalAccessPolicy -Identity global

</div>

<div>

## <a name="see-also"></a>Confira também


[Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  
[Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  


[Gerenciar parceiros XMPP federados no Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

