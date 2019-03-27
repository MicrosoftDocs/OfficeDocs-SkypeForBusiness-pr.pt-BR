---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode excluir qualquer política de site ou de usuário que está listada no Skype para painel de controle do servidor de negócios na página política de acesso externo.
ms.openlocfilehash: 24d26e8668d04f1c11a3039b4b524d25e209e619
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889801"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Excluir um site ou uma política de usuário para acesso de usuário externo

Se você criou ou configurou políticas de acesso de usuário externo que você não deseja mais usar, você pode fazer o seguinte:

  - Exclua qualquer política de site ou de usuário que você criou.

  - Redefina a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.


Você pode excluir qualquer política de site ou de usuário que está listada no Skype para painel de controle do servidor de negócios na página **Política de acesso externo** . Excluindo a política global não realmente excluí-lo, mas apenas o redefine com as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo. Para obter detalhes sobre como redefinir a política global, consulte [Redefinir a política global para acesso de usuário externo](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para excluir uma política de site ou usuário para acesso de usuário externo

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 

3.  Clique em **Acesso de usuário externo**, **Política de acesso externo**.

4.  Na guia **Política de acesso externo** , clique na política de site ou de usuário que você deseja excluir, clique em **Editar**e, em seguida, clique em **Excluir**.

5.  Quando solicitado a confirmar a exclusão, clique em **Okey**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Remover políticas de PIN usando Cmdlets do Windows PowerShell

Políticas de acesso externo podem ser excluídas, usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para remover uma política de acesso externo específica

  - Este comando remove a política de acesso externo aplicada ao site Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para remover todas as do external acessar políticas aplicadas ao escopo por usuário

  - Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para remover todas as políticas de acesso externo onde o acesso de usuário externo está desabilitado

  - Este comando exclui todas as políticas de acesso externo onde usuário externo access foi desativado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .
