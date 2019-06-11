---
title: 'Lync Server 2013: Configurar suporte para domínios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08191e8600f5e247ba6b4a358557ea3def0a1756
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836320"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurar suporte para domínios externos bloqueados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão bloqueados a partir da Federação em sua organização. A lista de domínios bloqueados atuará como uma lista de blocos (lista de entradas explícitas que não são permitidas) e será aplicada à descoberta de domínio federado, se você tiver essa opção habilitada. Para obter detalhes, consulte [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquear um ou mais domínios externos para se conectar à sua organização. Para fazer isso, adicione o domínio à lista de domínios bloqueados.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para adicionar um domínio externo à lista de domínios bloqueados

1.  Usando uma conta de usuário que é membro do grupo RTCUniversalServerAdmins (ou tem direitos de usuário equivalentes), ou está atribuída à função CsAdministrator, faça logon em qualquer computador de sua implantação interna.

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação à esquerda, clique em **acesso de usuário externo**.

4.  Clique em **domínios federados**, clique em **novo**e, em seguida, clique em **domínio bloqueado**.

5.  Em **novos domínios federados**, faça o seguinte:
    
      - Em **nome do domínio (ou FQDN)**, digite o nome do domínio do parceiro federado que você deseja bloquear.
        
        <div>
        

        > [!NOTE]  
        > O nome não pode exceder 256 caracteres de comprimento.<BR>A pesquisa no nome de domínio do parceiro federado executa uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.<BR>Um domínio de parceiro federado não pode ser bloqueado e permitido simultaneamente. O Lync Server 2013 evita que isso aconteça para que você não precise sincronizar suas listas.

        
        </div>
    
      - Adicionais Em **Comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.

7.  Repita as etapas 4 a 6 para cada parceiro federado que você deseja bloquear.

Para habilitar o acesso de usuário federado, você também deve habilitar o suporte para o acesso de usuários federados em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política aos usuários que você deseja que possam colaborar com os usuários federados. Para obter detalhes, consulte [Configurar políticas para controlar o acesso de usuários federados no Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

