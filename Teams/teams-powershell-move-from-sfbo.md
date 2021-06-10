---
title: Migrando do Skype for Business Online para o módulo Teams PowerShell
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: Saiba como mover do conector Skype for Business Online para o módulo Teams PowerShell para gerenciar Teams.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b08505ca97672d5285c8ff46b0e5d3cf58e9f84
ms.sourcegitcommit: 56bebf42f545af57fdf387faa90e555abc8acd40
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "52513864"
---
# <a name="migrating-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="8d0dc-103">Migrando do Skype for Business Online para o módulo Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0dc-103">Migrating from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="8d0dc-104">Teams O Módulo do PowerShell fornece um conjunto completo de cmdlets para gerenciar Teams diretamente da linha de comando do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-104">Teams PowerShell Module provides a complete set of cmdlets for managing Teams directly from the PowerShell command line.</span></span> <span data-ttu-id="8d0dc-105">Os administradores não exigem Skype conector para Empresas Online para sua Teams administração.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-105">Administrators do not require Skype For Business Online Connector for their Teams administration.</span></span>

> [!NOTE]
> <span data-ttu-id="8d0dc-106">Teams administrador foi notificado por meio da postagem da Central de Mensagens (MC244740, datada de 16 de março de 2021; MC250940, datado de 16 de abril de 2021) sobre essa alteração.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-106">Teams administrator were notified through Message center post (MC244740, dated March 16, 2021; MC250940, dated April 16 2021) about this change.</span></span>
>
> <span data-ttu-id="8d0dc-107">Teams O Módulo do PowerShell usa autenticação moderna, mas o cliente Windows Gerenciamento Remoto (WinRM) subjacente deve ser configurado para permitir a autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-107">Teams PowerShell Module uses modern authentication, but the underlying Windows Remote Management (WinRM) client must be configured to allow Basic authentication.</span></span> <span data-ttu-id="8d0dc-108">Consulte [Baixar e instalar Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) para obter instruções sobre como habilitar o WinRM para autenticação básica.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-108">See [Download and install Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) for instructions on how to enable WinRM for Basic authentication.</span></span>

> [!WARNING]
> <span data-ttu-id="8d0dc-109">Skype for Business As conexões do Conector Online serão rejeitadas a partir de 17 de maio de 2021.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-109">Skype for Business Online Connector connections will be rejected starting May 17, 2021.</span></span> <span data-ttu-id="8d0dc-110">Entre em contato com o Suporte da Microsoft para ter ajuda e suporte para migrar para Teams Módulo do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-110">Please contact Microsoft Support for help and support for migrating to Teams PowerShell Module.</span></span>

## <a name="how-to-migrate"></a><span data-ttu-id="8d0dc-111">Como migrar</span><span class="sxs-lookup"><span data-stu-id="8d0dc-111">How to Migrate</span></span>

<span data-ttu-id="8d0dc-112">Migrar do uso do Skype for Business Online para Teams módulo do PowerShell é fácil e simples.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-112">Migrating from using Skype for Business Online Connector to Teams PowerShell module is easy and simple.</span></span> <span data-ttu-id="8d0dc-113">As etapas a seguir explicam como fazer isso.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-113">The below steps explains how to do this.</span></span>

1. <span data-ttu-id="8d0dc-114">Instale o módulo Teams do PowerShell mais recente.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-114">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="8d0dc-115">Para ver etapas, [consulte Install Microsoft Teams PowerShell](teams-powershell-install.md).</span><span class="sxs-lookup"><span data-stu-id="8d0dc-115">For steps, see [Install Microsoft Teams PowerShell](teams-powershell-install.md).</span></span>

2. <span data-ttu-id="8d0dc-116">Desinstale Skype conector para Empresas Online.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-116">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="8d0dc-117">Para fazer isso, no Painel de Controle, vá para Programas e **Recursos,** selecione **Skype for Business Online, Windows PowerShell Módulo** e selecione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-117">To do this, in Control Panel, go to **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span>

