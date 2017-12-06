---
title: "Baixe e instale o Windows PowerShell 3.0"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 10/3/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: LIL_Placement
ms.assetid: d739cd71-3c18-42ea-879f-b408bf53b1f4

description: "Download, install, and then use Windows PowerShell 3.0 to create a remote PowerShell session that connects to Skype for Business Online."
---

# Baixe e instale o Windows PowerShell 3.0

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o [aviso de isenção de responsabilidade](d739cd71-3c18-42ea-879f-b408bf53b1f4.md#MT_Footer). Para sua referência, veja a versão em inglês deste artigo [aqui](https://support.office.com/en-us/article/d739cd71-3c18-42ea-879f-b408bf53b1f4). 
  
Se você estiver usando Windows 8.1, Windows 8, Windows Server 2012 R2 ou Windows Server 2012, você já deve ter Windows PowerShell 3.0. Isso ocorre porque este aplicativo vem pré-instalado com esses sistemas operacionais.
  
Se você estiver executando Windows 7 ou Windows Server 2008 R2, você pode também estar executando Windows PowerShell 3.0. No entanto, também é possível que você pode estar executando versão 2.0 em vez disso  a versão que acompanha originalmente com esses sistemas operacionais. Para determinar qual versão do Microsoft PowerShell l que você estiver usando, faça o seguinte no computador com Windows 7 ou Windows Server 2008 R2:
  
1. Clique em **Iniciar**, **Todos os** programas, clique em **Acessórios**, clique em **Windows PowerShell** e clique em **Windows PowerShell**.
    
2. No console de PowerShell, digite o seguinte comando e pressione ENTER:
    
  ```
  Get-Host | Select-Object Version
  ```

3. Informações semelhantes à seguinte depois devem ser exibidas na janela do console:
    
  ```
  Version
-------
3.0
  ```

Se o número da versão retornado for 3.0, você está executando Windows PowerShell 3.0. Se o número da versão retornado não for 3.0, você precisará instalar Windows PowerShell 3.0. Você pode baixar o Windows Management Framework 3.0, que inclui Windows PowerShell 3.0, do [Centro de Download da Microsoft](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
Depois de verificar que Windows PowerShell 3.0 estiver instalado, você deve garantir que PowerShell foi configurado para execução de scripts remotos. Para fazer isso, inicie PowerShell como administrador. No Windows 7, Windows Server 2008 R2, Windows Server 2012 ou Windows Server 2012 R2, faça o seguinte:
  
1. Clique em **Iniciar**, **Todos os** programas, clique em **Acessórios**, clique em **Windows PowerShell**, clique com botão direito **Do Windows PowerShell** e clique em **Executar como administrador**.
    
2. Se a caixa de diálogo de **Controle de conta de usuário** for exibida, clique em **Sim** para confirmar que você deseja executar PowerShell em credenciais de administrador.
    
Se você estiver executando Windows 8, conclua esse procedimento, em vez disso:
  
1. Acessar a barra de botões, clique em **Pesquisar** e, em seguida, clique com botão direito **Do Windows PowerShell**. Você pode acessar rapidamente a barra de botões em qualquer computador Windows 8 (tela sensível ao toque ou tela de toque não) mantendo pressionada a tecla Windows e pressionando C.
    
2. Na barra de ferramentas na parte inferior da tela, clique em **Executar como administrador**.
    
3. Se a caixa de diálogo de **Controle de conta de usuário** for exibida, clique em **Sim** para confirmar que você deseja executar PowerShell em credenciais de administrador.
    
Depois de PowerShell estiver em execução, você deve alterar a política de execução para permitir a execução de scripts remotos. No console de PowerShell, digite o seguinte comando e pressione ENTER:
  
```
Set-ExecutionPolicy RemoteSigned -Force
```

> [!NOTE]
> Quando você executa o comando anterior, você pode receber a seguinte mensagem de erro: > Set-ExecutionPolicy: Acessem o registro key'HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\PowerShell\\1\\ShellIds\\Micrsoft.PowerShell' negado. > Normalmente, essa mensagem de erro ocorre se você não estiver executando PowerShell em credenciais de administrador. Fechar sua sessão de PowerShell e iniciar uma nova sessão como administrador. 
  
Para verificar se a política de execução foi configurada corretamente, digite o seguinte no prompt de PowerShell e pressione ENTER:
  
```
Get-ExecutionPolicy
```

Se você acessar o seguinte valor, em seguida, tudo o que foi configurado corretamente:
  
```
RemoteSigned
```

Se você não estiver executando Windows PowerShell 3.0 atualmente, você também precisará baixar e instalar o Windows Management Framework 3.0 da Microsoft Download Center. Este é um pacote de instalação que inclui Windows PowerShell 3.0 e gerenciamento remoto do Windows (WinRM) 3.0. Este pacote de instalação pode ser necessário se você estiver executando o Windows 7 e ainda não tiver atualizado para Windows PowerShell 3.0. Se você estiver executando Windows Server 2012, Windows Server 2012 R2, Windows 8 ou Windows 8.1, deverá haver não é necessário instalar o Windows PowerShell 3.0. Windows PowerShell 3.0 vem pré-instalado nesses sistemas operacionais.
  
Antes de instalar o Windows Management Framework 3.0:
  
- Verifique se que você baixou a versão correta do pacote de instalação. Se você estiver executando a versão de 64 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x64. Se você estiver executando a versão de 32 bits do Windows 7, baixe o arquivo Windows 6.1-KB2506143-x86.
    
- Se você estiver executando o Windows 7 no seu computador, certifique-se de que você instalou o Windows 7 Service Pack 1.
    
Se não tiver certeza de qual versão do Windows você está executando ou você não tem certeza se você instalou o Windows 7 Service Pack 1, clique em **Iniciar**, clique com botão direito **computador** e clique em **Propriedades**. Essas informações serão relatadas na caixa de diálogo do sistema.
  
Para instalar o Windows Management Framework 3.0, conclua o procedimento a seguir:
  
1. Clique duas vezes na. Arquivo de instalação do MSU ( **Windows 6.1-KB2506143-x64** ou **Windows 6.1-KB2506143-x86** ).
    
2. No Assistente de Download e instalar atualizações, na página **Leia os termos desta licença (1 de 1)**, clique em **Aceitar**.
    
3. Quando a instalação estiver concluída, clique em **Reiniciar agora** para reiniciar o computador.
    
Após a reinicialização do computador, verifique se que o Windows PowerShell pode iniciar e que o aplicativo pode ser executado em credenciais administrativas. Para fazer isso:
  
1. Clique em **Iniciar**, **Todos os** programas, clique em **Acessórios**, clique em **Windows PowerShell**, clique com botão direito **Do Windows PowerShell** e clique em **Executar como administrador**.
    
2. Se a caixa de diálogo de controle de conta de usuário for exibida, clique em **Sim** para confirmar que você deseja executar PowerShell em credenciais de administrador.
    
Quando o console PowerShell for exibida, você deve, em seguida, verifique se o serviço WinRM está sendo executado e foi configurado corretamente. Para verificar se o serviço está em execução, digite o seguinte comando no prompt de PowerShell e pressione ENTER:
  
```
Get-Service winrm
```

Informações sobre o serviço WinRM então serão exibidas na tela:
  
```
Status   Name               DisplayName
------   ----               -----------
Running  winrm              Windows Remote Management (WS-Manag...
```

Se o serviço Status não igual a "Executando", inicie o serviço WinRM digitando o seguinte comando e depois pressionando ENTER:
  
```
Start-Service winrm
```

Após o serviço foi iniciado, execute o seguinte comando para certificar-se de que o WinRM está usando autenticação básica:
  
```
winrm set winrm/config/client/auth '@{Basic="True"}'
```

Informações semelhantes a seguinte mensagem serão exibidas na tela:
  
```
Auth
    Basic = true
    Digest = true
    Kerberos = true
    Negotiate = true
    Certificate = true
    CredSSP = false
```

Se a autenticação básica tiver sido definida como true, e em seguida, você está pronto para usar PowerShell para se conectar ao Skype for Business Online.
  
||
|:-----|
|![O ícone pequeno do LinkedIn Learning.](../images/7e5cb7c8-dc66-4c9a-a16d-a30f10a970bd.png) **Novo no Office 365?**         Descubra cursos de vídeo gratuitos para **Administradores do Office 365 e profissionais de TI**, disponibilizados pelo LinkedIn Learning. |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

