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
description: O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidores. Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos do Skype e dos produtos de servidor herdados do Lync.
ms.openlocfilehash: 24da9ac341129239399ea17218be8547f3549d6f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118580"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server
 
O Shell de Gerenciamento do Skype for Business Server fornece a interface de linha de comando para administração e gerenciamento de servidores. Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos do Skype e dos produtos de servidor herdados do Lync.
  
Windows PowerShell permite gerenciar aplicativos Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos do produto e um idioma de script completo. Windows PowerShell foi introduzida pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporada como a interface de linha de comando para gerenciar o Microsoft Exchange Server 2007. Ele foi incorporado à maioria dos produtos do Microsoft Server, incluindo servidores Lync e Skype a partir do Lync Server 2010. Há mais de 700 cmdlets específicos do Lync e do Skype disponíveis no Shell de Gerenciamento do Skype for Business Server.
  
> [!NOTE]
> A referência de cmdlet do Skype for Business foi movida para docs.microsoft.com. Clicar nos links abaixo o levará à nova página docs.microsoft.com. O conteúdo agora está aberto e disponível para contribuições da comunidade por meio do GitHub. Interessado em contribuir? Confira o README no repo aqui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
O Skype for Business Server vem com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de Gerenciamento do Skype for Business Server. Você pode recuperar ajuda para um cmdlet diretamente da linha de comando digitando um comando semelhante ao seguinte:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**. Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.
  
Para recuperar uma lista completa de cmdlets disponíveis para gerenciar o Skype for Business Server, digite o seguinte no prompt de comando do shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



O que saber sobre Windows PowerShell no Skype for Business Server:
  
- Para executar os cmdlets do Skype for Business Server, abra o Shell de Gerenciamento do Skype for Business Server.
    
    > [!CAUTION]
    > Se você abrir uma Windows PowerShell em vez do Shell de Gerenciamento do Skype for Business Server, por padrão, talvez não seja possível executar os cmdlets do Skype. Para executar cmdlets do Skype for Business Server de dentro Windows PowerShell, digite o seguinte no prompt de comando Windows PowerShell: >  `Import-Module SkypeforBusiness`
  
- O Shell de Gerenciamento do Skype for Business Server é instalado automaticamente em todos os servidores front-end do Skype for Business Server Enterprise Edition ou no servidor Standard Edition.
    
- Você pode atualizar o conteúdo da ajuda do Shell de Gerenciamento do Skype for Business Server executando o cmdlet [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) O Update-Help cmdlet baixa e instala os arquivos de ajuda mais novos disponíveis para todos os módulos instalados em seu computador, incluindo atualizações para cmdlets do Skype for Business.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados em seu Skype for Business Server. Se você quiser atualizar apenas determinados módulos, poderá usar o parâmetro _Module_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza apenas o módulo Skype for Business.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se você precisar atualizar a Ajuda em servidores que não estão conectados à Internet, use o cmdlet Save-Help para obter a versão mais recente da ajuda e [salvá-la](/powershell/module/microsoft.powershell.core/save-help) em um local especificado. Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _-SourcePath_ em servidores não conectados à Internet para obter a ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e, em seguida, atualizar a ajuda para o módulo Skype for Business do compartilhamento de arquivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).
    
    > [!NOTE]
    > Se você estiver usando o PowerShell remotamente, talvez seja necessário permitir a comunicação por meio de um firewall. Para saber mais sobre as portas que o PowerShell remoting usa, consulte [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).