3. <span data-ttu-id="8d0dc-118">Em seus scripts do PowerShell, altere o nome do módulo referenciado ```Import-Module``` de</span><span class="sxs-lookup"><span data-stu-id="8d0dc-118">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from</span></span>

    <span data-ttu-id="8d0dc-119">`SkypeOnlineConnector` ou `LyncOnlineConnector` `MicrosoftTeams` para .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-119">`SkypeOnlineConnector` or `LyncOnlineConnector` to `MicrosoftTeams`.</span></span>

    <span data-ttu-id="8d0dc-120">Por exemplo, altere `Import-Module -Name SkypeOnlineConnector` para `Import-Module -Name MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-120">For example, change `Import-Module -Name SkypeOnlineConnector` to `Import-Module -Name MicrosoftTeams`.</span></span>

4. <span data-ttu-id="8d0dc-121">Ao usar Teams Módulo 2.0 do PowerShell ou posterior, atualize seus scripts que se referem `New-CsOnlineSession` a `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-121">When using Teams PowerShell Module 2.0 or later, update your scripts that refers `New-CsOnlineSession` to `Connect-MicrosoftTeams`.</span></span> <span data-ttu-id="8d0dc-122">`Import-PsSession`não é mais necessário estabelecer uma sessão do PowerShell remoto Skype for Business Online, como é feito implícito ao usar `Connect-MicrosoftTeams` .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-122">`Import-PsSession` is no longer required to establish a Skype for Business Online Remote PowerShell Session as that is done implicit when using `Connect-MicrosoftTeams`.</span></span>

    ```powershell
       # When using the Skype for Business online connector
         
         # Establishing a session
         Import-Module SkypeOnlineConnector [LyncOnlineConnector]
         $credential = Get-Credential
         $SkypeSession = New-CsOnlineSession -Credential $credential
         Import-Session $SkypeSession
    
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session 
         Get-PsSession $SkypeSession | Remove-PsSession
    
       # When using Teams PowerShell Module 2.0 or later
       
         # Establishing a session
         Import-Module MicrosoftTeams
         $credential = Get-Credential
         Connect-MicrosoftTeams -Credential $credential
       
         # Example getting tenant details
         Get-csTenant
         
         # Disconnecting and closing the Session  
         Disconnect-MicrosoftTeams
    ```

## <a name="online-support"></a><span data-ttu-id="8d0dc-123">Suporte Online</span><span class="sxs-lookup"><span data-stu-id="8d0dc-123">Online Support</span></span>

<span data-ttu-id="8d0dc-124">Economize tempo iniciando sua solicitação de serviço online.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-124">Save time by starting your service request online.</span></span> <span data-ttu-id="8d0dc-125">Ajudaremos você a encontrar uma solução ou a conectá-lo ao suporte técnico.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-125">We'll help you find a solution or connect you to technical support.</span></span>

1.  <span data-ttu-id="8d0dc-126">Vá para o centro de administração em [https://admin.microsoft.com](https://admin.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="8d0dc-126">Go to the admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span> <span data-ttu-id="8d0dc-127">Se você receber uma mensagem que diga que não tem permissão para acessar esta página ou executar essa ação, então você não é um administrador. Who tem permissões de administrador na minha empresa?</span><span class="sxs-lookup"><span data-stu-id="8d0dc-127">If you get a message that says you don't have permission to access this page or perform this action, then you aren't an admin. Who has admin permissions in my business?</span></span>

2.  <span data-ttu-id="8d0dc-128">Selecione a **opção Precisa de ajuda?** button.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-128">Select the **Need help**? button.</span></span>

3.  <span data-ttu-id="8d0dc-129">Na Necessidade **de ajuda?** painel, diga-nos com o que você precisa de ajuda e pressione Enter.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-129">In the **Need help**? pane, tell us what you need help with, and then press Enter.</span></span>

4.  <span data-ttu-id="8d0dc-130">Se os resultados não ajudarem, selecione **Contatar suporte**.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-130">If the results don't help, select **Contact support**.</span></span>

5.  <span data-ttu-id="8d0dc-131">Insira uma descrição do seu problema, confirme seu número de contato e endereço de email, selecione seu método de contato preferencial e selecione **Contact me**.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-131">Enter a description of your issue, confirm your contact number and email address, select your preferred contact method, and then select **Contact me**.</span></span> <span data-ttu-id="8d0dc-132">O tempo de espera esperado é indicado no Need help? painel.</span><span class="sxs-lookup"><span data-stu-id="8d0dc-132">The expected wait time is indicated in the Need help? pane.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8d0dc-133">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="8d0dc-133">Related topics</span></span>

[<span data-ttu-id="8d0dc-134">Instalar Microsoft Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0dc-134">Install Microsoft Teams PowerShell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="8d0dc-135">Gerenciar Teams com Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0dc-135">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="8d0dc-136">Teams Notas de versão do PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d0dc-136">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="8d0dc-137">Microsoft Teams de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8d0dc-137">Microsoft Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)

[<span data-ttu-id="8d0dc-138">Skype for Business de cmdlet</span><span class="sxs-lookup"><span data-stu-id="8d0dc-138">Skype for Business cmdlet reference</span></span>](/powershell/skype/intro?view=skype-ps)
