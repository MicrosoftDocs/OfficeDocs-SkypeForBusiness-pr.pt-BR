---
title: Atualizar manualmente um Salas do Microsoft Teams dispositivo
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Saiba como atualizar manualmente seu Salas do Microsoft Teams para uma versão específica.
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117509"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="ae326-103">Atualizar manualmente um Salas do Microsoft Teams dispositivo</span><span class="sxs-lookup"><span data-stu-id="ae326-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="ae326-104">O Salas do Microsoft Teams aplicativo é distribuído por meio do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ae326-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="ae326-105">As atualizações do aplicativo são instaladas automaticamente no Microsoft Store durante a manutenção noturna; este é o método recomendado para obter atualizações.</span><span class="sxs-lookup"><span data-stu-id="ae326-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="ae326-106">No entanto, há algumas situações em que um dispositivo Salas do Teams não pode receber atualizações do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ae326-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="ae326-107">Por exemplo, as políticas de segurança podem não permitir que os dispositivos se conectem à Internet ou podem não permitir que os aplicativos sejam baixados do Microsoft Store.</span><span class="sxs-lookup"><span data-stu-id="ae326-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="ae326-108">Ou talvez você queira atualizar um dispositivo antes de executar a instalação, durante o qual o Microsoft Store não está disponível.</span><span class="sxs-lookup"><span data-stu-id="ae326-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="ae326-109">Se você não conseguir obter atualizações do Microsoft Store, poderá usar um script do PowerShell de atualização de aplicativo offline para atualizar manualmente seus dispositivos Salas do Teams para uma versão mais recente do aplicativo Salas do Teams.</span><span class="sxs-lookup"><span data-stu-id="ae326-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="ae326-110">Siga as etapas deste artigo para atualizar manualmente seus Salas do Teams dispositivos.</span><span class="sxs-lookup"><span data-stu-id="ae326-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="ae326-111">Esse processo só pode atualizar um Salas do Teams com o aplicativo Salas do Teams já instalado.</span><span class="sxs-lookup"><span data-stu-id="ae326-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="ae326-112">Ele não pode ser usado para executar uma nova instalação.</span><span class="sxs-lookup"><span data-stu-id="ae326-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="ae326-113">Ele também não pode ser usado para fazer o downgrade do aplicativo para uma versão mais antiga.</span><span class="sxs-lookup"><span data-stu-id="ae326-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="ae326-114">Para executar uma nova instalação do aplicativo Salas do Teams, entre em contato com o fabricante do dispositivo para mídia específica a ele ou consulte Preparar a [mídia de instalação](console.md#prepare-the-installation-media).</span><span class="sxs-lookup"><span data-stu-id="ae326-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="ae326-115">Etapa 1: Baixar o script de atualização de aplicativo offline</span><span class="sxs-lookup"><span data-stu-id="ae326-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="ae326-116">Primeiro, baixe a versão mais recente do script de atualização do aplicativo offline.</span><span class="sxs-lookup"><span data-stu-id="ae326-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="ae326-117">Para baixar o script, clique em <https://go.microsoft.com/fwlink/?linkid=2151817> .</span><span class="sxs-lookup"><span data-stu-id="ae326-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="ae326-118">O script será baixado para a pasta de downloads padrão em seu dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="ae326-119">Os arquivos baixados podem ser marcados como bloqueados por Windows.</span><span class="sxs-lookup"><span data-stu-id="ae326-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="ae326-120">Se você precisar executar o script sem nenhuma interação, será necessário desbloquear o script.</span><span class="sxs-lookup"><span data-stu-id="ae326-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="ae326-121">Para desbloquear o script, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ae326-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="ae326-122">Clique com o botão direito do mouse no arquivo no Explorador de Arquivos</span><span class="sxs-lookup"><span data-stu-id="ae326-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="ae326-123">Clique **em Propriedades**</span><span class="sxs-lookup"><span data-stu-id="ae326-123">Click **Properties**</span></span>
3. <span data-ttu-id="ae326-124">Selecionar **Desbloquear**</span><span class="sxs-lookup"><span data-stu-id="ae326-124">Select **Unblock**</span></span>
4. <span data-ttu-id="ae326-125">Clique **em OK**</span><span class="sxs-lookup"><span data-stu-id="ae326-125">Click **OK**</span></span>

<span data-ttu-id="ae326-126">Para desbloquear o script usando o PowerShell, consulte [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span><span class="sxs-lookup"><span data-stu-id="ae326-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="ae326-127">Depois que o script de atualização de aplicativo offline for baixado, transfira o arquivo para o Salas do Teams dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="ae326-128">Você pode transferir um arquivo para o dispositivo usando uma unidade USB ou acessando o arquivo de um compartilhamento de arquivos de rede enquanto estiver no Modo De Administração no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="ae326-129">Lembre-se de observar onde você salva o arquivo no dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="ae326-130">Etapa 2: executar o script para atualizar o Salas do Teams app</span><span class="sxs-lookup"><span data-stu-id="ae326-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="ae326-131">O script de atualização de aplicativo offline precisa ser executado a partir de um prompt de comando elevado enquanto o usuário Skype (o usuário sob o qual o aplicativo é executado) ainda está assinado.</span><span class="sxs-lookup"><span data-stu-id="ae326-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="ae326-132">Para obter mais informações sobre como fazer logon em uma conta de administrador para usar o prompt de comando com privilégios elevados enquanto o usuário do Skype ainda estiver conectado, consulte [Alternando](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)para o Modo de Administração e de volta quando o aplicativo Salas do Microsoft Teams estiver em execução .</span><span class="sxs-lookup"><span data-stu-id="ae326-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="ae326-133">Faça o seguinte para executar o script de um prompt de comando elevado:</span><span class="sxs-lookup"><span data-stu-id="ae326-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="ae326-134">Alternar para o Modo de Administração</span><span class="sxs-lookup"><span data-stu-id="ae326-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="ae326-135">Clique no ícone Iniciar, digite **Prompt de** Comando e selecione Executar **como administrador**</span><span class="sxs-lookup"><span data-stu-id="ae326-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="ae326-136">Execute o seguinte comando onde inclui o caminho completo para o script e `<path to script>` o nome do arquivo de script:</span><span class="sxs-lookup"><span data-stu-id="ae326-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="ae326-137">Por exemplo, se o arquivo de script estiver localizado em , e o nome do `C:\Users\Admin\Downloads` arquivo de script for , execute o seguinte `MTR-Update-4.5.6.7.ps1` comando:</span><span class="sxs-lookup"><span data-stu-id="ae326-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="ae326-138">Permitir que o script seja executado.</span><span class="sxs-lookup"><span data-stu-id="ae326-138">Allow the script to run.</span></span> <span data-ttu-id="ae326-139">Quando terminar, o script reiniciará o Salas do Teams dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="ae326-140">Você também pode executar o script usando o PowerShell Remoto.</span><span class="sxs-lookup"><span data-stu-id="ae326-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="ae326-141">Para obter mais informações sobre como usar o PowerShell remoto com Salas do Teams dispositivos, consulte [Gerenciamento Remoto usando o PowerShell](rooms-operations.md#remote-management-using-powershell).</span><span class="sxs-lookup"><span data-stu-id="ae326-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="ae326-142">Etapa 3: Verificar se o aplicativo foi atualizado com êxito</span><span class="sxs-lookup"><span data-stu-id="ae326-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="ae326-143">Se o script for executado com êxito, o dispositivo será reiniciado no Salas do Teams aplicativo.</span><span class="sxs-lookup"><span data-stu-id="ae326-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="ae326-144">Se o script encontrar um problema, ele indicará qual é o problema na linha de comando e registrará sua saída em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="ae326-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="ae326-145">Siga todas as instruções fornecidas pelo script.</span><span class="sxs-lookup"><span data-stu-id="ae326-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="ae326-146">Se precisar entrar em contato com o Suporte da Microsoft, certifique-se de incluir o arquivo de log juntamente com a solicitação de suporte.</span><span class="sxs-lookup"><span data-stu-id="ae326-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="ae326-147">O script fornecerá o caminho para o arquivo de log.</span><span class="sxs-lookup"><span data-stu-id="ae326-147">The script will provide you with the path to the log file.</span></span>