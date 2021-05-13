---
title: Usar arquivos de registro para solucionar problemas no Microsoft Teams
ms.reviewer: tejeshs
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 05/06/2021
audience: admin
ms.topic: troubleshooting
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
search.appverid: MET150
description: Saiba mais sobre logs de depuração, mídia e área de trabalho produzidos pelo Microsoft Teams, onde eles podem ser encontrados e como eles podem ajudar no monitoramento e solução de problemas.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 58460390d9562d77ed6a4e3dfcbb3948cbe2749e
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337738"
---
# <a name="use-log-files-to-monitor-and-troubleshoot-microsoft-teams"></a><span data-ttu-id="4b675-103">Usar arquivos de log para monitorar e solucionar Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4b675-103">Use log files to monitor and troubleshoot Microsoft Teams</span></span>

<span data-ttu-id="4b675-104">Há três tipos de arquivos de log produzidos automaticamente pelo cliente, que podem ser aproveitados para ajudar no monitoramento e solução de problemas Teams:</span><span class="sxs-lookup"><span data-stu-id="4b675-104">There are three types of log files automatically produced by the client, which can be leveraged to assist in monitoring and troubleshooting Teams:</span></span>

-   [<span data-ttu-id="4b675-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="4b675-105">Debug logs</span></span>](#debug-logs)

-   [<span data-ttu-id="4b675-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="4b675-106">Media logs</span></span>](#media-logs)

-   [<span data-ttu-id="4b675-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="4b675-107">Desktop logs</span></span>](#desktop-logs)

<span data-ttu-id="4b675-108">Este artigo descreve os três logs e como eles são usados.</span><span class="sxs-lookup"><span data-stu-id="4b675-108">This article describes the three logs and how they are used.</span></span> 

<span data-ttu-id="4b675-109">Para obter informações sobre como solucionar problemas específicos, consulte: [Teams Solução de Problemas](/MicrosoftTeams/troubleshoot/teams).</span><span class="sxs-lookup"><span data-stu-id="4b675-109">For information about troubleshooting specific issues, see: [Teams Troubleshooting](/MicrosoftTeams/troubleshoot/teams).</span></span> <span data-ttu-id="4b675-110">Para obter informações sobre como contatar o suporte, consulte [Obter suporte](/microsoft-365/business-video/get-help-support).</span><span class="sxs-lookup"><span data-stu-id="4b675-110">For information about how to contact support, see [Get support](/microsoft-365/business-video/get-help-support).</span></span>

<span data-ttu-id="4b675-111">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="4b675-111">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="4b675-112">Ter os logs de depuração em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="4b675-112">Having the debug logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="4b675-113">**Os** logs **de** mídia ou área de trabalho só serão necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b675-113">**Media** or **Desktop** logs are only required if requested by Microsoft.</span></span>

> [!NOTE]
> <span data-ttu-id="4b675-114">Neste artigo, o termo **Logs de depuração** se refere aos logs usados para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="4b675-114">In this article, the term **Debug logs** refers to the logs that are used for troubleshooting.</span></span> <span data-ttu-id="4b675-115">No entanto, os arquivos gerados para esses logs conterão o termo **logs de diagnóstico** em seus nomes.</span><span class="sxs-lookup"><span data-stu-id="4b675-115">However, the files that are generated for these logs will contain the term **diagnostic logs** in their names.</span></span>  

<span data-ttu-id="4b675-116">A tabela a seguir descreve os vários clientes e seus logs associados.</span><span class="sxs-lookup"><span data-stu-id="4b675-116">The following table outlines the various clients and their associated logs.</span></span> <span data-ttu-id="4b675-117">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="4b675-117">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="4b675-118">Cliente</span><span class="sxs-lookup"><span data-stu-id="4b675-118">Client</span></span> |<span data-ttu-id="4b675-119">Depuração</span><span class="sxs-lookup"><span data-stu-id="4b675-119">Debug</span></span>|<span data-ttu-id="4b675-120">Desktop</span><span class="sxs-lookup"><span data-stu-id="4b675-120">Desktop</span></span>|<span data-ttu-id="4b675-121">Mídia</span><span class="sxs-lookup"><span data-stu-id="4b675-121">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="4b675-122">Web</span><span class="sxs-lookup"><span data-stu-id="4b675-122">Web</span></span>    |<span data-ttu-id="4b675-123">X</span><span class="sxs-lookup"><span data-stu-id="4b675-123">X</span></span>         |-         |-         |
|<span data-ttu-id="4b675-124">Windows</span><span class="sxs-lookup"><span data-stu-id="4b675-124">Windows</span></span>     |<span data-ttu-id="4b675-125">X</span><span class="sxs-lookup"><span data-stu-id="4b675-125">X</span></span>         |<span data-ttu-id="4b675-126">X</span><span class="sxs-lookup"><span data-stu-id="4b675-126">X</span></span>         |<span data-ttu-id="4b675-127">X</span><span class="sxs-lookup"><span data-stu-id="4b675-127">X</span></span>         |
|<span data-ttu-id="4b675-128">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4b675-128">Mac OSX</span></span>     |<span data-ttu-id="4b675-129">X</span><span class="sxs-lookup"><span data-stu-id="4b675-129">X</span></span>         |<span data-ttu-id="4b675-130">X</span><span class="sxs-lookup"><span data-stu-id="4b675-130">X</span></span>         |<span data-ttu-id="4b675-131">X</span><span class="sxs-lookup"><span data-stu-id="4b675-131">X</span></span>         |
|<span data-ttu-id="4b675-132">Linux</span><span class="sxs-lookup"><span data-stu-id="4b675-132">Linux</span></span>     |<span data-ttu-id="4b675-133">X</span><span class="sxs-lookup"><span data-stu-id="4b675-133">X</span></span>         |<span data-ttu-id="4b675-134">X</span><span class="sxs-lookup"><span data-stu-id="4b675-134">X</span></span>         |<span data-ttu-id="4b675-135">X</span><span class="sxs-lookup"><span data-stu-id="4b675-135">X</span></span>         |
|<span data-ttu-id="4b675-136">iOS</span><span class="sxs-lookup"><span data-stu-id="4b675-136">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="4b675-137">Android</span><span class="sxs-lookup"><span data-stu-id="4b675-137">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="4b675-138">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="4b675-138">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

## <a name="debug-logs"></a><span data-ttu-id="4b675-139">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="4b675-139">Debug logs</span></span>

<span data-ttu-id="4b675-140">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b675-140">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="4b675-141">Os logs de depuração são produzidos pelos clientes de desktop Windows e Mac, bem como por clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="4b675-141">Debug logs are produced by the Windows and Mac desktop clients, as well as by browser-based clients.</span></span> <span data-ttu-id="4b675-142">Os logs são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="4b675-142">The logs are text based and are read from the bottom-up.</span></span> <span data-ttu-id="4b675-143">Eles podem ser lidos usando qualquer editor baseado em texto, e novos logs são criados ao efetuar o registro em log no cliente.</span><span class="sxs-lookup"><span data-stu-id="4b675-143">They can be read using any text-based editor, and new logs are created when logging into the client.</span></span>

<span data-ttu-id="4b675-144">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="4b675-144">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="4b675-145">Login</span><span class="sxs-lookup"><span data-stu-id="4b675-145">Login</span></span>

-   <span data-ttu-id="4b675-146">Solicitações de conexão para serviços de nível intermediário</span><span class="sxs-lookup"><span data-stu-id="4b675-146">Connection requests to middle-tier services</span></span>

-   <span data-ttu-id="4b675-147">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="4b675-147">Call/conversation</span></span>

<span data-ttu-id="4b675-148">Os registros de depuração são produzidos usando os seguintes métodos específicos do sistema operacional:</span><span class="sxs-lookup"><span data-stu-id="4b675-148">The debug logs are produced using the following OS-specific methods:</span></span>

-   <span data-ttu-id="4b675-149">Windows:</span><span class="sxs-lookup"><span data-stu-id="4b675-149">Windows:</span></span>

      <span data-ttu-id="4b675-150">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4b675-150">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="4b675-151">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="4b675-151">Mac OSX:</span></span>

      <span data-ttu-id="4b675-152">Atalho de teclado: Option + Command + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4b675-152">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="4b675-153">Linux:</span><span class="sxs-lookup"><span data-stu-id="4b675-153">Linux:</span></span>

      <span data-ttu-id="4b675-154">Atalho de teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="4b675-154">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="4b675-155">Os registros de depuração são baixados automaticamente para as seguintes pastas:</span><span class="sxs-lookup"><span data-stu-id="4b675-155">The debug logs are automatically downloaded to the following folders:</span></span>

-   <span data-ttu-id="4b675-156">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="4b675-156">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="4b675-157">Mac OSX: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="4b675-157">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="4b675-158">Linux: ~/Downloads</span><span class="sxs-lookup"><span data-stu-id="4b675-158">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="4b675-159">Navegador: será solicitado que você salve o registro de depuração no local de salvamento padrão</span><span class="sxs-lookup"><span data-stu-id="4b675-159">Browser: You will be prompted to save the debug log to default save location</span></span>

## <a name="media-logs"></a><span data-ttu-id="4b675-160">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="4b675-160">Media logs</span></span>

<span data-ttu-id="4b675-161">Os registros de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela nas reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b675-161">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="4b675-162">Eles são necessários para casos de suporte vinculados a problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="4b675-162">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="4b675-163">O registro de mídia está desabilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="4b675-163">Media logging is turned off by default.</span></span> <span data-ttu-id="4b675-164">Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="4b675-164">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="4b675-165">Vá para **Configurações** > **Gerais**, marque a caixa de seleção **Habilitar registro para diagnóstico de reunião (requer a reinicialização do Teams**), reinicie o Teams e reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="4b675-165">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, restart Teams, and reproduce the issue.</span></span> 

<span data-ttu-id="4b675-166">A tabela a seguir descreve os locais de registro de mídia.</span><span class="sxs-lookup"><span data-stu-id="4b675-166">The following table outlines the media log locations.</span></span> <span data-ttu-id="4b675-167">Ao enviar os arquivos de log para o suporte da Microsoft, verifique a data e hora dos arquivos de log para garantir que os logs abrangem o período de tempo em que você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="4b675-167">When you send the log files to Microsoft support, please verify the timestamp of the log files to ensure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="4b675-168">Cliente</span><span class="sxs-lookup"><span data-stu-id="4b675-168">Client</span></span> |<span data-ttu-id="4b675-169">Localização</span><span class="sxs-lookup"><span data-stu-id="4b675-169">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4b675-170">Windows</span><span class="sxs-lookup"><span data-stu-id="4b675-170">Windows</span></span>     |<span data-ttu-id="4b675-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-171">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="4b675-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-172">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="4b675-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span><span class="sxs-lookup"><span data-stu-id="4b675-173">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="4b675-174">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4b675-174">Mac OSX</span></span>     |<span data-ttu-id="4b675-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-175">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4b675-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-176">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="4b675-177">Linux</span><span class="sxs-lookup"><span data-stu-id="4b675-177">Linux</span></span>       |<span data-ttu-id="4b675-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-178">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="4b675-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-179">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="4b675-180">Aqui está uma lista dos arquivos de log gerados e as informações que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="4b675-180">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="4b675-181">Nome do arquivo de log</span><span class="sxs-lookup"><span data-stu-id="4b675-181">Log file name</span></span>  |<span data-ttu-id="4b675-182">Descrição</span><span class="sxs-lookup"><span data-stu-id="4b675-182">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="4b675-183">Teams.msrtc-0-s1039525249.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-183">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="4b675-184">Contém informações relacionadas à pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="4b675-184">Contains information related to the media stack.</span></span> <span data-ttu-id="4b675-185">Isso inclui o status do canal, como resolução, decodificadores e codificadores usados e o número de quadros enviados e recebidos, além do status da sessão de compartilhamento de tela com base em vídeo e câmera (VBSS).</span><span class="sxs-lookup"><span data-stu-id="4b675-185">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="4b675-186">rtmcontrol.msrtc-0-2415069487.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-186">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="4b675-187">Registra informações relacionadas a ações de controle remoto, como o carimbo de hora quando o controle é fornecido e informações do ponteiro do mouse.</span><span class="sxs-lookup"><span data-stu-id="4b675-187">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="4b675-188">Teams_MediaStackETW-2-U-xr-U.etl</span><span class="sxs-lookup"><span data-stu-id="4b675-188">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="4b675-189">Registra eventos de rastreamento de pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="4b675-189">Records media stack trace events.</span></span>         |
|<span data-ttu-id="4b675-190">Debug-0-s2790420889.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-190">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="4b675-191">Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.</span><span class="sxs-lookup"><span data-stu-id="4b675-191">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="4b675-192">tscalling-0-2061129496.blog</span><span class="sxs-lookup"><span data-stu-id="4b675-192">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="4b675-193">Registra eventos na API de chamada de ts.</span><span class="sxs-lookup"><span data-stu-id="4b675-193">Records events in the ts-calling API.</span></span>       |

## <a name="desktop-logs"></a><span data-ttu-id="4b675-194">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="4b675-194">Desktop logs</span></span>

<span data-ttu-id="4b675-195">Os logs da área de trabalho, também conhecidos como logs de bootstrapper, contêm dados de log que ocorrem entre o cliente da área de trabalho e o navegador.</span><span class="sxs-lookup"><span data-stu-id="4b675-195">Desktop logs, also known as bootstrapper logs, contain log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="4b675-196">Como os logs de mídia, esses logs só são necessários se solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b675-196">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="4b675-197">Os logs são baseados em texto e podem ser lidos usando qualquer editor baseado em texto em um formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="4b675-197">The logs are text based and can be read using any text-based editor in a top-down format.</span></span>

<span data-ttu-id="4b675-198">Windows:</span><span class="sxs-lookup"><span data-stu-id="4b675-198">Windows:</span></span>

 - <span data-ttu-id="4b675-199">Clique com o botão direito no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="4b675-199">Right-click the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

<span data-ttu-id="4b675-200">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="4b675-200">Mac OsX:</span></span>

 - <span data-ttu-id="4b675-201">Escolha **Obter Logs** no menu suspenso **Ajudar**.</span><span class="sxs-lookup"><span data-stu-id="4b675-201">Choose **Get Logs** from the **Help** pull-down menu.</span></span>

<span data-ttu-id="4b675-202">Linux:</span><span class="sxs-lookup"><span data-stu-id="4b675-202">Linux:</span></span>

 - <span data-ttu-id="4b675-203">Clique no ícone do **Microsoft Teams** na bandeja do sistema e selecione **Obter Logs**.</span><span class="sxs-lookup"><span data-stu-id="4b675-203">Click on the **Microsoft Teams** icon in your system tray, and select **Get Logs**.</span></span>

|<span data-ttu-id="4b675-204">Cliente</span><span class="sxs-lookup"><span data-stu-id="4b675-204">Client</span></span> |<span data-ttu-id="4b675-205">Localização</span><span class="sxs-lookup"><span data-stu-id="4b675-205">Location</span></span> |
|---------|---------|
|<span data-ttu-id="4b675-206">Windows</span><span class="sxs-lookup"><span data-stu-id="4b675-206">Windows</span></span>     |<span data-ttu-id="4b675-207">%appdata%\Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="4b675-207">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="4b675-208">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="4b675-208">Mac OSX</span></span>     |<span data-ttu-id="4b675-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4b675-209">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="4b675-210">Linux</span><span class="sxs-lookup"><span data-stu-id="4b675-210">Linux</span></span>       |<span data-ttu-id="4b675-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="4b675-211">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="browser-trace"></a><span data-ttu-id="4b675-212">Rastreamento do navegador</span><span class="sxs-lookup"><span data-stu-id="4b675-212">Browser trace</span></span>

<span data-ttu-id="4b675-213">Para algumas categorias de erros, o Suporte da Microsoft pode exigir que você colete um rastreamento do navegador.</span><span class="sxs-lookup"><span data-stu-id="4b675-213">For some categories of errors, Microsoft Support might require you to collect a browser trace.</span></span> <span data-ttu-id="4b675-214">Essas informações podem fornecer detalhes importantes sobre o estado do cliente Teams quando o erro ocorrer.</span><span class="sxs-lookup"><span data-stu-id="4b675-214">This information can provide important details about the state of the Teams client when the error occurs.</span></span>

<span data-ttu-id="4b675-215">Antes de iniciar o rastreamento do navegador, certifique-se de estar Teams.</span><span class="sxs-lookup"><span data-stu-id="4b675-215">Before you start the browser trace, make sure that you’re signed in to Teams.</span></span> <span data-ttu-id="4b675-216">É importante fazer isso antes de iniciar o rastreamento para que o rastreamento não contenha informações confidenciais de login.</span><span class="sxs-lookup"><span data-stu-id="4b675-216">It's important to do this before you start the trace so that the trace doesn't contain sensitive sign-in information.</span></span>

<span data-ttu-id="4b675-217">Depois de entrar, selecione um dos links a seguir, conforme apropriado para seu navegador, e siga as etapas fornecidas.</span><span class="sxs-lookup"><span data-stu-id="4b675-217">After you’re signed in, select one of the following links, as appropriate for your browser, and follow the provided steps.</span></span> 

-   [<span data-ttu-id="4b675-218">Borda & Chrome (Chromium)</span><span class="sxs-lookup"><span data-stu-id="4b675-218">Chrome & Edge (Chromium)</span></span>](/azure/azure-portal/capture-browser-trace#google-chrome-and-microsoft-edge-chromium?preserve-view=true#resolution)

-   [<span data-ttu-id="4b675-219">Borda</span><span class="sxs-lookup"><span data-stu-id="4b675-219">Edge</span></span>](/azure/azure-portal/capture-browser-trace#microsoft-edge-edgehtml?preserve-view=true#resolution)

-   [<span data-ttu-id="4b675-220">Safari</span><span class="sxs-lookup"><span data-stu-id="4b675-220">Safari</span></span>](/azure/azure-portal/capture-browser-trace#apple-safari?preserve-view=true#resolution)

-   [<span data-ttu-id="4b675-221">Firefox</span><span class="sxs-lookup"><span data-stu-id="4b675-221">Firefox</span></span>](/azure/azure-portal/capture-browser-trace#firefox?preserve-view=true#resolution)

> [!NOTE]
> <span data-ttu-id="4b675-222">Nas etapas, substitua todas as referências ao portal do Azure pelo Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="4b675-222">In the steps, replace all references to the Azure portal with the Teams client.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4b675-223">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b675-223">Related topics</span></span>

[<span data-ttu-id="4b675-224">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="4b675-224">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)
