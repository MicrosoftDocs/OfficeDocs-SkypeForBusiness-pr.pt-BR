---
title: 'Lync Server 2013: Configurar suprote para domínios externos permitidos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for allowed external domains
ms:assetid: 3ee6e175-986d-4c33-b03a-b9f93083dca6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425908(v=OCS.15)
ms:contentKeyID: 48183943
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfab1a41f39d975d2920bdf97ea601618277f35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836326"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-allowed-external-domains-in-lync-server-2013"></a>Configurar suprote para domínios externos permitidos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-19_

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios específicos podem federar a sua organização. Você pode configurar um ou mais domínios externos específicos como domínios federados permitidos. Para fazer isso, adicione cada domínio à lista de domínios permitidos. Mesmo se a descoberta de parceiro estiver habilitada para sua organização, faça isso se o domínio for um parceiro federado que pode precisar se comunicar com mais de 1.000 de seus usuários ou talvez precise enviar mais de 20 mensagens por segundo. Se a descoberta de parceiro não estiver habilitada para sua organização, somente os usuários de domínios externos que você adicionar à lista de domínios permitidos poderão participar de mensagens instantâneas e conferência com os usuários da sua organização. Se quiser restringir o acesso de um domínio federado a um servidor específico executando o serviço de borda de acesso do parceiro federado, você pode especificar o nome de domínio do servidor que executa o serviço de borda de acesso para cada domínio na lista de domínios permitidos.

<div>


> [!NOTE]  
> Este procedimento descreve como configurar o suporte para domínios específicos, mas a implementação do suporte a usuários federados também requer que você habilite o suporte para usuários federados para sua organização e configure e aplique políticas para controlar quais usuários podem Colabore com usuários federados. Para obter detalhes sobre como habilitar o suporte a usuários federados, consulte <A href="lync-server-2013-enable-or-disable-remote-user-access.md">habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013</A>. Para obter detalhes sobre a configuração de políticas para controlar a Federação, consulte <A href="lync-server-2013-configure-policies-to-control-federated-user-access.md">Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013</A>.



</div>

<div>

## <a name="to-add-an-external-domain-to-the-list-of-allowed-domains"></a>Para adicionar um domínio externo à lista de domínios permitidos

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso ao usuário externo**e, em seguida, clique em **domínios federados**.

4.  Na página **domínios federados** , clique em **novo**e, em seguida, clique em **domínio permitido**.

5.  Em **novos domínios federados**, faça o seguinte:
    
      - Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado.
        
        <div>
        

        > [!NOTE]  
        > Esse nome deve ser exclusivo e não pode já existir como um domínio permitido para este servidor que está executando o serviço de borda de acesso. O nome não pode exceder 256 caracteres de comprimento.<BR>A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.<BR>Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente. O Lync Server 2013 evita que isso aconteça para que você não precise sincronizar suas listas.

        
        </div>
    
      - Se você quiser restringir o acesso para esse domínio federado para os usuários de um servidor específico executando o serviço de borda de acesso, no **serviço de borda de acesso (FQDN)**, digite o FQDN do servidor do domínio federado executando o serviço de borda de acesso.
    
      - Se você quiser fornecer informações adicionais, em **Comentário**, digite as informações que deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.

7.  Repita as etapas 4 a 6 para cada domínio de parceiro federado que você deseja permitir.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

