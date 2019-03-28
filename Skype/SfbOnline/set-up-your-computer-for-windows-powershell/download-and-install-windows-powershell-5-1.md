---
title: Baixe e instale o Windows PowerShell 5.1
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
- LIL_Placement
description: Baixar, instalar e então usar o Windows PowerShell 5.1 para criar uma sessão PowerShell remota que se conecta ao Skype para negócios Online.
ms.openlocfilehash: 63f4924a30bfc910679f23a617cc5252ecc5b6aa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30926691"
---
# <a name="download-and-install-windows-powershell-51"></a><span data-ttu-id="1bdcf-103">Baixe e instale o Windows PowerShell 5.1</span><span class="sxs-lookup"><span data-stu-id="1bdcf-103">Download and install Windows PowerShell 5.1</span></span>

<span data-ttu-id="1bdcf-104">Se você estiver usando o Windows Update de aniversário 10 ou Windows Server 2016, você já deve ter o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-104">If you are using Windows 10 Anniversary Update, or Windows Server 2016, you should already have Windows PowerShell 5.1.</span></span> <span data-ttu-id="1bdcf-105">Isso acontece porque o aplicativo vem pré-instalado com esses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-105">That's because this application comes preinstalled with those operating systems.</span></span>
  
<span data-ttu-id="1bdcf-106">Para determinar qual versão do Microsoft PowerShelll que você estiver usando, faça o seguinte em seu Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012 computador:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-106">To determine which version of Microsoft PowerShelll you are using, do the following on your Windows 7 or Windows Server 2008 R2 or Windows Server 2012 computer:</span></span>
  
1. <span data-ttu-id="1bdcf-107">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-107">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, and then click **Windows PowerShell**.</span></span>
    
2. <span data-ttu-id="1bdcf-108">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-108">In the PowerShell console, type the following command and then press ENTER:</span></span>
    
   ```
   Get-Host | Select-Object Version
   ```

3. <span data-ttu-id="1bdcf-109">Informações semelhantes ao seguinte, em seguida, devem ser exibidas na janela do console:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-109">Information similar to the following should then be displayed in the console window:</span></span>
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    <span data-ttu-id="1bdcf-110">Se o número da versão retornado for 5.1, você está executando o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-110">If the returned Version number is 5.1, then you are running Windows PowerShell 5.1.</span></span> <span data-ttu-id="1bdcf-111">Se o número da versão retornado não for 5.1, você precisará instalar o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-111">If the returned Version number is not 5.1, then you'll need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="1bdcf-112">Você pode baixar Windows Management Framework 5.1, que inclui o Windows PowerShell 5.1, a partir do [Centro de Download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="1bdcf-112">You can download Windows Management Framework 5.1, which includes Windows PowerShell 5.1, from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=54616).</span></span>
  
<span data-ttu-id="1bdcf-113">Depois de verificar se o Windows PowerShell 5.1 está instalado, você deve se certificar que PowerShell foi configurado para execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-113">After you've verified that Windows PowerShell 5.1 is installed, you must make sure that PowerShell has been configured for running remote scripts.</span></span> <span data-ttu-id="1bdcf-114">Para fazer isso, inicie o PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-114">To do that, start PowerShell as an administrator.</span></span> <span data-ttu-id="1bdcf-115">No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-115">On Windows 7, Windows Server 2008 R2, Windows Server 2012, or Windows Server 2012 R2 do the following:</span></span>
  
1. <span data-ttu-id="1bdcf-116">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell**e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-116">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell**, and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1bdcf-117">Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-117">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1bdcf-118">Se você estiver executando o Windows 8, siga estas instruções:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-118">If you are running Windows 8, complete this procedure instead:</span></span>
  
1. <span data-ttu-id="1bdcf-119">Acessar a barra de botões, clique em **Pesquisar**e, em seguida, clique com botão direito **Do Windows PowerShell**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-119">Access the Charms bar, click **Search**, and then right-click **Windows PowerShell**.</span></span> <span data-ttu-id="1bdcf-120">Você pode acessar a barra de botões em qualquer computador Windows 8 (tela sensível ao toque ou tela não-sensível ao toque) rapidamente mantendo pressionada a tecla do Windows e pressionando C.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-120">You can quickly access the Charms bar on any Windows 8 computer (touch screen or non-touch screen) by holding down the Windows key and pressing C.</span></span>
    
