---
title: Atribuir políticas de conferência para dar suporte a usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos.
ms.openlocfilehash: 57d100569722cbe89811d15eb9fbe04e5d375711
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817451"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Atribuir políticas de conferência para dar suporte a usuários anônimos no Skype for Business Server 


Por padrão, todos os usuários são impedidos de convidar usuários anônimos a participar de uma reunião. Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para dar suporte a usuários anônimos e aplicando-a a usuários específicos. Para obter detalhes sobre como configurar uma política de conferência para suportar usuários anônimos, consulte Criar políticas de conferência no [Skype for Business Server](../../conferencing/create-policies.md) e gerenciar federação e acesso externo ao Skype for Business [Server.](../managing-federation-and-external-access.md)

Use o procedimento nesta seção para aplicar uma política de conferência que você já tenha criado para um ou mais usuários ou grupos de usuários.

> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte para usuários anônimos da sua organização. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário público no Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para participação anônima em reuniões

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Conferência** e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **Nova** e em **Política de usuário**. Crie um nome  exclusivo no campo Nome que indique o que a política de usuário cobre (por exemplo, **EnableAnonymous** para uma política de usuário que permite comunicações com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar** e em **Mostrar detalhes.**

4.  Na caixa **de diálogo Políticas** de Conferência, marque a caixa de seleção Permitir que os participantes **convidem usuários anônimos.**

5.  Clique em **Confirmar**.

6.  Na barra de navegação esquerda, clique **em Usuários,** pesquise a conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar Usuário do Skype for Business Server** em **Política** de Conferência, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a esse usuário.  

    > [!NOTE]  
    > As <STRONG> &lt; configurações &gt; </STRONG> automáticas aplicam as configurações de instalação padrão do servidor e são aplicadas automaticamente pelo servidor.


Para habilitar usuários para convidar usuários anônimos para conferências, você também deve habilitar o suporte para usuários anônimos em sua organização. Para obter detalhes, [consulte Configurar políticas para controlar o acesso de usuário público no Skype for Business Server.](../external-access-policies/configure-policies-to-control-public-user-access.md)

