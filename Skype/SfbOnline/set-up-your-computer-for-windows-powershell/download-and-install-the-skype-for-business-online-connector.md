---
title: Baixar e instalar o módulo do conector do Skype for Business Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 'Baixe, instale e use o conector Skype for Business online para criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online. '
ms.openlocfilehash: 8c5068c221c46f7be0d9d97c1c3d515ae244b316
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085697"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="20ec7-103">Baixar e instalar o módulo do conector do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="20ec7-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="20ec7-104">A versão mais recente do [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada ao conector do Skype for Business Online, fornecendo um único módulo para gerenciamento do teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ec7-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="20ec7-105">O módulo conector do Skype for Business Online inclui o cmdlet **New-CsOnlineSession** , que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="20ec7-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="20ec7-106">Este módulo, que tem suporte apenas em computadores de 64 bits (consulte [configurar seu computador para gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações) pode ser baixado no centro de download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="20ec7-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="20ec7-107">Baixe o arquivo SkypeOnlinePowershell.exe e, em seguida, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="20ec7-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="20ec7-108">Clique duas vezes no arquivo **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="20ec7-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="20ec7-109">No Skype for Business Online, assistente de configuração do Windows PowerShell, na página **termos de licença para software da Microsoft** , selecione **aceito os termos do contrato de licença**e clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="20ec7-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="20ec7-110">Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para continuar a instalação.</span><span class="sxs-lookup"><span data-stu-id="20ec7-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="20ec7-111">Na página **completada do Skype for Business Online, do módulo do Windows PowerShell** , clique em **concluir**.</span><span class="sxs-lookup"><span data-stu-id="20ec7-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="20ec7-112">O programa de instalação copia o módulo do conector do Skype for Business online (e o cmdlet **New-CsOnlineSession** ) para o seu computador.</span><span class="sxs-lookup"><span data-stu-id="20ec7-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="20ec7-113">Para acessar o módulo, inicie uma sessão do Windows PowerShell em credenciais do administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="20ec7-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="20ec7-114">Se você não quiser digitar esse comando toda vez que iniciar o Windows PowerShell, poderá adicionar o comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ec7-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="20ec7-115">Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="20ec7-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="20ec7-116">Quando o bloco de notas for exibido, adicione a seguinte linha na parte inferior dos comandos que já estão no perfil (se houver):</span><span class="sxs-lookup"><span data-stu-id="20ec7-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="20ec7-117">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="20ec7-117">Save the file.</span></span> <span data-ttu-id="20ec7-118">Da próxima vez que você iniciar o Windows PowerShell, o módulo do conector do Skype for Business online será importado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="20ec7-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="20ec7-119">Lembre-se de que você receberá uma mensagem de erro, e o módulo não será carregado, se você não estiver executando o Windows PowerShell em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="20ec7-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="20ec7-120">Além de instalar o módulo do conector Skype for Business Online, SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a IDCRL (biblioteca de tempo de execução do serviço de identidade), usada para manipular a autenticação do cliente para o Skype for Business Online; 2) .NET Framework 4,5; e 3) o pacote Microsoft Visual C++ 2012 Redistributable (x64) (versão 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="20ec7-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="20ec7-121">O .NET Framework 4,5 fornece a infraestrutura usada para compilar e executar aplicativos .NET, incluindo o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="20ec7-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="20ec7-122">O pacote redistribuível do Visual C++ instala componentes de tempo de execução do Visual C++ para computadores que não têm o Microsoft Visual Studio 2012 instalado.</span><span class="sxs-lookup"><span data-stu-id="20ec7-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="20ec7-123">Para verificar o número da versão do módulo conector que está instalado no seu computador, abra o painel de controle, abra **programas e recursos**e verifique o número da versão do **módulo do Windows PowerShell para o Skype for Business online**.</span><span class="sxs-lookup"><span data-stu-id="20ec7-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="20ec7-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="20ec7-124">Related topics</span></span>
[<span data-ttu-id="20ec7-125">Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="20ec7-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
