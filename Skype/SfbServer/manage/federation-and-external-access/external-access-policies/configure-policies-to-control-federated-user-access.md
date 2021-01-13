---
title: Configurar políticas para controlar acesso de usuário federado
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Quando você configurar políticas para fornecer suporte às comunicações de parceiros federados, as políticas se aplicam aos usuários de domínios federados. '
ms.openlocfilehash: 2b7976492fe4f789c2f3130fb51deaaef44af701
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817296"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário federado no Skype for Business Server

Quando você configurar políticas para fornecer suporte às comunicações de parceiros federados, as políticas se aplicam aos usuários de domínios federados. Você pode configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários de domínios federados podem colaborar com seus usuários do Skype for Business Server. Para controlar o acesso de usuários federados, você pode configurar políticas no nível global, de site e de usuário. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário federado, mesmo se você não tiver habilitado a federação para sua organização. No entanto, as políticas que você configurar entram em vigor somente quando o federação é habilitada para sua organização. Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md)  Além disso, se você especificar uma política de usuário para controlar o acesso de usuário federado, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política para suportar o acesso por usuários de domínios federados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:
    
      - Para configurar a política global para oferecer suporte ao acesso de usuário federado, clique na política global, clique em **Editar** e em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.
    
      - Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **Nova Política de Acesso Externo**, crie um nome exclusivo no campo **Nome** que indica o a abrangência da política de usuário (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite comunicações para usuários públicos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado na política, marque a caixa de seleção **Habilitar comunicações com usuários federados**.
    
      - Para desabilitar o acesso de usuário federado na política, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.

7.  Clique em **Confirmar**.

Para habilitar o acesso do usuário federado, você também deve habilitar o suporte para federação em sua organização. Para obter detalhes, [consulte Habilitar ou desabilitar federação e conectividade de IM pública.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Se essa for uma política de usuário, você também deverá aplicar a política aos usuários que também devem ser capazes de colaborar com usuários federados. Para obter detalhes, [consulte Atribuir uma política de acesso de usuário externo.](assign-an-external-user-access-policy.md)

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política existente usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Skype for Busines Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business Server** e no Shell de Gerenciamento do Skype for Business **Server.**

3.  Digite o seguinte no Shell de Gerenciamento do Skype for Business Server:
    
    ```PowerShell
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > O parâmetro "EnablePublicCloudAudioVideoAccess" não tem uma seleção correspondente no Painel de Controle do Skype for Business Server


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para criar uma nova política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Inicie o Shell de Gerenciamento do Skype for Business Server: Clique em **Iniciar,** Em Todos os **Programas,** clique em **Microsoft Skype for Business Server** e, em seguida, clique no Shell de Gerenciamento do Skype for Business **Server.**

3.  Digite o seguinte no Shell de Gerenciamento do Skype for Business Server:
    
    ```PowerShell
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Um exemplo de criação de uma nova política de site:
    
    ```PowerShell
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para excluir ou redefinir uma política usando o Windows PowerShell para dar suporte ao acesso por usuários de domínios federados

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Digite o seguinte no Shell de Gerenciamento do Skype for Business Server
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Um exemplo de redefinição de política global (A política global somente pode ter sua configuração removida. A política não pode ser excluída):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Para remover uma política de site, digite:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Exclua a política de site de Redmond. Para excluir uma política de usuário chamada UserEAPPolicy, digite:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md)

[Gerenciar domínios SIP federados para sua organização](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gerenciar fornecedores SIP federados para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

