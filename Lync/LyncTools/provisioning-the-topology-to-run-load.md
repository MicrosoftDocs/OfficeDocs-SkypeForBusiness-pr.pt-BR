---
title: Provisionando a topologia para executar o carregamento
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Provisioning the Topology to Run Load
ms:assetid: 6fba03df-3914-4d2a-8208-e252ad993aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945598(v=OCS.15)
ms:contentKeyID: 51541424
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45b1c9d320ef35555e83bbd8851d77e00a452631
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509098"
---
# <a name="provisioning-the-topology-to-run-load"></a><span data-ttu-id="abe7e-102">Provisionando a topologia para executar o carregamento</span><span class="sxs-lookup"><span data-stu-id="abe7e-102">Provisioning the Topology to Run Load</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abe7e-103">_**Última modificação do tópico:** 2013-02-04_</span><span class="sxs-lookup"><span data-stu-id="abe7e-103">_**Topic Last Modified:** 2013-02-04_</span></span>

<div>

<span data-ttu-id="abe7e-104">Dependendo das configurações e da configuração existentes do Lync Server 2013, talvez seja necessário fazer as seguintes alterações no ambiente:</span><span class="sxs-lookup"><span data-stu-id="abe7e-104">Depending on your existing settings and configuration of Lync Server 2013, you may need to make the following changes in your environment:</span></span>

1.  <span data-ttu-id="abe7e-105">Defina a política de execução do Windows PowerShell como irrestrita.</span><span class="sxs-lookup"><span data-stu-id="abe7e-105">Set the Windows PowerShell execution policy to Unrestricted.</span></span> <span data-ttu-id="abe7e-106">Para verificar as configurações da política de execução, abra o Shell de gerenciamento do Lync Server e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="abe7e-106">To check your execution policy settings, open the Lync Server Management Shell and run the following command:</span></span>

    ``` powershell
        Get-ExecutionPolicy
    ```        

    <span data-ttu-id="abe7e-107">Se este comando não retornar o valor Unrestricted, execute este comando:</span><span class="sxs-lookup"><span data-stu-id="abe7e-107">If this command does not return the value Unrestricted, run this command:</span></span>

    ``` powershell
        Set-ExecutionPolicy -Unrestricted
    ```

2.  <span data-ttu-id="abe7e-108">Para configurar efetivamente o Lync Server 2013, será necessário:</span><span class="sxs-lookup"><span data-stu-id="abe7e-108">To effectively configure Lync Server 2013, you will need to:</span></span>
    
      - <span data-ttu-id="abe7e-109">Familiarize-se com a topologia do Lync Server 2013 (por exemplo, nomes de computador, instâncias de serviço, nomes de site e políticas).</span><span class="sxs-lookup"><span data-stu-id="abe7e-109">Be familiar with Lync Server 2013 topology (for example, computer names, service instances, site names, and policies).</span></span>
    
      - <span data-ttu-id="abe7e-110">Atribua alguns dos usuários que foram criados a grupos, como grupos de busca de grupo de resposta (por exemplo, URIs SIP).</span><span class="sxs-lookup"><span data-stu-id="abe7e-110">Assign some of the users that were created to groups, such as Response Group hunt groups (for example, SIP URIs).</span></span>

3.  <span data-ttu-id="abe7e-111">Para executar o script a partir da linha de comando, você pode usar:</span><span class="sxs-lookup"><span data-stu-id="abe7e-111">To run the script from the command line, you may use:</span></span>

    ``` powershell
        Powershell.exe -file <path to the file>
    ```
    
4.  <span data-ttu-id="abe7e-112">Normalmente, depois que um dos scripts desse pacote é executado, os rastreamentos resultantes do script serão armazenados em um arquivo no mesmo caminho a partir do qual o script foi invocado, chamado \<scriptname\> $h $ m $s.txt.</span><span class="sxs-lookup"><span data-stu-id="abe7e-112">Typically, after one of the scripts in this package runs, the resulting traces from the script will be stored in a file in the same path from which the script was invoked, named \<scriptname\>$h$m$s.txt.</span></span> <span data-ttu-id="abe7e-113">Por exemplo, a execução de ArchivingPolicy.ps1 às 12:15 P.M.</span><span class="sxs-lookup"><span data-stu-id="abe7e-113">For example, running ArchivingPolicy.ps1 at 12:15 P.M.</span></span> <span data-ttu-id="abe7e-114">o irá gerar um arquivo de log, como ArchivingPolicy121500.txt.</span><span class="sxs-lookup"><span data-stu-id="abe7e-114">will generate a log file such as ArchivingPolicy121500.txt.</span></span>

5.  <span data-ttu-id="abe7e-115">Por fim, observe que, apesar de fornecermos exemplos para configurar o servidor, você é responsável por modificar ou excluir a configuração após concluir a execução da carga.</span><span class="sxs-lookup"><span data-stu-id="abe7e-115">Finally, note that although we have provided examples to configure the server, you are responsible for modifying or deleting the configuration after you have finished running the load.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

