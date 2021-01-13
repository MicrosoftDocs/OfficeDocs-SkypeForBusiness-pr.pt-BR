---
title: Shell de Gerenciamento do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento do servidor. Ele foi criado com base no Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração específicos do Skype e dos produtos de servidor herdados do Lync.
ms.openlocfilehash: 0653faa542bc9bc579bd7617e40d3efed030569f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816531"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server
 
O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento do servidor. Ele foi criado com base no Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração específicos do Skype e dos produtos de servidor herdados do Lync.
  
O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. O Windows PowerShell foi introduzido pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para capacidade de gerenciamento do Microsoft Exchange Server 2007. Ele foi incorporado à maioria dos produtos do Microsoft Server, incluindo os servidores do Lync e do Skype a partir do Lync Server 2010. Há mais de 700 cmdlets específicos do Lync e do Skype disponíveis no Shell de Gerenciamento do Skype for Business Server.
  
> [!NOTE]
> A referência de cmdlet do Skype for Business foi movida para docs.microsoft.com. Clicar nos links abaixo levará você para a nova docs.microsoft.com página. O conteúdo agora está livre e disponível para contribuições da comunidade por meio do GitHub. Interessado em contribuir? Confira o README no repo aqui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
O Skype for Business Server vem com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server. Você pode recuperar a ajuda de um cmdlet diretamente da linha de comando digitando um comando semelhante ao seguinte:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**. Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.
  
Para recuperar uma lista completa de cmdlets disponíveis para gerenciar o Skype for Business Server, digite o seguinte no prompt de comando do shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informações sobre o Windows PowerShell no Skype for Business Server:
  
- Para executar os cmdlets do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.
    
    > [!CAUTION]
    > Se você abrir uma janela do Windows PowerShell em vez do Shell de Gerenciamento do Skype for Business Server, por padrão, talvez não consiga executar os cmdlets do Skype. Para executar os cmdlets do Skype for Business Server no Windows PowerShell, digite o seguinte no prompt de comando do Windows PowerShell: >  `Import-Module SkypeforBusiness`
  
- O Shell de Gerenciamento do Skype for Business Server é instalado automaticamente em cada servidor front-end do Skype for Business Server Enterprise Edition ou servidor Standard Edition.
    
- Você pode atualizar o conteúdo de ajuda do Shell de Gerenciamento do Skype for Business Server executando o cmdlet [Update-Help.](https://technet.microsoft.com/library/hh849720.aspx) O cmdlet Update-Help baixa e instala os arquivos de ajuda mais novos disponíveis para todos os módulos instalados em seu computador, incluindo atualizações para os cmdlets do Skype for Business.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados no Skype for Business Server. Se você quiser atualizar apenas determinados módulos, poderá usar o parâmetro _Module_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza apenas o módulo do Skype for Business.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se precisar atualizar a Ajuda em servidores que não estão conectados à Internet, você pode usar o cmdlet Save-Help para obter a versão mais recente da ajuda e [salvá-la](https://technet.microsoft.com/library/hh849724.aspx) em um local especificado. Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _-SourcePath_ em servidores não conectados à Internet para obter a ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e atualizar a ajuda para o módulo do Skype for Business do compartilhamento de arquivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [Sobre a Ajuda Atualizável.](https://technet.microsoft.com/library/hh847735.aspx)
    
    > [!NOTE]
    > Se você estiver usando o PowerShell remotamente, talvez seja necessário permitir a comunicação por meio de um firewall. Para saber mais sobre as portas que o PowerShell remoting usa, consulte [Qual porta o PowerShell Remoting Usa?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

