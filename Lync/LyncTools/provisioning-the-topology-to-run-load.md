---
title: Provisionando a topologia para executar a carga
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf4c296068e2bd0deea9470dd84d8fd0c0c9d451
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Provisionando a topologia para executar a carga

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Provisionando a topologia para executar a carga

Dependendo das configurações e da configuração existentes do Lync Server 2013, talvez seja necessário fazer as seguintes alterações no seu ambiente:

1.  Defina a política de execução do Windows PowerShell como Irrestrito. Para verificar suas configurações de política de execução, abra o Shell de gerenciamento do Lync Server e execute o seguinte comando:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Se esse comando não retornar o valor irrestrito, execute este comando:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Para configurar efetivamente o Lync Server 2013, será necessário:
    
      - Familiarize-se com a topologia do Lync Server 2013 (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).
    
      - Atribua alguns dos usuários que foram criados a grupos, como os números coletivos de grupos de resposta (por exemplo, URIs SIP).

3.  Para executar o script a partir da linha de comando, você pode usar:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Normalmente, após a execução de um dos scripts neste pacote, os rastreamentos resultantes do script serão armazenados em um arquivo no mesmo caminho a partir do qual o script foi invocado \<, chamado\>scriptname $h $ m $ s. txt. Por exemplo, executando ArchivingPolicy. ps1 às 12:15 P.M. vai gerar um arquivo de log, como ArchivingPolicy121500. txt.

5.  Por fim, observe que, embora possamos fornecer exemplos para configurar o servidor, você é responsável por modificar ou excluir a configuração após concluir a execução da carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

