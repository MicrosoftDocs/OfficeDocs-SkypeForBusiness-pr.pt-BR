---
title: 'Lync Server 2013: Habilitar ou desabilitar acesso de usuário remoto'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable remote user access
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a8edd8d6736d181b59579db29cc1e7244b0a750
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829291"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-remote-user-access-in-lync-server-2013"></a>Habilitar ou desabilitar acesso de usuário remoto no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Usuários remotos são usuários de sua organização que têm uma identidade persistente do Active Directory dentro da organização. Usuários remotos geralmente se conectam ao Lync Server de fora da rede usando uma rede virtual privada (VPN) quando não estão conectados à rede da sua organização. Os usuários remotos incluem funcionários que trabalham em casa ou em trânsito e outros trabalhadores remotos, como fornecedores confiáveis, que receberam credenciais da empresa. Se você habilitar o acesso de usuários remotos para usuários remotos, os usuários remotos compatíveis se conectarem pela Internet e não precisarão se conectar usando uma VPN para colaborar com usuários internos usando o Lync Server.

Para dar suporte ao acesso de usuário remoto, você deve habilitar o acesso de usuários remotos. Ao habilitar o acesso de usuário remoto, habilite-o para toda a sua organização. Se, mais tarde, você quiser impedir temporariamente ou permanentemente o acesso do usuário remoto, você pode desabilitá-lo para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários remotos para sua organização.

<div>


> [!NOTE]  
> Habilitar o acesso de usuários remotos especifica que os servidores que executam o serviço de borda de acesso dão suporte a comunicações com usuários remotos, mas os usuários remotos não podem participar de mensagens instantâneas (IM) nem conferências em sua organização até você também configurar ao mesmo tempo. menos uma política para gerenciar o uso de acesso de usuário remoto. As configurações de política do Lync Server aplicadas em um nível de política podem substituir as configurações aplicadas em outro nível de política. A precedência da política do Lync Server é: a política do usuário (maior influência) substitui uma política do site e uma política de site substitui uma política global (influência mínima). Isso significa que, quanto mais perto a definição de política estiver do objeto que ela está afetando, maior será sua influência sobre o objeto. Para obter detalhes sobre a configuração de políticas para o uso de acesso de usuário remoto, consulte <A href="lync-server-2013-configure-policies-to-control-remote-user-access.md">Configurar políticas para controlar o acesso de usuários remotos no Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários remotos para sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso Externo e Federado** e clique em **Configuração de Borda de Acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário remoto para sua organização, marque a caixa de seleção **habilitar acesso do usuário remoto** .
    
      - Para desabilitar o acesso de usuário remoto para sua organização, desmarque a caixa de seleção **habilitar acesso de usuário remoto** .

6.  Clique em **Confirmar**.

Para permitir que os usuários remotos entrem em seus servidores que executam o Lync Server, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário remoto. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários remotos no Lync Server 2013](lync-server-2013-configure-policies-to-control-remote-user-access.md) na documentação de implantação ou a documentação de operações.

</div>

<div>

## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuário remoto usando cmdlets do Windows PowerShell

O acesso do usuário remoto pode ser gerenciado usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-remote-user-access"></a>Para habilitar o acesso de usuários remotos

  - Para habilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

</div>

<div>

## <a name="to-disable-remote-user-access"></a>Para desabilitar o acesso de usuários remotos

  - Para desabilitar o acesso de usuário remoto, defina o valor da propriedade **AllowOutsideUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

