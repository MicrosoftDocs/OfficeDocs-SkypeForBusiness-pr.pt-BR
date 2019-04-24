---
title: Configurar políticas para controlar o acesso de usuário público
ms.reviewer: ''
ms:assetid: 090aea0f-ef0b-49da-9c80-02d9279f2fa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520946(v=OCS.15)
ms:contentKeyID: 48183343
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: úblicos conectividade (IM) de mensagens instantâneos permite que os usuários em sua organização usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviços IM públicos.
ms.openlocfilehash: 3ed19bf692ccc7dfc39466e304b3b1371164758c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197608"
---
# <a name="configure-policies-to-control-public-user-access-in-skype-for-business-server"></a>Configurar políticas para controlar o acesso de usuário público na Skype para Business Server

Conectividade pública de instantâneas (IM) de mensagens permite aos usuários em sua organização usar mensagens Instantâneas para se comunicar com usuários de serviços de IM fornecidos por provedores de serviços IM públicos. Você configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários públicos podem colaborar com Skype interna para usuários corporativos Server. Conectividade pública de mensagens instantânea é um recurso adicionado depende da configuração de sua implantação e usuários. Ele também depende do provisionamento do serviço no provedor de IM público. 

Para controlar o acesso de usuário público, você pode configurar políticas no nível global, site e nível de usuário. Skype para configurações de diretiva de servidor de negócios que são aplicados em um nível de política pode substituir as configurações que são aplicadas no nível de política de outro. Skype para precedência da diretiva Business Server é: política de usuário (maior influência) substitui uma política de Site e, em seguida, uma política de Site substitui uma política Global (influência mínimos). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto.

No caso de convites para mensagens Instantâneas, a resposta depende do software do cliente. A solicitação é aceita, a menos que remetentes externos estejam explicitamente bloqueados por uma regra configurada pelo usuário (ou seja, as configurações no cliente do usuário **Permitir** e listas de **bloqueio** ). Além disso, os convites para mensagens Instantâneas poderão ser bloqueados se um usuário optar por bloquear todas as mensagens Instantâneas de usuários que não estejam em sua lista de **permissões** .



> [!NOTE]  
> Você pode configurar políticas para controlar o acesso de usuário público, mesmo se você não tiver habilitado a federação para sua organização. No entanto, as políticas que você definir estão em vigor somente quando você tem a federação habilitada para sua organização. Para obter detalhes sobre como habilitar a federação, consulte [Habilitar ou desabilitar o acesso de usuário remoto](../access-edge/enable-or-disable-remote-user-access.md). Além disso, se você especificar uma política de usuário para controlar o acesso de usuário público, a política se aplica somente aos usuários que estão habilitados para Skype para Business Server e configurados para usar a política. Para obter detalhes sobre como especificar usuários públicos que podem se conectar ao Skype para Business Server, consulte [atribuir uma política de acesso de usuário externo](assign-an-external-user-access-policy.md).


Use o procedimento a seguir para configurar uma política para suportar o acesso pelos usuários de um ou mais provedores públicos de IM.

## <a name="to-configure-an-external-access-policy-to-support-public-user-access"></a>Para configurar uma política de acesso externo para suportar o acesso de usuário público

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**e, em seguida, clique em **Política de acesso externo**.

4.  Na página **Política de acesso externo** , siga um destes procedimentos:
    
      - Para configurar a política global para suportar o acesso de usuário público, clique na política global, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.
    
      - Para criar uma nova política de site, clique em **novo**e, em seguida, clique em **política de Site**. Em **Selecionar um Site**, clique no local apropriado na lista e clique em **Okey**.
    
      - Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**. Na **Nova política de acesso externo**, crie um nome exclusivo no campo **nome** que indica que o usuário política abrange (por exemplo, **EnablePublicUsers** para uma política de usuário que permite a comunicação aos usuários públicos).
    
      - Para alterar uma política existente, clique na política adequada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  (Opcional) Se você deseja adicionar ou editar uma descrição, especifique as informações para a política em **Descrição**.

6.  Siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário público para a política, marque a caixa de seleção **Habilitar comunicações com usuários públicos** .
    
      - Para desabilitar o acesso de usuário público para a política, desmarque a caixa de seleção **Habilitar comunicações com usuários públicos** .

7.  Clique em **Confirmar**.

Para habilitar o acesso de usuário público, você também deve habilitar o suporte para federação na sua organização. Para obter detalhes, consulte [Configure políticas para controlar federated user access na Skype para Business Server](configure-policies-to-control-federated-user-access.md).

Se essa for uma política de usuário, você também deve aplicar a política aos usuários públicos que você deseja pudessem colaborar com usuários públicos. 


## <a name="see-also"></a>Consulte Também

[Gerenciar fornecedores SIP federados para sua organização](../sip-providers/manage-sip-federated-providers-for-your-organization.md)
