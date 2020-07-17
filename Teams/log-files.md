---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre registros de depuração, mídia e desktop produzidos pelo Microsoft Teams, onde podem ser encontrados e como eles podem ajudar na resolução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2303082c4f1c16a28a9116047d904a5d491a535a
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085747"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="c7eb1-103">Usar arquivos de registro para solucionar problemas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c7eb1-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="c7eb1-104">Existem três tipos de arquivos de registro produzidos automaticamente pelo cliente que podem ser aproveitados para ajudar na solução de problemas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="c7eb1-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="c7eb1-105">Debug logs</span></span>

-   <span data-ttu-id="c7eb1-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="c7eb1-106">Media logs</span></span>

-   <span data-ttu-id="c7eb1-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="c7eb1-107">Desktop logs</span></span>

<span data-ttu-id="c7eb1-108">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="c7eb1-109">Ter esses registros em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="c7eb1-110">Os registros de mídia ou de desktop só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="c7eb1-111">A tabela a seguir descreve os diversos clientes e seus registros associados.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="c7eb1-112">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="c7eb1-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="c7eb1-113">Client</span></span> |<span data-ttu-id="c7eb1-114">Depuração</span><span class="sxs-lookup"><span data-stu-id="c7eb1-114">Debug</span></span>|<span data-ttu-id="c7eb1-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="c7eb1-115">Desktop</span></span>|<span data-ttu-id="c7eb1-116">Mídia</span><span class="sxs-lookup"><span data-stu-id="c7eb1-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="c7eb1-117">Web</span><span class="sxs-lookup"><span data-stu-id="c7eb1-117">Web</span></span>    |<span data-ttu-id="c7eb1-118">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-118">X</span></span>         |-         |-         |
|<span data-ttu-id="c7eb1-119">Windows</span><span class="sxs-lookup"><span data-stu-id="c7eb1-119">Windows</span></span>     |<span data-ttu-id="c7eb1-120">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-120">X</span></span>         |<span data-ttu-id="c7eb1-121">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-121">X</span></span>         |<span data-ttu-id="c7eb1-122">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-122">X</span></span>         |
|<span data-ttu-id="c7eb1-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c7eb1-123">Mac OSX</span></span>     |<span data-ttu-id="c7eb1-124">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-124">X</span></span>         |<span data-ttu-id="c7eb1-125">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-125">X</span></span>         |<span data-ttu-id="c7eb1-126">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-126">X</span></span>         |
|<span data-ttu-id="c7eb1-127">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eb1-127">Linux</span></span>     |<span data-ttu-id="c7eb1-128">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-128">X</span></span>         |<span data-ttu-id="c7eb1-129">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-129">X</span></span>         |<span data-ttu-id="c7eb1-130">X</span><span class="sxs-lookup"><span data-stu-id="c7eb1-130">X</span></span>         |
|<span data-ttu-id="c7eb1-131">iOS</span><span class="sxs-lookup"><span data-stu-id="c7eb1-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="c7eb1-132">Android</span><span class="sxs-lookup"><span data-stu-id="c7eb1-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="c7eb1-133">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="c7eb1-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="c7eb1-134">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="c7eb1-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="c7eb1-135">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="c7eb1-136">Os logs de depuração são produzidos pelos clientes de área de trabalho do Windows e do Mac, bem como clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="c7eb1-137">Os registros são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="c7eb1-138">Eles podem ser lidos usando qualquer editor baseado em texto, e novos registros são criados ao acessar o cliente.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="c7eb1-139">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="c7eb1-140">Login</span><span class="sxs-lookup"><span data-stu-id="c7eb1-140">Login</span></span>

-   <span data-ttu-id="c7eb1-141">Solicitações de conexão para serviços de camada intermediária</span><span class="sxs-lookup"><span data-stu-id="c7eb1-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="c7eb1-142">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="c7eb1-142">Call/conversation</span></span>

<span data-ttu-id="c7eb1-143">Os registros de depuração são produzidos usando os seguintes métodos para o sistema operacional específico:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="c7eb1-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-144">Windows:</span></span>

      <span data-ttu-id="c7eb1-145">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="c7eb1-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="c7eb1-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-146">Mac OSX:</span></span>

      <span data-ttu-id="c7eb1-147">Atalho do teclado: Opção + Comando + Shift+1</span><span class="sxs-lookup"><span data-stu-id="c7eb1-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="c7eb1-148">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eb1-148">Linux:</span></span>

      <span data-ttu-id="c7eb1-149">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="c7eb1-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="c7eb1-150">Os registros de depuração serão baixados automaticamente nas seguintes pastas.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="c7eb1-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="c7eb1-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="c7eb1-152">Mac OSX: Downloads</span><span class="sxs-lookup"><span data-stu-id="c7eb1-152">Mac OSX: Downloads</span></span>

