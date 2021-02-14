---
title: Baixar e instalar o módulo Conector do Skype for Business Online
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
description: Baixe, instale e use o Skype for Business Online Connector para criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814560"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="2f492-103">Baixar e instalar o módulo Conector do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="2f492-103">Download and install the Skype for Business Online Connector module</span></span>

> [!NOTE]
> <span data-ttu-id="2f492-104">A versão [pública mais recente do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.</span><span class="sxs-lookup"><span data-stu-id="2f492-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="2f492-105">O módulo Conector do Skype for Business Online inclui o cmdlet **New-CsOnlineSession,** que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="2f492-105">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="2f492-106">Este módulo, que tem suporte apenas em computadores de 64 bits (consulte Configurar seu computador para gerenciamento do Skype for Business Online usando [o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações), pode ser baixado do Centro de Download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) .</span><span class="sxs-lookup"><span data-stu-id="2f492-106">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="2f492-107">Baixe o SkypeOnlinePowershell.exe arquivo e, em seguida, conclua o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="2f492-107">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="2f492-108">Clique duas vezes no **SkypeOnlinePowershell.exe** arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f492-108">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="2f492-109">No Skype for Business Online, assistente de configuração do Windows PowerShell, na página Termos de Licença de Software da **Microsoft,** selecione Aceitar os termos no Contrato de Licença e **clique** em **Instalar.**</span><span class="sxs-lookup"><span data-stu-id="2f492-109">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="2f492-110">Se a **caixa de diálogo Controle** de Conta de Usuário for exibida, clique em **Sim** para continuar a instalação.</span><span class="sxs-lookup"><span data-stu-id="2f492-110">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="2f492-111">Na página **Concluído do Skype for Business Online, módulo do Windows PowerShell,** clique em **Concluir.**</span><span class="sxs-lookup"><span data-stu-id="2f492-111">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="2f492-112">O programa de configuração copia o módulo Skype for Business Online Connector (e o cmdlet **New-CsOnlineSession)** para seu computador.</span><span class="sxs-lookup"><span data-stu-id="2f492-112">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="2f492-113">Para acessar o módulo, inicie uma sessão do Windows PowerShell com as credenciais de administrador e execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="2f492-113">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="2f492-114">Se você não quiser digitar esse comando sempre que iniciar o Windows PowerShell, poderá adicionar o comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f492-114">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="2f492-115">Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="2f492-115">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
notepad.exe $profile
```

 <span data-ttu-id="2f492-116">Quando o Bloco de Notas for exibido, adicione a seguinte linha na parte inferior dos comandos que já estão no perfil (se for o caso):</span><span class="sxs-lookup"><span data-stu-id="2f492-116">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```PowerShell
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="2f492-117">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="2f492-117">Save the file.</span></span> <span data-ttu-id="2f492-118">Na próxima vez que você iniciar o Windows PowerShell, o módulo Conector do Skype for Business Online será importado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2f492-118">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="2f492-119">Esteja ciente de que você receberá uma mensagem de erro e o módulo não será carregado se você não estiver executando o Windows PowerShell sob credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="2f492-119">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="2f492-120">Além de instalar o módulo Conector do Skype for Business Online, o SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a IDCRL (Identity Service Client Runtime Library), usada para lidar com a autenticação do cliente para o Skype for Business Online; 2) .NET Framework 4.5; e, 3) o pacote Microsoft Visual C++ 2012 Redistribuível (x64) (versão 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="2f492-120">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="2f492-121">O .NET Framework 4.5 fornece a infraestrutura usada para criar e executar aplicativos .NET, incluindo o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f492-121">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="2f492-122">O pacote Visual C++ Redistribuível instala componentes de tempo de execução do Visual C++ para computadores que não têm o Microsoft Visual Studio 2012 instalado.</span><span class="sxs-lookup"><span data-stu-id="2f492-122">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="2f492-123">Para verificar o número da versão do módulo Conector que está instalado no seu computador, abra o Painel de Controle, abra Programas e Recursos e verifique o número da versão do Skype for Business Online, módulo do **Windows PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="2f492-123">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2f492-124">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2f492-124">Related topics</span></span>
[<span data-ttu-id="2f492-125">Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f492-125">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