2. <span data-ttu-id="1bdcf-121">Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-121">In the toolbar at the bottom of the screen, click **Run as administrator**.</span></span>
    
3. <span data-ttu-id="1bdcf-122">Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-122">If the **User Account Control** dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1bdcf-123">Depois que o PowerShell estiver em execução, você deve alterar a diretiva de execução para permitir a execução de scripts remotos.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-123">After PowerShell is running, you must change the execution policy to allow the running of remote scripts.</span></span> <span data-ttu-id="1bdcf-124">No console do PowerShell, digite o seguinte comando e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-124">In the PowerShell console, type the following command and then press ENTER:</span></span>
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> <span data-ttu-id="1bdcf-125">Quando você executa o comando anterior, você poderá receber o seguinte erro mensagem: gt _ *Set-ExecutionPolicy: acesso à chave do registro ' HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' negado.*</span><span class="sxs-lookup"><span data-stu-id="1bdcf-125">When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.*</span></span> <span data-ttu-id="1bdcf-126">Essa mensagem de erro geralmente ocorre se você não estiver executando o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-126">This error message typically occurs if you are not running PowerShell under administrator credentials.</span></span> <span data-ttu-id="1bdcf-127">Feche a sessão do PowerShell e iniciar uma nova sessão como administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-127">Close your session of PowerShell, and start a new session as an administrator.</span></span>
 
