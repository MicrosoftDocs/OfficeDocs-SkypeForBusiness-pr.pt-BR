---
title: 'Lync Server 2013: Excluir um site ou uma política de usuário para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a site or user policy for external user access
ms:assetid: 6d907507-825b-4354-9c03-337a459f72de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521013(v=OCS.15)
ms:contentKeyID: 48184455
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e5539f1d6e55e94845e63b0f42c0ef855694d56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-site-or-user-policy-for-external-user-access-in-lync-server-2013"></a>Excluir um site ou uma política de usuário para acesso de usuário externo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Você pode excluir qualquer política de site ou de usuário listada no painel de controle do Lync Server na página de **política de acesso externo** . A exclusão da política global não a exclui realmente, mas só a redefine para as configurações padrão, que não incluem suporte para qualquer opção de acesso de usuário externo. Para obter detalhes sobre como redefinir a política global, consulte [redefinir a política global para acesso de usuário externo no Lync Server 2013](lync-server-2013-reset-the-global-policy-for-external-user-access.md).

<div>

## <a name="to-delete-a-site-or-user-policy-for-external-user-access"></a>Para excluir uma política de site ou de usuário para acesso de usuário externo

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Clique em **acesso de usuário externo**, clique em **política de acesso externo**.

4.  Na guia **política de acesso externo** , clique no site ou na política de usuário que você deseja excluir, clique em **Editar**e, em seguida, clique em **excluir**.

5.  Quando for solicitado a confirmar a exclusão, clique em **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

As políticas de acesso externo podem ser excluídas usando o Windows PowerShell e o cmdlet Remove-CsExternalAccessPolicy. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specific-external-access-policy"></a>Para remover uma política de acesso externo específica

  - Este comando Remove a política de acesso externo aplicada ao site Redmond:
    
        Remove-CsExternalAccessPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-applied-to-the-per-user-scope"></a>Para remover todas as políticas de acesso externo aplicadas ao escopo por usuário

  - Esse comando Remove todas as políticas de acesso externo configuradas no escopo por usuário:
    
        Get-CsExternalAccessPolicy -Filter "tag:*" | Remove-CsExternalAccessPolicy

</div>

<div>

## <a name="to-remove-all-the-external-access-policies-where-outside-user-access-is-disabled"></a>Para remover todas as políticas de acesso externo em que o acesso do usuário externo está desabilitado

  - Este comando exclui todas as políticas de acesso externo em que o acesso de usuário externo foi desabilitado:
    
        Get-CsExternalAccessPolicy | Where-Object {$_.EnableOutsideAccess -eq $False} | Remove-CsExternalAccessPolicy

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsExternalAccessPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

