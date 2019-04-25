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
ms.openlocfilehash: f7b7fa418b31a7b826319fc75c943819193161ea
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225809"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Baixe e instale o Skype para módulo Business Connector Online

O Skype para módulo Business Connector Online inclui o cmdlet **New-CsOnlineSession** , que permite a criação de uma sessão remota do Windows PowerShell que se conecta ao Skype para negócios Online. Neste módulo, o que é suportado apenas em computadores de 64 bits (consulte [configurar seu computador e Skype para gerenciamento de negócios Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações), podem ser baixados do Microsoft Download Center em [https://www.microsoft.com/en-us/download/details.aspx?id=39366](https://www.microsoft.com/en-us/download/details.aspx?id=39366). Baixe o arquivo SkypeOnlinePowershell.exe e conclua o procedimento a seguir:
  
1. Duas vezes no arquivo de **SkypeOnlinePowershell.exe** .
    
2. No Skype para Business Online, o Assistente de instalação do Windows PowerShell, na página **Termos de licença para Software Microsoft** , selecione **eu aceito os termos do contrato de licença**e, em seguida, clique em **instalar**. Se a caixa de diálogo **Controle de conta de usuário** for exibida, clique em **Sim** para continuar a instalação.
    
3. Na página **concluído o Skype para negócios Online, o módulo do Windows PowerShell** , clique em **Concluir**.
    
O programa de instalação copia o Skype para módulo Business Connector Online (e o cmdlet **New-CsOnlineSession** ) ao seu computador. Para acessar o módulo, iniciar uma sessão do Windows PowerShell sob as credenciais de administrador e, em seguida, execute o seguinte comando:
  
```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
```

Se você não quiser digitar esse comando sempre que você iniciar o Windows PowerShell, você pode adicionar o comando ao seu perfil do Windows PowerShell. Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:
  
```
notepad.exe $profile
```

 Quando o bloco de notas for exibida, adicione a seguinte linha ao final dos comandos que já estão no perfil (se houver):
  
```
Import-Module SkypeOnlineConnector
```

Salve o arquivo. Na próxima vez que você inicia o Windows PowerShell, o Skype para módulo Business Connector Online será importado automaticamente. Esteja ciente de que você receberá uma mensagem de erro e o módulo não será carregado, se você não estiver executando o Windows PowerShell sob as credenciais de administrador.
  
Além de instalar o Skype para módulo Business Connector Online, SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a identidade serviço cliente Runtime biblioteca (IDCRL), usado para lidar com a autenticação de cliente para Skype para negócios Online; 2) o .NET framework 4.5; e, 3) o pacote Microsoft Visual C++ 2012 redistribuível (x64) (versão 11.0.50727). .NET framework 4.5 fornece a infraestrutura usada para a criação e execução de aplicativos do .NET, incluindo o Windows PowerShell. O pacote redistribuível do Visual C++ instala os componentes de tempo de execução do Visual C++ para computadores que não possuem o Microsoft Visual Studio 2012 instalado.
  
Para verificar o número da versão do módulo conector que está instalado atualmente no seu computador, abra o painel de controle, abra **programas e recursos**e verifique o número de versão para o **Skype para negócios Online, o módulo do Windows PowerShell**.
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador e Skype para gerenciamento online de negócios usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
