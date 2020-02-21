---
title: Atualizar ou atualizar um servidor back end ou um servidor Standard Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Upgrade or update a Back End Server or Standard Edition server
ms:assetid: f95f8d3a-e039-484e-97bd-d727db21a12b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721942(v=OCS.15)
ms:contentKeyID: 49733879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd3617098c42cd38e9928f055a6348a7bf2f9342
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193074"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="upgrade-or-update-a-back-end-server-or-standard-edition-server-in-lync-server-2013"></a><span data-ttu-id="9de49-102">Atualizar ou atualizar um servidor back end ou um servidor Standard Edition no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9de49-102">Upgrade or update a Back End Server or Standard Edition server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9de49-103">_**Última modificação do tópico:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9de49-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9de49-104">Este tópico explica como instalar uma atualização em um servidor de back-end Enterprise Edition ou um servidor Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="9de49-104">This topic explains how to install an update on an Enterprise Edition Back End Server or a Standard Edition server.</span></span>

<span data-ttu-id="9de49-p101">Se o servidor Back End estiver inoperante por ao menos 30 minutos enquanto você o estiver atualizando, os usuários podem entrar em modo de resiliência. Quando a atualização for concluída e os servidores Back End tiver novamente se conectado aos servidores Front End no pool, os usuários são retornados à funcionalidade total. Se a atualização levar menos de 30 minutos, os usuários não serão afetados.</span><span class="sxs-lookup"><span data-stu-id="9de49-p101">If a Back End Server is down for at least 30 minutes while you are upgrading it, users may then go into resiliency mode. When the upgrade is finished and the Back End Servers has again connected with the Front End Servers in the pool, users are returned to full functionality. If the upgrade takes less than 30 minutes, users will not be affected.</span></span>

<div>

## <a name="to-update-a-back-end-server-or-standard-edition-server"></a><span data-ttu-id="9de49-108">Para atualizar um servidor back end ou um servidor Standard Edition</span><span class="sxs-lookup"><span data-stu-id="9de49-108">To update a back end server or Standard Edition server</span></span>

1.  <span data-ttu-id="9de49-109">Faça logon no servidor que você estiver atualizando como um membro da função CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="9de49-109">Log on to the server you are upgrading as a member of the CsAdministrator role.</span></span>

2.  <span data-ttu-id="9de49-110">Faça o download do pacote de atualizações e extraia os arquivos para um disco rígido local.</span><span class="sxs-lookup"><span data-stu-id="9de49-110">Download the update and extract it to the local hard disk.</span></span>

3.  <span data-ttu-id="9de49-111">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9de49-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

4.  <span data-ttu-id="9de49-p102">Pare os serviços do Lync Server. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9de49-p102">Stop Lync Server services. At the command line, type:</span></span>
    
        Stop-CsWindowsService

5.  <span data-ttu-id="9de49-p103">Pare o serviço World Wide Web. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9de49-p103">Stop the World Wide Web service. At the command line, type:</span></span>
    
        net stop w3svc

6.  <span data-ttu-id="9de49-116">Feche todas as janelas do Shell de gerenciamento do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9de49-116">Close all Lync Server Management Shell windows.</span></span>

7.  <span data-ttu-id="9de49-117">Atualize a atualização.</span><span class="sxs-lookup"><span data-stu-id="9de49-117">Install the update.</span></span>

8.  <span data-ttu-id="9de49-118">Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="9de49-118">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

9.  <span data-ttu-id="9de49-p104">Pare os serviços do Lync Server novamente para capturar os conjuntos GAC (cache de assembly global) –d. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9de49-p104">Stop Lync Server services again to catch Global Assembly Cache (GAC) –d assemblies. At the command line, type:</span></span>
    
        Stop-CsWindowsService

10. <span data-ttu-id="9de49-p105">Reinicie o serviço World Wide Web. Na linha de comando, digite:</span><span class="sxs-lookup"><span data-stu-id="9de49-p105">Restart the World Wide Web service. At the command line, type:</span></span>
    
        net start w3svc

11. <span data-ttu-id="9de49-123">Aplique as alterações feitas pelo LyncServerUpdateInstaller.exe para os bancos de dados SQL Server por meio de uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="9de49-123">Apply the changes made by LyncServerUpdateInstaller.exe to the SQL Server databases by doing one of the following:</span></span>
    
      - <span data-ttu-id="9de49-124">Se este for um servidor back-end Enterprise Edition e não houver bancos de dados colocados neste servidor, como os bancos de dados de arquivamento ou monitoramento, digite o seguinte na linha de comando:</span><span class="sxs-lookup"><span data-stu-id="9de49-124">If this is an Enterprise Edition Back End Server and there are no collocated databases on this server, such as Archiving or Monitoring databases, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>
    
      - <span data-ttu-id="9de49-125">Se este for um servidor back-end Enterprise Edition e houver bancos de dados colocados neste servidor, digite o seguinte em uma linha de comando:</span><span class="sxs-lookup"><span data-stu-id="9de49-125">If this is an Enterprise Edition Back End Server and there are collocated databases on this server, then type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -ConfiguredDatabases -SqlServerFqdn <SQL Server FQDN>  -ExcludeCollocatedStores
    
      - <span data-ttu-id="9de49-126">Se este for um servidor Standard Edition, digite o seguinte em uma linha de comando:</span><span class="sxs-lookup"><span data-stu-id="9de49-126">If this is an Standard Edition server, type the following at a command line:</span></span>
        
            Install-CsDatabase -Update -LocalDatabases

</div>

</div>

<span> </span>

</div>

</div>

</div>

