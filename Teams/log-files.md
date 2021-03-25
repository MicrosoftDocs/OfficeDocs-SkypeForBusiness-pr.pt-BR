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
ms.openlocfilehash: e3e2c4d42d511e2a33a797099132ac42c0475d36
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112187"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="e852c-103">Usar arquivos de registro para solucionar problemas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e852c-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="e852c-104">Existem três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para auxiliar na solução de problemas do Microsoft Teams:</span><span class="sxs-lookup"><span data-stu-id="e852c-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in troubleshooting Microsoft Teams:</span></span>

-   <span data-ttu-id="e852c-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="e852c-105">Debug logs</span></span>

-   <span data-ttu-id="e852c-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="e852c-106">Media logs</span></span>

-   <span data-ttu-id="e852c-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="e852c-107">Desktop logs</span></span>

<span data-ttu-id="e852c-108">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="e852c-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="e852c-109">Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="e852c-109">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="e852c-110">Os logs de **mídia** ou **área de trabalho** são necessários apenas se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e852c-110">**Media** or **desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="e852c-111">Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="e852c-111">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="e852c-112">No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="e852c-112">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="e852c-113">A tabela a seguir descreve os vários clientes e seus logs associados.</span><span class="sxs-lookup"><span data-stu-id="e852c-113">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="e852c-114">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="e852c-114">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="e852c-115">Cliente</span><span class="sxs-lookup"><span data-stu-id="e852c-115">Client</span></span> |<span data-ttu-id="e852c-116">Depuração</span><span class="sxs-lookup"><span data-stu-id="e852c-116">Debug</span></span>|<span data-ttu-id="e852c-117">Desktop</span><span class="sxs-lookup"><span data-stu-id="e852c-117">Desktop</span></span>|<span data-ttu-id="e852c-118">Mídia</span><span class="sxs-lookup"><span data-stu-id="e852c-118">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="e852c-119">Web</span><span class="sxs-lookup"><span data-stu-id="e852c-119">Web</span></span>    |<span data-ttu-id="e852c-120">X</span><span class="sxs-lookup"><span data-stu-id="e852c-120">X</span></span>         |-         |-         |
|<span data-ttu-id="e852c-121">Windows</span><span class="sxs-lookup"><span data-stu-id="e852c-121">Windows</span></span>     |<span data-ttu-id="e852c-122">X</span><span class="sxs-lookup"><span data-stu-id="e852c-122">X</span></span>         |<span data-ttu-id="e852c-123">X</span><span class="sxs-lookup"><span data-stu-id="e852c-123">X</span></span>         |<span data-ttu-id="e852c-124">X</span><span class="sxs-lookup"><span data-stu-id="e852c-124">X</span></span>         |
|<span data-ttu-id="e852c-125">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e852c-125">Mac OSX</span></span>     |<span data-ttu-id="e852c-126">X</span><span class="sxs-lookup"><span data-stu-id="e852c-126">X</span></span>         |<span data-ttu-id="e852c-127">X</span><span class="sxs-lookup"><span data-stu-id="e852c-127">X</span></span>         |<span data-ttu-id="e852c-128">X</span><span class="sxs-lookup"><span data-stu-id="e852c-128">X</span></span>         |
|<span data-ttu-id="e852c-129">Linux</span><span class="sxs-lookup"><span data-stu-id="e852c-129">Linux</span></span>     |<span data-ttu-id="e852c-130">X</span><span class="sxs-lookup"><span data-stu-id="e852c-130">X</span></span>         |<span data-ttu-id="e852c-131">X</span><span class="sxs-lookup"><span data-stu-id="e852c-131">X</span></span>         |<span data-ttu-id="e852c-132">X</span><span class="sxs-lookup"><span data-stu-id="e852c-132">X</span></span>         |
|<span data-ttu-id="e852c-133">iOS</span><span class="sxs-lookup"><span data-stu-id="e852c-133">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="e852c-134">Android</span><span class="sxs-lookup"><span data-stu-id="e852c-134">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="e852c-135">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="e852c-135">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="e852c-136">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="e852c-136">Debug logs</span></span>
---------------------------

<span data-ttu-id="e852c-137">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e852c-137">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="e852c-138">Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="e852c-138">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="e852c-139">Os logs são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="e852c-139">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="e852c-140">Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.</span><span class="sxs-lookup"><span data-stu-id="e852c-140">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="e852c-141">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="e852c-141">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="e852c-142">Login</span><span class="sxs-lookup"><span data-stu-id="e852c-142">Login</span></span>

-   <span data-ttu-id="e852c-143">Solicitações de conexão para serviços de nível intermediário</span><span class="sxs-lookup"><span data-stu-id="e852c-143">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="e852c-144">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="e852c-144">Call/conversation</span></span>

