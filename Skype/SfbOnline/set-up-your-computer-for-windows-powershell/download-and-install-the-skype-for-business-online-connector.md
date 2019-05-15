---
title: Baixe e instale o Skype para módulo Business Connector Online
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 'Baixar, instalar e usar o Skype para o Business Connector Online para criar uma sessão remota do Windows PowerShell que se conecta ao Skype para negócios Online. '
ms.openlocfilehash: a93cf1d3d09910001f25619969b6d504e23ec36f
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34036688"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a><span data-ttu-id="79ed9-103">Baixe e instale o Skype para módulo Business Connector Online</span><span class="sxs-lookup"><span data-stu-id="79ed9-103">Download and install the Skype for Business Online Connector module</span></span>

<span data-ttu-id="79ed9-104">O Skype para módulo Business Connector Online inclui o cmdlet **New-CsOnlineSession** , que permite a criação de uma sessão remota do Windows PowerShell que se conecta ao Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="79ed9-104">The Skype for Business Online Connector module includes the **New-CsOnlineSession** cmdlet, which enables you to create a remote Windows PowerShell session that connects to Skype for Business Online.</span></span> <span data-ttu-id="79ed9-105">Neste módulo, o que é suportado apenas em computadores de 64 bits (consulte [configurar seu computador e Skype para gerenciamento de negócios Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações), podem ser baixados do Microsoft Download Center em [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span><span class="sxs-lookup"><span data-stu-id="79ed9-105">This module, which is supported only on 64-bit computers (see [Set up your computer for Skype for Business Online management using Windows PowerShell](set-up-your-computer-for-windows-powershell.md) for more information), can be downloaded from the Microsoft Download Center at [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366).</span></span> <span data-ttu-id="79ed9-106">Baixe o arquivo SkypeOnlinePowershell.exe e conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="79ed9-106">Download the SkypeOnlinePowershell.exe file, and then complete the following procedure:</span></span>
  
1. <span data-ttu-id="79ed9-107">Duas vezes no arquivo de **SkypeOnlinePowershell.exe** .</span><span class="sxs-lookup"><span data-stu-id="79ed9-107">Double-click the **SkypeOnlinePowershell.exe** file.</span></span>
    
2. <span data-ttu-id="79ed9-108">No Skype para Business Online, o Assistente de instalação do Windows PowerShell, na página **Termos de licença para Software Microsoft** , selecione **eu aceito os termos do contrato de licença**e, em seguida, clique em **instalar**.</span><span class="sxs-lookup"><span data-stu-id="79ed9-108">In the Skype for Business Online, Windows PowerShell setup wizard, on the **Microsoft Software License Terms** page, select **I accept the terms in the License Agreement**, and then click **Install**.</span></span> <span data-ttu-id="79ed9-109">Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para continuar a instalação.</span><span class="sxs-lookup"><span data-stu-id="79ed9-109">If the **User Account Control** dialog box appears, click **Yes** to continue the installation.</span></span>
    
3. <span data-ttu-id="79ed9-110">Na página **concluído o Skype para negócios Online, o módulo do Windows PowerShell** , clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="79ed9-110">On the **Completed the Skype for Business Online, Windows PowerShell Module** page, click **Finish**.</span></span>
    
<span data-ttu-id="79ed9-111">O programa de instalação copia o Skype para módulo Business Connector Online (e o cmdlet **New-CsOnlineSession** ) ao seu computador.</span><span class="sxs-lookup"><span data-stu-id="79ed9-111">The setup program copies the Skype for Business Online Connector module (and the **New-CsOnlineSession** cmdlet) to your computer.</span></span> <span data-ttu-id="79ed9-112">Para acessar o módulo, iniciar uma sessão do Windows PowerShell sob as credenciais de administrador e, em seguida, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="79ed9-112">To access the module, start a Windows PowerShell session under administrator credentials, and then run the following command:</span></span>
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

<span data-ttu-id="79ed9-113">Se você não quiser digitar esse comando sempre que você iniciar o Windows PowerShell, você pode adicionar o comando ao seu perfil do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ed9-113">If you don't want to type this command every time you start Windows PowerShell, you can add the command to your Windows PowerShell profile.</span></span> <span data-ttu-id="79ed9-114">Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="79ed9-114">To do that, type the following command at the Windows PowerShell prompt and then press ENTER:</span></span>
  
```
notepad.exe $profile
```

 <span data-ttu-id="79ed9-115">Quando o bloco de notas for exibida, adicione a seguinte linha ao final dos comandos que já estão no perfil (se houver):</span><span class="sxs-lookup"><span data-stu-id="79ed9-115">When Notepad appears, add the following line to the bottom of the commands that are already in the profile (if any):</span></span>
  
```
Import-Module SkypeOnlineConnector
```

<span data-ttu-id="79ed9-116">Salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="79ed9-116">Save the file.</span></span> <span data-ttu-id="79ed9-117">Na próxima vez que você inicia o Windows PowerShell, o Skype para módulo Business Connector Online será importado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="79ed9-117">The next time you start Windows PowerShell, the Skype for Business Online Connector module will automatically be imported.</span></span> <span data-ttu-id="79ed9-118">Esteja ciente de que você receberá uma mensagem de erro e o módulo não será carregado, se você não estiver executando o Windows PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="79ed9-118">Be aware that you will get an error message, and the module will not be loaded, if you are not running Windows PowerShell under administrator credentials.</span></span>
  
<span data-ttu-id="79ed9-119">Além de instalar o Skype para módulo Business Connector Online, SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a identidade serviço cliente Runtime biblioteca (IDCRL), usado para lidar com a autenticação de cliente para Skype para negócios Online; 2) o .NET framework 4.5; e, 3) o pacote Microsoft Visual C++ 2012 redistribuível (x64) (versão 11.0.50727).</span><span class="sxs-lookup"><span data-stu-id="79ed9-119">In addition to installing the Skype for Business Online Connector module, SkypeOnlinePowershell.exe also installs three additional components: 1) the Identity Service Client Runtime Library (IDCRL), used to handle client authentication to Skype for Business Online; 2) .NET Framework 4.5; and, 3) the Microsoft Visual C++ 2012 Redistributable (x64) package (version 11.0.50727).</span></span> <span data-ttu-id="79ed9-120">.NET framework 4.5 fornece a infraestrutura usada para a criação e execução de aplicativos do .NET, incluindo o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="79ed9-120">.NET Framework 4.5 provides the infrastructure used for building and running .NET applications, including Windows PowerShell.</span></span> <span data-ttu-id="79ed9-121">O pacote redistribuível do Visual C++ instala os componentes de tempo de execução do Visual C++ para computadores que não possuem o Microsoft Visual Studio 2012 instalado.</span><span class="sxs-lookup"><span data-stu-id="79ed9-121">The Visual C++ Redistributable package installs Visual C++ runtime components for computers that do not have Microsoft Visual Studio 2012 installed.</span></span>
  
<span data-ttu-id="79ed9-122">Para verificar o número da versão do módulo conector que está instalado atualmente no seu computador, abra o painel de controle, abra **programas e recursos**e verifique o número de versão para o **Skype para negócios Online, o módulo do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="79ed9-122">To verify the version number of the Connector module that is currently installed on your computer, open Control Panel, open **Programs and Features**, and then check the version number for the **Skype for Business Online, Windows PowerShell Module**.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="79ed9-123">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="79ed9-123">Related topics</span></span>
[<span data-ttu-id="79ed9-124">Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="79ed9-124">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
