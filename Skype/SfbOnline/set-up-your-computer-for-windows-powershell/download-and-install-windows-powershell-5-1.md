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
ms.openlocfilehash: 42c466d476b95228674b8a58cdeafca785496f4e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285110"
---
# <a name="download-and-install-windows-powershell-51"></a>Baixar e instalar o Windows PowerShell 5,1

Se estiver usando a atualização de aniversário do Windows 10 ou o Windows Server 2016, você já deve ter o Windows PowerShell 5,1. Isso porque este aplicativo vem pré-instalado com esses sistemas operacionais.
  
Para determinar qual versão do Microsoft PowerShell você está usando, faça o seguinte no seu computador com Windows 7 ou Windows Server 2008 R2 ou Windows Server 2012:
  
1. Clique em **Iniciar**, **em todos os programas**, em **acessórios**, em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.
    
2. No console do PowerShell, digite o seguinte comando e pressione ENTER:
    
   ```
   Get-Host | Select-Object Version
   ```

3. Informações semelhantes às seguintes devem ser exibidas na janela do console:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Se o número de versão retornado for 5,1, então você está executando o Windows PowerShell 5,1. Se o número de versão retornado não for 5,1, você precisará instalar o Windows PowerShell 5,1. Você pode baixar o Windows Management Framework 5,1, que inclui o Windows PowerShell 5,1, a partir do [centro de download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=54616).
  
Depois de verificar se o Windows PowerShell 5,1 está instalado, você deve certificar-se de que o PowerShell foi configurado para executar scripts remotos. Para fazer isso, inicie o PowerShell como administrador. No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2 faça o seguinte:
  
1. Clique em **Iniciar**, em **todos os programas**, em **acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell**e, em seguida, clique em **Executar como administrador**.
    
2. Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.
    
Se você estiver executando o Windows 8, siga este procedimento em vez disso:
  
1. Acesse a barra de botões, clique em **Pesquisar**e, em seguida, clique com o botão direito do mouse no **Windows PowerShell**. Você pode acessar rapidamente a barra de botões em qualquer computador com o Windows 8 (tela sensível ao toque ou tela não sensível ao toque), mantendo pressionada a tecla Windows e pressionando C.
    
2. Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.
    
3. Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.
    
Após a execução do PowerShell, você deve alterar a política de execução para permitir a execução de scripts remotos. No console do PowerShell, digite o seguinte comando e pressione ENTER:
```
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Ao executar o comando anterior, você pode receber a seguinte mensagem de erro: > *Set-ExecutionPolicy: acesso ao registro key'HKEY_LOCAL_MACHINE\\software\\Microsoft\\PowerShell\\1 ShellIds\\\\Micrsoft. PowerShell ' negado.* Essa mensagem de erro geralmente ocorre se você não estiver executando o PowerShell em credenciais de administrador. Feche a sessão do PowerShell e inicie uma nova sessão como administrador.
 
Para verificar se a política de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:
  
```
Get-ExecutionPolicy
```

Se você receber o seguinte valor, então tudo foi configurado corretamente:
  
`RemoteSigned`

Se você não estiver atualmente executando o Windows PowerShell 5,1, também precisará baixar e instalar o Windows Management Framework 5,1 do centro de download da Microsoft. Este é um pacote de instalação que inclui o Windows PowerShell 5,1 e o gerenciamento remoto do Windows (WinRM) 3,0. Este pacote de instalação pode ser necessário se você, por exemplo, estiver executando o Windows 7 SP1 e ainda não tiver sido atualizado para o Windows PowerShell 5,1. Se você estiver executando o Windows Server 2016 ou a atualização de aniversário do Windows 10, não será necessário instalar o Windows PowerShell 5,1. O Windows PowerShell 5,1 vem pré-instalado nesses sistemas operacionais.
  
Antes de instalar o Windows Management Framework 5,1:
  
- Verifique se você fez o download da versão correta do pacote de instalação. Se você estiver executando a versão de 64 bits do Windows 7 SP1, baixe o arquivo Win7AndW2K8R2-KB3191566-x64. ZIP. Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Win7-KB3191566-x86. ZIP.
    
- Se você estiver executando o Windows 7 em seu computador, verifique se instalou o Windows 7 Service Pack 1.

Se não tiver certeza de qual versão do Windows você está executando ou se não tiver certeza de que instalou o Windows 7 Service Pack 1, clique em **Iniciar**, clique com o botão direito do mouse em **computador**e, em seguida, clique em **Propriedades**. Essas informações serão informadas na caixa de diálogo sistema.
  
Para instalar o Windows Management Framework 5,1, conclua o procedimento em [instalar e configurar o WMF 5,1](https://docs.microsoft.com/en-us/powershell/wmf/5.1/install-configure)
  
Após a reinicialização do computador, verifique se o Windows PowerShell pode iniciar e se o aplicativo pode ser executado em credenciais administrativas. Para fazer isto:
  
1. Clique em **Iniciar**, em **todos os programas**, em **acessórios**, clique em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e clique em **Executar como administrador**.
    
2. Se a caixa de diálogo controle de conta de usuário for exibida, clique em **Sim** para verificar se você deseja executar o PowerShell em credenciais de administrador.
    
Quando o console do PowerShell for exibido, verifique se o serviço WinRM está em execução e configurado corretamente. Para verificar se o serviço está em execução, digite o seguinte comando no prompt do PowerShell e pressione ENTER:
  
```
Get-Service winrm
```

As informações sobre o serviço WinRM serão exibidas na tela:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Se o status do serviço não for igual a "Running", inicie o serviço WinRM digitando o seguinte comando e pressionando ENTER:
  
```
Start-Service winrm
```

Após o início do serviço, execute o seguinte comando para ter certeza de que o WinRM está usando a autenticação básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Informações semelhantes às seguintes serão exibidas na tela:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Se a autenticação básica tiver sido definida como true, você estará pronto para usar o PowerShell para se conectar ao Skype for Business online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 
