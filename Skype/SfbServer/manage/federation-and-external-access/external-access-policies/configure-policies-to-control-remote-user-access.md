---
title: Configurar políticas para controle de acesso de usuário remoto
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com Skype interna para usuários corporativos Server. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, site e nível de usuário.
ms.openlocfilehash: f6d316f022e671bc7f7e70ebbe2a801b0b3e312c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899530"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário remoto no Skype para Business Server

Você configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários remotos podem colaborar com Skype interna para usuários corporativos Server. Para controlar o acesso de usuário remoto, você pode configurar políticas no nível global, site e nível de usuário. Políticas de site de substituem a política global e site e políticas globais substituem as políticas de usuário. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Managing federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md). Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário remoto, mesmo se você não tiver ativado o acesso de usuário remoto para sua organização. No entanto, as políticas que você definir estão em vigor somente quando você tem acesso de usuário remoto habilitado para sua organização. Além disso, se você especificar uma política de usuário para controlar o acesso de usuário remoto, a política se aplica somente aos usuários que estão habilitados para Skype para Business Server e configurados para usar a política. Para obter detalhes sobre como especificar os usuários que podem se conectar ao Skype para Business Server de locais remotos, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso de usuário remoto.


> [!NOTE]  
> Este procedimento descreve como configurar uma política somente para habilitar as comunicações com usuários remotos, mas cada política que você configurar para suportar o acesso de usuário remoto também pode configurar o acesso de usuário federado e acesso de usuário público. Para obter detalhes sobre como configurar políticas para oferecer suporte a usuários federados, consulte [Configure políticas para controlar federated user access na Skype para Business Server](configure-policies-to-control-federated-user-access.md). Para obter detalhes sobre como configurar políticas para oferecer suporte a usuários públicos, consulte [Gerenciar SIP federated providers para sua organização no Skype para Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para suportar o acesso de usuário remoto

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Política de acesso externo**.

4.  Na página **Política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para suportar o acesso de usuário remoto, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política de Site**. Em **Selecionar um Site**, clique no local apropriado na lista e clique em **Okey**.
    
      - Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**. Na **Nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica que o usuário política abrange (por exemplo, **EnableRemoteUsers** para uma política de usuário que habilita as comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique as informações para a política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para a política, marque a caixa de seleção **Habilitar comunicações com usuários remotos** .
    
      - Para desabilitar o acesso de usuário remoto para a política, desmarque a caixa de seleção **Habilitar comunicações com usuários remotos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte para acesso de usuário remoto em sua organização. Para obter detalhes, consulte [Habilitar ou desabilitar a federação e conectividade IM pública](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se essa for uma política de usuário, você também deve aplicar a política aos usuários que você deseja ser capaz de conectar-se remotamente. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).
