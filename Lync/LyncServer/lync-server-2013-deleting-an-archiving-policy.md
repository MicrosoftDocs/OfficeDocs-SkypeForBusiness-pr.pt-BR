---
title: 'Lync Server 2013: excluindo uma política de arquivamento'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an Archiving policy
ms:assetid: 4739a691-41cc-4128-8bb8-6d5a4c02107a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520989(v=OCS.15)
ms:contentKeyID: 48184043
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 926cc7e45fe3e57c189b01ff92da49342506dc2b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763069"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-archiving-policy-in-lync-server-2013"></a>Excluindo uma política de arquivamento no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Você pode excluir uma política de usuário ou política do site. A política global não pode ser removida. Se você tentar excluir a política global, o Lync Server 2013 redefine automaticamente a política para os valores padrão.

<div>


> [!NOTE]  
> Se você tiver habilitado a integração do Microsoft Exchange para a implantação, as políticas do Exchange controlarão se o arquivamento está habilitado para os usuários que estão hospedados no Exchange 2013 e ter suas caixas de correio no bloqueio in-loco. Para obter detalhes, consulte <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Configurando políticas para arquivamento no Lync server 2013 ao usar a integração com o Exchange Server</A> na documentação de implantação.



</div>

<div>

## <a name="to-delete-a-user-or-site-policy-for-archiving"></a>Para excluir um usuário ou uma política de site para arquivamento

1.  Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.

4.  Na lista de políticas de arquivamento, clique na política de usuário ou site que deseja excluir, clique em **Editar** e em **Excluir**.

5.  Clique em **Confirmar**.

</div>

<div>

## <a name="removing-archiving-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de arquivamento usando cmdlets do Windows PowerShell

As políticas de arquivamento podem ser excluídas usando o Windows PowerShell e o cmdlet **Remove-CsArchivingPolicy** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-archiving-policy"></a>Para remover uma política de arquivamento especificada

  - Como exemplo, **Remove-CsArchivingPolicy** exclui a política com o site de identidade: Redmond. Observe que, quando uma política configurada no escopo do site for excluída, os usuários gerenciados anteriormente pela política do site serão automaticamente regidos pela política de arquivamento global. O comando a seguir remove o arquivamento aplicado ao site Redmond:
    
        Remove-CsArchivingPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-applied-to-the-per-user-scope"></a>Para remover todas as políticas de arquivamento aplicadas ao escopo por usuário

  - Esse comando Remove todas as políticas de arquivamento aplicadas ao escopo por usuário:
    
        Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy

</div>

<div>

## <a name="to-remove-all-the-archiving-policies-that-disable-internal-archiving"></a>Para remover todas as políticas de arquivamento que desativam o arquivamento interno

  - Este comando remove todas as políticas de arquivamento onde o arquivamento interno foi desativado:
    
        Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsArchivingPolicy) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Gerenciar o arquivamento de comunicações internas e externas no Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

