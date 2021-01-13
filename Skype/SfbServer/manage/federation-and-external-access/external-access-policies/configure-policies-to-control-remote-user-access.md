---
title: Configurar políticas para controle de acesso de usuário remoto
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
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
description: Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com usuários internos do Skype for Business Server. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, de site e de usuário.
ms.openlocfilehash: 0fd24f7c57cfaa4a131bcd1648cb1b6e6eb5f05a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817291"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário remoto no Skype for Business Server

Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com usuários internos do Skype for Business Server. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, de site e de usuário. As políticas de site substituem a política global, e as políticas de usuário substituem as políticas de site e globais. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte Gerenciando federação [e acesso externo ao Skype for Business Server.](../managing-federation-and-external-access.md) As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário remoto, mesmo se não tiver habilitado o acesso de usuário remoto para sua organização. No entanto, as políticas que você configurar só entrarão em vigor quando você tiver o acesso de usuário remoto habilitado para sua organização. Além disso, se você especificar uma política de usuário para controlar o acesso de usuário remoto, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários que podem entrar no Skype for Business Server a partir de locais remotos, consulte Atribuir uma [política de acesso de usuário externo.](assign-an-external-user-access-policy.md)

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso de usuário remoto.


> [!NOTE]  
> Este procedimento descreve como configurar uma política apenas para permitir comunicações com usuários remotos, mas cada política configurada para suportar o acesso de usuário remoto também pode configurar o acesso de usuário federado e o acesso de usuário público. Para obter detalhes sobre como configurar políticas para suportar usuários federados, consulte Configurar políticas para controlar o acesso de usuário [federado no Skype for Business Server.](configure-policies-to-control-federated-user-access.md) Para obter detalhes sobre como configurar políticas para suportar usuários públicos, consulte [Gerenciar provedores SIP federados](../sip-providers/manage-sip-federated-providers-for-your-organization.md)para sua organização no Skype for Business Server.


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuário remoto

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo** e em **Política de Acesso Externo**.

4.  Na página **Política de Acesso Externo**, execute um dos seguintes procedimentos:
    
      - Para configurar a política global para suportar o acesso de usuário remoto, clique na política global, clique em **Editar** e em **Mostrar detalhes.**
    
      - Para criar uma nova política de site, clique em **Nova** e em **Política de site**. Em **Selecionar um Site**, clique no site apropriado na lista e em **OK**.
    
      - Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Em **Nova** Política de Acesso Externo,  crie um nome exclusivo no campo Nome que indica o que a política de usuário abrange (por exemplo, **EnableRemoteUsers** para uma política de usuário que permite comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar** e em **Exibir detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique a informação da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto à política, marque a caixa de seleção Habilitar **comunicações com usuários remotos.**
    
      - Para desabilitar o acesso de usuário remoto à política, des limpe a caixa de seleção Habilitar **comunicações com usuários remotos.**

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte para acesso de usuário remoto em sua organização. Para obter detalhes, [consulte Habilitar ou desabilitar federação e conectividade de IM pública.](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md)

Se esta for uma política de usuário, você também deverá aplicar a política aos usuários que você deseja que se conectem remotamente. Para obter detalhes, [consulte Atribuir uma política de acesso de usuário externo.](assign-an-external-user-access-policy.md)
