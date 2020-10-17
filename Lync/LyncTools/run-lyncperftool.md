---
title: Executar LyncPerfTool
description: Execute o LyncPerfTool.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3278754c9154f47602c5c4f1fa95cdc4b465b228
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560077"
---
# <a name="run-lyncperftool"></a><span data-ttu-id="34367-103">Executar LyncPerfTool</span><span class="sxs-lookup"><span data-stu-id="34367-103">Run LyncPerfTool</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34367-104">_**Última modificação do tópico:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="34367-104">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="34367-105">Antes de executar a ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool.exe), você deve criar usuários, contatos e cenários.</span><span class="sxs-lookup"><span data-stu-id="34367-105">Before running the Lync Server 2013 Stress and Performance Tool (LyncPerfTool.exe), you must create users, contacts, and scenarios.</span></span> <span data-ttu-id="34367-106">Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [Create Users and contacts](create-users-and-contacts.md) e [Configure User Profile](configure-user-profile.md).</span><span class="sxs-lookup"><span data-stu-id="34367-106">For details about using the tools to perform these actions, see [Create Users and Contacts](create-users-and-contacts.md) and [Configure User Profile](configure-user-profile.md).</span></span> <span data-ttu-id="34367-107">A execução dessas ferramentas também gerará um arquivo que será executado LyncPerfTool.exe como parte de um arquivo em lote com os parâmetros necessários incluídos.</span><span class="sxs-lookup"><span data-stu-id="34367-107">Running these tools will also generate a file that will run LyncPerfTool.exe as part of a batch file with the required parameters included.</span></span>

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a><span data-ttu-id="34367-108">Executando a ferramenta de estresse e desempenho do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="34367-108">Running the Lync Server 2013 Stress and Performance Tool</span></span>

<span data-ttu-id="34367-109">A ferramenta UserProfileGenerator.exe cria um arquivo em lotes que permite que você execute LyncPerfTool.exe registrando os contadores de desempenho do LyncPerfTool e carregando o arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="34367-109">The UserProfileGenerator.exe tool creates a batch file that enables you to run LyncPerfTool.exe by registering the LyncPerfTool performance counters and loading the XML configuration file.</span></span> <span data-ttu-id="34367-110">O arquivo em lotes executa uma instância do LyncPerfTool.exe por arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="34367-110">The batch file runs one instance of LyncPerfTool.exe per configuration file.</span></span> <span data-ttu-id="34367-111">Para executar o arquivo em lotes, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="34367-111">To run the batch file, do the following:</span></span>

1.  <span data-ttu-id="34367-112">Copie a pasta que contém as pastas e os arquivos de configuração para o diretório que contém LyncStressTool.exe em cada computador cliente.</span><span class="sxs-lookup"><span data-stu-id="34367-112">Copy the folder that contains the configuration folders and files to the directory that contains LyncStressTool.exe on each client computer.</span></span> <span data-ttu-id="34367-113">(Por exemplo, se você gerou os arquivos de configuração na pasta chamada 1,28 \_ 13.16.16, copie essa pasta para a pasta que contém LyncPerfTool.exe em cada cliente.)</span><span class="sxs-lookup"><span data-stu-id="34367-113">(For example, if you generated the configuration files in the folder named 1.28\_13.16.16, copy that folder to the folder that contains LyncPerfTool.exe on each client.)</span></span>

