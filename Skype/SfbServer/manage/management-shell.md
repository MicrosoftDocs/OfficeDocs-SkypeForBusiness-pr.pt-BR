---
title: Shell de Gerenciamento do Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Shell de gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento do servidor. Ele foi criado no Windows PowerShell e inclui um conjunto abrangente de cmdlets de administração e gerenciamento que são específicos do Skype e dos produtos herdados do Lync Server.
ms.openlocfilehash: ce031b15e2146036d77c7336aa9c2b73f000fe4a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279589"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server
 
O Shell de gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento do servidor. Ele foi criado no Windows PowerShell e inclui um conjunto abrangente de cmdlets de administração e gerenciamento que são específicos do Skype e dos produtos herdados do Lync Server.
  
O Windows PowerShell permite que você gerencie aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos de produtos e uma linguagem de script completa. O Windows PowerShell foi introduzido pela primeira vez como uma versão disponível para download para o sistema operacional Windows, em 2006, e foi incorporado como a interface de linha de comando para a capacidade de gerenciamento do Microsoft Exchange Server 2007. Ele foi incorporado à maioria dos produtos de servidor da Microsoft, incluindo os servidores do Lync e do Skype, começando com o Lync Server 2010. Há mais de 700 cmdlets do Lync e do Skype específicos disponíveis no Shell de gerenciamento do Skype for Business Server.
  
> [!NOTE]
> A referência do cmdlet do Skype for Business mudou para docs.microsoft.com. Ao clicar nos links abaixo, você será direcionado para a nova página docs.microsoft.com. O conteúdo agora está aberto e disponível para contribuições da comunidade através do GitHub. Tem interesse em contribuir? Confira o LEIAme no repositório aqui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
O Skype for Business Server vem com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de gerenciamento do Skype for Business Server. Você pode obter ajuda para um cmdlet diretamente a partir da linha de comando digitando um comando similar ao seguinte:
  
```
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**. Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.
  
Para recuperar uma lista completa dos cmdlets disponíveis para gerenciamento do Skype for Business Server, digite o seguinte no prompt de comando do shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



O que se deve saber sobre o Windows PowerShell no Skype for Business Server:
  
- Para executar os cmdlets do Skype for Business Server, abra o Shell de gerenciamento do Skype for Business Server.
    
    > [!CAUTION]
    > Se você abrir uma janela do Windows PowerShell em vez do Shell de gerenciamento do Skype for Business Server, por padrão, talvez não seja possível executar os cmdlets do Skype. Para executar cmdlets do Skype for Business Server no Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- O Shell de gerenciamento do Skype for Business Server é instalado automaticamente em cada servidor front-end da edição do Skype for Business Server Enterprise ou Standard Edition.
    
- Você pode atualizar o conteúdo da ajuda do Shell de gerenciamento do Skype for Business Server executando o cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . O cmdlet Update-Help baixa e instala os arquivos de ajuda mais recentes disponíveis para todos os módulos instalados em seu computador, incluindo atualizações para cmdlets do Skype for Business.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados no seu Skype for Business Server. Se quiser atualizar apenas alguns módulos, você pode usar o parâmetro _Module_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza somente o módulo Skype for Business.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Se precisar atualizar a ajuda em servidores que não estão conectados à Internet, você pode usar o cmdlet de [salvar-ajuda](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obter a versão mais recente da ajuda e salvá-la em um local especificado. Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _-Caminho_de_Origem_ em servidores que não estão conectados à Internet para obter a ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e, em seguida, atualizar a ajuda do módulo do Skype for Business a partir do compartilhamento de arquivos.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [sobre a ajuda atualizável](https://technet.microsoft.com/library/hh847735.aspx).
    
    > [!NOTE]
    > Se você estiver usando o PowerShell remotamente, talvez seja necessário permitir a comunicação por meio de um firewall. Para saber mais sobre as portas que o PowerShell Remoting usa, confira [qual porta o PowerShell Remoting usa?](https://blogs.technet.microsoft.com/christwe/2012/06/20/what-port-does-powershell-remoting-use/).
    