<span data-ttu-id="e852c-145">Os registros de depuração são produzidos usando os seguintes métodos específicos do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="e852c-145">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="e852c-146">Windows:</span><span class="sxs-lookup"><span data-stu-id="e852c-146">Windows:</span></span>

      <span data-ttu-id="e852c-147">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e852c-147">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="e852c-148">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="e852c-148">Mac OSX:</span></span>

      <span data-ttu-id="e852c-149">Atalho de teclado: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e852c-149">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="e852c-150">Linux:</span><span class="sxs-lookup"><span data-stu-id="e852c-150">Linux:</span></span>

      <span data-ttu-id="e852c-151">Atalho de teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="e852c-151">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="e852c-152">Os registros de depuração são baixados automaticamente para as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="e852c-152">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="e852c-153">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="e852c-153">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="e852c-154">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e852c-154">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="e852c-155">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="e852c-155">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="e852c-156">Navegador: será solicitado que você salve o registro de depuração no local de salvamento padrão</span><span class="sxs-lookup"><span data-stu-id="e852c-156">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="e852c-157">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="e852c-157">Media logs</span></span>
---------------------------

<span data-ttu-id="e852c-158">Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="e852c-158">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="e852c-159">Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="e852c-159">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="e852c-160">O registro de mídia está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="e852c-160">Media logging is turned off by default.</span></span> <span data-ttu-id="e852c-161">Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="e852c-161">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="e852c-162">Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="e852c-162">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="e852c-163">A tabela a seguir descreve os locais de registro de mídia.</span><span class="sxs-lookup"><span data-stu-id="e852c-163">The following table outlines the media log locations.</span></span> <span data-ttu-id="e852c-164">Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="e852c-164">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="e852c-165">Cliente</span><span class="sxs-lookup"><span data-stu-id="e852c-165">Client</span></span> |<span data-ttu-id="e852c-166">Localização</span><span class="sxs-lookup"><span data-stu-id="e852c-166">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e852c-167">Windows</span><span class="sxs-lookup"><span data-stu-id="e852c-167">Windows</span></span>     |<span data-ttu-id="e852c-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-168">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="e852c-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-169">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="e852c-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span><span class="sxs-lookup"><span data-stu-id="e852c-170">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="e852c-171">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e852c-171">Mac OSX</span></span>     |<span data-ttu-id="e852c-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-172">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e852c-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-173">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="e852c-174">Linux</span><span class="sxs-lookup"><span data-stu-id="e852c-174">Linux</span></span>       |<span data-ttu-id="e852c-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-175">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="e852c-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-176">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="e852c-177">Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="e852c-177">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="e852c-178">Nome do arquivo de log</span><span class="sxs-lookup"><span data-stu-id="e852c-178">Log file name</span></span>  |<span data-ttu-id="e852c-179">Descrição</span><span class="sxs-lookup"><span data-stu-id="e852c-179">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="e852c-180">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-180">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="e852c-181">Contém informações relacionadas à pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e852c-181">Contains information related to the media stack.</span></span> <span data-ttu-id="e852c-182">Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="e852c-182">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="e852c-183">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-183">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="e852c-184">Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.</span><span class="sxs-lookup"><span data-stu-id="e852c-184">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="e852c-185">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="e852c-185">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="e852c-186">Registra eventos de rastreamento de pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="e852c-186">Records media stack trace events.</span></span>         |
|<span data-ttu-id="e852c-187">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-187">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="e852c-188">Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.</span><span class="sxs-lookup"><span data-stu-id="e852c-188">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="e852c-189">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="e852c-189">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="e852c-190">Registra eventos na API de chamada de ts.</span><span class="sxs-lookup"><span data-stu-id="e852c-190">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="e852c-191">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="e852c-191">Desktop logs</span></span>
---------------------

<span data-ttu-id="e852c-192">Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador.</span><span class="sxs-lookup"><span data-stu-id="e852c-192">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="e852c-193">Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e852c-193">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="e852c-194">Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="e852c-194">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="e852c-195">Windows:</span><span class="sxs-lookup"><span data-stu-id="e852c-195">Windows:</span></span>

 - <span data-ttu-id="e852c-196">Clique com o botão direito no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="e852c-196">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="e852c-197">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="e852c-197">Mac OsX:</span></span>

 - <span data-ttu-id="e852c-198">Escolha **Obter Logs** no menu suspenso **Ajudar**.</span><span class="sxs-lookup"><span data-stu-id="e852c-198">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="e852c-199">Linux:</span><span class="sxs-lookup"><span data-stu-id="e852c-199">Linux:</span></span>

 - <span data-ttu-id="e852c-200">Clique no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="e852c-200">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="e852c-201">Cliente</span><span class="sxs-lookup"><span data-stu-id="e852c-201">Client</span></span> |<span data-ttu-id="e852c-202">Localização</span><span class="sxs-lookup"><span data-stu-id="e852c-202">Location</span></span> |
|---------|---------|
|<span data-ttu-id="e852c-203">Windows</span><span class="sxs-lookup"><span data-stu-id="e852c-203">Windows</span></span>     |<span data-ttu-id="e852c-204">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="e852c-204">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="e852c-205">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="e852c-205">Mac OSX</span></span>     |<span data-ttu-id="e852c-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e852c-206">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="e852c-207">Linux</span><span class="sxs-lookup"><span data-stu-id="e852c-207">Linux</span></span>       |<span data-ttu-id="e852c-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="e852c-208">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="e852c-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e852c-209">Related topics</span></span>

[<span data-ttu-id="e852c-210">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="e852c-210">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)