---
title: 'Lync Server 2013: Habilitar ou desabilitar federação e conectividade de IM pública'
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
ms.openlocfilehash: edbf03ee2e2772e6df1425ffd666176c1947f0e4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736061"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-federation-and-public-im-connectivity-in-lync-server-2013"></a>Habilitar ou desabilitar federação e conectividade de IM pública no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-06-24_

O suporte para Federação é necessário para permitir que os usuários que têm uma conta com um cliente ou uma organização de parceiro confiável, incluindo domínios de parceiros e usuários de provedores de serviços de mensagens instantâneas (IM) que você dá suporte a colaborar com os usuários em seu porte. A Federação também é necessária para usar um provedor de serviços do Exchange hospedado para fornecer correio de voz para usuários do Enterprise Voice cujas caixas de correio estão localizadas em um serviço hospedado do Exchange, como o Microsoft Exchange Online. Quando tiver estabelecido uma relação de confiança com esses domínios externos, você poderá autorizar os usuários desses domínios a acessarem sua implantação e participar de comunicações do Lync Server. Essa relação de confiança é chamada de Federação e não é relacionada à relação de confiança do Active Directory, ou depende dela.

Para dar suporte ao acesso por usuários de domínios federados, você deve habilitar a Federação. Se você habilitar a Federação para sua organização, também deverá especificar se deseja implementar as seguintes opções:

  - **Habilitar a descoberta**   de domínio de parceiro se você habilitar essa opção, o Lync Server usará os registros de sistema de nome de domínio (DNS) para tentar descobrir domínios não listados na lista de domínios permitidos, avaliando automaticamente o tráfego de entrada de parceiros federados descobertos e limitando ou bloqueando esse tráfego com base no nível de confiança, na quantidade de tráfego e nas configurações do administrador. Se você não selecionar essa opção, o acesso do usuário federado será habilitado somente para os usuários nos domínios que você incluir na lista de domínios permitidos. Independentemente de você selecionar essa opção, você pode especificar que domínios individuais sejam bloqueados ou permitidos, incluindo a restrição de acesso a servidores específicos que executam o serviço de borda de acesso no domínio federado. Para obter detalhes sobre o controle do acesso a domínios federados, consulte [Configurar o suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md).

  - **Enviar uma isenção de responsabilidade de arquivamento a**     um aviso de isenção de responsabilidade de parcerias federadas é enviada para parceiros federados que o arquivamento em sua implantação está em vigor. Se você oferecer suporte ao arquivamento de comunicações externas com domínios de parceiros federados, habilite a notificação de exclusão de isenção de arquivo para avisar os parceiros de que suas mensagens estão sendo arquivadas.

Se, mais tarde, você quiser impedir o acesso temporário ou permanente por usuários de domínios federados, poderá desabilitar a Federação para a sua organização. Use o procedimento desta seção para habilitar ou desabilitar o acesso de usuário federado à sua organização, incluindo a especificação das opções de Federação adequadas para ter suporte para sua organização.

<div>


> [!NOTE]  
> Habilitar a Federação para a sua organização especifica apenas que os servidores que executam o serviço de borda de acesso dão suporte a roteamento para domínios federados. Os usuários em domínios federados não podem participar de mensagens instantâneas nem conferências em sua organização até você também configurar pelo menos uma política para dar suporte ao acesso de usuários federados. Os usuários de provedores de serviços públicos de mensagens instantâneas não podem participar de mensagens instantâneas nem conferências em sua organização até você também configurar pelo menos uma política para dar suporte à conectividade de mensagens de chat públicas. O Lync Server não pode usar um serviço hospedado do Exchange para fornecer atendimento de chamada, Outlook Voice Access (incluindo correio de voz) ou serviços de atendedor automático para usuários cujas caixas de correio estão localizadas em um serviço do Exchange hospedado até você configurar uma política de caixa postal hospedada Isso fornece informações de roteamento. Para obter detalhes sobre como configurar políticas para comunicação com usuários de domínios federados em outras organizações, consulte <A href="lync-server-2013-manage-sip-federated-domains-for-your-organization.md">gerenciar domínios federados SIP para sua organização no Lync Server 2013</A> na documentação de operações. Além disso, se quiser dar suporte à comunicação com usuários de provedores de serviços de mensagens instantâneas, você deve configurar políticas para dar suporte a ele e também configurar o suporte para provedores de serviços individuais aos quais você deseja dar suporte. Para obter detalhes, consulte <A href="lync-server-2013-manage-sip-federated-providers-for-your-organization.md">gerenciar provedores federados SIP para sua organização no Lync Server 2013</A> na documentação de operações. Para obter detalhes sobre como criar uma política de caixa postal hospedada, consulte <A href="lync-server-2013-manage-hosted-voice-mail-policies.md">gerenciar políticas de caixa postal hospedadas no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a>Para habilitar ou desabilitar o acesso de usuário federado à sua organização

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**e, em seguida, clique em **configuração de borda de acesso**.

4.  Na página **configuração de borda de acesso** , clique em **global**, clique em **Editar**e, em seguida, clique em **Mostrar detalhes**.

5.  Em **Editar configuração de borda de acesso**, siga um destes procedimentos:
    
      - Para habilitar o acesso de usuário federado à sua organização, marque a caixa de seleção **habilitar comunicações com usuários federados** .
    
      - Para desabilitar o acesso de usuário federado à sua organização, desmarque a caixa de seleção **habilitar comunicações com usuários federados** .

6.  Se você tiver marcado a caixa de seleção **habilitar comunicações com usuários federados** , faça o seguinte:
    
    1.  Se você quiser dar suporte à descoberta automática de domínios de parceiros, marque a caixa de seleção **habilitar descoberta de domínio de parceiro** .
    
    2.  Se a sua organização oferecer suporte para o arquivamento de comunicações externas, marque a caixa de seleção **Enviar isenção de arquivo para parceiros federados** .

7.  Clique em **Confirmar**.

Para habilitar os usuários federados a colaborar com usuários em sua implantação do Lync Server 2013, você também deve configurar pelo menos uma política de acesso externo para dar suporte ao acesso de usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md) na documentação de implantação ou a documentação de operações. Para controlar o acesso para domínios federados específicos, consulte [Configurar o suporte para domínios externos permitidos no Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) na documentação de implantação ou documentação de operações.

</div>

<div>

## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a>Habilitar ou desabilitar a conectividade de mensagens de chat pública e de Federação usando cmdlets do Windows PowerShell

A Federação e a conectividade de mensagens de chat públicas também podem ser gerenciadas usando o Windows PowerShell e o cmdlet Set-CsAccessEdgeConfiguration. Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.

<div>

## <a name="to-enable-federation-and-public-im-connectivity"></a>Para habilitar a conectividade de mensagens de chat pública e de Federação

  - Para habilitar a conectividade de mensagens de chat pública e de Federação, defina o valor da propriedade **AllowFederatedUsers** como True ($true):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-disable-federation-and-public-im-connectivity"></a>Para desabilitar a conectividade de mensagens de chat pública e de Federação

  - Para desabilitar a conectividade de mensagens de chat pública e de Federação, defina o valor da propriedade **AllowFederatedUsers** como False ($false):
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

