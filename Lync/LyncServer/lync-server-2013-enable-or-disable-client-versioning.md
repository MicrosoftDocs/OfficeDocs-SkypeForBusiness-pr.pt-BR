---
title: 'Lync Server 2013: habilitar ou desabilitar o controle de versão do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable client versioning
ms:assetid: 33a98cb9-a979-4bb6-afb2-512f601d7ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898475(v=OCS.15)
ms:contentKeyID: 50873755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86fc41847485cbe797da9e9c9ace4a0a8794280
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-client-versioning-in-lync-server-2013"></a>Habilitar ou desabilitar o controle de versão do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

As definições de configuração de versão do cliente são usadas para ativar ou desativar o controle de versão do cliente, globalmente ou para sites específicos. A configuração de versão do cliente global é instalada com o Lync Server 2013 e é usada para habilitar ou desabilitar o controle de versão do cliente para toda a implantação do servidor. Quando a configuração global estiver habilitada, todas as políticas de versão do cliente que estiverem em vigor serão efetivadas quando os usuários tentarem fazer logon. Você pode desabilitar a configuração de versão do cliente global se não quiser que qualquer controle de versão do cliente ocorra. Você pode habilitar ou desabilitar o controle de versão do cliente no painel de controle do Lync Server 2013 ou no Shell de gerenciamento do Lync Server 2013.

<div>


> [!NOTE]  
> Como os usuários anônimos não são associados a um usuário, site ou serviço, eles são afetados somente por políticas de nível global.



</div>

<div>

## <a name="to-enable-or-disable-client-versioning-by-using-lync-server-control-panel"></a>Para habilitar ou desabilitar a controle de versão do cliente usando o painel de controle do Lync Server

1.  Por uma conta de usuário atribuída à função CsUserAdministrator role ou CsAdministrator, faça o login em qualquer computador na sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **clientes**e, em seguida, clique no botão de navegação **configuração da versão do cliente** .

4.  Faça o seguinte:
    
      - Para habilitar ou desabilitar globalmente o controle de versão do cliente, clique duas vezes na configuração **global** e modifique as configurações.
    
      - Para habilitar ou desabilitar o controle de versão de cliente para um site específico, clique em **novo**, selecione o site, clique em **OK**e modifique as configurações do site.

</div>

<div>

## <a name="enabling-or-disabling-client-versioning-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o controle de versão do cliente usando cmdlets do Windows PowerShell

Você pode habilitar ou desabilitar o controle de versão do cliente usando o cmdlet **set-CsClientVersionConfiguration** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-client-versioning"></a>Para habilitar o controle de versão do cliente

  - Você pode habilitar o controle de versão do cliente definindo a propriedade **Enabled** como True ($true).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning"></a>Para desabilitar o controle de versão do cliente

  - Você pode desabilitar o controle de versão do cliente definindo a propriedade **Enabled** como False ($false).
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

Para obter detalhes, consulte o tópico de ajuda para o cmdlet [set-CsClientVersionConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

