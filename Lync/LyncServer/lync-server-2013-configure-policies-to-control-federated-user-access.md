---
title: 'Lync Server 2013: Configurar políticas para controlar acesso de usuário federado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure policies to control federated user access
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1aeb1b29637fd3f4a8add770470069e8b4a6eb8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763283"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-policies-to-control-federated-user-access-in-lync-server-2013"></a>Configurar políticas para controlar acesso de usuário federado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-05_

Quando você configura políticas para dar suporte a comunicações com parceiros federados, as políticas se aplicam a usuários de domínios federados. Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários de domínios federados podem colaborar com os usuários do Lync Server 2013. Para controlar o acesso do usuário federado, você pode configurar políticas nos níveis global, de site e de usuário. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

<div>


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso do usuário federado, mesmo se você não tiver habilitado a Federação para sua organização. No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou documentação de operações. Além disso, se você especificar uma política de usuário para controlar o acesso do usuário federado, a política se aplicará somente aos usuários habilitados para o Lync Server 2013 e configurados para usar a política.



</div>

<div>

## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política para dar suporte ao acesso por usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso de usuário federado, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica o conteúdo da política do usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários do domínio federado).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado para a política, marque a caixa de seleção **habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado para a política, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para Federação em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md).

Se esta for uma política de usuário, você também deverá aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md).

</div>

<div>

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Um exemplo de comando que define a política global para acesso de usuário federado ao acesso de domínio federado habilitado, XMPP para acesso ao usuário remoto habilitado, acesso de usuário remoto para habilitado, acesso do provedor público como habilitado e conceder a capacidade de usar áudio e vídeo para provedores públicos que dão suporte a ele:
    
        Set-CsExternalAccessPolicy -Identity global -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    
    <div>
    

    > [!TIP]  
    > O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no painel de controle do Lync Server

    
    </div>

</div>

<div>

## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

3.  Digite o seguinte no Shell de gerenciamento do Lync Server:
    
        New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    
    Um exemplo de como criar uma nova política de site:
    
        New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true

</div>

<div>

## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Digite o seguinte no Shell de gerenciamento do Lync Server
    
        Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy> 
    
    Um exemplo de como redefinir a política global (a política global pode ter apenas sua configuração removida. A política não pode ser excluída):
    
        Remove-CsExternalAccessPolicy -Identity global 
    
    Para remover uma política de site, digite:
    
        Remove-CsExternalAccessPolicy -Identity site:Redmond 
    
    Exclui a política do site Redmond. Para excluir uma política de usuário chamada UserEAPPolicy, digite:
    
        Remove-CsExternalAccessPolicy -Identity UserEAPPolicy

</div>

<div>

## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md)  
[Atribuir uma política de usuário externo a um usuário habilitado do Lync no Lync Server 2013](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)  


[Gerenciar domínios SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[Gerenciar fornecedores SIP federados para sua organização no Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
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

