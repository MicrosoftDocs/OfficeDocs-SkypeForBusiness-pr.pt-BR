---
title: Usar a ferramenta de recuperação das Salas do Microsoft Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para salas de equipes da Microsoft, que você usaria para trazer um sistema desatualizado para um estado com suporte.
ms.openlocfilehash: 9580a94c96b7982a3030ccc0435be8e05f7c4a25
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362555"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="e677c-103">Usar a ferramenta de recuperação das Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e677c-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="e677c-104">Este artigo discute como usar a ferramenta de recuperação para salas de equipes da Microsoft, que você usaria para trazer um sistema desatualizado para um estado com suporte.</span><span class="sxs-lookup"><span data-stu-id="e677c-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="e677c-105">Quando o console de salas de equipes da Microsoft mostra um erro "system config desatualizada", você usaria esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="e677c-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="e677c-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="e677c-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="e677c-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e677c-107">Prerequisites</span></span>

<span data-ttu-id="e677c-108">Baixe o mais recente [pacote de instalação de salas de equipes da Microsoft](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um USB memória pente ou compartilhamento de rede acessível para o dispositivo de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e677c-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="e677c-109">Você também pode precisar instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="e677c-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="e677c-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="e677c-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="e677c-111">Verifique se a versão do Windows</span><span class="sxs-lookup"><span data-stu-id="e677c-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="e677c-112">Login com uma conta de administrador, indo para **Settings> Windows Setting> Admin entrar** do dispositivo Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="e677c-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="e677c-113">Essa opção leva a tela de login.</span><span class="sxs-lookup"><span data-stu-id="e677c-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="e677c-114">Conta de entrada em uma conta de administrador, o administrador padrão que está sendo `admin` com a senha `sfb`.</span><span class="sxs-lookup"><span data-stu-id="e677c-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="e677c-115">Clique no menu Iniciar e digite `winver.exe` na caixa Pesquisar e clique em \**Comando executar* no resultado.</span><span class="sxs-lookup"><span data-stu-id="e677c-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="e677c-116">Anote o número após 'Versão' na segunda linha do painel informações.</span><span class="sxs-lookup"><span data-stu-id="e677c-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="e677c-117">Se a versão mostrada for 1607 ou anterior, siga as etapas nas etapas <a href="#Windows-up">Windows Update antes de recuperação</a> antes de proceding para as etapas de <a href="#Perform">executar uma recuperação</a> .</span><span class="sxs-lookup"><span data-stu-id="e677c-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="e677c-118">Se a versão mostrada for maior que 1607, siga somente as etapas em <a href="#Perform">Perform uma recuperação</a>.</span><span class="sxs-lookup"><span data-stu-id="e677c-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="e677c-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="e677c-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="e677c-120">Atualizar o Windows antes de recuperação (se necessário)</span><span class="sxs-lookup"><span data-stu-id="e677c-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="e677c-121">Enquanto ainda logado como um usuário admin, inicie um prompt elevado do Powershell.</span><span class="sxs-lookup"><span data-stu-id="e677c-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="e677c-122">Execute o comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="e677c-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="e677c-123">Execute o Windows Update e instalar a atualização para Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="e677c-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="e677c-124">Após a atualização para 1709 está entrada completa que voltou ao conta de administrador e instala [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="e677c-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="e677c-125">A atualização pode ser feita no link ou usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e677c-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="e677c-126">Como uma etapa opcional, instale quaisquer atualizações adicionais disponíveis do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="e677c-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="e677c-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="e677c-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="e677c-128">Executar uma recuperação</span><span class="sxs-lookup"><span data-stu-id="e677c-128">Perform a recovery</span></span>

1. <span data-ttu-id="e677c-129">Entrar com a conta de administrador no seu dispositivo de salas de equipes da Microsoft e inicie um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="e677c-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="e677c-130">Verificar do dispositivo salas de equipes da Microsoft se você é capaz de acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação do Microsoft equipes salas.</span><span class="sxs-lookup"><span data-stu-id="e677c-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="e677c-131">O kit pode ser encontrado no compartilhamento de rede ou unidade USB usado durante a preparação de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="e677c-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="e677c-132">Execute o comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="e677c-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="e677c-133">Quando solicitado, selecione a opção o script `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="e677c-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="e677c-134">Após a conclusão, reinicialize o dispositivo de salas de equipes da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e677c-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="e677c-135">Ela será reinicializar novamente automaticamente e surgirem recuperada totalmente a segunda vez.</span><span class="sxs-lookup"><span data-stu-id="e677c-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="e677c-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="e677c-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="e677c-137">Confira também</span><span class="sxs-lookup"><span data-stu-id="e677c-137">See also</span></span>
 
[<span data-ttu-id="e677c-138">Suporte às Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e677c-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="e677c-139">Gerenciar Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e677c-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)