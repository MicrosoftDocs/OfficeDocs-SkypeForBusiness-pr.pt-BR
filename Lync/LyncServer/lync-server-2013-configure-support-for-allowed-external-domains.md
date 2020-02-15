---
title: 'Lync Server 2013: configurar suporte para domínios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c8926bd9cdbc64b336b72c62c5171047ae096868
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurar suporte para domínios externos permitidos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-19_

Se você configurou suporte para parceiros federados, você pode gerenciar quais domínios federar com a sua organização. Você configura um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que talvez precise se comunicar com mais de 1.000 usuários ou talvez precise enviar mais de 20 mensagens por segundo. Se a descoberta de parceiro não estiver habilitada para a sua organização, somente os usuários de domínios externos que você adiciona à lista de domínios permitidos podem participar em conferência e mensagens instantâneas com usuários em sua organização. Se você quiser restringir o acesso de um domínio federado a um servidor específico que executa o serviço de Borda de Acesso do parceiro federado, poderá especificar o nome de domínio do servidor que executa o serviço de Borda de Acesso para cada domínio na lista de domínios permitidos.

<div>


> [!NOTE]  
> Este procedimento descreve como configurar o suporte para domínios específicos, mas implementar suporte para usuários federados também exige que você habilite o suporte para usuários federados de sua organização, bem como configure e aplique políticas para controlar quais usuários podem colaborar com usuários federados. Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>. Para obter detalhes sobre a configuração de políticas para controlar a Federação, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configure Policies to Control Federated User Access in Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para adicionar um domínio externo à lista de domínios permitidos

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo** e em **Domínios Federados**.

4.  Na página **Domínios Federados**, clique em **Novo** e em **Domínio permitido**.

5.  Em **Novos Domínios Federados**, faça o seguinte:
    
      - Em **Nome de domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.
        
        <div>
        

        > [!NOTE]  
        > Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que executa o serviço de Borda de Acesso. O nome não pode exceder 256 caracteres.<BR>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.<BR>Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido. O Lync Server 2013 impede que isso aconteça para que você não precise sincronizar suas listas.

        
        </div>
    
      - Se você quiser restringir o acesso para esse domínio federado a usuários de um servidor específico que execute o serviço de Borda de Acesso, em **Serviço de Borda de Acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de Borda de Acesso.
    
      - Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.

7.  Repita as etapas 4 a 6 para cada domínio de parceiro federado que deseja permitir.

Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados. Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

