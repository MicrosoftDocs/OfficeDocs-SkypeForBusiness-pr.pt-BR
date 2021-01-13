---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
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
description: Não é possível excluir completamente uma política global. Usar a opção **Excluir** na política global simplesmente a redefine para as configurações padrão, o que não inclui suporte a opções de acesso de usuário externo.
ms.openlocfilehash: be4f99c5b98ca46e7fed57781cf1661a2755a4ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817241"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Redefinir a política global para acesso de usuário externo no Skype for Business Server 

Se você criou ou configurou políticas de acesso de usuário externo que não vai mais usar, poderá fazer o seguinte:

  - Excluir qualquer política local ou de usuário que você criou.

  - Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.

Não é possível excluir completamente uma política global. Usar a opção **Excluir** na política global simplesmente a redefine para as configurações padrão, o que não inclui suporte a opções de acesso de usuário externo.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server.

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo**, em **Política de Acesso Externa**.

4.  Na guia **Política de Acesso Externa**, clique em política global, clique em **Editar** e em **Excluir**.

5.  Quando lhe for solicitado confirmar a exclusão, clique em **OK**. Uma mensagem aparece na parte superior da página informando que a política global foi redefinida.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell

A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o Remove-CsExternalAccessPolicy cmdlet. Esse cmdlet pode ser executado a partir do Shell de Gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Esse comendo redefine a política de acesso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy.](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy)


