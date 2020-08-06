---
title: Baixar e instalar o módulo do conector do Skype for Business Online
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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Baixe, instale e use o conector Skype for Business online para criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online.
ms.openlocfilehash: 8e9441e152314fafdee8fe8292d0b62a1b17d6da
ms.sourcegitcommit: 5bcc25fb20ed72bac02bc78e40b591e67eb58686
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2020
ms.locfileid: "46564770"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Baixar e instalar o módulo do conector do Skype for Business Online

> [!NOTE]
> A versão mais recente do [Teams PowerShell Public Preview](https://www.powershellgallery.com/packages/MicrosoftTeams/) está integrada ao conector do Skype for Business Online, fornecendo um único módulo para gerenciamento do teams PowerShell.

O módulo conector do Skype for Business Online inclui o cmdlet **New-CsOnlineSession** , que permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business online. Este módulo, que tem suporte apenas em computadores de 64 bits (consulte [configurar seu computador para gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações) pode ser baixado no centro de download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Baixe o arquivo SkypeOnlinePowershell.exe e, em seguida, conclua o seguinte procedimento:
  
1. Clique duas vezes no arquivo **SkypeOnlinePowershell.exe** .
    
2. No Skype for Business Online, assistente de configuração do Windows PowerShell, na página **termos de licença para software da Microsoft** , selecione **aceito os termos do contrato de licença**e clique em **instalar**. Se a caixa de diálogo **controle de conta de usuário** for exibida, clique em **Sim** para continuar a instalação.
    
3. Na página **completada do Skype for Business Online, do módulo do Windows PowerShell** , clique em **concluir**.
    
O programa de instalação copia o módulo do conector do Skype for Business online (e o cmdlet **New-CsOnlineSession** ) para o seu computador. Para acessar o módulo, inicie uma sessão do Windows PowerShell em credenciais do administrador e execute o seguinte comando:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Se você não quiser digitar esse comando toda vez que iniciar o Windows PowerShell, poderá adicionar o comando ao seu perfil do Windows PowerShell. Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:
  
```PowerShell
notepad.exe $profile
```

 Quando o bloco de notas for exibido, adicione a seguinte linha na parte inferior dos comandos que já estão no perfil (se houver):
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Salve o arquivo. Da próxima vez que você iniciar o Windows PowerShell, o módulo do conector do Skype for Business online será importado automaticamente. Lembre-se de que você receberá uma mensagem de erro, e o módulo não será carregado, se você não estiver executando o Windows PowerShell em credenciais de administrador.
  
Além de instalar o módulo do conector Skype for Business Online, SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a IDCRL (biblioteca de tempo de execução do serviço de identidade), usada para manipular a autenticação do cliente para o Skype for Business Online; 2) .NET Framework 4,5; e 3) o pacote Microsoft Visual C++ 2012 Redistributable (x64) (versão 11.0.50727). O .NET Framework 4,5 fornece a infraestrutura usada para compilar e executar aplicativos .NET, incluindo o Windows PowerShell. O pacote redistribuível do Visual C++ instala componentes de tempo de execução do Visual C++ para computadores que não têm o Microsoft Visual Studio 2012 instalado.
  
Para verificar o número da versão do módulo conector que está instalado no seu computador, abra o painel de controle, abra **programas e recursos**e verifique o número da versão do **módulo do Windows PowerShell para o Skype for Business online**.
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para o gerenciamento do Skype for Business online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