-   <span data-ttu-id="c7eb1-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="c7eb1-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="c7eb1-154">Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento</span><span class="sxs-lookup"><span data-stu-id="c7eb1-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="c7eb1-155">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="c7eb1-155">Media Logs</span></span>
---------------------------

<span data-ttu-id="c7eb1-156">Os registros de mídia contêm dados de diagnóstico de áudio, vídeo e compartilhamento de tela.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-156">Media logs contain diagnostic data about audio, video and screen sharing.</span></span> <span data-ttu-id="c7eb1-157">Eles são necessários para casos de suporte apenas mediante solicitação e só podem ser inspecionados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-157">They are required for support cases only upon request and can only be inspected by Microsoft.</span></span> <span data-ttu-id="c7eb1-158">A tabela a seguir descreve a localização dos arquivos.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-158">The following table outlines the log location.</span></span>


|<span data-ttu-id="c7eb1-159">Cliente</span><span class="sxs-lookup"><span data-stu-id="c7eb1-159">Client</span></span> |<span data-ttu-id="c7eb1-160">Localização</span><span class="sxs-lookup"><span data-stu-id="c7eb1-160">Location</span></span> |
|---------|---------|
|<span data-ttu-id="c7eb1-161">Windows</span><span class="sxs-lookup"><span data-stu-id="c7eb1-161">Windows</span></span>     |<span data-ttu-id="c7eb1-162">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-162">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="c7eb1-163">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-163">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="c7eb1-164">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="c7eb1-164">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="c7eb1-165">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c7eb1-165">Mac OSX</span></span>     |<span data-ttu-id="c7eb1-166">~/Library/Application Support Support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-166">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="c7eb1-167">~/Library/Application Support Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-167">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="c7eb1-168">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eb1-168">Linux</span></span>       |<span data-ttu-id="c7eb1-169">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-169">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="c7eb1-170">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="c7eb1-170">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |



<a name="desktop-logs"></a><span data-ttu-id="c7eb1-171">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="c7eb1-171">Desktop logs</span></span>
---------------------

<span data-ttu-id="c7eb1-172">Os registros de desktop, também conhecidos como registros de bootstrapper, contém dados de registro que ocorrem entre o clientes desktop e o navegador.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-172">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="c7eb1-173">Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-173">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="c7eb1-174">Os registros são baseados em texto e podem ser lidos usando qualquer editor baseado em texto no formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="c7eb1-174">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="c7eb1-175">Windows:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-175">Windows:</span></span>

1.  <span data-ttu-id="c7eb1-176">Clique com o botão direito do mouse no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**</span><span class="sxs-lookup"><span data-stu-id="c7eb1-176">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="c7eb1-177">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="c7eb1-177">Mac OsX:</span></span>

1.  <span data-ttu-id="c7eb1-178">Escolher **Obter registros** no menu suspenso de **Ajuda**</span><span class="sxs-lookup"><span data-stu-id="c7eb1-178">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="c7eb1-179">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eb1-179">Linux:</span></span>

1.  <span data-ttu-id="c7eb1-180">Clique no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**</span><span class="sxs-lookup"><span data-stu-id="c7eb1-180">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="c7eb1-181">Cliente</span><span class="sxs-lookup"><span data-stu-id="c7eb1-181">Client</span></span> |<span data-ttu-id="c7eb1-182">Localização</span><span class="sxs-lookup"><span data-stu-id="c7eb1-182">Location</span></span> |
|---------|---------|
|<span data-ttu-id="c7eb1-183">Windows</span><span class="sxs-lookup"><span data-stu-id="c7eb1-183">Windows</span></span>     |<span data-ttu-id="c7eb1-184">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="c7eb1-184">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="c7eb1-185">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="c7eb1-185">Mac OSX</span></span>     |<span data-ttu-id="c7eb1-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="c7eb1-186">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="c7eb1-187">Linux</span><span class="sxs-lookup"><span data-stu-id="c7eb1-187">Linux</span></span>       |<span data-ttu-id="c7eb1-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="c7eb1-188">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="c7eb1-189">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c7eb1-189">Related topics</span></span>

[<span data-ttu-id="c7eb1-190">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="c7eb1-190">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

