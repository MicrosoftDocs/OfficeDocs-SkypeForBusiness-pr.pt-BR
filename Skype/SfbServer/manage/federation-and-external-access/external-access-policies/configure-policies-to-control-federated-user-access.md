---
title: Configurar políticas para controlar acesso de usuário federado
ms.reviewer: ''
ms:assetid: 5485e208-81e4-4e59-9aeb-1232c11dd8a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398359(v=OCS.15)
ms:contentKeyID: 48184180
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Quando você configura políticas para suportar a comunicação com parceiros federados, as diretivas serão aplicadas aos usuários de domínios federados. '
ms.openlocfilehash: 81eced8db10c9ffd017b5b79a54980b773b300bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920655"
---
# <a name="configure-policies-to-control-federated-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário federado na Skype para Business Server

Quando você configura políticas para suportar a comunicação com parceiros federados, as diretivas serão aplicadas aos usuários de domínios federados. Você pode configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários de domínios federados podem colaborar com sua Skype para usuários corporativos Server. Para controlar o acesso de usuário federado, você pode configurar políticas no nível global, site e nível de usuário. Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.


> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário federado, mesmo se você não tiver habilitado a federação para sua organização. No entanto, as políticas que você definir estão em vigor somente quando você tem a federação habilitada para sua organização. Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md).  Além disso, se você especificar uma política de usuário para controlar o acesso de usuário federado, a política se aplica somente aos usuários que estão habilitados para Skype para Business Server e configurados para usar a política.


## <a name="to-configure-a-policy-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política para suportar o acesso por usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Política de acesso externo**.

4.  Na página **Política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para suportar o acesso de usuário federado, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política de Site**. Em **Selecionar um Site**, clique no local apropriado na lista e clique em **Okey**.
    
      - Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**. Na **Nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica que o usuário política abrange (por exemplo, **EnableFederatedUsers** para uma política de usuário que permite a comunicação aos usuários de domínio federado).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique as informações para a política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado para a política, marque a caixa de seleção **Habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado para a política, desmarque a caixa de seleção **Habilitar comunicações com usuários federados** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para federação na sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar a federação e conectividade IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se essa for uma política de usuário, você também deve aplicar a política aos usuários que você deseja pudessem colaborar com usuários federados. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).

## <a name="to-configure-an-existing-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para configurar uma política existente usando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Skype para visita do Shell de gerenciamento do servidor: clique em **Iniciar**, clique em **Todos os programas**, clique em **Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de Business**.

3.  Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios:
    
    ```
    Set-CsExternalAccessPolicy -Identity <name of global, site or user policy - policy must exist when using Set-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAcess <$true, $false> -EnablePublicCloudAudioVideoAcess <$true, $false> -EnableOutsideAcess <$true, $false>
    ```
       

    > [!TIP]  
    > O parâmetro "EnablePublicCloudAudioVideoAccess" não possui uma seleção correspondente no Skype para painel de controle do servidor de negócios


## <a name="to-create-a-new-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para criar uma nova política utilizando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Inicie o Skype do Shell de gerenciamento do servidor de negócios: clique em **Iniciar**, clique em **Todos os programas**, clique em **Microsoft Skype para Business Server**e clique em **Skype do Shell de gerenciamento do servidor de negócios**.

3.  Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios:
    
    ```
    New-CsExtenalAccessPolicy -Identity <name of site or user policy - you cannot create a new global policy using New-CsExternalAccessPolicy > -Description <descriptive name for policy> -EnableFederationAccess <$true, $false> -EnableXmppAccess <$true, $false> -EnablePublicCloudAccess <$true, $false> -EnablePublicCloudAudioVideoAccess <$true, $false> -EnableOutsideAccess <$true, $false>
    ```
    
    Um exemplo de como criar uma nova política de site:
    
    ```
    New-CsExternalAccessPolicy -Identity site:Redmond -EnableFederationAccess $true -EnableXmppAccess $true -EnableOutsideAccess $true -EnablePublicCloudAccess $true -EnablePublicCloudAudioVideoAccess $true
    ```


## <a name="to-delete-or-reset-a-policy-using-windows-powershell-to-support-access-by-users-of-federated-domains"></a>Para excluir ou redefinir uma política utilizando o Windows PowerShell para suportar o acesso pelos usuários de domínios federados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Digite o seguinte no Skype do Shell de gerenciamento do servidor de negócios
    
    `Remove-CsExternalAccessPolicy -Identity <name of global, site or user policy>`
    
    Um exemplo de redefinido a política global (a política global só pode ter sua configuração removidos. A diretiva não pode ser excluída):
    
    `Remove-CsExternalAccessPolicy -Identity global`
    
    Para remover uma política de site, digite:
    
    `Remove-CsExternalAccessPolicy -Identity site:Redmond` 
    
    Exclui a política de site de Redmond. Para excluir uma política de usuário chamada UserEAPPolicy, digite:
    
    `Remove-CsExternalAccessPolicy -Identity UserEAPPolicy`


## <a name="see-also"></a>Confira também


[Habilitar ou desabilitar federação e conectividade de IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md) 

[Atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md)

[Gerenciar domínios SIP federados para sua organização](../sip-domains/manage-sip-federated-domains-for-your-organization.md)
 
[Gerenciar fornecedores SIP federados para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md)

[Set-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsExternalAccessPolicy)  
[New-CsExternalAccessPolicy.](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsExternalAccessPolicy)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy)  
[Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)  
  

