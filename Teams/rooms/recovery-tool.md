---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
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
description: Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.
ms.openlocfilehash: 755a85c9013d160197c8a8d57f74ef18b207e052
ms.sourcegitcommit: 3d393ceded4d64963411cfdc96931952d480ded5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225275"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="1e499-103">Usar a ferramenta de recuperação das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e499-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="1e499-104">Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.</span><span class="sxs-lookup"><span data-stu-id="1e499-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="1e499-105">Essa ferramenta deve ser aplicada quando o console de salas do Microsoft Teams mostra um erro de "configuração do sistema desatualizada" ou antes de executar um botão de ação redefinir a [restauração de fábrica](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span><span class="sxs-lookup"><span data-stu-id="1e499-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/rooms/rooms-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1e499-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1e499-106">Prerequisites</span></span>

<span data-ttu-id="1e499-107">Baixe o [pacote de instalação das salas do Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) mais recente e extraia-o em um joystick de memória USB ou compartilhamento de rede acessível ao dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e499-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="1e499-108">A extração de arquivos do MSI pode ser realizada muitas formas.</span><span class="sxs-lookup"><span data-stu-id="1e499-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="1e499-109">Qualquer mecanismo que extrai todos os arquivos e preserva a estrutura do diretório é aceitável.</span><span class="sxs-lookup"><span data-stu-id="1e499-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="1e499-110">Uma dessas formas é usar o comando `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` em que `PathToMsi` representa o caminho completo para o pacote de instalação da sala do Microsoft `PathToTarget` Teams e representa o caminho completo da pasta para a qual você deseja que os arquivos sejam extraídos.</span><span class="sxs-lookup"><span data-stu-id="1e499-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="1e499-111">Executar a ferramenta</span><span class="sxs-lookup"><span data-stu-id="1e499-111">Running the tool</span></span>

1) <span data-ttu-id="1e499-112">Entre na conta de administrador em seu dispositivo de salas do Microsoft Teams e inicie um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="1e499-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="1e499-113">Verifique o dispositivo de salas Microsoft Teams que você pode acessar `RecoveryTool.ps1 file`, que está incluído nos arquivos extraídos do pacote de instalação de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e499-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="1e499-114">O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="1e499-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="1e499-115">Executar `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="1e499-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="1e499-116">Se você estiver executando uma restauração de fábrica:</span><span class="sxs-lookup"><span data-stu-id="1e499-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="1e499-117">Quando solicitado pelo script, selecione a opção 2: **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="1e499-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="1e499-118">Se o BitLocker estiver ativado, siga as instruções fornecidas no final da saída do script para desabilitá-lo.</span><span class="sxs-lookup"><span data-stu-id="1e499-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="1e499-119">Realize a restauração de fábrica.</span><span class="sxs-lookup"><span data-stu-id="1e499-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="1e499-120">Abra o aplicativo **configurações** e selecione **Atualizar & segurança**</span><span class="sxs-lookup"><span data-stu-id="1e499-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="1e499-121">Navegue até a guia **recuperação** .</span><span class="sxs-lookup"><span data-stu-id="1e499-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="1e499-122">Abaixo **restaurar este PC**, selecione **introdução**</span><span class="sxs-lookup"><span data-stu-id="1e499-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="1e499-123">Selecione **remover tudo**e, em seguida, **Avançar** e **Redefinir**</span><span class="sxs-lookup"><span data-stu-id="1e499-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="1e499-124">O sistema será reiniciado várias vezes.</span><span class="sxs-lookup"><span data-stu-id="1e499-124">The system will reboot multiple times.</span></span> <span data-ttu-id="1e499-125">Quando a reinicialização estiver concluída, o sistema estará na tela OOBE do Windows.</span><span class="sxs-lookup"><span data-stu-id="1e499-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="1e499-126">Se você estiver reparando um sistema "desatualizado":</span><span class="sxs-lookup"><span data-stu-id="1e499-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="1e499-127">Quando solicitado pelo script, selecione a opção 1: **reparar**.</span><span class="sxs-lookup"><span data-stu-id="1e499-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="1e499-128">Após a conclusão, reinicie o dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1e499-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="1e499-129">Ele reiniciará novamente automaticamente e a recuperação será completada na segunda vez.</span><span class="sxs-lookup"><span data-stu-id="1e499-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="1e499-130">Há um problema conhecido em que as salas do Microsoft Teams podem ficar inúteis se a opção **manter meus arquivos-remove meus arquivos-remove aplicativos e configurações, mas mantém a opção arquivos pessoais** selecionada durante o processo de redefinição do Windows.</span><span class="sxs-lookup"><span data-stu-id="1e499-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="1e499-131">Não *Use essa* opção.</span><span class="sxs-lookup"><span data-stu-id="1e499-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e499-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="1e499-132">See also</span></span>

[<span data-ttu-id="1e499-133">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e499-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="1e499-134">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1e499-134">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
