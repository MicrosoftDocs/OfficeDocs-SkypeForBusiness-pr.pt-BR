---
title: Atribuir uma política de acesso de usuário externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um usuário foi habilitado para o Skype for Business Server, você pode configurar a Federação do SIP, o acesso de usuários remotos e a conectividade de mensagens instantâneas públicas no painel de controle do Skype for Business Server, aplicando as políticas apropriadas a usuários específicos.
ms.openlocfilehash: ae8bea38a01f9211fc3338faf3e97f737c99e1a4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280170"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Atribuir uma política de acesso de usuário externo a um usuário habilitado do Skype for Business

Se um usuário foi habilitado para o Skype for Business Server, você pode configurar a Federação do SIP, o acesso de usuários remotos e a conectividade de mensagens instantâneas públicas no painel de controle do Skype for Business Server, aplicando as políticas apropriadas a usuários específicos. Por exemplo, se você criou uma política para dar suporte ao acesso de usuário remoto, deve aplicá-la ao usuário antes que o usuário possa se conectar ao Skype for Business Server de um local remoto e colaborar com usuários internos do local remoto.


> [!NOTE]  
> Para dar suporte ao acesso de usuário externo, você deve habilitar o suporte para cada tipo de acesso de usuário externo ao qual você deseja dar suporte e configurar as políticas adequadas e outras opções para controlar seu uso. Para obter detalhes, consulte [Gerenciamento de Federação e acesso externo ao Skype for Business Server](../managing-federation-and-external-access.md).


Use o procedimento deste tópico para aplicar uma política de acesso externo do usuário criada anteriormente a uma ou mais contas de usuário.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário externa a uma conta de usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar o usuário do Skype for Business Server** na **política de acesso externo**, selecione a política de usuário que você deseja aplicar.
     
> [!NOTE]  
> As configurações do ** \<Automatic>** aplicam as configurações padrão do servidor ou da política global.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Atribuindo políticas de acesso externo por usuário usando cmdlets do Windows PowerShell

Políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para atribuir uma política de acesso externo por usuário a um único usuário

  - Esse comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para atribuir uma política de acesso externo por usuário a vários usuários

  - Esse comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários que têm contas na UO Estados Unidos no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para cancelar a atribuição de uma política de acesso externo por usuário

  - Esse comando cancela a atribuição de qualquer política de acesso externo por usuário atribuída anteriormente a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


