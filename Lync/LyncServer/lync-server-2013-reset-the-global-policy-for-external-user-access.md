---
title: 'Lync Server 2013: Redefinir a política global para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 327a658bcd75c05e291798598e53947b23c0c12f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823263"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Redefinir a política global para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Não é possível excluir completamente uma política global. Usar a opção **excluir** na política global somente redefine a política global para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**, clique em **política de acesso externo**.

4.  Na guia **política de acesso externo** , clique na política global, clique em **Editar**e, em seguida, clique em **excluir**.

5.  Quando for solicitado a confirmar a exclusão, clique em **OK**. Uma mensagem é exibida na parte superior da página informando que a política global foi redefinida.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell

A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Este comando redefine a política global de acesso externo:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

