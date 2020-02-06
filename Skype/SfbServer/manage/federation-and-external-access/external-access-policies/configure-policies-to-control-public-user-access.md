---
title: Configurar políticas para controlar o acesso de usuário público
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
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
description: a conectividade de mensagens de chat (IM) do ublic permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com os usuários de serviços de mensagens instantâneas fornecidos pelos provedores de serviço de IM públicos.
ms.openlocfilehash: d661ca9a4ef7840cbc955d0c999ae5a1490a63cb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818302"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuários públicos no Skype for Business Server

A conectividade de mensagens instantâneas públicas permite que os usuários em sua organização usem mensagens instantâneas para se comunicar com usuários de serviços de mensagens instantâneas fornecidos por provedores de serviço de mensagens de chat públicas. Você pode configurar uma ou mais políticas de acesso de usuários externos para controlar se os usuários públicos podem colaborar com usuários internos do Skype for Business Server. A conectividade de mensagens instantâneas públicas é um recurso adicionado que depende da configuração da sua implantação e dos usuários. Ele também depende do provisionamento do serviço no provedor público de IM. 

Para controlar o acesso do usuário público, você pode configurar políticas nos níveis global, de site e de usuário. As configurações de política do Skype for Business Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência de política do Skype for Business Server é: a política do usuário (maior influência) substitui uma política do site e, em seguida, uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

No caso de convites por mensagem instantânea, a resposta depende do software cliente. A solicitação é aceita, a menos que remetentes externos sejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações nas listas **permitir** e **Bloquear** do cliente do usuário). Além disso, os convites de mensagem instantânea podem ser bloqueados se um usuário optar por bloquear todas as mensagens instantâneas de usuários que não estão na sua lista de **permissões** .



> [!NOTE]  
> Você pode configurar políticas para controlar o acesso ao usuário público, mesmo se você não tiver habilitado a Federação para sua organização. No entanto, as políticas que você configura são efetivadas apenas quando você tem a Federação habilitada para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte [habilitar ou desabilitar o acesso de usuários remotos](../access-edge/enable-or-disable-remote-user-access.md). Além disso, se você especificar uma política de usuário para controlar o acesso ao usuário público, a política se aplicará somente aos usuários habilitados para o Skype for Business Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários públicos que podem entrar no Skype for Business Server, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).


Use o procedimento a seguir para configurar uma política para dar suporte ao acesso por usuários de um ou mais provedores de mensagens de chat públicos.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar uma política de acesso externo para dar suporte ao acesso de usuários públicos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **política de acesso externo**.

4.  Na página **política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para dar suporte ao acesso a usuários públicos, clique na política global, clique em **Editar**e clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política do site**. Em **selecionar um site**, clique no site apropriado na lista e, em seguida, clique em **OK**.
    
      - Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Em **nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indique a capa da política do usuário (por exemplo, **EnablePublicUsers** para uma política de usuário que permita comunicações para usuários públicos).
    
      - Para alterar uma política existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Adicionais Se você quiser adicionar ou editar uma descrição, especifique as informações da política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário público para a política, marque a caixa de seleção **habilitar comunicações com usuários públicos** .
    
      - Para desabilitar o acesso de usuário público para a política, desmarque a caixa de seleção **habilitar comunicações com usuários públicos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário público, você também deve habilitar o suporte para Federação em sua organização. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Skype for Business Server](configure-policies-to-control-federated-user-access.md).

Se esta for uma política de usuário, você também deverá aplicar a política a usuários públicos que você deseja que possam colaborar com usuários públicos. 


## <a name="see-also"></a>Confira também

[Gerenciar fornecedores SIP federados para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