2.  <span data-ttu-id="34367-114">Navegue até a pasta de cliente numerada apropriadamente e execute o script de lote do RunClient.</span><span class="sxs-lookup"><span data-stu-id="34367-114">Navigate to the appropriately numbered client folder and run the RunClient batch script.</span></span> <span data-ttu-id="34367-115">Você pode simplesmente clicar duas vezes no arquivo em lotes no Windows Explorer e ele executará todos os arquivos de configuração desse número de cliente.</span><span class="sxs-lookup"><span data-stu-id="34367-115">You can simply double-click the batch file in Windows Explorer and it will run all of the configuration files for that client number.</span></span> <span data-ttu-id="34367-116">Você também pode executar o script a partir da pasta de cliente apropriada usando a seguinte sintaxe:</span><span class="sxs-lookup"><span data-stu-id="34367-116">You can also run the script from the appropriate client folder by using the following syntax:</span></span>

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
<span data-ttu-id="34367-117">Para executar o LyncPerfTool.exe diretamente, abra um prompt de comando e, em seguida, digite o seguinte comando na linha de comando (ao fazer isso pela primeira vez, não se esqueça de registrar os contadores de desempenho regsvr32/i/n LyncPerfToolPerf.dll, conforme mostrado na observação posteriormente neste tópico) :LyncPerfTool.exe/file:\<configXML\></span><span class="sxs-lookup"><span data-stu-id="34367-117">To run LyncPerfTool.exe directly, open a command prompt, and then type the following command at the command line (when doing this for the first time, be sure to register the performance counters regsvr32 /i /n /s LyncPerfToolPerf.dll, as show in the note later in this topic):LyncPerfTool.exe /file:\<configXML\></span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
<span data-ttu-id="34367-118">Para que a ferramenta exiba os valores no arquivo de configuração, inclua o parâmetro/displayfile no comando anterior, da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="34367-118">To have the tool display the values in the configuration file, include the /displayfile parameter on the preceding command, like this:</span></span>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
<span data-ttu-id="34367-119">Para finalizar o processo, pressione CTRL + C.</span><span class="sxs-lookup"><span data-stu-id="34367-119">To end the process, press Ctrl+C.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34367-120">Antes de executar o LyncPerfTool diretamente, você deve registrar os contadores de desempenho.</span><span class="sxs-lookup"><span data-stu-id="34367-120">Before running LyncPerfTool directly, you must register the performance counters.</span></span> <span data-ttu-id="34367-121">Insira o seguinte comando para registrar contadores de desempenho:</span><span class="sxs-lookup"><span data-stu-id="34367-121">Enter the following command to register performance counters:</span></span>



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> <span data-ttu-id="34367-122">Cada instância do LyncPerfTool.exe que você inicia imediatamente começará a se conectar aos usuários, normalmente com uma taxa de um usuário por segundo.</span><span class="sxs-lookup"><span data-stu-id="34367-122">Every instance of LyncPerfTool.exe that you start will immediately start signing in users, usually at a rate of one user per second.</span></span> <span data-ttu-id="34367-123">A taxa de entrada de pico do pool de usuários é de cerca de 12 por segundo.</span><span class="sxs-lookup"><span data-stu-id="34367-123">The peak user sign-in rate for the pool is about 12 per second.</span></span> <span data-ttu-id="34367-124">Isso significa que você não deve iniciar mais de 12 instâncias do LyncPerfTool ao mesmo tempo, enquanto os usuários ainda estão entrando.</span><span class="sxs-lookup"><span data-stu-id="34367-124">This means that you should not start more than 12 LyncPerfTool instances at the same time, while the users are still signing in.</span></span> <span data-ttu-id="34367-125">1000 os usuários levarão cerca de 20 minutos para entrar totalmente, de uma por segundo.</span><span class="sxs-lookup"><span data-stu-id="34367-125">1000 users will take about 20 minutes to fully sign in, at one per second.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="34367-126">Confira também</span><span class="sxs-lookup"><span data-stu-id="34367-126">See Also</span></span>


[<span data-ttu-id="34367-127">Criar usuários e contatos</span><span class="sxs-lookup"><span data-stu-id="34367-127">Create Users and Contacts</span></span>](create-users-and-contacts.md)  
[<span data-ttu-id="34367-128">Configurar perfil de usuário</span><span class="sxs-lookup"><span data-stu-id="34367-128">Configure User Profile</span></span>](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

