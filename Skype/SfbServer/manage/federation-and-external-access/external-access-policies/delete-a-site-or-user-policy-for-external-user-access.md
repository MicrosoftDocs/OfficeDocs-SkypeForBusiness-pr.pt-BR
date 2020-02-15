---
title: Excluir uma política de site ou de usuário para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
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
description: Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página política de acesso externo.
ms.openlocfilehash: ae0a0499e7497c4d62884860a2730960e5070ac8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041230"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Excluir uma política de site ou de usuário para acesso de usuário externo

Se você criou ou configurou políticas de acesso de usuário externo que não vai mais usar, poderá fazer o seguinte:

  - Excluir qualquer política local ou de usuário que você criou.

  - Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.


Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página **política de acesso externo** . Excluir a política global não causa sua exclusão propriamente dita, mas apenas a redefine para suas configurações padrão, que não incluem suporte para nenhuma opção de acesso de usuário externo. Para obter detalhes sobre como redefinir a política global, consulte [Reset The Global Policy for External User Access](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para excluir uma política de site ou de usuário para o acesso de usuário externo

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel de controle do Skype for Business Server. 

3.  Clique em **Acesso de Usuário Externo**, em **Política de Acesso Externo**.

4.  Na guia **Política de Acesso Externo**, clique na política de site ou de usuário que deseja excluir, clique em **Editar**e em **Excluir**.

5.  Quando for solicitado que você confirme a exclusão, clique em **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para remover uma política de acesso externo específica

  - Este comando remove a política de acesso externo aplicada ao site Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário

  - Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para remover todas as políticas de acesso externo onde o acesso de usuário externo está desabilitado

  - Este comando exclui todas as políticas de acesso externo com acesso de usuário externo desabilitado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .
