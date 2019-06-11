---
title: 'Lync Server 2013: excluir uma política de PIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85b8f77056c61fbeed32ab06f6ce4296bc32105f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829645"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Excluir uma política de PIN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Siga estas etapas para excluir uma política de PIN (número de identificação pessoal).

<div>


> [!NOTE]  
> Não é possível excluir a política de PIN global.



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Para excluir uma política de PIN no painel de controle do Lync Server 2013

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Segurança** e em **Política de PIN**.

4.  Na página **Política de PIN** e no campo de pesquisa, digite o nome todo ou parcial da política que deseja excluir.

5.  Na lista de políticas, clique na política que você deseja, clique em **Editar** e em **Excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Removendo políticas de PIN usando cmdlets do Windows PowerShell

Você pode excluir políticas de PIN usando o Windows PowerShell e o cmdlet Remove-CsPinPolicy. Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specific-pin-policy"></a>Para remover uma política de PIN específica

  - Este comando remove a política de PIN com a Identidade RedmondPinPolicy:
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Para remover todas as políticas de PIN aplicadas ao escopo do site

  - Este comando remove todas as políticas de PIN configuradas no escopo do site:
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Para remover todas as políticas de PIN que permitem o uso de padrões comuns

  - Isso remove todas as políticas de PIN que permitem o uso dos padrões comuns:G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

Para obter mais informações, consulte o tópico da ajuda para o cmdlet [Remove-CsPinPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

