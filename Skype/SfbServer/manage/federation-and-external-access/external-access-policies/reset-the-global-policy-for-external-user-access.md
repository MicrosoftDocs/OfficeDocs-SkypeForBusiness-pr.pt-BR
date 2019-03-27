---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Completamente, você não pode excluir uma política global. Apenas usando a opção **Excluir** a política global redefine a política global para as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo.
ms.openlocfilehash: 048d1f1aabd2e188cefa25358068ea6ec150b8f3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877871"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Redefinir a política global para acesso de usuário externo no Skype para Business Server 

Se você criou ou configurou políticas de acesso de usuário externo que você não deseja mais usar, você pode fazer o seguinte:

  - Exclua qualquer política de site ou de usuário que você criou.

  - Redefina a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.

Completamente, você não pode excluir uma política global. Apenas usando a opção **Excluir** a política global redefine a política global para as configurações padrão, que não incluem o suporte para quaisquer opções de acesso de usuário externo.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.

3.  Na barra de navegação à esquerda, clique em **Acesso de usuário externo**, **Política de acesso externo**.

4.  Na guia **Política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **Excluir**.

5.  Quando solicitado a confirmar a exclusão, clique em **Okey**. Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinido a política de acesso externo Global usando Cmdlets do Windows PowerShell

Pode ser redefinida a política de acesso externo global usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Este cmdlet pode ser executado a partir do Skype do Shell de gerenciamento do servidor de negócios ou de uma sessão remota do Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Esse comendo redefine a política de acesso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


