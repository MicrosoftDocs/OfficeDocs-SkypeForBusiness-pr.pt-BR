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
ms.openlocfilehash: 2ff24ddb8aaf63b539959119138aebf2f5d4e81f
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650824"
---
<a name="use-log-files-in-troubleshooting-microsoft-teams"></a><span data-ttu-id="cfb90-103">Usar arquivos de registro para solucionar problemas no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cfb90-103">Use log files in troubleshooting Microsoft Teams</span></span>
=================================================

<span data-ttu-id="cfb90-104">Existem três tipos de arquivos de registro produzidos automaticamente pelo cliente que podem ser aproveitados para ajudar na solução de problemas no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cfb90-104">There are three types of log files automatically produced by the client that can be leveraged to assist in troubleshooting Microsoft Teams.</span></span>

-   <span data-ttu-id="cfb90-105">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="cfb90-105">Debug logs</span></span>

-   <span data-ttu-id="cfb90-106">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="cfb90-106">Media logs</span></span>

-   <span data-ttu-id="cfb90-107">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="cfb90-107">Desktop logs</span></span>

<span data-ttu-id="cfb90-108">Ao criar uma solicitação de suporte com o Suporte da Microsoft, o engenheiro de suporte precisará dos registros de depuração.</span><span class="sxs-lookup"><span data-stu-id="cfb90-108">When creating a support request with Microsoft Support, the support engineer will require the debug logs.</span></span> <span data-ttu-id="cfb90-109">Ter esses registros em mãos antes de criar a solicitação de suporte permitirá que a Microsoft comece a solucionar o problema rapidamente.</span><span class="sxs-lookup"><span data-stu-id="cfb90-109">Having these logs on hand before creating the support request will allow Microsoft to quickly start troubleshooting the problem.</span></span> <span data-ttu-id="cfb90-110">Os registros de mídia ou de desktop só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cfb90-110">Media or desktop logs are only required if requested by Microsoft.</span></span>

<span data-ttu-id="cfb90-111">A tabela a seguir descreve os diversos clientes e seus registros associados.</span><span class="sxs-lookup"><span data-stu-id="cfb90-111">The following table outlines the various clients, and their associated logs.</span></span> <span data-ttu-id="cfb90-112">Os arquivos de registro são armazenados os locais específicos do cliente e do sistema operacional.</span><span class="sxs-lookup"><span data-stu-id="cfb90-112">Log files are stored in locations specific to the client and operating system.</span></span>


|<span data-ttu-id="cfb90-113">Cliente</span><span class="sxs-lookup"><span data-stu-id="cfb90-113">Client</span></span> |<span data-ttu-id="cfb90-114">Depuração</span><span class="sxs-lookup"><span data-stu-id="cfb90-114">Debug</span></span>|<span data-ttu-id="cfb90-115">Desktop</span><span class="sxs-lookup"><span data-stu-id="cfb90-115">Desktop</span></span>|<span data-ttu-id="cfb90-116">Mídia</span><span class="sxs-lookup"><span data-stu-id="cfb90-116">Media</span></span>|
|---------|---------|---------|---------|
|<span data-ttu-id="cfb90-117">Web</span><span class="sxs-lookup"><span data-stu-id="cfb90-117">Web</span></span>    |<span data-ttu-id="cfb90-118">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-118">X</span></span>         |-         |-         |
|<span data-ttu-id="cfb90-119">Windows</span><span class="sxs-lookup"><span data-stu-id="cfb90-119">Windows</span></span>     |<span data-ttu-id="cfb90-120">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-120">X</span></span>         |<span data-ttu-id="cfb90-121">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-121">X</span></span>         |<span data-ttu-id="cfb90-122">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-122">X</span></span>         |
|<span data-ttu-id="cfb90-123">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="cfb90-123">Mac OSX</span></span>     |<span data-ttu-id="cfb90-124">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-124">X</span></span>         |<span data-ttu-id="cfb90-125">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-125">X</span></span>         |<span data-ttu-id="cfb90-126">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-126">X</span></span>         |
|<span data-ttu-id="cfb90-127">Linux</span><span class="sxs-lookup"><span data-stu-id="cfb90-127">Linux</span></span>     |<span data-ttu-id="cfb90-128">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-128">X</span></span>         |<span data-ttu-id="cfb90-129">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-129">X</span></span>         |<span data-ttu-id="cfb90-130">X</span><span class="sxs-lookup"><span data-stu-id="cfb90-130">X</span></span>         |
|<span data-ttu-id="cfb90-131">iOS</span><span class="sxs-lookup"><span data-stu-id="cfb90-131">iOS</span></span>     |-         |-         |-         |
|<span data-ttu-id="cfb90-132">Android</span><span class="sxs-lookup"><span data-stu-id="cfb90-132">Android</span></span>     |-         |-         |-         |

