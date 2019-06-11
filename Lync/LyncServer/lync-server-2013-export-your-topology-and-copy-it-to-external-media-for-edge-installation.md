---
title: Exportar sua topologia e copiá-la na mídia externa para instalação de borda
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7cdd947287ec5b7fef90d27df6df2dd256481000
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829185"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exportar sua topologia do Lync Server 2013 e copiá-la na mídia externa para instalação de borda

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Depois de publicar sua topologia, o assistente de implantação do Lync Server precisa acessar os dados do repositório de gerenciamento central para iniciar o processo de implantação no servidor. Na rede interna, os dados estão disponíveis diretamente nos servidores, mas os servidores de borda que não estão no domínio interno não podem acessar os dados. Para disponibilizar os dados de configuração de topologia para uma implantação de servidor de borda, você deve exportar os dados de topologia para um arquivo e copiá-los para mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que esteja disponível no servidor de borda) antes de executar a DEP do Lync Server Assistente de loyment no servidor de borda. Use o procedimento a seguir para disponibilizar os dados de configuração de topologia no servidor de borda que você está implantando.

<div>


> [!NOTE]
> Depois de instalar o Lync Server 2013 em um servidor de borda, você gerencia o servidor de borda usando as ferramentas administrativas da rede interna, que replica automaticamente a configuração para qualquer servidor de borda na sua implantação. A única exceção é atribuir e instalar certificados e interromper e iniciar serviços, ambos devem ser feitos no servidor de borda.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Para disponibilizar os dados de topologia em um servidor de borda usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  No Shell de gerenciamento do Lync Server, execute o seguinte cmdlet:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copie o arquivo exportado para mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que esteja disponível no servidor de borda durante a implantação).

</div>

</div>

<span> </span>

</div>

</div>

</div>

