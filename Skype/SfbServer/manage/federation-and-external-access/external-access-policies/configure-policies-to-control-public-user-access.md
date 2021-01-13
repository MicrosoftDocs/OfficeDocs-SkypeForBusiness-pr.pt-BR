---
title: Configurar políticas para controlar o acesso de usuário público
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: A conectividade ublic de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores de serviços públicos de mensagens instantâneas.
ms.openlocfilehash: 28bb1c94cb42068fe99f07a6608a3ac1c50991ad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823582"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário público no Skype for Business Server

A conectividade pública de mensagens instantâneas (IM) permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores de serviços públicos de mensagens instantâneas. Você configura uma ou mais políticas de acesso de usuário externo para controlar se os usuários públicos podem colaborar com usuários internos do Skype for Business Server. A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração de sua implantação e dos usuários. Também depende do provisionamento do serviço no provedor de IM público. 

Para controlar o acesso do usuário público, é possível configurar políticas no nível global, site e de usuário. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Skype for Business Server é: políticas de usuário (maior influência) substituem políticas de site, e políticas de site substituem políticas globais (menor influência). Isso significa que quanto mais próxima a configuração da política estiver do objeto que a política estiver afetando, maior será a influência sobre o objeto.

No caso de convites de IM, a resposta depende do software cliente. A solicitação é aceita a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas de cliente **Permitir** e **Bloquear** do usuário). Além disso, os convites de IM podem ser bloqueados se um usuário optar por bloquear toda IM de usuários que não estão na lista **Permitir**.



> [!NOTE]  
> É possível configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a federação para sua organização. No entanto, as políticas configuradas entram em vigor somente quando a federação está habilitada para sua organização. Para obter detalhes sobre como habilitar a federação, [consulte Habilitar ou desabilitar o acesso de usuário remoto.](../access-edge/enable-or-disable-remote-user-access.md) Além disso, se você especificar uma política de usuário para controlar o acesso de usuário público, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários públicos que podem entrar no Skype for Business Server, consulte Atribuir uma política de acesso de [usuário externo.](assign-an-external-user-access-policy.md)


Use o procedimento a seguir para configurar uma política para suportar o acesso de usuários de um ou mais provedores de IM público.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar uma política de acesso externo para suportar o acesso de usuário público

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

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

Para habilitar o acesso do usuário público, você também deve habilitar o suporte para federação em sua organização. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário federado no Skype for Business Server.](configure-policies-to-control-federated-user-access.md)

Se for uma política de usuário, também será necessário aplicar a política aos usuários públicos para os quais você deseja permitir a colaboração com usuários públicos. 


## <a name="see-also"></a>Confira também

[Gerenciar fornecedores SIP federados para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