<span data-ttu-id="cfb90-133">Para obter uma lista completa dos sistemas operacionais e navegadores compatíveis, consulte [Obter clientes para o Microsoft Teams](get-clients.md).</span><span class="sxs-lookup"><span data-stu-id="cfb90-133">For a complete list of supported operating systems and browsers, see [Get clients for Microsoft Teams](get-clients.md).</span></span>

<a name="debug-logs"></a><span data-ttu-id="cfb90-134">Registros de depuração</span><span class="sxs-lookup"><span data-stu-id="cfb90-134">Debug logs</span></span>
---------------------------

<span data-ttu-id="cfb90-135">Estes são os registros mais comuns e são necessários para todos os casos de suporte da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cfb90-135">These are the most common logs and are required for all Microsoft support cases.</span></span> <span data-ttu-id="cfb90-136">Os logs de depuração são produzidos pelos clientes de área de trabalho do Windows e do Mac, bem como clientes baseados em navegador.</span><span class="sxs-lookup"><span data-stu-id="cfb90-136">Debug logs are produced by the Windows and Mac desktop clients, as well as browser based clients.</span></span> <span data-ttu-id="cfb90-137">Os registros são baseados em texto e são lidos de baixo para cima.</span><span class="sxs-lookup"><span data-stu-id="cfb90-137">The logs are text based and are read from the bottom up.</span></span> <span data-ttu-id="cfb90-138">Eles podem ser lidos usando qualquer editor baseado em texto, e novos registros são criados ao acessar o cliente.</span><span class="sxs-lookup"><span data-stu-id="cfb90-138">They can be read using any text based editor and new logs are created when logging into the client.</span></span>

<span data-ttu-id="cfb90-139">Os registros de depuração mostram os seguintes fluxos de dados:</span><span class="sxs-lookup"><span data-stu-id="cfb90-139">Debug logs show the following data flows:</span></span>

-   <span data-ttu-id="cfb90-140">Login</span><span class="sxs-lookup"><span data-stu-id="cfb90-140">Login</span></span>

-   <span data-ttu-id="cfb90-141">Solicitações de conexão para serviços de camada intermediária</span><span class="sxs-lookup"><span data-stu-id="cfb90-141">Connection requests to middle tier services</span></span>

-   <span data-ttu-id="cfb90-142">Chamada/conversa</span><span class="sxs-lookup"><span data-stu-id="cfb90-142">Call/conversation</span></span>

<span data-ttu-id="cfb90-143">Os registros de depuração são produzidos usando os seguintes métodos para o sistema operacional específico:</span><span class="sxs-lookup"><span data-stu-id="cfb90-143">The debug logs are produced using the following OS specific methods:</span></span>

-   <span data-ttu-id="cfb90-144">Windows:</span><span class="sxs-lookup"><span data-stu-id="cfb90-144">Windows:</span></span>

      <span data-ttu-id="cfb90-145">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="cfb90-145">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

-   <span data-ttu-id="cfb90-146">Mac OSX:</span><span class="sxs-lookup"><span data-stu-id="cfb90-146">Mac OSX:</span></span>

      <span data-ttu-id="cfb90-147">Atalho do teclado: Opção + Comando + Shift+1</span><span class="sxs-lookup"><span data-stu-id="cfb90-147">Keyboard shortcut: Option + Command + Shift+1</span></span>

-   <span data-ttu-id="cfb90-148">Linux</span><span class="sxs-lookup"><span data-stu-id="cfb90-148">Linux:</span></span>

      <span data-ttu-id="cfb90-149">Atalho do teclado: Ctrl + Alt + Shift + 1</span><span class="sxs-lookup"><span data-stu-id="cfb90-149">Keyboard shortcut: Ctrl + Alt + Shift + 1</span></span>

