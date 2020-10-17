---
title: 'Lync Server 2013: restaurar um repositório de arquivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd1984c6e51866b1ace707f305fb2a6cc356a132
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511608"
---
# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restaurando um repositório de arquivos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-18_

Os repositórios de arquivos do Standard Edition geralmente estão localizados no servidor Standard Edition. Os Repositórios de Arquivo para o Enterprise Edition estão normalmente localizados em um cluster ou servidor de arquivos. O procedimento a seguir descreve como restaurar um repositório de arquivos.

<div>

## <a name="to-restore-a-file-store"></a>Para restaurar um Re positório de arquivo

1.  Se um repositório de arquivos falhar, copie o repositório de arquivos apropriado de $Backup \\ para o local do repositório de arquivos no servidor de arquivos ou no servidor Standard Edition e, em seguida, compartilhe a pasta.
    
    <div>
    

    > [!IMPORTANT]  
    > O caminho e o nome de arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do repositório de arquivos de backup, para que os componentes que usam os arquivos possam acessá-los.

    
    </div>

2.  Se necessário, defina as listas de controle de acesso (ACLs) para o repositório de arquivos. Na linha de comando, digite:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Você só precisará executar esta etapa se não tiver executado o construtor de topologias durante o processo de restauração.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

