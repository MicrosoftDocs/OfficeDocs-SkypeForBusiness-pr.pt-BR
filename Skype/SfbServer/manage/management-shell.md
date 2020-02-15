---
title: Shell de Gerenciamento do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Shell de gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidor. Ele é criado no Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos para o Skype e produtos herdados do Lync Server.
ms.openlocfilehash: 085c8f4a8a454f97dc4fbc640a6f5c8a70baec31
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044253"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server
 
O Shell de gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidor. Ele é criado no Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos para o Skype e produtos herdados do Lync Server.
  
O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos do produto e uma linguagem de script completa. O Windows PowerShell foi introduzido pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para a capacidade de gerenciamento do Microsoft Exchange Server 2007. Ele foi incorporado à maioria dos produtos de servidor da Microsoft, incluindo os servidores Lync e Skype, começando com o Lync Server 2010. Há mais de 700 cmdlets específicos do Lync e do Skype disponíveis no Shell de gerenciamento do Skype for Business Server.
  
> [!NOTE]
> A referência de cmdlet do Skype for Business foi movida para o docs.microsoft.com. Clicando nos links abaixo, você será retirado da nova página do docs.microsoft.com. O conteúdo agora é aberto e está disponível para contribuições da Comunidade por meio do GitHub. Interessado em contribuir? Confira o LEIAme no repositório aqui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
O Skype for Business Server é fornecido com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de gerenciamento do Skype for Business Server. Você pode recuperar a ajuda para um cmdlet diretamente da linha de comando, digitando um comando semelhante ao seguinte:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**. Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.
  
Para recuperar uma lista completa dos cmdlets disponíveis para gerenciar o Skype for Business Server, digite o seguinte no prompt de comando do Shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Coisas que você precisa saber sobre o Windows PowerShell no Skype for Business Server:
  
- Para executar os cmdlets do Skype for Business Server, abra o Shell de gerenciamento do Skype for Business Server.
    
    > [!CAUTION]
    > Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Skype for Business Server, por padrão, talvez não seja possível executar os cmdlets do Skype. Para executar os cmdlets do Skype for Business Server de dentro do Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- O Shell de gerenciamento do Skype for Business Server é instalado automaticamente em todos os servidores front-end do Skype for Business Server Enterprise Edition ou Standard Edition.
    
- Você pode atualizar o conteúdo da ajuda do Shell de gerenciamento do Skype for Business Server executando o cmdlet [Update-Help](https://technet.microsoft.com/library/hh849720.aspx) . O cmdlet Update-Help baixa e instala os arquivos de ajuda mais recentes disponíveis para todos os módulos instalados no computador, incluindo atualizações para os cmdlets do Skype for Business.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados no Skype for Business Server. Se quiser atualizar apenas determinados módulos, você pode usar o parâmetro _Module_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza somente o módulo Skype for Business.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se for necessário atualizar a ajuda nos servidores que não estão conectados à Internet, você poderá usar o cmdlet [Save-Help](https://technet.microsoft.com/library/hh849724.aspx) para obter a versão mais recente da ajuda e salvá-la em um local especificado. Você pode usar o cmdlet **Update-Help** com o parâmetro _-SourcePath_ nos servidores que não estão conectados à Internet para obter a ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e, em seguida, atualizar a ajuda para o módulo do Skype for Business a partir do compartilhamento de arquivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [sobre a ajuda atualizável](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Se você estiver usando o PowerShell remotamente, talvez precise permitir a comunicação através de um firewall. Para saber mais sobre as portas de uso remoto do PowerShell, confira [qual porta o PowerShell usa de modo remoto?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