<span data-ttu-id="cfb90-150">Os registros de depuração serão baixados automaticamente nas seguintes pastas.</span><span class="sxs-lookup"><span data-stu-id="cfb90-150">The debug logs are automatically downloaded to the following folders.</span></span>

-   <span data-ttu-id="cfb90-151">Windows: %userprofile%\\Downloads</span><span class="sxs-lookup"><span data-stu-id="cfb90-151">Windows: %userprofile%\\Downloads</span></span>

-   <span data-ttu-id="cfb90-152">Mac OSX: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="cfb90-152">Mac OSX: ~/Downloads</span></span>

-   <span data-ttu-id="cfb90-153">Linux: ~/downloads</span><span class="sxs-lookup"><span data-stu-id="cfb90-153">Linux: ~/Downloads</span></span>

-   <span data-ttu-id="cfb90-154">Navegador: Você será instruído para salvar o registro de depuração no local padrão de salvamento</span><span class="sxs-lookup"><span data-stu-id="cfb90-154">Browser: You will be prompted to save the debug log to default save location</span></span>

<a name="media-logs"></a><span data-ttu-id="cfb90-155">Registros de mídia</span><span class="sxs-lookup"><span data-stu-id="cfb90-155">Media logs</span></span>
---------------------------

<span data-ttu-id="cfb90-156">Os logs de mídia contêm dados de diagnóstico sobre áudio, vídeo e compartilhamento de tela em reuniões do teams.</span><span class="sxs-lookup"><span data-stu-id="cfb90-156">Media logs contain diagnostic data about audio, video, and screen sharing in Teams meetings.</span></span> <span data-ttu-id="cfb90-157">Elas são necessárias para casos de suporte vinculados a problemas relacionados a chamadas.</span><span class="sxs-lookup"><span data-stu-id="cfb90-157">They are required for support cases that are linked to call-related issues.</span></span>

<span data-ttu-id="cfb90-158">O log de mídia está desativado por padrão.</span><span class="sxs-lookup"><span data-stu-id="cfb90-158">Media logging is turned off by default.</span></span> <span data-ttu-id="cfb90-159">Para registrar dados de diagnóstico para reuniões do Teams, os usuários devem ativar a opção no cliente do teams.</span><span class="sxs-lookup"><span data-stu-id="cfb90-159">To log diagnostic data for Teams meetings, users must turn on the option in the Teams client.</span></span> <span data-ttu-id="cfb90-160">Vá para **configurações**  >  **geral**, marque a caixa de seleção **habilitar o registro em log para diagnóstico de reunião (requer a reinicialização de equipes**) e reinicie o Microsoft Teams e reproduza o problema.</span><span class="sxs-lookup"><span data-stu-id="cfb90-160">Go to **Settings** > **General**, select the **Enable logging for meeting diagnostics (requires restarting Teams**) check box, and then restart Teams and reproduce the issue.</span></span> 

<span data-ttu-id="cfb90-161">A tabela a seguir descreve os locais do log de mídia.</span><span class="sxs-lookup"><span data-stu-id="cfb90-161">The following table outlines the media log locations.</span></span> <span data-ttu-id="cfb90-162">Ao enviar os arquivos de log para o suporte da Microsoft, verifique o carimbo de data/hora dos arquivos de log para garantir que os logs cubram o intervalo de tempo quando você reproduziu o problema.</span><span class="sxs-lookup"><span data-stu-id="cfb90-162">When you send the log files to Microsoft support, please verify the timestamp of the log files to make sure the logs cover the time frame when you reproduced the issue.</span></span>

