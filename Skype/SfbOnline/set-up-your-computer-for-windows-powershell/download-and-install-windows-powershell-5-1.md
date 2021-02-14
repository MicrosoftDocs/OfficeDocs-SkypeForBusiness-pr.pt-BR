---
title: Baixar e instalar o Windows PowerShell 5.1
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
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Baixar, instalar e usar o Windows PowerShell 5.1 para criar uma sessão remota do PowerShell que se conecta ao Skype for Business online.
ms.openlocfilehash: 64d1ed1b3e3031f5186a09289ab6e1d9088840cf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029092"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="149b1-103">Baixar e instalar o Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="149b1-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="149b1-104">Caso esteja usando a Atualização de Aniversário do Windows 10 ou o Windows Server 2016, você já deve ter o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="149b1-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="149b1-105">Esse aplicativo vem pré-instalado com esses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="149b1-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="149b1-106">Para determinar a versão do Microsoft PowerShell em uso, faça o seguinte em seu computador com o Windows 7, o Windows Server 2008 R2 ou o Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="149b1-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="149b1-107">Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell** e em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="149b1-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="149b1-108">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="149b1-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="149b1-109">Informações semelhantes às seguintes devem então ser exibidas na janela do console:</span><span class="sxs-lookup"><span data-stu-id="149b1-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="149b1-110">Se o número de versão retornado for 5.1, o Windows PowerShell 5.1 está em execução.</span><span class="sxs-lookup"><span data-stu-id="149b1-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="149b1-111">Se o número de versão retornado não for 5.1, será necessário instalar o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="149b1-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="149b1-112">Você pode baixar o Windows Management Framework 5.1, que inclui o Windows PowerShell 5.1, no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="149b1-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="149b1-113">Depois de verificar se o Windows PowerShell 5.1 está instalado, verifique se o PowerShell foi configurado para executar scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="149b1-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="149b1-114">Para isso, inicie o Windows PowerShell como um administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="149b1-115">No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou no Windows Server 2012 R2, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="149b1-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="149b1-116">Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="149b1-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="149b1-117">Se a caixa de diálogo **Controle da Conta de Usuário** for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="149b1-118">Se você estiver executando o Windows 8, conclua este procedimento:</span><span class="sxs-lookup"><span data-stu-id="149b1-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="149b1-119">Acesse a barra de Botões, clique em **Pesquisar** e, em seguida, clique com o botão direito do mouse em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="149b1-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="149b1-120">Você pode acessar rapidamente a barra Botões em qualquer computador com o Windows 8 (tela sensível ao toque ou não) ao manter a tecla do Windows pressionada e pressionando C.</span><span class="sxs-lookup"><span data-stu-id="149b1-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="149b1-121">Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="149b1-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="149b1-122">Se a caixa de diálogo **Controle da Conta de Usuário** for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="149b1-123">Depois que o PowerShell estiver em execução, você deverá alterar a política de execução para permitir a execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="149b1-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="149b1-124">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="149b1-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="149b1-125">Ao executar o comando anterior, você pode receber a seguinte mensagem de erro:> *Set-ExecutionPolicy: o acesso à chave do registro'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' foi negado.*</span><span class="sxs-lookup"><span data-stu-id="149b1-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="149b1-126">Esta mensagem de erro normalmente ocorrerá se você não estiver executado o PowerShell sob credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="149b1-127">Feche sua sessão do PowerShell e inicie uma nova sessão como um administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="149b1-128">Para verificar se a política de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="149b1-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-ExecutionPolicy
```

<span data-ttu-id="149b1-129">Se você obtiver o valor a seguir, tudo estará configurado corretamente:</span><span class="sxs-lookup"><span data-stu-id="149b1-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="149b1-130">Se o Windows PowerShell 5.1 não estiver em execução no momento, você também precisará baixar e instalar o Windows Management Framework 5.1 no Centro de Download da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="149b1-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="149b1-131">Este é um pacote de instalação que inclui o Windows PowerShell 5.1 e o Gerenciamento Remoto do Windows (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="149b1-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="149b1-132">Este pacote de instalação pode ser necessário caso você esteja executando, por exemplo, o Windows 7 SP1 e ainda não tenha atualizado para o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="149b1-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="149b1-133">Se você estiver executando o Windows Server 2016 ou a Atualização de Aniversário do Windows 10, não deve ser necessário instalar o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="149b1-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="149b1-134">O Windows PowerShell 5.1 vem pré-instalado nestes sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="149b1-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="149b1-135">Antes de instalar o Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="149b1-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="149b1-136">Verifique se baixou a versão correta do pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="149b1-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="149b1-137">Se você estiver executando a versão de 64 bits do Windows 7 SP1, baixe o arquivo Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="149b1-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="149b1-138">Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="149b1-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="149b1-139">Se você estiver executando o Windows 7 em seu computador, verifique se instalou o Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="149b1-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="149b1-140">Se não tiver certeza sobre qual versão do Windows está em execução ou se o Windows 7 Service Pack 1 está instalado, clique em **Iniciar**, clique com o botão direito do mouse em **Computador** e clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="149b1-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="149b1-141">Essas informações são relatadas na caixa de diálogo Sistema.</span><span class="sxs-lookup"><span data-stu-id="149b1-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="149b1-142">Para instalar o Windows Management Framework 5.1, conclua o procedimento em [Instalar e configurar o WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span><span class="sxs-lookup"><span data-stu-id="149b1-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/powershell/scripting/wmf/setup/install-configure).</span></span>
  
<span data-ttu-id="149b1-143">Após a reinicialização do computador, verifique se é possível iniciar o Windows PowerShell e se o aplicativo pode ser executado sob credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="149b1-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="149b1-144">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="149b1-144">To do this:</span></span>
  
1. <span data-ttu-id="149b1-145">Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="149b1-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="149b1-146">Se a caixa de diálogo Controle da Conta de Usuário for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="149b1-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="149b1-147">Quando o console do PowerShell for exibido, verifique se o serviço WinRM está em execução e se foi configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="149b1-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="149b1-148">Para verificar se o serviço está em execução, digite o comando a seguir no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="149b1-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```PowerShell
Get-Service winrm
```

<span data-ttu-id="149b1-149">As informações sobre o serviço WinRM serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="149b1-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="149b1-150">Se o Status do serviço não for "Em execução", inicie o serviço WinRM digitando o comando a seguir e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="149b1-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```PowerShell
Start-Service winrm
```

<span data-ttu-id="149b1-151">Depois que o serviço iniciar, execute o comando a seguir para garantir que o WinRM esteja usando a autenticação Básica:</span><span class="sxs-lookup"><span data-stu-id="149b1-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="149b1-152">Informações semelhantes às seguintes deverão ser exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="149b1-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="149b1-153">Se a autenticação básica for definida como verdadeira, então você está pronto para usar o PowerShell para se conectar ao Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="149b1-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="149b1-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="149b1-154">Related topics</span></span>
[<span data-ttu-id="149b1-155">Configurar o computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="149b1-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
