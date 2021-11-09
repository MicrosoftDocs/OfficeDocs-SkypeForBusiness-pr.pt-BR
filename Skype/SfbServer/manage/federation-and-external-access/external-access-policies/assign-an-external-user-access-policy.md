---
title: Atribuir uma política de acesso de usuário externo
ms.reviewer: ''
ms:assetid: 736fcaad-9f95-4896-b767-e199d86a00a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398551(v=OCS.15)
ms:contentKeyID: 48184483
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Se um usuário tiver sido habilitado para Skype for Business Server, você poderá configurar a federação SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas públicas (IM) no Painel de Controle Skype for Business Server aplicando as políticas apropriadas a usuários específicos.
ms.openlocfilehash: 400c49dfc7d0c893af98a8da7bc53894a39d6a9a
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843914"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Atribuir uma política de acesso de usuário externo a um Skype for Business usuário habilitado

Se um usuário tiver sido habilitado para Skype for Business Server, você poderá configurar a federação SIP, o acesso de usuário remoto e a conectividade de mensagens instantâneas públicas (IM) no Painel de Controle Skype for Business Server aplicando as políticas apropriadas a usuários específicos. Por exemplo, se você criou uma política para dar suporte ao acesso de usuário remoto, você deve aplicá-la ao usuário antes que o usuário possa se conectar ao Skype for Business Server de um local remoto e colaborar com usuários internos do local remoto.


> [!NOTE]  
> Para oferecer suporte ao acesso de usuário externo, você deve ativar o suporte para cada tipo de acesso de usuário externo ao qual deseja oferecer suporte e configurar as políticas apropriadas e outras opções para controlar o uso. Para obter detalhes, consulte [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).


Use o procedimento neste tópico para aplicar uma política de acesso de usuário externo criada anteriormente para uma ou mais contas de usuário.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário externo a uma conta de usuário

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar Skype for Business Server Usuário em** Política de acesso **externo,** selecione a política de usuário que você deseja aplicar.
     
> [!NOTE]  
> As configurações aplicam as configurações de política global ou servidor **\<Automatic>** padrão.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Atribuir Per-User políticas de acesso externo usando Windows PowerShell cmdlets

As políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy usuário. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para atribuir uma política de acesso externo por usuário a um único usuário

  - Este comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para atribuir uma política de acesso externo por usuário a vários usuários

  - Este comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários com contas no OU UnitedStates no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação do cmdlet [Get-CsUser.](/powershell/module/skype/Get-CsUser)<br/><br/>Get-CsUser -OU "ou=Estados Unidos,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para desaignar uma política de acesso externo por usuário

  - Este comando cancela a atribuição de qualquer política de acesso externo por usuário atribuída a Ken Myer. Após o cancelamento da atribuição da política por usuário, Ken Myer será automaticamente gerenciado usando a política global ou a política de site local (se houver). Um política de site tem prioridade sobre a política global.<br/><br/>Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsExternalAccessPolicy.](/powershell/module/skype/Grant-CsExternalAccessPolicy)
