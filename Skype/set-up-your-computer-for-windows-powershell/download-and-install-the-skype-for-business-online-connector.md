---
title: "Baixe e instale o Skype para módulo Business Connector Online"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: get-started-article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
description: "Download, install, and then use the Skype for Business Online Connector to create a remote Windows PowerShell session that connects to Skype for Business Online.
"
---

# Baixe e instale o Skype para módulo Business Connector Online

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
O Módulo Conector do Skype for Business Online inclui o cmdlet **New-CsOnlineSession**, que permite que você crie uma sessão remota Windows PowerShell que se conecta ao Skype for Business Online. Neste módulo, que é suportado apenas em computadores de 64 bits (consulte[Configurar seu computador para Skype para gerenciamento de negócios Online usando o Windows PowerShell](set-up-your-computer-for-skype-for-business-online-management-using-windows-powe.md) para obter mais informações), pode ser baixado da Centro de Download da Microsoft em[https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Baixar o arquivo SkypeOnlinePowershell.exe e, em seguida, conclua o procedimento a seguir:
  
1. Clique duas vezes no arquivo **SkypeOnlinePowershell.exe**.
    
2. No Skype for Business Online, Assistente de configuração do Windows PowerShell, na página **Termos de licença para Software Microsoft**, selecione **aceito os termos do contrato de licença** e clique em **instalar**. Se a caixa de diálogo de **Controle de conta de usuário** for exibida, clique em **Sim** para continuar a instalação.
    
3. Na página **concluído o Skype for Business Online, módulo do Windows PowerShell**, clique em **Concluir**.
    
O programa de instalação copia o Módulo Conector do Skype for Business Online (e o cmdlet **New-CsOnlineSession** ) com seu computador. Para acessar o módulo, inicie uma sessão de Windows PowerShell em credenciais de administrador e, em seguida, execute o seguinte comando:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Se você não quiser digitar este comando toda vez que iniciar Windows PowerShell, você pode adicionar o comando ao seu perfil de Windows PowerShell. Para fazer isso, digite o seguinte comando no prompt de Windows PowerShell e pressione ENTER:
  
```
notepad.exe $profile
```

Quando aparece o bloco de notas, adicione a seguinte linha até a parte inferior dos comandos que já estão no perfil (se houver):
  
```
Import-Module SkypeOnlineConnector
```

Salve o arquivo. Na próxima vez que você inicia Windows PowerShell, o Módulo Conector do Skype for Business Online automaticamente serão importados. Esteja ciente de que você obterá uma mensagem de erro e o módulo não será carregado, se você não estiver executando Windows PowerShell em credenciais de administrador.
  
Além de instalar o Módulo Conector do Skype for Business Online, SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a identidade serviço cliente Runtime biblioteca (IDCRL), usado para lidar com a autenticação de cliente para Skype for Business Online; 2) .NET framework 4,5; e, 3) o pacote Microsoft Visual C++ 2012 redistribuível (x64) (versão 11.0.50727). .NET framework 4,5 fornece a infraestrutura usada para criar e executar aplicativos .NET, incluindo Windows PowerShell. O pacote Visual C++ redistribuível instala os componentes de tempo de execução do Visual C++ para computadores que não tenham o Microsoft Visual Studio 2012 instalado.
  
Para verificar o número da versão do módulo conector atualmente instalado no seu computador, abra o painel de controle, abra **programas e recursos** e, em seguida, procure o número da versão do **Skype for Business Online, módulo do Windows PowerShell**.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

