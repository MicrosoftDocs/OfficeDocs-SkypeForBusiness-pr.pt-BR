---
title: 'Lync Server 2013: habilitar ou desabilitar a descoberta de parceiros de Federação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 893f61ce972ae85bcc88f47fe83c4fde220bb5c9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a>Habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Na ocasião em que você implantou seus Servidores de Borda e habilitou a federação para a sua organização, deve ter especificado se haveria suporte para a descoberta automática de domínios parceiros federados. Use o procedimento deste tópico para alterar essa configuração.

<div>


> [!NOTE]  
> O procedimento a seguir assume que você já habilitou a federação para sua organização. Para obter detalhes sobre como habilitar a Federação, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A> na documentação de implantação ou na documentação operações.



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a>Para habilitar ou desabilitar a descoberta automática de domínios federados para a sua organização

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **Acesso de Usuário Externo** e em **Configuração da Borda de Acesso**.

4.  Na página **Configuração da Borda de Acesso**, clique em **Global**, **Editar** e em **Exibir detalhes**.

5.  Em **Editar Configuração da Borda de Acesso**, sob **Habilitar comunicações com usuários federados**, selecione ou desmarque a opção **Habilitar descoberta de domínios de parceiros** para habilitar ou desabilitar a descoberta automática de domínios de parceiros.

6.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários na sua implantação do Lync Server, você também deve ter configurado pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados. Para obter detalhes, consulte [habilitar ou desabilitar Federação e conectividade de im pública no Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) na documentação de implantação ou na documentação operações. Para obter detalhes sobre como controlar o acesso para domínios federados específicos, consulte [Manage SIP Federated Domains for Your Organization in Lync server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP Federated Providers for Your Organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) e [Manage XMPP Federated Partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) na documentação operações.

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a descoberta de parceiros de Federação usando cmdlets do Windows PowerShell

A descoberta de parceiros de Federação pode ser gerenciada usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-discovery-of-federation-partners"></a>Para habilitar a descoberta de parceiros de Federação

  - Para habilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Verdadeiro ($True). Observe que é necessário habilitar o roteamento DNS SRV para alterar o valor dessa propriedade.
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a>Para desabilitar a descoberta de parceiros de Federação

  - Para desabilitar a descoberta de parceiros de federação, defina o valor da propriedade **EnablePartnerDiscovery** como Falso ($False).
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