|<span data-ttu-id="cfb90-163">Cliente</span><span class="sxs-lookup"><span data-stu-id="cfb90-163">Client</span></span> |<span data-ttu-id="cfb90-164">Localização</span><span class="sxs-lookup"><span data-stu-id="cfb90-164">Location</span></span> |
|---------|---------|
|<span data-ttu-id="cfb90-165">Windows</span><span class="sxs-lookup"><span data-stu-id="cfb90-165">Windows</span></span>     |<span data-ttu-id="cfb90-166">%appdata%\Microsoft\Teams\media-stack \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-166">%appdata%\Microsoft\Teams\media-stack\\*.blog</span></span>         |
|            |<span data-ttu-id="cfb90-167">%appdata%\Microsoft\Teams\skylib \\ \*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-167">%appdata%\Microsoft\Teams\skylib\\*.blog</span></span>
|            |<span data-ttu-id="cfb90-168">%appdata%\Microsoft\Teams\media-stack \\ \*. etl</span><span class="sxs-lookup"><span data-stu-id="cfb90-168">%appdata%\Microsoft\Teams\media-stack\\*.etl</span></span>         |
|<span data-ttu-id="cfb90-169">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="cfb90-169">Mac OSX</span></span>     |<span data-ttu-id="cfb90-170">~/Library/Application Support Support/Microsoft/Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-170">~/Library/Application Support/Microsoft/Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="cfb90-171">~/Library/Application Support Support/Microsoft/Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-171">~/Library/Application Support/Microsoft/Teams/skylib/\*.blog</span></span>         |
|<span data-ttu-id="cfb90-172">Linux</span><span class="sxs-lookup"><span data-stu-id="cfb90-172">Linux</span></span>       |<span data-ttu-id="cfb90-173">~/.config/Microsoft/Microsoft Teams/Media-Stack/\*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-173">~/.config/Microsoft/Microsoft Teams/media-stack/\*.blog</span></span>         |
|            |<span data-ttu-id="cfb90-174">~/.config/Microsoft/Microsoft Teams/skylib/\*. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-174">~/.config/Microsoft/Microsoft Teams/skylib/\*.blog</span></span>         |

<span data-ttu-id="cfb90-175">Aqui está uma lista dos arquivos de log que são gerados e as informações que eles contêm.</span><span class="sxs-lookup"><span data-stu-id="cfb90-175">Here's a list of the log files that are generated and the information they contain.</span></span>

|<span data-ttu-id="cfb90-176">Nome do arquivo de log</span><span class="sxs-lookup"><span data-stu-id="cfb90-176">Log file name</span></span>  |<span data-ttu-id="cfb90-177">Descrição</span><span class="sxs-lookup"><span data-stu-id="cfb90-177">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="cfb90-178">Teams. msRTC-0-s1039525249. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-178">Teams.msrtc-0-s1039525249.blog</span></span>     | <span data-ttu-id="cfb90-179">Contém informações relacionadas à pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="cfb90-179">Contains information related to the media stack.</span></span> <span data-ttu-id="cfb90-180">Isso inclui o status do canal, como resolução, decodificadores e codificadores usados, e o número de quadros enviados e recebidos, e o status da sessão de câmera e compartilhamento de tela baseado em vídeo (VBSS).</span><span class="sxs-lookup"><span data-stu-id="cfb90-180">This includes channel status such as resolution, decoders and encoders used, and the number of frames sent and received, and camera and video-based screen sharing (VBSS) session status.</span></span>         |
|<span data-ttu-id="cfb90-181">rtmcontrol. msRTC-0-2415069487. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-181">rtmcontrol.msrtc-0-2415069487.blog</span></span>      |<span data-ttu-id="cfb90-182">Registra informações relacionadas a ações de controle remoto, como o carimbo de data/hora quando o controle é fornecido, e informações de ponteiro do mouse.</span><span class="sxs-lookup"><span data-stu-id="cfb90-182">Records information related to remote control actions, such as the time stamp when control is given, and mouse pointer information.</span></span>          |
|<span data-ttu-id="cfb90-183">Teams_MediaStackETW -2-U-xr-U. etl</span><span class="sxs-lookup"><span data-stu-id="cfb90-183">Teams_MediaStackETW-2-U-xr-U.etl</span></span>      |<span data-ttu-id="cfb90-184">Registra eventos de rastreamento de pilha de mídia.</span><span class="sxs-lookup"><span data-stu-id="cfb90-184">Records media stack trace events.</span></span>         |
|<span data-ttu-id="cfb90-185">Debug-0-s2790420889. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-185">Debug-0-s2790420889.blog</span></span>    | <span data-ttu-id="cfb90-186">Contém informações relacionadas ao agente de mídia, incluindo qualidade de renderização.</span><span class="sxs-lookup"><span data-stu-id="cfb90-186">Contains information related to the media agent, including rendering quality.</span></span>          |
|<span data-ttu-id="cfb90-187">tscalling-0-2061129496. blog</span><span class="sxs-lookup"><span data-stu-id="cfb90-187">tscalling-0-2061129496.blog</span></span>   |<span data-ttu-id="cfb90-188">Registra eventos na API de chamadas para TS.</span><span class="sxs-lookup"><span data-stu-id="cfb90-188">Records events in the ts-calling API.</span></span>       |

