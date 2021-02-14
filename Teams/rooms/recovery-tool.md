---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: Este artigo aborda como usar a ferramenta de recuperação de Salas do Microsoft Teams, que você usaria para trazer um sistema desa atualizado para um estado com suporte.
ms.openlocfilehash: 47e9bed4377a111a1c1284684bbc40517dbb42d8
ms.sourcegitcommit: 4099da7b1db7663e63ef5bece16e3090c33ea207
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/02/2020
ms.locfileid: "45021719"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="9a88f-103">Usar a ferramenta de recuperação das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a88f-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="9a88f-104">Este artigo aborda como usar a ferramenta de recuperação de Salas do Microsoft Teams, que você usaria para trazer um sistema desa atualizado para um estado com suporte.</span><span class="sxs-lookup"><span data-stu-id="9a88f-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="9a88f-105">Essa ferramenta deve ser aplicada quando o console salas do Microsoft Teams mostrar um erro "configuração do sistema des des date" ou antes de executar uma restauração de fábrica de restauração de botão [de push.](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore)</span><span class="sxs-lookup"><span data-stu-id="9a88f-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="9a88f-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="9a88f-106">Prerequisites</span></span>

<span data-ttu-id="9a88f-107">Baixe o pacote [de instalação mais recente do Microsoft Teams Rooms](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um cartão de memória USB ou compartilhamento de rede acessível para o dispositivo Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a88f-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="9a88f-108">Extrair os arquivos do MSI pode ser realizado de várias maneiras.</span><span class="sxs-lookup"><span data-stu-id="9a88f-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="9a88f-109">Qualquer mecanismo que extraia todos os arquivos e preserve sua estrutura de diretórios é aceitável.</span><span class="sxs-lookup"><span data-stu-id="9a88f-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="9a88f-110">Uma delas é usar o comando onde representa o caminho completo para o pacote de instalação da Sala do Microsoft Teams e representa o caminho completo para a pasta para a qual você gostaria que os arquivos fosse `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` extraídos.</span><span class="sxs-lookup"><span data-stu-id="9a88f-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="9a88f-111">Executando a ferramenta</span><span class="sxs-lookup"><span data-stu-id="9a88f-111">Running the tool</span></span>

1) <span data-ttu-id="9a88f-112">Entre na conta de administrador em seu dispositivo Salas do Microsoft Teams e iniciar um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="9a88f-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="9a88f-113">Verifique no dispositivo Salas do Microsoft Teams que você pode acessar, que está incluído nos arquivos extraídos do pacote de instalação salas `RecoveryTool.ps1 file` do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9a88f-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="9a88f-114">O kit pode ser encontrado no compartilhamento de rede ou unidade USB usada durante a preparação de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="9a88f-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="9a88f-115">`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`Executar.</span><span class="sxs-lookup"><span data-stu-id="9a88f-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="9a88f-116">Para executar uma restauração de fábrica:</span><span class="sxs-lookup"><span data-stu-id="9a88f-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="9a88f-117">Quando solicitado pelo script, selecione a opção 2: **Redefinir.**</span><span class="sxs-lookup"><span data-stu-id="9a88f-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="9a88f-118">Se o BitLocker estiver on, siga as instruções fornecidas no final da saída do script para desabilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="9a88f-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="9a88f-119">Executar a restauração de fábrica.</span><span class="sxs-lookup"><span data-stu-id="9a88f-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="9a88f-120">Abra o **aplicativo Configurações** e selecione **Atualizar & Segurança**</span><span class="sxs-lookup"><span data-stu-id="9a88f-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="9a88f-121">Navegue até a **guia Recuperação.**</span><span class="sxs-lookup"><span data-stu-id="9a88f-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="9a88f-122">Beneath **Reset this PC,** select **Get started**</span><span class="sxs-lookup"><span data-stu-id="9a88f-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="9a88f-123">Selecione **Remover tudo** e, em **seguida, Próximo** e **Redefinir**</span><span class="sxs-lookup"><span data-stu-id="9a88f-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="9a88f-124">O dispositivo Salas do Microsoft Teams pode se tornar inutilizável se o arquivo Manter meus arquivos **– remove aplicativos** e configurações, mas mantém sua opção de arquivos pessoais selecionada durante o processo de Redefinição do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a88f-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="9a88f-125">Não selecione essa opção.</span><span class="sxs-lookup"><span data-stu-id="9a88f-125">Do not select this option.</span></span>
      5. <span data-ttu-id="9a88f-126">O sistema será reiniciado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="9a88f-126">The system will reboot multiple times.</span></span> <span data-ttu-id="9a88f-127">Quando a redefinição for concluída, o sistema estará na tela "experiência fora da caixa" (OOBE) do Windows.</span><span class="sxs-lookup"><span data-stu-id="9a88f-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="9a88f-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="9a88f-128">See also</span></span>

[<span data-ttu-id="9a88f-129">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a88f-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="9a88f-130">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9a88f-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
