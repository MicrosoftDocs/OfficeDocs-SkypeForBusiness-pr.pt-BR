---
title: 'Lync Server 2013: Publicar sua topologia'
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
ms.openlocfilehash: 6bd80b5b3dfdb71a054c7600a06e892f1396f048
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Publicar sua topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Toda vez que você usa o construtor de topologias para criar sua topologia, você deve publicar a topologia em um banco de dados no repositório de gerenciamento central para que os dados possam ser usados para implantar o Lync Server 2013. Use o procedimento a seguir para publicar sua topologia.

<div>

## <a name="to-publish-the-topology"></a>Para publicar a topologia

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, clique com o botão direito do mouse no **Lync 2013**e clique em **publicar topologia**.

3.  Na página **Bem-vindo** do assistente, clique em **Avançar**.

4.  No **Construtor de topologias localizou uma** página de repositório de CMS, clique em **Avançar**.

5.  Na página **Criar outros bancos de dados**, clique em **Avançar**.

6.  Quando o status indicar que a criação do banco de dados foi bem-sucedida, faça o seguinte:
    
      - Para exibir o log, clique em **Exibir log**.
    
      - Para fechar o assistente, clique em **Concluir**.
        
        <div>
        

        > [!IMPORTANT]  
        > Se esta for uma nova instalação de um servidor de borda ou de um pool de bordas, você deverá exportar a configuração do servidor de borda de um servidor front-end existente, um pool de front-end ou um servidor Standard Edition. Para exportar a configuração, confira <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">exportar sua topologia do Lync Server 2013 e copiá-la para a mídia externa para instalação do Edge</A>. Você vai importar o arquivo de configuração da mídia externa ou do compartilhamento de rede durante a fase de configuração e implantação dos servidores de borda por meio do assistente de implantação do Lync Server.<BR>Depois que os servidores de borda estiverem operacionais e o banco de dados do repositório de gerenciamento de configuração local estiver sendo replicado com a implantação interna, as atualizações subsequentes para a configuração do Lync Server 2013 serão publicadas e replicadas para os servidores de borda.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

