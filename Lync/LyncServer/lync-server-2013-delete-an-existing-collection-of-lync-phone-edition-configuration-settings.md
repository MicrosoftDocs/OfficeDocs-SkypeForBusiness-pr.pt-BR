---
title: Excluir uma coleção existente de definições de configuração do Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829615"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Excluir uma coleção existente de definições de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Se você não quiser mais usar um conjunto de configurações para dispositivos que executam o Lync Phone Edition, exclua-o. Se você excluir uma coleção de um site, as configurações globais serão aplicadas aos telefones desse site. Não é possível excluir a coleção global.

<div>


> [!NOTE]
> Em vez de excluir uma coleção, talvez você queira apenas alterar algumas das configurações. Para obter detalhes sobre como fazer isso, consulte <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">criar ou modificar um conjunto de configurações do Lync Phone Edition no Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Para excluir uma coleção de definições de configuração do Lync Phone Edition

1.  Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração de dispositivo** .

4.  Na página **configuração de dispositivo** , clique na coleção que você deseja excluir, clique no menu **Editar** e, em seguida, clique em **excluir**.
    
    <div>
    

    > [!NOTE]
    > Se você excluir a coleção global, as configurações apenas reverterão para as configurações padrão. A coleção não desaparece.

    
    </div>

5.  Na caixa de confirmação, clique em **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode excluir as configurações de configuração do Lync Phone Edition usando o Windows PowerShell e o cmdlet **Remove-CsUCConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Para remover uma coleção especificada de definições de configuração do Lync Phone Edition

  - Esse comando exclui as definições de configuração de telefone UC aplicadas ao site Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as configurações de configuração do Lync Phone Edition aplicadas ao escopo do site

  - Esse comando Remove todas as definições de configuração de telefone UC aplicadas ao escopo do serviço:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Para remover todas as configurações de configuração do Lync Phone Edition em que o bloqueio de telefone está desabilitado

  - Esse comando exclui qualquer conjunto de configurações de configuração de telefone UC em que o bloqueio de telefone foi desabilitado:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Para obter detalhes, consulte [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

