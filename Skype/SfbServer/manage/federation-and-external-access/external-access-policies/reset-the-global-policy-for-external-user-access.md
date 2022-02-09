---
title: Redefinir a política global para acesso de usuário externo
ms.reviewer: ''
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
mtps_version: v=OCS.15
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Não é possível excluir completamente uma política global. Usar a **opção Excluir** na política global apenas redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.
ms.openlocfilehash: e65eb4f2a87789b22654b8de5e3681b1dda47d1a
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62416554"
---
# <a name="reset-the-global-policy-for-external-user-access-in-skype-for-business-server"></a>Redefinir a política global para acesso de usuário externo Skype for Business Server 

Se você tiver criado ou configurado políticas de acesso de usuário externo que não deseja mais usar, poderá usar os seguintes métodos:

  - Excluir qualquer política local ou de usuário que você criou.

  - Redefinir a política global para as configurações padrão. As configurações de política global padrão negam qualquer acesso de usuário externo. A política global não pode ser excluída.

Não é possível excluir completamente uma política global. A **opção Excluir** na política global apenas redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  De uma conta de usuário que é membro do grupo RTCUniversalServerAdmins ou que tem direitos de usuário equivalentes ou é atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo**, em **Política de Acesso Externa**.

4.  Na guia **Política de Acesso Externa**, clique em política global, clique em **Editar** e em **Excluir**.

5.  Quando lhe for solicitado confirmar a exclusão, clique em **OK**. Uma mensagem aparece na parte superior da página informando que a política global foi redefinida.


## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinindo a Política de Acesso Externo Global usando Windows PowerShell Cmdlets

A política de acesso externo global pode ser redefinida usando Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Você pode executar esse cmdlet no Shell de Gerenciamento Skype for Business Server ou em uma sessão remota Windows PowerShell. 

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Esse comendo redefine a política de acesso externo global:<br/><br/>Remove-CsExternalAccessPolicy -Identity "global"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](/powershell/module/skype/Remove-CsExternalAccessPolicy) .
