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
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se um usuário tiver sido habilitado para Skype para Business Server, você pode configurar a federação SIP, acesso de usuário remoto e pública mensagens instantâneas conectividade (IM) no Skype para painel de controle do Business Server, aplicando as políticas adequadas a usuários específicos.
ms.openlocfilehash: 7a2563900ae72bf57b26b5eff9997f3d1c65a71e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920672"
---
# <a name="assign-an-external-user-access-policy-to-a-skype-for-business-enabled-user"></a>Atribuir uma política de acesso de usuário externo a um Skype para usuário comercial habilitado

Se um usuário tiver sido habilitado para Skype para Business Server, você pode configurar a federação SIP, acesso de usuário remoto e pública mensagens instantâneas conectividade (IM) no Skype para painel de controle do Business Server, aplicando as políticas adequadas a usuários específicos. Por exemplo, se você criou uma política para suportar o acesso de usuário remoto, você deve aplicá-lo ao usuário antes que o usuário pode se conectar ao Skype para Business Server de um local remoto e colaborar com usuários internos do local remoto.


> [!NOTE]  
> Para suportar o acesso de usuário externo, você deve habilitar o suporte para cada tipo de acesso de usuário externo que você deseja suportar e configurar as políticas adequadas e outras opções para controlar seu uso. Para obter detalhes, consulte [Gerenciando federação e acesso externo à Skype para Business Server](../managing-federation-and-external-access.md).


Use o procedimento neste tópico para aplicar uma política de acesso de usuário externo criada anteriormente para uma ou mais contas de usuário.


## <a name="to-apply-an-external-user-policy-to-a-user-account"></a>Para aplicar uma política de usuário externo para uma conta de usuário

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.

4.  Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.

5.  Em **Editar Skype para usuário de servidor de negócios** em **política de acesso externo**, selecione a política de usuário que você deseja aplicar.
     
> [!NOTE]  
> O ** \<Automatic>** configurações se aplicam as configurações de política global ou de servidor padrão.


## <a name="assigning-per-user-external-access-policies-by-using-windows-powershell-cmdlets"></a>Atribuindo políticas de acesso externo por usuário usando Cmdlets do Windows PowerShell

Políticas de acesso externo por usuário podem ser atribuídas usando o Windows PowerShell e o cmdlet Grant-CsExternalAccessPolicy. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

## <a name="to-assign-a-per-user-external-access-policy-to-a-single-user"></a>Para atribuir uma política de acesso externo por usuário a um único usuário

  - Este comando atribui a política de acesso externo por usuário RedmondExternalAccessPolicy ao usuário Ken Myer.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName "RedmondExternalAccessPolicy"


## <a name="to-assign-a-per-user-external-access-policy-to-multiple-users"></a>Para atribuir uma política de acesso externo por usuário a vários usuários

  - Este comando atribui a política de acesso externo por usuário USAExternalAccessPolicy a todos os usuários que tiverem contas na unidade Organizacional Estados Unidos no Active Directory. Para obter mais informações sobre o parâmetro OU usado neste comando, consulte a documentação para o cmdlet [Get-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUser) .
    
        Get-CsUser -OU "ou=UnitedStates,dc=litwareinc,dc=com" | Grant-CsExternalAccessPolicy -PolicyName "USAExternalAccessPolicy"


## <a name="to-unassign-a-per-user-external-access-policy"></a>Para retirar a atribuição de uma política de acesso externo por usuário

  - Este comando remove a atribuição de qualquer política de acesso externo por usuário previamente atribuída a Ken Myer. Após a política por usuário ser retirada, Ken irá automaticamente ser gerenciado usando a política global ou, se existir, sua política de site local. Uma política de site tem precedência sobre a política global.
    
        Grant-CsExternalAccessPolicy -Identity "Ken Myer" -PolicyName $Null



Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy) .


