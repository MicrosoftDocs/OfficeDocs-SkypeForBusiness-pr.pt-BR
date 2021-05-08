---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: f816830f24a3d1180cb33a91a3f02d30d360cfef
ms.sourcegitcommit: 2c2176b9d32b8f7218e8d11e82c0ae01318bfdc5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52264871"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="e7c4e-103">Usar arquivos de registro para solucionar problemas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e7c4e-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="e7c4e-104">Existem três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para auxiliar na solução de problemas do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="e7c4e-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="e7c4e-105">Debug logs</span></span>

-   <span data-ttu-id="e7c4e-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="e7c4e-106">Media logs</span></span>

-   <span data-ttu-id="e7c4e-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="e7c4e-107">Desktop logs</span></span>

<span data-ttu-id="e7c4e-108">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="e7c4e-109">Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="e7c4e-110">**Os** logs **de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-110">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e7c4e-111">Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="e7c4e-112">No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="e7c4e-113">A tabela a seguir descreve os vários clientes e seus logs associados.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="e7c4e-114">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="e7c4e-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="e7c4e-115">Client</span></span> |<span data-ttu-id="e7c4e-116">Depuração</span><span class="sxs-lookup"><span data-stu-id="e7c4e-116">Debug</span></span>|<span data-ttu-id="e7c4e-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="e7c4e-117">Desktop</span></span>|<span data-ttu-id="e7c4e-118">Mídia</span><span class="sxs-lookup"><span data-stu-id="e7c4e-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="e7c4e-119">Web</span><span class="sxs-lookup"><span data-stu-id="e7c4e-119">Web</span></span>    |<span data-ttu-id="e7c4e-120">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-120">X</span></span>         |-         |-         |
|<span data-ttu-id="e7c4e-121">Windows</span><span class="sxs-lookup"><span data-stu-id="e7c4e-121">Windows</span></span>     |<span data-ttu-id="e7c4e-122">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-122">X</span></span>         |<span data-ttu-id="e7c4e-123">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-123">X</span></span>         |<span data-ttu-id="e7c4e-124">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-124">X</span></span>         |
|<span data-ttu-id="e7c4e-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e7c4e-125">Mac OSX</span></span>     |<span data-ttu-id="e7c4e-126">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-126">X</span></span>         |<span data-ttu-id="e7c4e-127">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-127">X</span></span>         |<span data-ttu-id="e7c4e-128">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-128">X</span></span>         |
|<span data-ttu-id="e7c4e-129">Linux</span><span class="sxs-lookup"><span data-stu-id="e7c4e-129">Linux</span></span>     |<span data-ttu-id="e7c4e-130">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-130">X</span></span>         |<span data-ttu-id="e7c4e-131">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-131">X</span></span>         |<span data-ttu-id="e7c4e-132">X</span><span class="sxs-lookup"><span data-stu-id="e7c4e-132">X</span></span>         |
|<span data-ttu-id="e7c4e-133">iOS</span><span class="sxs-lookup"><span data-stu-id="e7c4e-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="e7c4e-134">Android</span><span class="sxs-lookup"><span data-stu-id="e7c4e-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="e7c4e-135">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e7c4e-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="e7c4e-136">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="e7c4e-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="e7c4e-137">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="e7c4e-138">Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="e7c4e-139">Os logs são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="e7c4e-140">Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="e7c4e-141">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="e7c4e-142">Login</span><span class="sxs-lookup"><span data-stu-id="e7c4e-142">Login</span></span>

-   <span data-ttu-id="e7c4e-143">Solicitações de conexão para serviços de nível intermediário</span><span class="sxs-lookup"><span data-stu-id="e7c4e-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="e7c4e-144">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="e7c4e-144">Call/conversation</span></span>

<span data-ttu-id="e7c4e-145">Os registros de depuração são produzidos usando os seguintes métodos específicos do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="e7c4e-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-146">Windows:</span></span>

      <span data-ttu-id="e7c4e-147">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e7c4e-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="e7c4e-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-148">Mac OSX:</span></span>

      <span data-ttu-id="e7c4e-149">Atalho de teclado: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e7c4e-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="e7c4e-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-150">Linux:</span></span>

      <span data-ttu-id="e7c4e-151">Atalho de teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e7c4e-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="e7c4e-152">Os registros de depuração são baixados automaticamente para as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="e7c4e-153">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="e7c4e-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="e7c4e-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e7c4e-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="e7c4e-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e7c4e-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="e7c4e-156">Navegador: será solicitado que você salve o registro de depuração no local de salvamento padrão</span><span class="sxs-lookup"><span data-stu-id="e7c4e-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="e7c4e-157">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="e7c4e-157">Media logs</span></span>
---------------------------

