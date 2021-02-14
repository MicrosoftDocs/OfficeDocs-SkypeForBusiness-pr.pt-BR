---
title: Baixar e instalar o módulo Conector do Skype for Business Online
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
description: Baixe, instale e use o Skype for Business Online Connector para criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online.
ms.openlocfilehash: 3928e77e5bac77dbfe89f7be5e762dd0d8ff93eb
ms.sourcegitcommit: 1a31ff16b8218d30059f15c787e157d06260666f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47814560"
---
# <a name="download-and-install-the-skype-for-business-online-connector-module"></a>Baixar e instalar o módulo Conector do Skype for Business Online

> [!NOTE]
> A versão [pública mais recente do Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) é integrada ao Skype for Business Online Connector, fornecendo um único módulo para o gerenciamento do PowerShell do Teams.

O módulo Conector do Skype for Business Online inclui o cmdlet **New-CsOnlineSession,** que permite criar uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Este módulo, que tem suporte apenas em computadores de 64 bits (consulte Configurar seu computador para gerenciamento do Skype for Business Online usando [o Windows PowerShell](set-up-your-computer-for-windows-powershell.md) para obter mais informações), pode ser baixado do Centro de Download da Microsoft em [https://www.microsoft.com/download/details.aspx?id=39366](https://www.microsoft.com/download/details.aspx?id=39366) . Baixe o SkypeOnlinePowershell.exe arquivo e, em seguida, conclua o seguinte procedimento:
  
1. Clique duas vezes no **SkypeOnlinePowershell.exe** arquivo.
    
2. No Skype for Business Online, assistente de configuração do Windows PowerShell, na página Termos de Licença de Software da **Microsoft,** selecione Aceitar os termos no Contrato de Licença e **clique** em **Instalar.** Se a **caixa de diálogo Controle** de Conta de Usuário for exibida, clique em **Sim** para continuar a instalação.
    
3. Na página **Concluído do Skype for Business Online, módulo do Windows PowerShell,** clique em **Concluir.**
    
O programa de configuração copia o módulo Skype for Business Online Connector (e o cmdlet **New-CsOnlineSession)** para seu computador. Para acessar o módulo, inicie uma sessão do Windows PowerShell com as credenciais de administrador e execute o seguinte comando:
  
```PowerShell
Import-Module "C:\Program Files\Common Files\Skype for Business Online\Modules\SkypeOnlineConnector\SkypeOnlineConnector.psd1"
```

Se você não quiser digitar esse comando sempre que iniciar o Windows PowerShell, poderá adicionar o comando ao seu perfil do Windows PowerShell. Para fazer isso, digite o seguinte comando no prompt do Windows PowerShell e pressione ENTER:
  
```PowerShell
notepad.exe $profile
```

 Quando o Bloco de Notas for exibido, adicione a seguinte linha na parte inferior dos comandos que já estão no perfil (se for o caso):
  
```PowerShell
Import-Module SkypeOnlineConnector
```

Salve o arquivo. Na próxima vez que você iniciar o Windows PowerShell, o módulo Conector do Skype for Business Online será importado automaticamente. Esteja ciente de que você receberá uma mensagem de erro e o módulo não será carregado se você não estiver executando o Windows PowerShell sob credenciais de administrador.
  
Além de instalar o módulo Conector do Skype for Business Online, o SkypeOnlinePowershell.exe também instala três componentes adicionais: 1) a IDCRL (Identity Service Client Runtime Library), usada para lidar com a autenticação do cliente para o Skype for Business Online; 2) .NET Framework 4.5; e, 3) o pacote Microsoft Visual C++ 2012 Redistribuível (x64) (versão 11.0.50727). O .NET Framework 4.5 fornece a infraestrutura usada para criar e executar aplicativos .NET, incluindo o Windows PowerShell. O pacote Visual C++ Redistribuível instala componentes de tempo de execução do Visual C++ para computadores que não têm o Microsoft Visual Studio 2012 instalado.
  
Para verificar o número da versão do módulo Conector que está instalado no seu computador, abra o Painel de Controle, abra Programas e Recursos e verifique o número da versão do Skype for Business Online, módulo do **Windows PowerShell.**
  
## <a name="related-topics"></a>Tópicos relacionados
[Configurar seu computador para gerenciamento do Skype for Business Online usando o Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
