---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
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
localization_priority: Normal
description: Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página de política de acesso externo.
ms.openlocfilehash: 615df309088a329e07f5417dce16e98366a371c7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280121"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Excluir um site ou uma política de usuário para acesso de usuário externo

Se você criou ou configurou políticas de acesso externo do usuário que não deseja mais usar, pode fazer o seguinte:

  - Exclua qualquer site ou política de usuário que você criou.

  - Redefina a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.


Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Skype for Business Server na página de **política de acesso externo** . A exclusão da política global não a exclui realmente, mas só a redefine para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo. Para obter detalhes sobre como redefinir a política global, consulte [redefinir a política global para acesso de usuários externos](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para excluir uma política de site ou de usuário para acesso de usuário externo

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server. 

3.  Clique em **acesso de usuário externo**, clique em **política de acesso externo**.

4.  Na guia **política de acesso externo** , clique no site ou na política de usuário que você deseja excluir, clique em **Editar**e, em seguida, clique em **excluir**.

5.  Quando for solicitado a confirmar a exclusão, clique em **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Skype for Business Server ou em uma sessão remota do Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para remover uma política de acesso externo específica

  - Este comando Remove a política de acesso externo aplicada ao site Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário

  - Esse comando Remove todas as políticas de acesso externo configuradas no escopo por usuário:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para remover todas as políticas de acesso externo em que o acesso do usuário externo está desabilitado

  - Este comando exclui todas as políticas de acesso externo em que o acesso de usuário externo foi desabilitado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
