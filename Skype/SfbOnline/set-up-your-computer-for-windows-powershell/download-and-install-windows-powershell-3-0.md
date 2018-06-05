---
title: Baixe e instale o Windows PowerShell 3.0
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Baixar, instalar e, em seguida, use o Windows PowerShell 3.0 para criar uma sessão PowerShell remota que se conecta ao Skype para negócios Online.
ms.openlocfilehash: 6679e9749efd6ee09a7c26f383b1b411caadb43e
ms.sourcegitcommit: a5b8b0a1e5ae5eb718e296ca6df6687368ee9174
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19493988"
---
# <a name="download-and-install-windows-powershell-30"></a><span data-ttu-id="e94e8-103">Baixe e instale o Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="e94e8-103">Download and install Windows PowerShell 3.0</span></span>

<span data-ttu-id="e94e8-104">Se você estiver usando o Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, você já deve ter o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-104">If you are using Windows 8.1, Windows 8, Windows Server 2012 R2, or Windows Server 2012, you should already have Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-105">Isso acontece porque o aplicativo vem pré-instalado com esses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="e94e8-105">That's because this application comes preinstalled with those operating systems.</span></span> 
  
<span data-ttu-id="e94e8-106">Se você estiver executando o Windows 7 ou Windows Server 2008 R2, você pode também estar executando o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-106">If you are running Windows 7 or Windows Server 2008 R2, you might also be running Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-107">No entanto, também é possível que você pode estar executando a versão 2.0 em vez disso — a versão que acompanha originalmente com esses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="e94e8-107">However, it's also possible that you might be running version 2.0 instead—the version that originally shipped with those operating systems.</span></span> <span data-ttu-id="e94e8-108">Para determinar qual versão do Microsoft PowerShelll que você estiver usando, faça o seguinte no computador com Windows 7 ou Windows Server 2008 R2:</span><span class="sxs-lookup"><span data-stu-id="e94e8-108">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 computer:</span></span>
  
1. <span data-ttu-id="e94e8-109">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-109">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="e94e8-110">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e94e8-110">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
    ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="e94e8-111">Informações semelhantes ao seguinte, em seguida, devem ser exibidas na janela do console:</span><span class="sxs-lookup"><span data-stu-id="e94e8-111">Information similar to the following should then be displayed in the console window:</span></span>
    
    ```
    Version
    -------
    3.0
    ```

    <span data-ttu-id="e94e8-112">Se o número da versão retornado for 3.0, você está executando o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-112">If the returned Version number is 3.0, then you are running Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-113">Se o número da versão retornado não for 3.0, você precisará instalar o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-113">If the returned Version number is not 3.0, then you'll need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-114">Você pode baixar Windows Management Framework 3.0, que inclui o Windows PowerShell 3.0, a partir do [Centro de Download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span><span class="sxs-lookup"><span data-stu-id="e94e8-114">You can download Windows Management Framework 3.0, which includes Windows PowerShell 3.0, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=34595).</span></span>
  
<span data-ttu-id="e94e8-115">Depois de verificar se o Windows PowerShell 3.0 está instalado, você deve se certificar que PowerShell foi configurado para execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="e94e8-115">After you've verified that Windows PowerShell 3.0 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="e94e8-116">Para fazer isso, inicie o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-116">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="e94e8-117">No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e94e8-117">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="e94e8-118">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell**e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-118">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="e94e8-119">Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-119">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e94e8-120">Se você estiver executando o Windows 8, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="e94e8-120">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="e94e8-121">Acessar a barra de botões, clique em **Pesquisar**e, em seguida, clique com botão direito **Do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-121">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="e94e8-122">Você pode acessar a barra de botões em qualquer computador Windows 8 (tela sensível ao toque ou tela não-sensível ao toque) rapidamente mantendo pressionada a tecla do Windows e pressionando C.</span><span class="sxs-lookup"><span data-stu-id="e94e8-122">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="e94e8-123">Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-123">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="e94e8-124">Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-124">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e94e8-125">Depois que o PowerShell estiver em execução, você deve alterar a diretiva de execução para permitir a execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="e94e8-125">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="e94e8-126">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e94e8-126">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="e94e8-127">Ao executar o comando anterior, você poderá receber a seguinte mensagem de erro: > *Set-ExecutionPolicy: acesso à chave do registro ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' negado.*</span><span class="sxs-lookup"><span data-stu-id="e94e8-127">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="e94e8-128">Essa mensagem de erro geralmente ocorre se você não estiver executando o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-128">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="e94e8-129">Feche a sessão do PowerShell e iniciar uma nova sessão como administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-129">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="e94e8-130">Para verificar se a diretiva de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e94e8-130">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="e94e8-131">Se você receber novamente o seguinte valor, em seguida, tudo o que foi configurado corretamente:</span><span class="sxs-lookup"><span data-stu-id="e94e8-131">If you get back the following value, then everything has been configured correctly:</span></span>
  
```
RemoteSigned
```

