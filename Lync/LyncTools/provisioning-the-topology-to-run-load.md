---
title: Provisionando a topologia para executar o carregamento
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
ms.openlocfilehash: 08f9cd219e70f1f761ac49932b73ca0d8c618121
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196084"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-the-topology-to-run-load"></a>Provisionando a topologia para executar o carregamento

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-04_

<div>

## <a name="provisioning-the-topology-to-run-load"></a>Provisionando a topologia para executar o carregamento

Dependendo das configurações e da configuração existentes do Lync Server 2013, talvez seja necessário fazer as seguintes alterações no ambiente:

1.  Defina a política de execução do Windows PowerShell como irrestrita. Para verificar as configurações da política de execução, abra o Shell de gerenciamento do Lync Server e execute o seguinte comando:

    ``` powershell
        Get-ExecutionPolicy
    ```        

    Se este comando não retornar o valor Unrestricted, execute este comando:

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  Para configurar efetivamente o Lync Server 2013, será necessário:
    
      - Familiarize-se com a topologia do Lync Server 2013 (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).
    
      - Atribua alguns dos usuários que foram criados a grupos, como grupos de busca de grupo de resposta (por exemplo, URIs SIP).

3.  Para executar o script a partir da linha de comando, você pode usar:

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  Normalmente, depois que um dos scripts desse pacote é executado, os rastreamentos resultantes do script serão armazenados em um arquivo no mesmo caminho a partir do qual o script foi invocado \<, chamado\>scriptname $h $ m $ s. txt. Por exemplo, executando ArchivingPolicy. ps1 às 12:15 P.M. o irá gerar um arquivo de log, como ArchivingPolicy121500. txt.

5.  Por fim, observe que, apesar de fornecermos exemplos para configurar o servidor, você é responsável por modificar ou excluir a configuração após concluir a execução da carga.

</div>

</div>

<span> </span>

</div>

</div>

</div>

