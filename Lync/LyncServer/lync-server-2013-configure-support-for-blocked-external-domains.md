---
title: 'Lync Server 2013: configurar suporte para domínios externos bloqueados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure support for blocked external domains
ms:assetid: 49103138-e1ab-42bf-91aa-57cf23bbf260
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619176(v=OCS.15)
ms:contentKeyID: 49733638
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f24c7db21daa02ff67dc8eb4ddf375c78f96b6d8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179868"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-support-for-blocked-external-domains-in-lync-server-2013"></a>Configurar suporte para domínios externos bloqueados no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Se você tiver configurado o suporte para parceiros federados, poderá gerenciar quais domínios serão impedidos de Federação na sua organização. A lista de domínios bloqueados atuará como uma lista de bloqueios (lista de entradas explícitas que não devem ser permitidas) e será aplicada em descoberta de domínio federado, se você tiver essa opção habilitada. Para obter detalhes, consulte [habilitar ou desabilitar a descoberta de parceiros de Federação no Lync Server 2013](lync-server-2013-enable-or-disable-discovery-of-federation-partners.md).

Bloquear um ou mais domínios externos para se conectar à sua organização. Para fazer isso, adicione o domínio à lista de domínios bloqueados.

<div>

## <a name="to-add-an-external-domain-to-the-list-of-blocked-domains"></a>Para adicionar um domínio externo à lista de domínios bloqueados

1.  A partir de uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou tenha direitos de usuário equivalentes) ou atribuída à função CsAdministrator, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Acesso de Usuário Externo**.

4.  Clique em **domínios federados**, clique em **novo**e em **domínio bloqueado**.

5.  Em **Novos Domínios Federados**, faça o seguinte:
    
      - Em **nome de domínio (ou FQDN)**, digite o nome do domínio de parceiro federado que você deseja bloquear.
        
        <div>
        

        > [!NOTE]  
        > O nome não pode exceder 256 caracteres.<BR>A pesquisa no nome de domínio do parceiro federado realiza uma correspondência de sufixo. Por exemplo, se você digitar <STRONG>contoso.com</STRONG>, a pesquisa também retornará o domínio <STRONG>it.contoso.com</STRONG>.<BR>Um domínio de parceiro federado não pode ser simultaneamente bloqueado e permitido. O Lync Server 2013 impede que isso aconteça para que você não precise sincronizar suas listas.

        
        </div>
    
      - Opcion Em **Comentário**, digite as informações que você deseja compartilhar com outros administradores de sistema sobre essa configuração.

6.  Clique em **Confirmar**.

7.  Repita as etapas de 4 a 6 para cada parceiro federado que você deseja bloquear.

Para habilitar o acesso de usuário federado, habilite também o suporte para acesso de usuário federado em sua organização. Para obter detalhes, consulte [habilitar ou desabilitar o acesso de usuário remoto no Lync Server 2013](lync-server-2013-enable-or-disable-remote-user-access.md).

Além disso, você deve configurar e aplicar a política a usuários que possam colaborar com usuários federados. Para obter detalhes, consulte [Configure Policies to Control Federated User Access in Lync Server 2013](lync-server-2013-configure-policies-to-control-federated-user-access.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

