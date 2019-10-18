---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.
ms.openlocfilehash: 04fd6b4b0786cffb4f1bb050a7b0bbdac8e2e653
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573644"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="0d5ff-103">Usar a ferramenta de recuperação das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d5ff-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="0d5ff-104">Este artigo discute como usar a ferramenta de recuperação para salas do Microsoft Teams, que você usaria para colocar um sistema desatualizado em um estado com suporte.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="0d5ff-105">Você usaria essa ferramenta quando o console de salas do Microsoft Teams mostra um erro de "configuração do sistema desatualizada".</span><span class="sxs-lookup"><span data-stu-id="0d5ff-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="0d5ff-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="0d5ff-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="0d5ff-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="0d5ff-107">Prerequisites</span></span>

<span data-ttu-id="0d5ff-108">Baixe o [pacote de instalação das salas do Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=851168) mais recente e extraia-o em um joystick de memória USB ou compartilhamento de rede acessível ao dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="0d5ff-109">Você também pode precisar instalar o [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="0d5ff-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="0d5ff-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="0d5ff-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="0d5ff-111">Verificar versão do Windows</span><span class="sxs-lookup"><span data-stu-id="0d5ff-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="0d5ff-112">Faça logon em uma conta de administrador acessando **configurações> configuração do Windows> entrar no Microsoft Teams Inscreva-se** no dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="0d5ff-113">Essa opção traz para a tela de login.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="0d5ff-114">Conecte-se a uma conta de administrador, a conta `admin` de administrador padrão `sfb`que está usando a senha.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="0d5ff-115">Clique no menu iniciar e digite `winver.exe` na caixa de pesquisa e clique em \**executar comando* no resultado.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="0d5ff-116">Anote o número após ' version ' na segunda linha do painel de informações.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="0d5ff-117">Se a versão mostrada for 1607 ou anterior, siga as etapas nas etapas <a href="#Windows-up">atualizar o Windows antes da recuperação</a> antes de <a href="#Perform">realizar uma</a> etapa de recuperação.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="0d5ff-118">Se a versão mostrada for maior que 1607, siga apenas as etapas em <a href="#Perform">executar uma recuperação</a>.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="0d5ff-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="0d5ff-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="0d5ff-120">Atualizar o Windows antes da recuperação (se necessário)</span><span class="sxs-lookup"><span data-stu-id="0d5ff-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="0d5ff-121">Enquanto estiver conectado como um usuário administrador, inicie um prompt elevado do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="0d5ff-122">Executar o comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="0d5ff-123">Execute o Windows Update e instale a atualização para o Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="0d5ff-124">Depois que a atualização para o 1709 for concluída, conecte-se novamente à conta de administrador e instale o [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="0d5ff-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="0d5ff-125">A atualização pode ser feita a partir do link ou usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="0d5ff-126">Como uma etapa opcional, instale as atualizações adicionais disponíveis no Windows Update.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="0d5ff-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="0d5ff-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="0d5ff-128">Executar uma recuperação</span><span class="sxs-lookup"><span data-stu-id="0d5ff-128">Perform a recovery</span></span>

1. <span data-ttu-id="0d5ff-129">Entre na conta de administrador em seu dispositivo de salas do Microsoft Teams e inicie um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="0d5ff-130">Verifique o dispositivo de salas Microsoft Teams que você pode acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="0d5ff-131">O kit pode ser encontrado no compartilhamento de rede ou na unidade USB usada ao preparar pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="0d5ff-132">Execute o comando `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`PowerShell. exe.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="0d5ff-133">Quando solicitado pela opção `1:"Repair System"`de seleção de script.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="0d5ff-134">Após a conclusão, reinicie o dispositivo de salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="0d5ff-135">Ele reiniciará novamente automaticamente e a recuperação será completada na segunda vez.</span><span class="sxs-lookup"><span data-stu-id="0d5ff-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="0d5ff-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="0d5ff-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="0d5ff-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="0d5ff-137">See also</span></span>
 
[<span data-ttu-id="0d5ff-138">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d5ff-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="0d5ff-139">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0d5ff-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
