---
title: Use a ferramenta de recuperação de v2 de sistemas de sala do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Este artigo discute como usar a ferramenta de recuperação para sistemas de sala Skype v2, que você usaria para trazer um sistema desatualizado para um estado com suporte.
ms.openlocfilehash: 63deb332a520a0752242140f85f200a160eefe0d
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="use-the-skype-room-systems-v2-recovery-tool"></a><span data-ttu-id="f2b3a-103">Use a ferramenta de recuperação de v2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="f2b3a-103">Use the Skype Room Systems v2 recovery tool</span></span>
 
<span data-ttu-id="f2b3a-104">Este artigo discute como usar a ferramenta de recuperação para sistemas de sala Skype v2, que você usaria para trazer um sistema desatualizado para um estado com suporte.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-104">This article discusses how to use the recovery tool for Skype Room Systems v2, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="f2b3a-105">Quando o console do Skype sala sistemas v2 mostra um erro "system config desatualizada", você usaria esta ferramenta.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-105">You would use this tool when the Skype Room Systems v2 console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="f2b3a-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b3a-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="f2b3a-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f2b3a-107">Prerequisites</span></span>

<span data-ttu-id="f2b3a-108">Baixe o mais recente [pacote de instalação do Skype sala sistemas v2](https://go.microsoft.com/fwlink/?linkid=851168) e extraia-o para um USB memória pente ou compartilhamento de rede acessível ao dispositivo v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-108">Download the latest [Skype Room Systems v2 installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Skype Room Systems v2 device.</span></span>

<span data-ttu-id="f2b3a-109">Você também pode precisar instalar [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="f2b3a-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="f2b3a-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b3a-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="f2b3a-111">Verifique se a versão do Windows</span><span class="sxs-lookup"><span data-stu-id="f2b3a-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="f2b3a-112">Login com uma conta de administrador indo para **Configurações > Configuração do Windows > Admin entrar** do dispositivo v2 Skype sistemas de sala.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Skype Room Systems v2 device.</span></span> <span data-ttu-id="f2b3a-113">Essa opção leva a tela de login.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="f2b3a-114">Conta de entrada em uma conta de administrador, o administrador padrão que está sendo `admin` com a senha `sfb`.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="f2b3a-115">Clique no menu Iniciar e digite `winver.exe` na caixa Pesquisar e clique em \**Comando executar* no resultado.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="f2b3a-116">Anote o número após 'Versão' na segunda linha do painel informações.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="f2b3a-117">Se a versão mostrada for 1607 ou anterior, siga as etapas nas etapas <a href="#Windows-up">Windows Update antes de recuperação</a> antes de proceding para as etapas de <a href="#Perform">executar uma recuperação</a> .</span><span class="sxs-lookup"><span data-stu-id="f2b3a-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="f2b3a-118">Se a versão mostrada for maior que 1607, siga somente as etapas em <a href="#Perform">Perform uma recuperação</a>.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="f2b3a-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b3a-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="f2b3a-120">Atualizar o Windows antes de recuperação (se necessário)</span><span class="sxs-lookup"><span data-stu-id="f2b3a-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="f2b3a-121">Enquanto ainda logado como um usuário admin, inicie um prompt elevado do Powershell.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="f2b3a-122">Execute o comando `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="f2b3a-123">Execute o Windows Update e instalar a atualização para Windows 1709.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="f2b3a-124">Após a atualização para 1709 está entrada completa que voltou ao conta de administrador e instala [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span><span class="sxs-lookup"><span data-stu-id="f2b3a-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="f2b3a-125">A atualização pode ser feita no link ou usando o Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="f2b3a-126">Como uma etapa opcional, instale quaisquer atualizações adicionais disponíveis do Windows Update.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="f2b3a-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b3a-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="f2b3a-128">Executar uma recuperação</span><span class="sxs-lookup"><span data-stu-id="f2b3a-128">Perform a recovery</span></span>

1. <span data-ttu-id="f2b3a-129">Entrar com a conta de administrador no seu dispositivo de v2 Skype sistemas de sala e inicie um prompt de comando elevado.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-129">Sign in to the admin account on your Skype Room Systems v2 device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="f2b3a-130">Verifique se o Skype sala v2 dispositivos de sistemas que você seja capaz de acessar o `RecoveryTool.ps1` arquivo, que está incluído nos arquivos extraídos do pacote de instalação do Skype sala sistemas v2.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-130">Verify from the Skype Room Systems v2 device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Skype Room Systems v2 installation package.</span></span> <span data-ttu-id="f2b3a-131">O kit pode ser encontrado no compartilhamento de rede ou unidade USB usado durante a preparação de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="f2b3a-132">Execute o comando Powershell.exe `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="f2b3a-133">Quando solicitado, selecione a opção o script `1:"Repair System"`.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="f2b3a-134">Após a conclusão, reinicialize o dispositivo de v2 de sistemas de sala Skype.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-134">Upon completion, reboot the Skype Room Systems v2 device.</span></span> <span data-ttu-id="f2b3a-135">Ela será reinicializar novamente automaticamente e surgirem recuperada totalmente a segunda vez.</span><span class="sxs-lookup"><span data-stu-id="f2b3a-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="f2b3a-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="f2b3a-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="f2b3a-137">Ver também</span><span class="sxs-lookup"><span data-stu-id="f2b3a-137">See also</span></span>


#### 
[<span data-ttu-id="f2b3a-138">Ajuda da versão 2 de sistemas de sala do Skype</span><span class="sxs-lookup"><span data-stu-id="f2b3a-138">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="f2b3a-139">Gerenciar Skype sala v2 de sistemas</span><span class="sxs-lookup"><span data-stu-id="f2b3a-139">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
