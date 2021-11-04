---
title: Configurar políticas para controle de acesso de usuário remoto
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com usuários internos Skype for Business Server usuários. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, de site e de usuário.
ms.openlocfilehash: 4029a2fe21c4d7a013808cd77b28d670d1bf994f
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60772037"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuários remotos Skype for Business Server

Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com usuários internos Skype for Business Server usuários. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, de site e de usuário. As políticas de site substituem a política global e as políticas de usuário substituem políticas globais e de site. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md). Skype for Business Server configurações de política aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário remoto, mesmo que não tenha habilitado o acesso de usuário remoto para sua organização. No entanto, as políticas que você configurar só estão em vigor quando você tem o acesso de usuário remoto habilitado para sua organização. Além disso, se você especificar uma política de usuário para controlar o acesso de usuário remoto, a política se aplicará somente aos usuários habilitados para Skype for Business Server e configurados para usar a política. Para obter detalhes sobre a especificação de usuários que podem entrar Skype for Business Server locais remotos, consulte Atribuir uma política de acesso de [usuário externo.](assign-an-external-user-access-policy.md)

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso de usuário remoto.


> [!NOTE]  
> Este procedimento descreve como configurar uma política apenas para habilitar comunicações com usuários remotos, mas cada política configurada para dar suporte ao acesso de usuário remoto também pode configurar o acesso de usuário federado e o acesso de usuário público. Para obter detalhes sobre como configurar políticas para dar suporte a usuários federados, consulte [Configure policies to control federated user access in Skype for Business Server](configure-policies-to-control-federated-user-access.md). Para obter detalhes sobre como configurar políticas para dar suporte a usuários públicos, consulte [Manage SIP federated providers for](../sip-providers/manage-sip-federated-providers-for-your-organization.md)your organization in Skype for Business Server .


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuário remoto

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso de usuário remoto, clique na política global, clique em **Editar** e em **Mostrar detalhes.**
    
      - Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.
    
      - Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **Nova** Política de Acesso Externo  , crie um nome exclusivo no campo Nome que indica o que a política de usuário aborda (por exemplo, **EnableRemoteUsers** para uma política de usuário que habilita as comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto à política, marque a caixa de seleção Habilitar **comunicações com usuários remotos.**
    
      - Para desabilitar o acesso de usuário remoto à política, desempure a caixa de seleção **Habilitar comunicações com usuários remotos.**

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte para o acesso de usuário remoto em sua organização. Para obter detalhes, [consulte Enable or disable federation and public IM connectivity](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se essa for uma política de usuário, você também deve aplicar a política aos usuários que deseja conectar remotamente. Para obter detalhes, [consulte Assign an external user access policy](assign-an-external-user-access-policy.md).
