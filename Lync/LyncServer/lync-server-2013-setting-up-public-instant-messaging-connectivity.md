---
title: 'Lync Server 2013: Configurar conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up public instant messaging connectivity
ms:assetid: 816dea2a-96fa-4a36-b6c2-a9402675868b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205041(v=OCS.15)
ms:contentKeyID: 48184661
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871f513170fcb0491f6732751cfc1b23877526b8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732251"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configurar conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Se a sua organização quiser dar suporte à conectividade de mensagens instantâneas (IM) pública com a AOL, você não poderá usar o assistente de implantação do Lync Server para solicitar o certificado. Em vez disso, siga as etapas do procedimento a seguir.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configurar a conectividade de mensagens instantâneas públicas

1.  Em um servidor front-end, abra o construtor de topologias. Expanda Pools de bordas e clique com o botão direito do mouse no seu servidor de borda ou no pool do servidor Selecione Editar propriedades.

2.  Em Editar propriedades em geral, selecione Habilitar Federação para este pool de bordas (porta 5061). Clique em OK.

3.  Clique em ação, selecione topologia, selecione publicar. Quando solicitado em publicar a topologia, clique em Avançar. Quando a publicação estiver concluída, clique em concluir.

4.  No servidor de borda, abra o assistente de implantação do Lync Server. Clique em instalar ou atualizar o Lync Server System e, em seguida, clique em configurar ou remover componentes do Lync Server. Clique em executar novamente.

5.  Em configurar componentes do Lync Server, clique em Avançar. A tela Resumo mostrará as ações conforme elas são executadas. Depois que a implantação for concluída, clique em Exibir log para exibir os arquivos de log disponíveis. Clique em concluir para concluir a implantação.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para criar uma solicitação de certificado para a interface externa do servidor de borda para dar suporte à conectividade de mensagem de chat pública com a AOL

1.  Quando o modelo obrigatório estiver disponível para a autoridade de certificação, use o seguinte cmdlet do Windows PowerShell no servidor de borda para solicitar o certificado
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    O nome de certificado padrão do modelo usado para o Lync Server é o servidor Web. Especifique somente o \<nome\> do modelo se precisar usar um modelo diferente do modelo padrão.
    
    <div>
    

    > [!IMPORTANT]  
    > Se a sua organização quiser dar suporte à conectividade de mensagem instantânea pública com a AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso. Isso ocorre porque o modelo de servidor Web da autoridade de certificação (CA) que o assistente de certificado usa para solicitar um certificado não oferece suporte à configuração de EKU de cliente. Antes de usar o Windows PowerShell para criar o certificado, o administrador da CA deve criar e implantar um novo modelo compatível com o EKU do cliente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

