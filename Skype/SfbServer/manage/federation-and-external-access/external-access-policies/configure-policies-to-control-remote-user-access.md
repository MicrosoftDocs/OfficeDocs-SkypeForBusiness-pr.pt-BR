---
title: Configurar políticas para controle de acesso de usuário remoto
ms.reviewer: ''
ms:assetid: 8f556849-692b-44a0-9514-4468fc9a39d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398725(v=OCS.15)
ms:contentKeyID: 48184825
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários remotos podem colaborar com usuários internos do Skype for Business Server. Para controlar o acesso do usuário remoto, você pode configurar políticas nos níveis global, de site e de usuário.
ms.openlocfilehash: 7735f15e61654f55a70f18ca032cd6b1613fec58
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818292"
---
# <a name="configure-policies-to-control-remote-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuários remotos no Skype for Business Server

Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários remotos podem colaborar com usuários internos do Skype for Business Server. Para controlar o acesso do usuário remoto, você pode configurar políticas nos níveis global, de site e de usuário. Políticas de site substituem a política global e as políticas de usuário substituem políticas globais e do site. Para obter detalhes sobre os tipos de políticas que você pode configurar, consulte [Gerenciamento de Federação e acesso externo ao Skype for Business Server](../managing-federation-and-external-access.md). As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

> [!NOTE]  
> Você pode configurar políticas para controlar o acesso do usuário remoto, mesmo se você não tiver habilitado o acesso de usuário remoto para a sua organização. No entanto, as políticas que você configura são efetivadas apenas quando você tem acesso de usuário remoto habilitado para sua organização. Além disso, se você especificar uma política de usuário para controlar o acesso do usuário remoto, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política. Para obter detalhes sobre como especificar os usuários que podem entrar no Skype for Business Server de locais remotos, consulte [atribuir uma política de acesso a usuários externos](assign-an-external-user-access-policy.md).

Use o procedimento a seguir para configurar cada política de acesso externo que você deseja usar para controlar o acesso do usuário remoto.


> [!NOTE]  
> Este procedimento descreve como configurar uma política somente para permitir comunicações com usuários remotos, mas cada política que você configura para dar suporte ao acesso de usuário remoto também pode configurar o acesso de usuário federado e acesso de usuário público. Para obter detalhes sobre como configurar políticas para dar suporte a usuários federados, consulte [Configurar políticas para controlar o acesso de usuários federados no Skype for Business Server](configure-policies-to-control-federated-user-access.md). Para obter detalhes sobre como configurar as políticas para dar suporte a usuários públicos, consulte [gerenciar provedores federados SIP para sua organização no Skype for Business Server](../sip-providers/manage-sip-federated-providers-for-your-organization.md).


## <a name="to-configure-an-external-access-policy-to-support-remote-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuários remotos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso de usuário remoto, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnableRemoteUsers** para uma política de usuário que permita comunicações para usuários remotos).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para a política, marque a caixa de seleção **habilitar comunicações com usuários remotos** .
    
      - Para desabilitar o acesso de usuário remoto para a política, desmarque a caixa de seleção **habilitar comunicações com usuários remotos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário remoto, você também deve habilitar o suporte ao acesso de usuários remotos em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar a conectividade de mensagens de chat públicas e de Federação](../access-edge/enable-or-disable-federation-and-public-im-connectivity.md).

Se esta for uma política de usuário, você também deverá aplicar a política aos usuários para os quais você deseja poder se conectar remotamente. Para obter detalhes, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).