<a name="desktop-logs"></a><span data-ttu-id="cfb90-189">Registros de desktop</span><span class="sxs-lookup"><span data-stu-id="cfb90-189">Desktop logs</span></span>
---------------------

<span data-ttu-id="cfb90-190">Os registros de desktop, também conhecidos como registros de bootstrapper, contém dados de registro que ocorrem entre o clientes desktop e o navegador.</span><span class="sxs-lookup"><span data-stu-id="cfb90-190">Desktop logs, also known as bootstrapper logs, contains log data that occurs between the desktop client and the browser.</span></span> <span data-ttu-id="cfb90-191">Assim como os registros de mídia, esses registros só são necessários se forem solicitados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cfb90-191">Like media logs, these logs are only needed if requested by Microsoft.</span></span> <span data-ttu-id="cfb90-192">Os registros são baseados em texto e podem ser lidos usando qualquer editor baseado em texto no formato de cima para baixo.</span><span class="sxs-lookup"><span data-stu-id="cfb90-192">The logs are text based and can be read using any text based editor in a top down format.</span></span>

<span data-ttu-id="cfb90-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="cfb90-193">Windows:</span></span>

1.  <span data-ttu-id="cfb90-194">Clique com o botão direito do mouse no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**</span><span class="sxs-lookup"><span data-stu-id="cfb90-194">Right-click the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

<span data-ttu-id="cfb90-195">Mac OsX:</span><span class="sxs-lookup"><span data-stu-id="cfb90-195">Mac OsX:</span></span>

1.  <span data-ttu-id="cfb90-196">Escolher **Obter registros** no menu suspenso de **Ajuda**</span><span class="sxs-lookup"><span data-stu-id="cfb90-196">Choosing **Get Logs** from the **Help** pull-down menu</span></span>

<span data-ttu-id="cfb90-197">Linux</span><span class="sxs-lookup"><span data-stu-id="cfb90-197">Linux:</span></span>

1.  <span data-ttu-id="cfb90-198">Clique no ícone do **Microsoft Teams** na bandeja do sistema, selecione **obter logs**</span><span class="sxs-lookup"><span data-stu-id="cfb90-198">Click on the **Microsoft Teams** icon in your system tray, select **Get Logs**</span></span>

|<span data-ttu-id="cfb90-199">Cliente</span><span class="sxs-lookup"><span data-stu-id="cfb90-199">Client</span></span> |<span data-ttu-id="cfb90-200">Localização</span><span class="sxs-lookup"><span data-stu-id="cfb90-200">Location</span></span> |
|---------|---------|
|<span data-ttu-id="cfb90-201">Windows</span><span class="sxs-lookup"><span data-stu-id="cfb90-201">Windows</span></span>     |<span data-ttu-id="cfb90-202">% AppData% \Microsoft\Teams\logs.txt</span><span class="sxs-lookup"><span data-stu-id="cfb90-202">%appdata%\Microsoft\Teams\logs.txt</span></span>         |
|<span data-ttu-id="cfb90-203">Mac OSX</span><span class="sxs-lookup"><span data-stu-id="cfb90-203">Mac OSX</span></span>     |<span data-ttu-id="cfb90-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="cfb90-204">~/Library/Application Support/Microsoft/Teams/logs.txt</span></span>         |
|<span data-ttu-id="cfb90-205">Linux</span><span class="sxs-lookup"><span data-stu-id="cfb90-205">Linux</span></span>       |<span data-ttu-id="cfb90-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span><span class="sxs-lookup"><span data-stu-id="cfb90-206">~/.config/Microsoft/Microsoft Teams/logs.txt</span></span>         |


## <a name="related-topics"></a><span data-ttu-id="cfb90-207">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cfb90-207">Related topics</span></span>

[<span data-ttu-id="cfb90-208">Solução de problemas do Teams</span><span class="sxs-lookup"><span data-stu-id="cfb90-208">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)
