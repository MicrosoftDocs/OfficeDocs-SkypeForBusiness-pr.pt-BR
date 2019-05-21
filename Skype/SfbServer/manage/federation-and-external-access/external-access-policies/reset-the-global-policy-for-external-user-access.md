---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Não é possível excluir completamente uma política global. Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.
ms.openlocfilehash: 339ad22e1d049510416bfc3433c6c8a104455504
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280142"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Redefinir a política global para o acesso de usuários externos no Skype for Business Server 

Se você criou ou configurou políticas de acesso externo do usuário que não deseja mais usar, pode fazer o seguinte:

  - Exclua qualquer site ou política de usuário que você criou.

  - Redefina a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.

Não é possível excluir completamente uma política global. Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Skype for Business Server.

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**, clique em **política de acesso externo**.

4.  Na guia **política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **excluir**.

5.  Quando for solicitado a confirmar a exclusão, clique em **OK**. Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell

A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Esse cmdlet pode ser executado do Shell de gerenciamento do Skype for Business Server ou de uma sessão remota do Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Este comando redefine a política global de acesso externo:
    
        Remove-CsExternalAccessPolicy -Identity "global"

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsExternalAccessPolicy) .


