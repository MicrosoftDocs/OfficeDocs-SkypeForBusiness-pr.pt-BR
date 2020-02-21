---
title: Excluir um conjunto existente de definições de configuração do Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e5c601726cfc18d230519741ebcc7561da54d73
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202707"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Excluir um conjunto existente de definições de configuração do Lync Phone Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Se você não quiser mais usar um conjunto de configurações para dispositivos que executam o Lync Phone Edition, exclua-o. Se você excluir um conjunto de um site, as configurações globais serão aplicadas aos telefones neste site. Não é possível excluir o conjunto global.

<div>


> [!NOTE]
> Ao invés de excluir um conjunto, você pode alterar algumas configurações. Para obter detalhes sobre como fazer isso, consulte <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">create or Modify a Collection of Lync Phone Edition Configuration Settings in Lync Server 2013</A>.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Para excluir uma coleção de definições de configuração do Lync Phone Edition

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Clientes** e no botão de navegação **Configuração do Dispositivo**.

4.  Na página **Configuração do Dispositivo**, clique no conjunto que você deseja excluir, clique no menu **Editar** e em **Excluir**.
    
    <div>
    

    > [!NOTE]
    > Se você excluir o conjunto global, as configurações são revertidas para as configurações padrões. O conjunto não some.

    
    </div>

5.  Na caixa de confirmação, clique em **OK**.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Removendo definições de configuração do Lync Phone Edition usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do Lync Phone Edition usando o Windows PowerShell e o cmdlet **Remove-CsUCConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Para remover uma coleção especificada das definições de configuração do Lync Phone Edition

  - Este comando excluir as definições de configuração do telefone UC para o site Redmond:
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>Para remover todas as definições de configuração do Lync Phone Edition aplicadas ao escopo do site

  - Este comando remove todas as definições de configuração do telefone UC aplicadas ao escopo de serviço:
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>Para remover todas as definições de configuração do Lync Phone Edition onde o bloqueio de telefone está desabilitado

  - Este comando exclui qualquer conjunto de definições de configuração do telefone UC onde o bloqueio de telefone foi desabilitado:
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

Para obter detalhes, consulte [Remove-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15)).

</div>

</div>

<span> </span>

</div>

</div>

</div>

