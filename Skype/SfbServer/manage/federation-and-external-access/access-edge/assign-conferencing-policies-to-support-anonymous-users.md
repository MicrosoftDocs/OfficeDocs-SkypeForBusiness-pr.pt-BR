---
title: Atribuir políticas de conferência para suporte de usuários anônimos
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para oferecer suporte a usuários anônimos e aplicar essa política de conferência para usuários específicos.
ms.openlocfilehash: 62ff84b19fadbeaf0f26fa3e5869026254d28d1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881124"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a>Atribuir políticas de conferência para oferecer suporte aos usuários anônimos Skype para Business Server 


Por padrão, todos os usuários são impedidos de convidem usuários anônimos para participar de uma reunião. Você controla quem pode convidar usuários anônimos, configurando uma política de conferência para oferecer suporte a usuários anônimos e aplicar essa política de conferência para usuários específicos. Para obter detalhes sobre como configurar um políticas de conferência para oferecer suporte a usuários anônimos, consulte [criar políticas de conferência no Skype para Business Server](../../conferencing/create-policies.md) e [Managing federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md).

Use o procedimento desta seção para aplicar uma política de conferência que você criou a um ou mais usuários ou grupos de usuários.

> [!NOTE]  
> Além de configurar e aplicar uma política para permitir que os usuários convidem usuários anônimos, você também deve habilitar o suporte a usuários anônimos para sua organização. Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário público na Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a>Para configurar uma política de usuário para participação anônima em reuniões

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação à esquerda, clique em **conferência**e siga um destes procedimentos:
    
    1.  Para criar uma nova política de usuário, clique em **novo**e clique em **política de usuário**. Crie um nome exclusivo no campo **nome** que indica o que aborda a política de usuário (por exemplo, **EnableAnonymous** para uma política de usuário que permite a comunicação com usuários anônimos).
    
    2.  Para configurar uma política de usuário existente, clique na política apropriada listada na tabela, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

4.  Na caixa de diálogo **Diretivas de conferência** , marque a caixa de seleção **Permitir que os participantes convidem usuários anônimos** .

5.  Clique em **Confirmar**.

6.  Na barra de navegação à esquerda, clique em **usuários**e pesquise a conta de usuário que você deseja configurar.

7.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

8.  Em **Editar Skype para usuário de servidor de negócios** em **política de conferência**, selecione a política de usuário com a configuração de acesso de usuário anônimo que você deseja aplicar a este usuário.  

    > [!NOTE]  
    > O <STRONG> &lt;automática&gt; </STRONG> configurações se aplicam as configurações de instalação de servidor padrão e são aplicadas automaticamente pelo servidor.


Para permitir que os usuários convidem usuários anônimos para conferências, você também deve habilitar o suporte a usuários anônimos em sua organização. Para obter detalhes, consulte [Configure políticas para controlar o acesso de usuário público na Skype para Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).

