---
title: 'Lync Server 2013: excluir definições de configuração de registrador existentes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9fe0ee46ff823a5184ee79f3b06bb02bb68115d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829597"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Excluir configurações de registrador existentes no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Siga estas etapas para excluir um registrador.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>Para excluir as definições de configuração do Registrador

1.  Em uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes) ou atribuído à função CsServerAdministrator ou CsAdministrator, faça logon em qualquer computador que esteja na rede na qual você implantou o Lync Server 2013.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Segurança** e em **Registrador**.

4.  Na página **Registrador Avançado** e no campo de pesquisa, digite todo ou parte do nome do Registrador Avançado que você deseja excluir.

5.  Na lista, clique no Registrador Avançado desejado, clique em **Editar** e em **Excluir**.

6.  Clique em **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Como remover as configurações de registrador usando cmdlets do Windows PowerShell

Você pode excluir as definições de configuração do registrador usando o Windows PowerShell e o cmdlet **Remove-CsProxyConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Para remover um conjunto específico de configurações de segurança do Registrador

  - O seguinte comando remove as configurações de segurança do Registrador aplicadas ao servidor de borda atl-edge-011.litwareinc.com:
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Para remover todas as configurações de segurança do Registrador aplicadas ao escopo do site

  - O seguinte comando remove todas as configurações de segurança do Registrador aplicadas ao serviço registrador:
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Para remover todas as configurações de segurança do Registrador que permitem a autenticação de NTLM

  - O seguinte comando exclui todas as configurações de segurança do Registrador que permite o uso de NTLM para autenticação do cliente:
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Para obter detalhes, consulte [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

