---
title: Atribuir políticas de conferência para suporte de usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos.
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818412"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Atribuir políticas de conferência para dar suporte a usuários anônimos no Skype for Business Server 


Por padrão, todos os usuários são impedidos de convidar usuários anônimos para participarem de uma reunião. Você controla quem pode convidar usuários anônimos Configurando uma política de conferência para dar suporte a usuários anônimos e aplicar essa política de conferência a usuários específicos. Para obter detalhes sobre como configurar uma política de conferência para dar suporte a usuários anônimos, consulte [criar políticas de conferência no Skype for Business Server](../../conferencing/create-policies.md) e [gerenciar Federação e acesso externo ao Skype for Business Server](../managing-federation-and-external-access.md).

Use o procedimento desta seção para aplicar uma política de conferência que você já tenha criado a um ou mais usuários ou grupos de usuários.

> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para a sua organização. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para a participação anônima em reuniões

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **novo**e, em seguida, clique em **política de usuário**. Crie um nome exclusivo no campo **nome** que indica a capa da política do usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

4.  Na caixa de diálogo **políticas de conferência** , marque a caixa de seleção **permitir que os participantes convidem usuários anônimos** .

5.  Clique em **Confirmar**.

6.  Na barra de navegação à esquerda, clique em **usuários**e procure a conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar o usuário do Skype for Business Server** em **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.  

    > [!NOTE]  
    > As <STRONG> &lt;configurações&gt; automáticas</STRONG> aplicam as configurações de instalação do servidor padrão e são aplicadas automaticamente pelo servidor.


Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários públicos no Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

