---
title: 'Lync Server 2013: habilitar ou desabilitar o acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c673295f2344d2ca3ca853f76775bbae47a74328
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045623"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Usuários remotos são usuários em suas organizações com uma identidade do Active Directory persistente dentro da organização. Os usuários remotos freqüentemente entram no Lync Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização. Os usuários remotos incluem funcionários trabalhando em casa ou na estrada e outros trabalhadores remotos, como vendedores confiáveis, que foram concedidos com credenciais empresariais. Se você habilitar o acesso de usuário remoto para usuários remotos, os usuários remotos suportados se conectam pela Internet e não precisam se conectar usando uma VPN para colaborar com usuários internos usando o Lync Server.

Para suportar acesso de usuário remoto, você deve habilitar o acesso de usuário remoto. Ao habilitar o acesso de usuário remoto, você o habilita para toda sua organização. Se posteriormente você quiser impedir temporariamente ou permanentemente o acesso dos domínios federados pelos usuários, poderá desabilitar a federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso do usuário federado para sua organização.

<div>


> [!NOTE]  
> Habilitar o acesso de usuário remoto apenas especifica que seus servidores executando as comunicações de suporte do serviço de Borda de Acesso com usuário remotos, mas os usuários remotos não podem participar de mensagem instantânea (IM) ou conferências em sua organização até que você também configure pelo menos uma política para gerenciar o uso do acesso de usuário remoto. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações que são aplicadas em outro nível de política. A precedência de política do Lync Server é: a política de usuário (maior influência) substitui uma política de site e, em seguida, uma política de site substitui uma política global (menos influência). Isso significa que quanto mais próxima a configuração de diretiva for o objeto que a política está afetando, maior será a influência sobre o objeto. Para obter detalhes sobre como configurar políticas para o uso de acesso de usuário remoto, consulte <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configure Policies to Control Remote User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso do usuário federado na sua organização

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso ao usuário remoto para sua organização, marque a caixa de seleção **Habilitar comunicações com usuários federados**.
    
      - Para desabilitar o acesso ao usuário remoto para sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários federados**.

6.  Clique em **Confirmar**.

Para permitir que os usuários remotos entrem em seus servidores que executam o Lync Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário remoto. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) na documentação de implantação ou na documentação operações.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o acesso de usuário remoto usando cmdlets do Windows PowerShell

O acesso de usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuário remoto

  - Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para True ($True):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuário remoto

  - Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** para False ($False):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

