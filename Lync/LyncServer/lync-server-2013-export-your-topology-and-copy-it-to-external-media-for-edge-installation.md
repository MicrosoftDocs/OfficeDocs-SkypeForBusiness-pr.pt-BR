---
title: Exportar sua topologia e copiá-la para a mídia externa para instalação de borda
description: Exporte sua topologia e copie-a para a mídia externa para instalação de borda.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47fcee032b4c0e667455ae7f35afe8b99c2d12cc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564757"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>Exporte sua topologia do Lync Server 2013 e copie-a para a mídia externa para instalação de borda

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Depois de publicar sua topologia, o assistente de implantação do Lync Server precisa acessar os dados do repositório de gerenciamento central para iniciar o processo de implantação no servidor. Na rede interna, os dados estão disponíveis diretamente nos servidores, mas os servidores de borda que não estão no domínio interno não podem acessar os dados. Para disponibilizar os dados de configuração de topologia para uma implantação de servidor de borda, você deve exportar os dados de topologia para um arquivo e copiá-los para a mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que está disponível no servidor de borda) antes de executar o assistente de implantação do Lync Server no servidor de borda. Use o procedimento a seguir para tornar os dados de configuração de topologia disponíveis no servidor de borda que você está implantando.

<div>


> [!NOTE]
> Após instalar o Lync Server 2013 em um servidor de borda, você gerencia o servidor de borda usando as ferramentas administrativas da rede interna, que replicam automaticamente a configuração para qualquer servidor de borda em sua implantação. A única exceção é a atribuição e instalação de certificados e a interrupção e início de serviços, que devem ser feitos no servidor de borda.



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>Para disponibilizar os dados de topologia em um servidor de borda usando o Shell de gerenciamento do Lync Server

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  No Shell de gerenciamento do Lync Server, execute o seguinte cmdlet:
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  Copie o arquivo exportado para a mídia externa (por exemplo, uma unidade USB ou um compartilhamento de rede que está disponível no servidor de borda durante a implantação).

</div>

</div>

<span> </span>

</div>

</div>

</div>

