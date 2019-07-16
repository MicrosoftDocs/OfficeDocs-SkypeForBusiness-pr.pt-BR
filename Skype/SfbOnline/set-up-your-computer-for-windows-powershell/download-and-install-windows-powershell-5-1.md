---
title: Baixar e instalar o Windows PowerShell 5,1
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Baixe, instale e use o Windows PowerShell 5,1 para criar uma sessão remota do PowerShell que se conecta ao Skype for Business online.
ms.openlocfilehash: 5afca0ef1fd5d7437c3974de1424a664c99ab1a1
ms.sourcegitcommit: 9c54fd0a51ece8624155dc543d5df922834aa51e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/16/2019
ms.locfileid: "35701547"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="15c4c-103">Baixar e instalar o Windows PowerShell 5,1</span><span class="sxs-lookup"><span data-stu-id="15c4c-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="15c4c-104">Se estiver usando a atualização de aniversário do Windows 10 ou o Windows Server 2016, você já deve ter o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="15c4c-105">Isso porque este aplicativo vem pré-instalado com esses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="15c4c-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="15c4c-106">Para determinar qual versão do Microsoft PowerShell você está usando, faça o seguinte no seu computador com Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="15c4c-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="15c4c-107">Clique em **Iniciar**, **em todos os programas**, em **acessórios**, em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="15c4c-108">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="15c4c-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="15c4c-109">Informações semelhantes às seguintes devem ser exibidas na janela do console:</span><span class="sxs-lookup"><span data-stu-id="15c4c-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="15c4c-110">Se o número de versão retornado for 5,1, então você está executando o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="15c4c-111">Se o número de versão retornado não for 5,1, você precisará instalar o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="15c4c-112">Você pode baixar o Windows Management Framework 5,1, que inclui o Windows PowerShell 5,1, a partir do [centro de download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="15c4c-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="15c4c-113">Depois de verificar se o Windows PowerShell 5,1 está instalado, você deve certificar-se de que o PowerShell foi configurado para executar scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="15c4c-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="15c4c-114">Para fazer isso, inicie o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="15c4c-115">No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="15c4c-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="15c4c-116">Clique em **Iniciar**, em **todos os programas**, em **acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="15c4c-117">Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="15c4c-118">Se você estiver executando o Windows 8, siga este procedimento em vez disso:</span><span class="sxs-lookup"><span data-stu-id="15c4c-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="15c4c-119">Acesse a barra de botões, clique em **Pesquisar**e, em seguida, clique com o botão direito do mouse no **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="15c4c-120">Você pode acessar rapidamente a barra de botões em qualquer computador com o Windows 8 (tela sensível ao toque ou tela não sensível ao toque), mantendo pressionada a tecla Windows e pressionando C.</span><span class="sxs-lookup"><span data-stu-id="15c4c-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="15c4c-121">Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="15c4c-122">Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="15c4c-123">Após a execução do PowerShell, você deve alterar a política de execução para permitir a execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="15c4c-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="15c4c-124">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="15c4c-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="15c4c-125">Ao executar o comando anterior, você pode receber a seguinte mensagem de erro: > *set\\-ExecutionPolicy: acesso ao key'HKEY_LOCAL_MACHINE do registro do\\software\\Microsoft\\PowerShell\\1 ShellIds\\Micrsoft. PowerShell ' negado.*</span><span class="sxs-lookup"><span data-stu-id="15c4c-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="15c4c-126">Essa mensagem de erro geralmente ocorre se você não estiver executando o PowerShell em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="15c4c-127">Feche a sessão do PowerShell e inicie uma nova sessão como administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="15c4c-128">Para verificar se a política de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="15c4c-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="15c4c-129">Se você receber o seguinte valor, então tudo foi configurado corretamente:</span><span class="sxs-lookup"><span data-stu-id="15c4c-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="15c4c-130">Se você não estiver atualmente executando o Windows PowerShell 5,1, também precisará baixar e instalar o Windows Management Framework 5,1 do centro de download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="15c4c-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="15c4c-131">Este é um pacote de instalação que inclui o Windows PowerShell 5,1 e o gerenciamento remoto do Windows (WinRM) 3,0.</span><span class="sxs-lookup"><span data-stu-id="15c4c-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="15c4c-132">Este pacote de instalação pode ser necessário se você, por exemplo, estiver executando o Windows 7 SP1 e ainda não tiver sido atualizado para o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="15c4c-133">Se você estiver executando o Windows Server 2016 ou a atualização de aniversário do Windows 10, não será necessário instalar o Windows PowerShell 5,1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="15c4c-134">O Windows PowerShell 5,1 vem pré-instalado nesses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="15c4c-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="15c4c-135">Antes de instalar o Windows Management Framework 5,1:</span><span class="sxs-lookup"><span data-stu-id="15c4c-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="15c4c-136">Verifique se você fez o download da versão correta do pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="15c4c-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="15c4c-137">Se você estiver executando a versão de 64 bits do Windows 7 SP1, baixe o arquivo Win7AndW2K8R2-KB3191566-x64. ZIP.</span><span class="sxs-lookup"><span data-stu-id="15c4c-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="15c4c-138">Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Win7-KB3191566-x86. ZIP.</span><span class="sxs-lookup"><span data-stu-id="15c4c-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="15c4c-139">Se você estiver executando o Windows 7 em seu computador, verifique se instalou o Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="15c4c-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="15c4c-140">Se não tiver certeza de qual versão do Windows você está executando ou se não tiver certeza de que instalou o Windows 7 Service Pack 1, clique em **Iniciar**, clique com o botão direito do mouse em **computador**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="15c4c-141">Essas informações serão informadas na caixa de diálogo sistema.</span><span class="sxs-lookup"><span data-stu-id="15c4c-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="15c4c-142">Para instalar o Windows Management Framework 5,1, conclua o procedimento em [instalar e configurar o WMF 5,1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="15c4c-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="15c4c-143">Após a reinicialização do computador, verifique se o Windows PowerShell pode iniciar e se o aplicativo pode ser executado em credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="15c4c-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="15c4c-144">Para fazer isto:</span><span class="sxs-lookup"><span data-stu-id="15c4c-144">To do this:</span></span>
  
1. <span data-ttu-id="15c4c-145">Clique em **Iniciar**, em **todos os programas**, em **acessórios**, clique em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="15c4c-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="15c4c-146">Se a caixa de diálogo controle de conta de usuário for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="15c4c-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="15c4c-147">Quando o console do PowerShell for exibido, verifique se o serviço WinRM está em execução e configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="15c4c-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="15c4c-148">Para verificar se o serviço está em execução, digite o seguinte comando no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="15c4c-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="15c4c-149">As informações sobre o serviço WinRM serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="15c4c-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="15c4c-150">Se o status do serviço não for igual a "Running", inicie o serviço WinRM digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="15c4c-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="15c4c-151">Após o início do serviço, execute o seguinte comando para ter certeza de que o WinRM está usando a autenticação básica:</span><span class="sxs-lookup"><span data-stu-id="15c4c-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="15c4c-152">Informações semelhantes às seguintes serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="15c4c-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="15c4c-153">Se a autenticação básica tiver sido definida como true, você estará pronto para usar o PowerShell para se conectar ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="15c4c-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="15c4c-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="15c4c-154">Related topics</span></span>
[<span data-ttu-id="15c4c-155">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15c4c-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
