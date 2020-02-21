---
title: 'Lync Server 2013: Configurando conectividade de mensagens instantâneas públicas'
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
ms.openlocfilehash: e4b3efe4e5d8e5cb84631969205842e56024394c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-public-instant-messaging-connectivity-in-lync-server-2013"></a>Configurando a conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Se sua organização desejar oferecer suporte à conectividade pública de mensagens instantâneas com o AOL, você não pode usar o Assistente de Implantação do Lync Server para solicitar o certificado. Em vez disso, siga o procedimento abaixo.

<div>

## <a name="setting-up-public-instant-messaging-connectivity"></a>Configurando a conectividade para redes públicas de mensagens instantâneas

1.  Em um servidor Front End, abra o Construtor de Topologias. Expanda os pools de borda e clique em seu servidor de borda ou pool de servidor de borda. Selecione as Editar propriedades.

2.  Em Editar Propriedades, sob Geral, selecione Habilitar Federação para este pool de borda (Porta 5061). Clique em OK.

3.  Clique em Ação, selecione Topologia, selecione Publicar. Quando a mensagem sobre Publicar a topologia surgir, clique em Próxima. Quando Publicar for concluído, clique em Concluir.

4.  No servidor de borda, abra o Assistente de Implantação do Lync Server. Clique em Instalar ou Atualizar Sistema do Lync Server; em seguida, clique em Instalação ou Remover Componentes do Lync Server. Clique em Executar Novamente.

5.  Em Componentes de Configuração Lync Server, clique em Próxima. A tela de resumo mostrará as ações conforme forem executadas. Quando a implantação for concluída, clique em Exibir Log para ver os arquivos de log disponíveis. Clique em Concluir para finalizar a implantação.

</div>

<div>

## <a name="to-create-a-certificate-request-for-the-external-interface-of-the-edge-server-to-support-public-im-connectivity-with-aol"></a>Para criar uma solicitação de certificado para a interface externa do Servidor de Borda para oferecer suporte à conectividade pública de IM com o AOL

1.  Quando o modelo necessário estiver disponível para a autoridade de certificação, use o seguinte cmdlet Windows PowerShell no Servidor de Borda para solicitar o certificado:
    
        Request-CsCertificate -New -Type AccessEdgeExternal  -Output C:\ <certfilename.txt or certfilename.csr>  -ClientEku $true -Template <template name>
    
    O nome de certificado padrão do modelo usado para o Lync Server é o servidor Web. Só especifique o \<nome\> do modelo se você precisar usar um modelo diferente do modelo padrão.
    
    <div>
    

    > [!IMPORTANT]  
    > Se sua organização quiser suportar a conectividade pública de IM com o AOL, você deve usar o Windows PowerShell em vez do assistente de certificado para solicitar que o certificado seja atribuído à borda externa do serviço de borda de acesso. Isso ocorre porque o modelo de Servidor Web da Autoridade (CA) usado pelo Assistente de Certificados para solicitar um certificado não oferece suporte à configuração de cliente EKU. Antes de usar o Windows PowerShell para criar o certificado, o administrador da autoridade de certificação deve criar e implantar um novo modelo que dê suporte ao EKU do cliente.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