<span data-ttu-id="e7c4e-158">Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="e7c4e-159">Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="e7c4e-160">O registro de mídia está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-160">Media logging is turned off by default.</span></span> <span data-ttu-id="e7c4e-161">Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="e7c4e-162">Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="e7c4e-163">A tabela a seguir descreve os locais de registro de mídia.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="e7c4e-164">Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="e7c4e-165">Cliente</span><span class="sxs-lookup"><span data-stu-id="e7c4e-165">Client</span></span> |<span data-ttu-id="e7c4e-166">Localização</span><span class="sxs-lookup"><span data-stu-id="e7c4e-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e7c4e-167">Windows</span><span class="sxs-lookup"><span data-stu-id="e7c4e-167">Windows</span></span>     |<span data-ttu-id="e7c4e-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="e7c4e-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="e7c4e-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span><span class="sxs-lookup"><span data-stu-id="e7c4e-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="e7c4e-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e7c4e-171">Mac OSX</span></span>     |<span data-ttu-id="e7c4e-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e7c4e-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="e7c4e-174">Linux</span><span class="sxs-lookup"><span data-stu-id="e7c4e-174">Linux</span></span>       |<span data-ttu-id="e7c4e-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e7c4e-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="e7c4e-177">Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="e7c4e-178">Nome do arquivo de log</span><span class="sxs-lookup"><span data-stu-id="e7c4e-178">Log file name</span></span>  |<span data-ttu-id="e7c4e-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="e7c4e-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e7c4e-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="e7c4e-181">Contém informações relacionadas à pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-181">Contains information related to the media stack.</span></span> <span data-ttu-id="e7c4e-182">Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="e7c4e-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="e7c4e-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="e7c4e-184">Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="e7c4e-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="e7c4e-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="e7c4e-186">Registra eventos de rastreamento de pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="e7c4e-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="e7c4e-188">Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="e7c4e-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="e7c4e-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="e7c4e-190">Registra eventos na API de chamada de ts.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="e7c4e-191">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="e7c4e-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="e7c4e-192">Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="e7c4e-193">Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="e7c4e-194">Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="e7c4e-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-195">Windows:</span></span>

 - <span data-ttu-id="e7c4e-196">Clique com o botão direito no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="e7c4e-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-197">Mac OsX:</span></span>

 - <span data-ttu-id="e7c4e-198">Escolha **Obter Logs** no menu suspenso **Ajudar**.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="e7c4e-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="e7c4e-199">Linux:</span></span>

 - <span data-ttu-id="e7c4e-200">Clique no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="e7c4e-201">Cliente</span><span class="sxs-lookup"><span data-stu-id="e7c4e-201">Client</span></span> |<span data-ttu-id="e7c4e-202">Localização</span><span class="sxs-lookup"><span data-stu-id="e7c4e-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e7c4e-203">Windows</span><span class="sxs-lookup"><span data-stu-id="e7c4e-203">Windows</span></span>     |<span data-ttu-id="e7c4e-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="e7c4e-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="e7c4e-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e7c4e-205">Mac OSX</span></span>     |<span data-ttu-id="e7c4e-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e7c4e-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="e7c4e-207">Linux</span><span class="sxs-lookup"><span data-stu-id="e7c4e-207">Linux</span></span>       |<span data-ttu-id="e7c4e-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e7c4e-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


<a name="browser-trace"></a><span data-ttu-id="e7c4e-209">Rastreamento do navegador</span><span class="sxs-lookup"><span data-stu-id="e7c4e-209">Browser trace</span></span>
---------------------------

<span data-ttu-id="e7c4e-210">Para algumas categorias de erros, o Suporte da Microsoft pode exigir que você colete um rastreamento do navegador.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-210">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="e7c4e-211">Essas informações podem fornecer detalhes importantes sobre o estado do cliente Teams quando o erro ocorrer.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-211">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="e7c4e-212">Antes de iniciar o rastreamento do navegador, certifique-se de estar Teams.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-212">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="e7c4e-213">É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de login.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-213">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="e7c4e-214">Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-214">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="e7c4e-215">Borda & Chrome (Chromium)</span><span class="sxs-lookup"><span data-stu-id="e7c4e-215">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="e7c4e-216">Borda</span><span class="sxs-lookup"><span data-stu-id="e7c4e-216">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="e7c4e-217">Safari</span><span class="sxs-lookup"><span data-stu-id="e7c4e-217">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="e7c4e-218">Firefox</span><span class="sxs-lookup"><span data-stu-id="e7c4e-218">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="e7c4e-219">Nas etapas, substitua todas as referências ao portal do Azure pelo Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-219">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="e7c4e-220">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e7c4e-220">Related topics</span></span>

[<span data-ttu-id="e7c4e-221">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="e7c4e-221">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