<span data-ttu-id="1bdcf-128">Para verificar se a diretiva de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-128">To verify that the execution policy has been configured correctly, type the following at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-ExecutionPolicy
```

<span data-ttu-id="1bdcf-129">Se você receber novamente o seguinte valor, em seguida, tudo o que foi configurado corretamente:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-129">If you get back the following value, then everything has been configured correctly:</span></span>
  
`RemoteSigned`

<span data-ttu-id="1bdcf-130">Se você não estiver executando o Windows PowerShell 5.1, você também precisará baixar e instalar o Windows Management Framework 5.1 do Microsoft Download Center.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-130">If you are not currently running Windows PowerShell 5.1, you'll also need to download and install Windows Management Framework 5.1 from the Microsoft Download Center.</span></span> <span data-ttu-id="1bdcf-131">Este é um pacote de instalação que inclui o Windows PowerShell 5.1 e Windows Remote Management (WinRM) 3.0.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-131">This is an installation package that includes Windows PowerShell 5.1 and Windows Remote Management (WinRM) 3.0.</span></span> <span data-ttu-id="1bdcf-132">Esse pacote de instalação pode ser necessário se você, por exemplo, se estiver executando o Windows 7 SP1 e ainda não tiver atualizado para o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-132">This installation package might be required if you, for example, are running Windows 7 SP1 and have not yet updated to Windows PowerShell 5.1.</span></span> <span data-ttu-id="1bdcf-133">Se você estiver executando o Windows Server 2016, ou o Windows Update de aniversário 10, não deve haver nenhuma necessidade de instalar o Windows PowerShell 5.1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-133">If you are running Windows Server 2016, or Windows 10 Anniversary Update, there should be no need to install Windows PowerShell 5.1.</span></span> <span data-ttu-id="1bdcf-134">Windows PowerShell 5.1 vem pré-instalado nesses sistemas operacionais.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-134">Windows PowerShell 5.1 comes preinstalled on those operating systems.</span></span>
  
<span data-ttu-id="1bdcf-135">Antes de instalar o Windows Management Framework 5.1:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-135">Before installing Windows Management Framework 5.1:</span></span>
  
- <span data-ttu-id="1bdcf-136">Certificar-se de que você baixou a versão correta do pacote de instalação.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-136">Make sure you have downloaded the correct version of the installation package.</span></span> <span data-ttu-id="1bdcf-137">Se você estiver executando a versão de 64 bits do Windows 7 SP1, baixe o arquivo Win7AndW2K8R2-KB3191566-x64.ZIP.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-137">If you are running the 64-bit version of Windows 7 SP1, download the file Win7AndW2K8R2-KB3191566-x64.ZIP.</span></span> <span data-ttu-id="1bdcf-138">Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Win7-KB3191566-x86.ZIP.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-138">If you are running the 32-bit version of Windows 7, download the file Win7-KB3191566-x86.ZIP.</span></span>
    
- <span data-ttu-id="1bdcf-139">Se você estiver executando o Windows 7 no seu computador, certifique-se de que você instalou o Windows 7 Service Pack 1.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-139">If you are running Windows 7 on your computer, make sure that you have installed Windows 7 Service Pack 1.</span></span>

<span data-ttu-id="1bdcf-140">Se você não tiver certeza de qual versão do Windows você está executando ou não tiver certeza se você instalou o Service Pack 1 do Windows 7, clique em **Iniciar**, do mouse em **computador**e, em seguida, clique em **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-140">If you aren't sure which version of Windows you are running, or you aren't sure if you've installed Windows 7 Service Pack 1, click **Start**, right-click **Computer**, and then click **Properties**.</span></span> <span data-ttu-id="1bdcf-141">Essas informações serão exibidas na caixa de diálogo do sistema.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-141">This information will be reported in the System dialog box.</span></span>
  
<span data-ttu-id="1bdcf-142">Para instalar o Windows Management Framework 5.1, complete o procedimento no [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span><span class="sxs-lookup"><span data-stu-id="1bdcf-142">To install Windows Management Framework 5.1, complete the procedure in [Install and Configure WMF 5.1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)</span></span>
  
<span data-ttu-id="1bdcf-143">Depois que o computador foi reiniciado, verifique se que o Windows PowerShell pode iniciar e que o aplicativo pode ser executado sob as credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-143">After the computer has rebooted, verify that Windows PowerShell can start and that the application can be run under administrative credentials.</span></span> <span data-ttu-id="1bdcf-144">Para fazer isso:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-144">To do this:</span></span>
  
1. <span data-ttu-id="1bdcf-145">Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell** e, em seguida, clique em **Executar como administrador**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-145">Click **Start**, click **All Programs**, click **Accessories**, click **Windows PowerShell**, right-click **Windows PowerShell** and then click **Run as administrator**.</span></span>
    
2. <span data-ttu-id="1bdcf-146">Se o controle de conta de usuário for exibida a caixa de diálogo, clique em **Sim** para verificar se você deseja executar o PowerShell sob as credenciais de administrador.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-146">If the User Account Control dialog box appears, click **Yes** to verify that you want to run PowerShell under administrator credentials.</span></span>
    
<span data-ttu-id="1bdcf-147">Quando o console do PowerShell for exibida, em seguida, você deve verificar que o serviço WinRM está sendo executado e foi configurado corretamente.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-147">When the PowerShell console appears, you should then verify that the WinRM service is running and has been configured correctly.</span></span> <span data-ttu-id="1bdcf-148">Para verificar se o serviço está em execução, digite o seguinte comando no prompt do PowerShell e pressione ENTER:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-148">To verify that the service is running, type the following command at the PowerShell prompt and then press ENTER:</span></span>
  
```
Get-Service winrm
```

<span data-ttu-id="1bdcf-149">Informações sobre o serviço WinRM, em seguida, serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-149">Information about the WinRM service will then be displayed on screen:</span></span>
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

<span data-ttu-id="1bdcf-150">Se o serviço de Status não igual a "Executar", inicie o serviço WinRM digitando o seguinte comando e pressionando ENTER:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-150">If the service Status does not equal "Running", start the WinRM service by typing the following command and then pressing ENTER:</span></span>
  
```
Start-Service winrm
```

<span data-ttu-id="1bdcf-151">Depois que o serviço foi iniciado, execute o seguinte comando para certificar-se de que o WinRM é usando a autenticação básica:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-151">After the service has started, run the following command to make sure that WinRM is using Basic authentication:</span></span>
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

<span data-ttu-id="1bdcf-152">Informações semelhantes à seguinte serão exibidas na tela:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-152">Information similar to the following will be displayed onscreen:</span></span>
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

<span data-ttu-id="1bdcf-153">Se a autenticação básica tiver sido definida como verdadeiro, e em seguida, você está pronto para usar o PowerShell para se conectar ao Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-153">If basic authentication has been set to true, then you're ready to use PowerShell to connect to Skype for Business Online.</span></span>
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a><span data-ttu-id="1bdcf-154">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1bdcf-154">Related topics</span></span>
[<span data-ttu-id="1bdcf-155">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1bdcf-155">Set up your computer for Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md) 

  
 
