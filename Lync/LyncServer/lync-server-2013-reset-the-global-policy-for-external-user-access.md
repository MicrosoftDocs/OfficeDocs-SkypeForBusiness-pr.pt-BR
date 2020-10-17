---
title: 'Lync Server 2013: redefinir a política global para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset the global policy for external user access
ms:assetid: 8207e1b1-de9e-461f-975f-fcc5c526849a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182545(v=OCS.15)
ms:contentKeyID: 48184675
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72c025c15841e55462a5bab4f269e2fc4ed5f49a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511788"
---
# <a name="reset-the-global-policy-for-external-user-access-in-lync-server-2013"></a>Redefinir a política global para acesso de usuário externo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

Não é possível excluir completamente uma política global. Usar a opção **Excluir** na política global simplesmente a redefine para as configurações padrão, o que não inclui suporte a opções de acesso de usuário externo.

<div>

## <a name="to-reset-the-global-policy-to-the-default-settings"></a>Para redefinir a política global para as configurações padrão

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso do Usuário Externo**, em **Política de Acesso Externa**.

4.  Na guia **Política de Acesso Externa**, clique em política global, clique em **Editar** e em **Excluir**.

5.  Quando lhe for solicitado confirmar a exclusão, clique em **OK**. Uma mensagem aparece na parte superior da página informando que a política global foi redefinida.

</div>

<div>

## <a name="resetting-the-global-external-access-policy-by-using-windows-powershell-cmdlets"></a>Redefinindo a política de acesso externo global usando cmdlets do Windows PowerShell

A política de acesso externo global pode ser redefinida usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-reset-the-global-external-access-policy"></a>Para redefinir a política de acesso externo global

  - Esse comendo redefine a política de acesso externo global:
    
        Remove-CsExternalAccessPolicy -Identity "global"

</div>

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