<span data-ttu-id="e94e8-132">Se você não estiver executando o Windows PowerShell 3.0, você também precisará baixar e instalar o Windows Management Framework 3.0 do Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="e94e8-132">If you are not currently running Windows PowerShell 3.0, you'll also need to download and install Windows Management Framework 3.0 from the Microsoft Download Center.</span></span> <span data-ttu-id="e94e8-133">Este é um pacote de instalação que inclui o Windows PowerShell 3.0 e o Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-133">This is an installation package that includes Windows PowerShell 3.0 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="e94e8-134">Esse pacote de instalação pode ser necessário se você estiver executando o Windows 7 e ainda não tiver atualizado para o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-134">This installation package might be required if you are running Windows 7 and have not yet updated to Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-135">Se você estiver executando o Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, não deve haver nenhuma necessidade de instalar o Windows PowerShell 3.0.</span><span class="sxs-lookup"><span data-stu-id="e94e8-135">If you are running Windows Server 2012, Windows Server 2012 R2, Windows 8, or Windows 8.1, there should be no need to install Windows PowerShell 3.0.</span></span> <span data-ttu-id="e94e8-136">Windows PowerShell 3.0 vem pré-instalado nesses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="e94e8-136">Windows PowerShell 3.0 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="e94e8-137">Antes de instalar o Windows Management Framework 3.0:</span><span class="sxs-lookup"><span data-stu-id="e94e8-137">Before installing Windows Management Framework 3.0:</span></span>
  
- <span data-ttu-id="e94e8-138">Certificar-se de que você baixou a versão correta do pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="e94e8-138">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="e94e8-139">Se você estiver executando a versão de 64 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x64.</span><span class="sxs-lookup"><span data-stu-id="e94e8-139">If you are running the 64-bit version of Windows 7, download the file Windows6.1-KB2506143-x64.msu.</span></span> <span data-ttu-id="e94e8-140">Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x86. msu.</span><span class="sxs-lookup"><span data-stu-id="e94e8-140">If you are running the 32-bit version of Windows 7, download the file Windows6.1-KB2506143-x86.msu.</span></span>
    
- <span data-ttu-id="e94e8-141">Se você estiver executando o Windows 7 no seu computador, certifique-se de que você instalou o Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="e94e8-141">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>
    
<span data-ttu-id="e94e8-142">Se você não tiver certeza de qual versão do Windows você está executando ou não tiver certeza se você instalou o Service Pack 1 do Windows 7, clique em **Iniciar**, do mouse em **computador**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-142">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="e94e8-143">Essas informações serão exibidas na caixa de diálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="e94e8-143">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="e94e8-144">Para instalar o Windows Management Framework 3.0, conclua o procedimento a seguir:</span><span class="sxs-lookup"><span data-stu-id="e94e8-144">To install Windows Management Framework 3.0, complete the following procedure:</span></span>
  
1. <span data-ttu-id="e94e8-145">Clique duas vezes a. Arquivo de instalação MSU ( **Windows 6.1-KB2506143-x64** ou **Windows 6.1-KB2506143-x86. msu**).</span><span class="sxs-lookup"><span data-stu-id="e94e8-145">Double-click the .MSU installation file (either **Windows6.1-KB2506143-x64.msu** or **Windows6.1-KB2506143-x86.msu**).</span></span>
    
2. <span data-ttu-id="e94e8-146">No Assistente de Download e instalar atualizações, na página **ler estes termos de licença (1-1)** , clique em **eu aceito**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-146">In the Download and Install Updates wizard, on the **Read these license terms (1 of 1)** page, click **I Accept**.</span></span>
    
3. <span data-ttu-id="e94e8-147">Quando a instalação estiver concluída, clique em **Reiniciar agora** para reiniciar o computador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-147">When installation is complete, click **Restart Now** to restart your computer.</span></span>
    
<span data-ttu-id="e94e8-148">Depois que o computador foi reiniciado, verifique se que o Windows PowerShell pode iniciar e que o aplicativo pode ser executado sob as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="e94e8-148">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="e94e8-149">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="e94e8-149">To do this:</span></span>
  
1. <span data-ttu-id="e94e8-150">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell** e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="e94e8-150">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="e94e8-151">Se o controle de conta de usuário for exibida a caixa de diálogo, clique em **Sim** para verificar se você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="e94e8-151">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="e94e8-152">Quando o console do PowerShell for exibida, em seguida, você deve verificar que o serviço WinRM está sendo executado e foi configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="e94e8-152">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="e94e8-153">Para verificar se o serviço está em execução, digite o seguinte comando no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="e94e8-153">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="e94e8-154">Informações sobre o serviço WinRM, em seguida, serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="e94e8-154">Information about the WinRM service will then be displayed on screen:</span></span>
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

<span data-ttu-id="e94e8-155">Se o serviço de Status não igual a "Executar", inicie o serviço WinRM digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="e94e8-155">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="e94e8-156">Depois que o serviço foi iniciado, execute o seguinte comando para certificar-se de que o WinRM é usando a autenticação básica:</span><span class="sxs-lookup"><span data-stu-id="e94e8-156">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="e94e8-157">Informações semelhantes à seguinte serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="e94e8-157">Information similar to the following will be displayed onscreen:</span></span>
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

<span data-ttu-id="e94e8-158">Se a autenticação básica tiver sido definida como verdadeiro, e em seguida, você está pronto para usar o PowerShell para se conectar ao Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="e94e8-158">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="e94e8-159">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="e94e8-159">Related topics</span></span>
[<span data-ttu-id="e94e8-160">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e94e8-160">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 