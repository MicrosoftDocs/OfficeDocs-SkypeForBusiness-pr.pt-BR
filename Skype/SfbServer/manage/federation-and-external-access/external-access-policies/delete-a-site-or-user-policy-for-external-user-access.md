---
title: Excluir um site ou uma política de usuário para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
mtps_version: v=OCS.15
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você pode excluir qualquer política de site ou usuário listada no Painel de Controle Skype for Business Server na página Política de Acesso Externo.
ms.openlocfilehash: 53be2748328211c901a2daeeb0ca84e70cfd6511
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60765449"
---
# <a name="delete-a-site-or-user-policy-for-external-user-access"></a>Excluir um site ou uma política de usuário para acesso de usuário externo

Se você tiver criado ou configurado políticas de acesso de usuário externo que não deseja mais usar, poderá fazer o seguinte método:

  - Excluir qualquer política local ou de usuário que você criou.

  - Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.


Você pode excluir qualquer política de site ou usuário listada no Painel de Controle Skype for Business Server na página **Política de Acesso** Externo. A exclusão da política global não a exclui, mas apenas a redefine para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo. Para obter detalhes sobre como redefinir a política global, consulte [Reset the global policy for external user access](reset-the-global-policy-for-external-user-access.md).


## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para excluir uma política de site ou de usuário para o acesso de usuário externo

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 

3.  Clique em **Acesso de Usuário Externo**, em **Política de Acesso Externo**.

4.  Na guia **Política de Acesso Externo**, clique na política de site ou de usuário que deseja excluir, clique em **Editar** e em **Excluir**.

5.  Quando for solicitado que você confirme a exclusão, clique em **OK**.


## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando Windows PowerShell cmdlets

As políticas de acesso externo podem ser excluídas usando-se o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota de Windows PowerShell. 


## <a name="to-remove-a-specific-external-access-policy"></a>Para remover uma política de acesso externo específica

  - Este comando remove a política de acesso externo aplicada ao site Redmond:<br/><br/>Remove-CsExternalAccessPolicy -Identity "site:Redmond"


## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário

  - Este comando remove todas as políticas de acesso externo configuradas no escopo por usuário:<br/><br/>Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy


## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para remover todas as políticas de acesso externo em que o acesso externo do usuário está desabilitado

  - Este comando exclui todas as políticas de acesso externo com acesso de usuário externo desabilitado:<br/><br/>Get-CsExternalAccessPolicy | Where-Object {$_. EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy


Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy.](/powershell/module/skype/Remove-CsExternalAccessPolicy)
