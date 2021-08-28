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
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
- LIL_Placement
description: Baixar, instalar e usar o Windows PowerShell 5.1 para criar uma sessão remota do PowerShell que se conecta ao Skype for Business online.
ms.openlocfilehash: 2cbfa65f3170dd516e8bb46365ef663fd237d542
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58612830"
---
# <a name="download-and-install-windows-powershell-51"></a>Baixar e instalar o Windows PowerShell 5.1

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Caso esteja usando a Atualização de Aniversário do Windows 10 ou o Windows Server 2016, você já deve ter o Windows PowerShell 5.1. Esse aplicativo vem pré-instalado com esses sistemas operacionais.
  
Para determinar a versão do Microsoft PowerShell em uso, faça o seguinte em seu computador com o Windows 7, o Windows Server 2008 R2 ou o Windows Server 2012:
  
1. Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell** e em **Windows PowerShell**.
    
2. No console do PowerShell, digite o seguinte comando e pressione ENTER:
    
   ```PowerShell
   Get-Host | Select-Object Version
   ```

3. Informações semelhantes às seguintes devem então ser exibidas na janela do console:
    
    <pre>
    Version <BR>
    ------- <BR>
    4.0
    </pre>

    Se o número de versão retornado for 5.1, o Windows PowerShell 5.1 está em execução. Se o número de versão retornado não for 5.1, será necessário instalar o Windows PowerShell 5.1. Você pode baixar o Windows Management Framework 5.1, que inclui o Windows PowerShell 5.1, no [Centro de Download da Microsoft](https://www.microsoft.com/download/details.aspx?id=54616).
  
Depois de verificar se o Windows PowerShell 5.1 está instalado, verifique se o PowerShell foi configurado para executar scripts remotos. Para isso, inicie o Windows PowerShell como um administrador. No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou no Windows Server 2012 R2, faça o seguinte:
  
1. Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.
    
2. Se a caixa de diálogo **Controle da Conta de Usuário** for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.
    
Se você estiver executando o Windows 8, conclua este procedimento:
  
1. Acesse a barra de Botões, clique em **Pesquisar** e, em seguida, clique com o botão direito do mouse em **Windows PowerShell**. Você pode acessar rapidamente a barra Botões em qualquer computador com o Windows 8 (tela sensível ao toque ou não) ao manter a tecla do Windows pressionada e pressionando C.
    
2. Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.
    
3. Se a caixa de diálogo **Controle da Conta de Usuário** for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.
    
Depois que o PowerShell estiver em execução, você deverá alterar a política de execução para permitir a execução de scripts remotos. No console do PowerShell, digite o seguinte comando e pressione ENTER:
```PowerShell
Set-ExecutionPolicy RemoteSigned -Force
```
   
 
> [!NOTE]
> Ao executar o comando anterior, você pode receber a seguinte mensagem de erro:> *Set-ExecutionPolicy: o acesso à chave do registro'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' foi negado.* Esta mensagem de erro normalmente ocorrerá se você não estiver executado o PowerShell sob credenciais de administrador. Feche sua sessão do PowerShell e inicie uma nova sessão como um administrador.
 
Para verificar se a política de execução foi configurada corretamente, digite o seguinte no prompt do PowerShell e pressione ENTER:
  
```PowerShell
Get-ExecutionPolicy
```

Se você obtiver o valor a seguir, tudo estará configurado corretamente:
  
`RemoteSigned`

Se o Windows PowerShell 5.1 não estiver em execução no momento, você também precisará baixar e instalar o Windows Management Framework 5.1 no Centro de Download da Microsoft. Este é um pacote de instalação que inclui o Windows PowerShell 5.1 e o Gerenciamento Remoto do Windows (WinRM) 3.0. Este pacote de instalação pode ser necessário caso você esteja executando, por exemplo, o Windows 7 SP1 e ainda não tenha atualizado para o Windows PowerShell 5.1. Se você estiver executando o Windows Server 2016 ou a Atualização de Aniversário do Windows 10, não deve ser necessário instalar o Windows PowerShell 5.1. O Windows PowerShell 5.1 vem pré-instalado nestes sistemas operacionais.
  
Antes de instalar o Windows Management Framework 5.1:
  
- Verifique se baixou a versão correta do pacote de instalação. Se você estiver executando a versão de 64 bits do Windows 7 SP1, baixe o arquivo Win7AndW2K8R2-KB3191566-x64.ZIP. Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Win7-KB3191566-x86.ZIP.
    
- Se você estiver executando o Windows 7 em seu computador, verifique se instalou o Windows 7 Service Pack 1.

Se não tiver certeza sobre qual versão do Windows está em execução ou se o Windows 7 Service Pack 1 está instalado, clique em **Iniciar**, clique com o botão direito do mouse em **Computador** e clique em **Propriedades**. Essas informações são relatadas na caixa de diálogo Sistema.
  
Para instalar o Windows Management Framework 5.1, conclua o procedimento em [Instalar e configurar o WMF 5.1](/powershell/scripting/wmf/setup/install-configure).
  
Após a reinicialização do computador, verifique se é possível iniciar o Windows PowerShell e se o aplicativo pode ser executado sob credenciais administrativas. Para fazer isso:
  
1. Clique em **Iniciar**, em **Todos os Programas**, em **Acessórios**, em **Windows PowerShell**, clique com o botão direito do mouse em **Windows PowerShell** e depois clique em **Executar como administrador**.
    
2. Se a caixa de diálogo Controle da Conta de Usuário for exibida, clique em **Sim** para verificar se você deseja executar o Windows PowerShell sob as credenciais de administrador.
    
Quando o console do PowerShell for exibido, verifique se o serviço WinRM está em execução e se foi configurado corretamente. Para verificar se o serviço está em execução, digite o comando a seguir no prompt do PowerShell e pressione ENTER:
  
```PowerShell
Get-Service winrm
```

As informações sobre o serviço WinRM serão exibidas na tela:
  
<pre>
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
</pre>

Se o Status do serviço não for "Em execução", inicie o serviço WinRM digitando o comando a seguir e pressione ENTER:
  
```PowerShell
Start-Service winrm
```

Depois que o serviço iniciar, execute o comando a seguir para garantir que o WinRM esteja usando a autenticação Básica:
  
```PowerShell
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Informações semelhantes às seguintes deverão ser exibidas na tela:
  
<pre>
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
</pre>

Se a autenticação básica for definida como verdadeira, então você está pronto para usar o PowerShell para se conectar ao Skype for Business Online.
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Tópicos relacionados
[Configurar o computador para o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) 

  
