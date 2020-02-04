---
title: 'Lync Server 2013: restaurando um armazenamento de arquivos'
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
ms.openlocfilehash: c013159de83d258273e381dd54556bcceec056f7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723561"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Restaurando um armazenamento de arquivos no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-18_

Os repositórios de arquivos para a edição Standard estão geralmente localizados no servidor Standard Edition. O armazenamento de arquivos para Enterprise Edition geralmente está localizado em um servidor de arquivos ou cluster. O procedimento a seguir descreve como restaurar um armazenamento de arquivos.

<div>

## <a name="to-restore-a-file-store"></a>Para restaurar um armazenamento de arquivos

1.  Se um armazenamento de arquivos falhar, copie o armazenamento de arquivos apropriado\\ de $backup para o local do repositório de arquivos no servidor de arquivos ou no servidor Standard Edition e, em seguida, compartilhe a pasta.
    
    <div>
    

    > [!IMPORTANT]  
    > O caminho e o nome do arquivo do repositório de arquivos restaurados devem ser exatamente os mesmos do armazenamento de arquivos de backup, para que os componentes que usam os arquivos possam acessá-los.

    
    </div>

2.  Se necessário, defina as listas de controle de acesso (ACLs) para o repositório de arquivos. Na linha de comando, digite:
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > Você só precisará executar essa etapa se não tiver executado o construtor de topologias durante o processo de restauração.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

