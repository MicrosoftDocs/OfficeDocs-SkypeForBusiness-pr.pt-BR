---
title: Atribuir políticas de conferência para dar suporte a usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos.
ms.openlocfilehash: 31978a997b3344367068c00978de9257585c6d4b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399705"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Atribuir políticas de conferência para dar suporte a usuários anônimos Skype for Business Server 


Por padrão, todos os usuários são impedidos de convidar usuários anônimos a participar de uma reunião. Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos. Para obter detalhes sobre como configurar uma política de conferência para dar suporte a usuários anônimos, consulte [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).

Use o procedimento nesta seção para aplicar uma política de conferência que você já criou a um ou mais usuários ou grupos de usuários.

> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte para usuários anônimos para sua organização. Para obter detalhes, consulte [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para participação anônima em reuniões

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Conferência** e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Crie um nome exclusivo no campo **Nome** que indica o que a política de usuário abrange (por exemplo, **EnableAnonymous** para uma política de usuário que habilita as comunicações com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar** e em **Mostrar detalhes**.

4.  Na caixa **de diálogo Políticas de** Conferência, marque a caixa de seleção **Permitir que os participantes convidem usuários anônimos** .

5.  Clique em **Confirmar**.

6.  Na barra de navegação esquerda, clique em **Usuários**, pesquise na conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar Skype for Business Server Usuário** em **Política** de Conferência, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a esse usuário.  

    > [!NOTE]  
    > As <STRONG>&lt;configurações&gt;</STRONG> automáticas aplicam as configurações de instalação padrão do servidor e são aplicadas automaticamente pelo servidor.


Para habilitar usuários para convidar usuários anônimos para conferências, você também deve habilitar o suporte para usuários anônimos em sua organização. Para obter detalhes, consulte [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

