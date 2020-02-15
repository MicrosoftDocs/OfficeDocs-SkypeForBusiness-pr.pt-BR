---
title: 'Lync Server 2013: habilitar ou desabilitar Federação e conectividade de IM pública'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable federation and public IM connectivity
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9281b4dab225ddb336dbc74a5d2892f0f4a015d5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040199"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Habilitar ou desabilitar Federação e conectividade de IM pública no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-06-24_

O suporte para Federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, incluindo domínios de parceiros e usuários de usuários de provedores públicos de mensagens instantâneas (IM) que você suporta, para colaborar com usuários no seu departamento. A Federação também é necessária para usar um provedor de serviço do Exchange hospedado para fornecer correio de voz para usuários do Enterprise Voice cujas caixas de correio estão localizadas em um serviço do Exchange hospedado, como o Microsoft Exchange Online. Quando tiver estabelecido uma relação de confiança com esses domínios externos, você poderá autorizar os usuários nesses domínios a acessar sua implantação e participar de comunicações do Lync Server. Essa relação de confiança é chamada de Federação e não está relacionada ou dependente de uma relação de confiança do Active Directory.

Para dar suporte ao acesso por usuários de domínios federados, você deve habilitar a Federação. Se você habilitar a Federação para sua organização, também deverá especificar se deseja implementar as seguintes opções:

  - **Habilitar descoberta**   de domínio de parceiro se você habilitar essa opção, o Lync Server usará registros de DNS (sistema de nomes de domínio) para tentar descobrir domínios não listados na lista de domínios permitidos, automaticamente avaliando o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações de administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para usuários nos domínios que você incluir na lista de domínios permitidos. Mesmo que você não selecione essa opção, poderá especificar o bloqueio ou permissão de domínios individuais, incluindo a restrição do acesso a servidores específicos, executando o serviço Borda de Acesso no domínio federado. Para obter detalhes sobre como controlar o acesso por domínios federados, consulte [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Enviar uma isenção de responsabilidade de arquivamento para parceiros**     federados aviso de isenção de responsabilidade é enviado para parceiros federados que o arquivamento em sua implantação está em vigor. Se você oferecer suporte ao arquivamento de comunicações externas com domínios de parceiros federados, deverá habilitar a notificação de aviso de isenção de responsabilidade para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se posteriormente você quiser impedir o acesso temporário ou permanente por usuários de domínios federados, poderá desabilitar a Federação para sua organização. Use o procedimento nesta seção para habilitar ou desabilitar o acesso de usuário federado à sua organização, incluindo a especificação das opções de Federação apropriadas para ter suporte para sua organização.

<div>


> [!NOTE]  
> Habilitar a Federação para sua organização especifica apenas que os servidores que executam o serviço de borda de acesso dão suporte ao roteamento para domínios federados. Os usuários de domínios federados não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política para dar suporte ao acesso de usuário federado. Os usuários de provedores de serviço de mensagens instantâneas públicos não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política para suportar a conectividade pública de IM. O Lync Server não pode usar um serviço do Exchange hospedado para fornecer atendimento de chamadas, Outlook Voice Access (incluindo caixa postal) ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado até que você configure uma política de caixa postal hospedada que fornece informações de roteamento. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">Manage SIP Federated Domains for Your Organization in Lync Server 2013</A> na documentação operações. Além disso, se você quiser dar suporte à comunicação com usuários de provedores de serviços de mensagens instantâneas, configure as políticas para dar suporte a ela e também configure o suporte para os provedores de serviços individuais que você deseja suportar. Para obter detalhes, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">Manage SIP Federated Providers for Your Organization no Lync Server 2013</A> na documentação operações. Para obter detalhes sobre como criar uma política de caixa postal hospedada, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage Hosted voice mail Policies in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado à sua organização

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  No menu de navegação à esquerda, clique em **Acesso de Usuário Externo** e depois em **Configuração de Borda de Acesso**.

4.  Na página **Configuração de Borda de Acesso**, clique em **Global**, em **Editar** e clique em **Mostrar detalhes**.

5.  Em **Editar Configuração de Borda de Acesso**, execute uma das ações a seguir:
    
      - Para habilitar o acesso de usuário federado à sua organização, marque a caixa de seleção **habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado para sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .

6.  Se você marcou a caixa de seleção **habilitar comunicações com usuários federados** , faça o seguinte:
    
    1.  Se você quiser oferecer suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **habilitar descoberta de domínio de parceiro** .
    
    2.  Se sua organização oferecer suporte ao arquivamento de comunicações externas, marque a caixa de seleção **Enviar aviso de isenção de arquivamento para parceiros federados** .

7.  Clique em **Confirmar**.

Para permitir que usuários federados colaborem com usuários em sua implantação do Lync Server 2013, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuário federado. Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) na documentação de implantação ou a documentação de operações. Para controlar o acesso de domínios federados específicos, confira [Configurar suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) na documentação de implantação ou documentação de operações.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitando ou desabilitando a Federação e conectividade de IM pública usando cmdlets do Windows PowerShell

A Federação e a conectividade de IM pública também podem ser gerenciadas usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a Federação e conectividade de IM pública

  - Para habilitar a Federação e a conectividade de IM pública, defina o valor da propriedade **AllowFederatedUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a Federação e conectividade de IM pública

  - Para desabilitar a Federação e a conectividade de IM pública, defina o valor da propriedade **AllowFederatedUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

