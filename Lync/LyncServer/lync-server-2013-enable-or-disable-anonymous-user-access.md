---
title: 'Lync Server 2013: habilitar ou desabilitar o acesso de usuário anônimo'
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
ms.openlocfilehash: f58ab7d0f3d47da8bae3df94c3c83b1eae0059e6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501078"
---
# <a name="enable-or-disable-anonymous-user-access-in-lync-server-2013"></a>Habilitar ou desabilitar o acesso de usuário anônimo no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Usuários anônimos são usuários que não possuem uma conta de usuário nos serviços de domínio do Active Directory da sua organização ou em um domínio federado com suporte, mas podem ser convidados a participar remotamente em uma conferência local. Ao permitir a participação anônima em reuniões, você habilita os usuários anônimos (isto é, usuários cuja identidade é verificada apenas por meio da chave de reunião ou conferência) a participarem de reuniões. Para permitir a participação anônima em sua organização, é necessário que você habilite esse recurso.

Se mais tarde você quiser prevenir o acesso de usuários anônimos temporariamente ou permanentemente, é possível desabilitar esse acesso à sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuários anônimos à sua organização.

<div>


> [!NOTE]  
> Habilitar o acesso de usuários anônimos à sua organização apenas especifica que seus servidores que estão executando o serviço de Borda de Acesso dão suporte ao acesso de usuários anônimos. Os usuários anônimos não podem participar de nenhuma reunião da sua organização até que seja configurada ao menos uma política de conferência e que esta seja aplicada a um ou mais usuários ou grupos de usuários. Os únicos usuários que podem convidar usuários anônimos para reuniões são aqueles com uma política de conferência designada configurada para dar suporte aos usuários anônimos. Para obter detalhes sobre como configurar as políticas de conferência para suportar o convite de usuários anônimos, consulte <A href="lync-server-2013-conferencing-policies.md">políticas de conferência no Lync Server 2013</A>.



</div>

<div>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuários anônimos à sua organização

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuários anônimos à sua organização, marque a caixa de seleção **Habilitar comunicações com usuários anônimos**.
    
      - Para desabilitar o acesso de usuários anônimos à sua organização, desmarque a caixa de seleção **Habilitar comunicações com usuários anônimos**.

6.  Clique em **Confirmar**

</div>

<div>

## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando o acesso de usuário anônimo usando cmdlets do Windows PowerShell

Você pode gerenciar o acesso de usuários anônimos usando o Windows PowerShell e o cmdlet **set-CsAccessEdgeConfiguration** . Você pode executar esse cmdlet do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-anonymous-user-access"></a>Para habilitar o acesso de usuário anônimo

  - Para habilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Verdadeiro ($True):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

</div>

<div>

## <a name="to-disable-anonymous-user-access"></a>Para desabilitar o acesso de usuário anônimo

  - Para desabilitar o acesso de usuário anônimo, defina o valor da propriedade **AllowAnonymousUsers** para Falso ($False):
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False

</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Referência de configurações de política de conferência para Lync Server 2013](lync-server-2013-conferencing-policy-settings-reference.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

