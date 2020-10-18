---
title: Instalando os arquivos principais do Lync Server 2013 e o banco de dados RTCLocal
description: Instalando os arquivos principais do Lync Server 2013 e o banco de dados RTCLocal.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing the Lync Server 2013 core files and the RTCLocal database
ms:assetid: 206f0c1d-40f7-45b6-aa62-88aaef6cf7f6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204734(v=OCS.15)
ms:contentKeyID: 48183591
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68964f8b80f6377afd859d113783d61e33afbebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573857"
---
# <a name="installing-the-lync-server-2013-core-files-and-the-rtclocal-database"></a><span data-ttu-id="ba354-103">Instalando os arquivos principais do Lync Server 2013 e o banco de dados RTCLocal</span><span class="sxs-lookup"><span data-stu-id="ba354-103">Installing the Lync Server 2013 core files and the RTCLocal database</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ba354-104">_**Última modificação do tópico:** 2012-10-20_</span><span class="sxs-lookup"><span data-stu-id="ba354-104">_**Topic Last Modified:** 2012-10-20_</span></span>

<span data-ttu-id="ba354-105">Para instalar os arquivos principais do Lync Server 2013 em um computador, conclua o procedimento a seguir.</span><span class="sxs-lookup"><span data-stu-id="ba354-105">To install the Lync Server 2013 core files on a computer, complete the following procedure.</span></span> <span data-ttu-id="ba354-106">O banco de dados RTCLocal é instalado automaticamente ao instalar os principais arquivos.</span><span class="sxs-lookup"><span data-stu-id="ba354-106">The RTCLocal database is automatically installed when you install the core files.</span></span> <span data-ttu-id="ba354-107">Observe que não é necessário instalar o SQL Server nos nós do Inspetor.</span><span class="sxs-lookup"><span data-stu-id="ba354-107">Note that you do not need to install SQL Server on the watcher nodes.</span></span> <span data-ttu-id="ba354-108">Em vez disso, o SQL Server Express é instalado automaticamente para você.</span><span class="sxs-lookup"><span data-stu-id="ba354-108">Instead, SQL Server Express is automatically installed for you.</span></span>

<span data-ttu-id="ba354-109">Para instalar os arquivos principais do Lync Server 2013 e o banco de dados do RTCLocal:</span><span class="sxs-lookup"><span data-stu-id="ba354-109">To install the Lync Server 2013 core files and the RTCLocal database:</span></span>

1.  <span data-ttu-id="ba354-110">No computador do nó do observador, clique em **Iniciar**, em **Todos os programas**, em **Acessórios**, clique com o botão direito no **Prompt de comando** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="ba354-110">On the watcher node computer, click **Start**, click **All Programs**, click **Accessories**, right-click **Command Prompt**, and then click **Run as administrator**.</span></span>

2.  <span data-ttu-id="ba354-111">Na janela do console, digite o seguinte comando e pressione ENTER, usando o caminho apropriado para seus arquivos de instalação do Lync Server:</span><span class="sxs-lookup"><span data-stu-id="ba354-111">In the console window, type the following command and then press ENTER, using the appropriate path to your Lync Server setup files:</span></span>
    
        D:\Setup.exe /BootstrapLocalMgmt

<span data-ttu-id="ba354-112">Para verificar se os principais componentes do Lync Server foram instalados com êxito, clique em **Iniciar**, em **todos os programas**, em **Lync Server 2013**e em **Shell de gerenciamento do Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="ba354-112">To verify that the core Lync Server components were successfully installed, click **Start**, click **All Programs**, click **Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span> <span data-ttu-id="ba354-113">No Shell de gerenciamento do Lync Server 2013, digite o seguinte comando do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="ba354-113">In the Lync Server 2013 Management Shell, type the following Windows PowerShell command, and then press ENTER:</span></span>

    Get-CsWatcherNodeConfiguration

<span data-ttu-id="ba354-114">A primeira vez que você executar este comando, nenhum dado é retornado porque você não configurou qualquer computador do nó do observador.</span><span class="sxs-lookup"><span data-stu-id="ba354-114">The first time you run this command, you no data is returned because you have not configured any watcher node computers yet.</span></span> <span data-ttu-id="ba354-115">Contanto que o comando seja executado sem retornar um erro, você pode supor que a instalação do Lync Server foi concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="ba354-115">As long as the command runs without returning an error, you can assume that the Lync Server setup completed successfully.</span></span>

<span data-ttu-id="ba354-116">Se seu computador do nó do observador estiver localizado dentro de sua rede de perímetro, você poderá executar o seguinte comando para verificar a instalação do Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="ba354-116">If your watcher node computer is located inside your perimeter network, you can run the following command to verify the installation of Lync Server 2013:</span></span>

    Get-CsPinPolicy

<span data-ttu-id="ba354-117">Você irá receber informações semelhantes ao seguinte, dependendo do número de políticas de PIN configuradas para uso em sua organização:</span><span class="sxs-lookup"><span data-stu-id="ba354-117">You will receive information similar to the following, depending on the number of personal identification number (PIN) policies configured for use in your organization:</span></span>

    Identity             : Global
    Description          :
    MinPasswordLength    : 5
    PINHistoryCount      : 0
    AllowCommonPatterns  : False
    PINLifetime          : 0
    MaximumLogonAttempts :

<span data-ttu-id="ba354-118">Se você ver informações sobre suas políticas de PIN, significa que você instalou com sucesso os principais componentes.</span><span class="sxs-lookup"><span data-stu-id="ba354-118">If you see information about your PIN policies, it means that you have successfully installed the core components.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

