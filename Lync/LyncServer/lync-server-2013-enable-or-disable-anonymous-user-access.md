---
title: 'Lync Server 2013: Habilitar ou desabilitar acesso de usuário anônimo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable anonymous user access
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d38d0d9f50ff06b2f7eb95944d9214c2c4c64a5c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Habilitar ou desabilitar acesso de usuário anônimo no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

Usuários anônimos são usuários que não têm uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local. Ao permitir a participação anônima em reuniões, usuários anônimos (ou seja, usuários cuja identidade são verificadas apenas na reunião ou na chave da conferência) para ingressar em reuniões. Permitir a participação anônima exige a habilitação da sua organização.

Se, mais tarde, você quiser impedir o acesso temporário ou permanente de usuários anônimos, pode desabilitá-lo para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos para sua organização.

<div>


> [!NOTE]  
> Ao habilitar o acesso de usuários anônimos para sua organização, você está especificando que seus servidores que executam o serviço de borda de acesso oferecem suporte a usuários anônimos. Usuários anônimos não podem participar de nenhuma reunião em sua organização até você também configurar pelo menos uma política de conferência e aplicá-la a um ou mais usuários ou grupos de usuários. Os únicos usuários que podem convidar usuários anônimos para reuniões são os usuários que recebem uma política de conferência configurada para dar suporte a usuários anônimos. Para obter detalhes sobre como configurar as políticas de conferência para dar suporte ao convite para usuários anônimos, consulte <A href="lync-server-2013-conferencing-policies.md">políticas de conferência no Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários anônimos para a sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**e, em seguida, clique em **configuração de borda de acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuários anônimos para sua organização, marque a caixa de seleção **habilitar comunicações com usuários anônimos** .
    
      - Para desabilitar o acesso de usuários anônimos para sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários anônimos** .

6.  Clique em **Confirmar**.

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar o acesso de usuários anônimos usando cmdlets do Windows PowerShell

Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** . Você pode executar esse cmdlet a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-anonymous-user-access"></a>Para habilitar o acesso de usuários anônimos

  - Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Para desativar o acesso de usuários anônimos

  - Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Referência de configurações de política de conferência para o Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

