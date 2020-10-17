---
title: 'Lync Server 2013: publicar sua topologia'
description: 'Lync Server 2013: publicar sua topologia.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4d27d2d3644eb1f174e2f3fab47197f2c122a97
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571747"
---
# <a name="publish-your-topology-in-lync-server-2013"></a>Publicar sua topologia no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Toda vez que você usa o construtor de topologias para criar sua topologia, você deve publicar a topologia em um banco de dados no repositório de gerenciamento central para que os dados possam ser usados para implantar o Lync Server 2013. Execute o procedimento a seguir para publicar a topologia.

<div>

## <a name="to-publish-the-topology"></a>Para publicar a topologia

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, clique com o botão direito do mouse em **Lync 2013**e clique em **publicar topologia**.

3.  Na página **Bem-vindo** do assistente, clique em **Avançar**.

4.  Na página **Construtor de Topologia encontrou um repositório CMS**, clique em **Avançar**.

5.  Na página **Criar outros bancos de dados**, clique em **Avançar**.

6.  Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:
    
      - Para exibir o log, clique em **Exibir log**.
    
      - Para fechar o assistente, clique em **Concluir**.
        
        <div>
        

        > [!IMPORTANT]  
        > Se esta é uma nova instalação de um servidor de borda ou de um pool de borda, você deve exportar a configuração do servidor de borda de um servidor front-end existente, pool de front-end ou servidor Standard Edition. Para exportar a configuração, confira <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar sua topologia do Lync Server 2013 e copiá-la para mídia externa para instalação de borda</A>. Você importará o arquivo de configuração da mídia externa ou compartilhamento de rede durante a fase de instalação e implantação dos servidores de borda por meio do assistente de implantação do Lync Server.<BR>Depois que os servidores de borda estiverem operacionais e o banco de dados do repositório de configuração local estiver replicando com a implantação interna, as atualizações subsequentes para a configuração do Lync Server 2013 serão publicadas e replicadas para os servidores de borda.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

