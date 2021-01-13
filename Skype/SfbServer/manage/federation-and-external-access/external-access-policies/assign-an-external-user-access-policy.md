---
title: Atribuir uma política de acesso de usuário externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
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
description: Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá configurar a federação SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas (IM) públicas no Painel de Controle do Skype for Business Server aplicando as políticas apropriadas a usuários específicos.
ms.openlocfilehash: 25e9a63363dc4f982e142defd2164c2423471961
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826621"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Atribuir uma política de acesso de usuário externo a um usuário habilitado para o Skype for Business

Se um usuário tiver sido habilitado para o Skype for Business Server, você poderá configurar a federação SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas (IM) públicas no Painel de Controle do Skype for Business Server aplicando as políticas apropriadas a usuários específicos. Por exemplo, se você criou uma política para suportar o acesso de usuário remoto, deve aplicá-la ao usuário antes que o usuário possa se conectar ao Skype for Business Server de um local remoto e colaborar com usuários internos do local remoto.


> [!NOTE]  
> Para oferecer suporte ao acesso de usuário externo, você deve ativar o suporte para cada tipo de acesso de usuário externo ao qual deseja oferecer suporte e configurar as políticas apropriadas e outras opções para controlar o uso. Para obter detalhes, [consulte Gerenciando federação e acesso externo ao Skype for Business Server](../managing-federation-and-external-access.md).


Use o procedimento neste tópico para aplicar uma política de acesso de usuário externo criada anteriormente para uma ou mais contas de usuário.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário externo a uma conta de usuário

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar Usuário do Skype for Business Server em** Política de acesso **externo,** selecione a política de usuário que você deseja aplicar.
     
> [!NOTE]  
> As **\<Automatic>** configurações aplicam as configurações de política global ou de servidor padrão.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Atribuindo Per-User políticas de acesso externo usando cmdlets do Windows PowerShell

As políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o Grant-CsExternalAccessPolicy cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para atribuir uma política de acesso externo por usuário a um único usuário

  - Este comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para atribuir uma política de acesso externo por usuário a vários usuários

  - Este comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários com contas no OU UnitedStates no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser.](https://docs.microsoft.com/powershell/module/skype/Get-CsUser)
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para desa designar uma política de acesso externo por usuário

  - Este comando cancela a atribuição de qualquer política de acesso externo por usuário atribuída a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global ou a política de site local (se houver). Um política de site tem prioridade sobre a política global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)


