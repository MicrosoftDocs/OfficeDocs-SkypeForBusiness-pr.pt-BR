---
title: Instalando os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 99eccdd8d6473c25c6096c370f616975c7da141f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="3ae77-102">Instalando os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal</span><span class="sxs-lookup"><span data-stu-id="3ae77-102">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ae77-103">_**Tópico da última modificação:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="3ae77-103">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="3ae77-104">Para instalar os arquivos do Lync Server 2013 Core em um computador, conclua o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="3ae77-104">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="3ae77-105">O banco de dados do RTCLocal é instalado automaticamente quando você instala os arquivos principais.</span><span class="sxs-lookup"><span data-stu-id="3ae77-105">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="3ae77-106">Observe que você não precisa instalar o SQL Server nos nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3ae77-106">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="3ae77-107">Em vez disso, o SQL Server Express é instalado automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="3ae77-107">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="3ae77-108">Para instalar os arquivos do Lync Server 2013 Core e o banco de dados do RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="3ae77-108">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="3ae77-109">No computador do nó do Inspetor, clique em **Iniciar**, **em todos os programas**, em **acessórios**, clique com o botão direito do mouse em **prompt de comando**e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="3ae77-109">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="3ae77-110">Na janela do console, digite o seguinte comando e pressione ENTER, usando o caminho apropriado para os arquivos de instalação do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="3ae77-110">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="3ae77-111">Para verificar se os componentes principais do Lync Server foram instalados com êxito, clique em **Iniciar**, clique em **todos os programas**, clique em **Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="3ae77-111">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="3ae77-112">No Shell de gerenciamento do Lync Server 2013, digite o seguinte comando do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="3ae77-112">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="3ae77-113">Na primeira vez que você executar esse comando, nenhum dado será retornado porque você ainda não configurou nenhum computador do nó do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="3ae77-113">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="3ae77-114">Desde que o comando seja executado sem retornar um erro, você pode presumir que a instalação do Lync Server foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="3ae77-114">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="3ae77-115">Se o seu computador do nó do Inspetor estiver localizado dentro da sua rede de perímetro, você pode executar o seguinte comando para verificar a instalação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="3ae77-115">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="3ae77-116">Você receberá informações semelhantes às seguintes, dependendo do número de políticas de PIN (número de identificação pessoal) configuradas para usar em sua organização:</span><span class="sxs-lookup"><span data-stu-id="3ae77-116">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="3ae77-117">Se você vir informações sobre suas políticas de PIN, isso significa que você instalou os componentes principais com êxito.</span><span class="sxs-lookup"><span data-stu-id="3ae77-117">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

