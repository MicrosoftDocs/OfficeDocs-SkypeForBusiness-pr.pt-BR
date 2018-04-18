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
ms.openlocfilehash: e3f1ca14b5c9e134ee5186b6c441fc948d1ef65b
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="download-and-install-windows-powershell-30"></a>Baixe e instale o Windows PowerShell 3.0

Se você estiver usando o Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, você já deve ter o Windows PowerShell 3.0. Isso acontece porque o aplicativo vem pré-instalado com esses sistemas operacionais. 
  
Se você estiver executando o Windows 7 ou Windows Server 2008 R2, você pode também estar executando o Windows PowerShell 3.0. No entanto, também é possível que você pode estar executando a versão 2.0 em vez disso — a versão que acompanha originalmente com esses sistemas operacionais. Para determinar qual versão do Microsoft PowerShelll que você estiver usando, faça o seguinte no computador com Windows 7 ou Windows Server 2008 R2:
  
1. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**e, em seguida, clique em **Windows PowerShell**.
    
2. No console do PowerShell, digite o seguinte comando e pressione ENTER:
    
    ```
   Get-Host | Select-Object Version
   ```

3. Informações semelhantes ao seguinte, em seguida, devem ser exibidas na janela do console:
    
    ```
    Version
    -------
    3.0
    ```

    Se o número da versão retornado for 3.0, você está executando o Windows PowerShell 3.0. Se o número da versão retornado não for 3.0, você precisará instalar o Windows PowerShell 3.0. Você pode baixar Windows Management Framework 3.0, que inclui o Windows PowerShell 3.0, a partir do [Centro de Download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Depois de verificar se o Windows PowerShell 3.0 está instalado, você deve se certificar que PowerShell foi configurado para execução de scripts remotos. Para fazer isso, inicie o PowerShell como administrador. No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, faça o seguinte:
  
1. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell**e, em seguida, clique em **Executar como administrador**.
    
2. Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.
    
Se você estiver executando o Windows 8, siga estas instruções:
  
1. Acessar a barra de botões, clique em **Pesquisar**e, em seguida, clique com botão direito **Do Windows PowerShell**. Você pode acessar a barra de botões em qualquer computador Windows 8 (tela sensível ao toque ou tela não-sensível ao toque) rapidamente mantendo pressionada a tecla do Windows e pressionando C.
    
2. Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.
    
3. Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para verificar que você deseja executar o PowerShell sob as credenciais de administrador.
    
Depois que o PowerShell estiver em execução, você deve alterar a diretiva de execução para permitir a execução de scripts remotos. No console do PowerShell, digite o seguinte comando e pressione ENTER:
```
Set-ExecutionPolicy RemoteSigned -Force
```
    > [!NOTE]
    >  When you run the preceding command, you might receive the following error message:> *Set-ExecutionPolicy : Access to the registry key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' is denied.* This error message typically occurs if you are not running PowerShell under administrator credentials. Close your session of PowerShell, and start a new session as an administrator. 
  
Para verificar se a diretiva de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:
  
```
Get-ExecutionPolicy
```

Se você receber novamente o seguinte valor, em seguida, tudo o que foi configurado corretamente:
  
```
RemoteSigned
```

Se você não estiver executando o Windows PowerShell 3.0, você também precisará baixar e instalar o Windows Management Framework 3.0 do Microsoft Download Center. Este é um pacote de instalação que inclui o Windows PowerShell 3.0 e o Windows Remote Management (WinRM) 3.0. Esse pacote de instalação pode ser necessário se você estiver executando o Windows 7 e ainda não tiver atualizado para o Windows PowerShell 3.0. Se você estiver executando o Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, não deve haver nenhuma necessidade de instalar o Windows PowerShell 3.0. Windows PowerShell 3.0 vem pré-instalado nesses sistemas operacionais.
  
Antes de instalar o Windows Management Framework 3.0:
  
- Certificar-se de que você baixou a versão correta do pacote de instalação. Se você estiver executando a versão de 64 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x64. Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x86. msu.
    
- Se você estiver executando o Windows 7 no seu computador, certifique-se de que você instalou o Windows 7 Service Pack 1.
    
Se você não tiver certeza de qual versão do Windows você está executando ou não tiver certeza se você instalou o Service Pack 1 do Windows 7, clique em **Iniciar**, do mouse em **computador**e, em seguida, clique em **Propriedades**. Essas informações serão exibidas na caixa de diálogo do sistema.
  
Para instalar o Windows Management Framework 3.0, conclua o procedimento a seguir:
  
1. Clique duas vezes a. Arquivo de instalação MSU ( **Windows 6.1-KB2506143-x64** ou **Windows 6.1-KB2506143-x86. msu**).
    
2. No Assistente de Download e instalar atualizações, na página **ler estes termos de licença (1-1)** , clique em **eu aceito**.
    
3. Quando a instalação estiver concluída, clique em **Reiniciar agora** para reiniciar o computador.
    
Depois que o computador foi reiniciado, verifique se que o Windows PowerShell pode iniciar e que o aplicativo pode ser executado sob as credenciais administrativas. Para fazer isso:
  
1. Clique em **Iniciar**, clique em **Todos os programas**, clique em **Acessórios**, clique em **Windows PowerShell**, com o botão direito **Do Windows PowerShell** e, em seguida, clique em **Executar como administrador**.
    
2. Se o controle de conta de usuário for exibida a caixa de diálogo, clique em **Sim** para verificar se você deseja executar o PowerShell sob as credenciais de administrador.
    
Quando o console do PowerShell for exibida, em seguida, você deve verificar que o serviço WinRM está sendo executado e foi configurado corretamente. Para verificar se o serviço está em execução, digite o seguinte comando no prompt do PowerShell e pressione ENTER:
  
```
Get-Service winrm
```

Informações sobre o serviço WinRM, em seguida, serão exibidas na tela:
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Se o serviço de Status não igual a "Executar", inicie o serviço WinRM digitando o seguinte comando e pressionando ENTER:
  
```
Start-Service winrm
```

Depois que o serviço foi iniciado, execute o seguinte comando para certificar-se de que o WinRM é usando a autenticação básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Informações semelhantes à seguinte serão exibidas na tela:
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Se a autenticação básica tiver sido definida como verdadeiro, e em seguida, você está pronto para usar o PowerShell para se conectar ao Skype para negócios Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
 