---
title: Shell de Gerenciamento do Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Skype for Business Server Shell de Gerenciamento fornece a interface de linha de comando para administração e gerenciamento de servidores. Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos para Skype e produtos de servidor herdados do Lync.
ms.openlocfilehash: 2d8caadfb1dfe80af74861cf20fa0b155dd20d1a
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750310"
---
# <a name="skype-for-business-server-management-shell"></a>Shell de Gerenciamento do Skype for Business Server
 
O Skype for Business Server Shell de Gerenciamento fornece a interface de linha de comando para administração e gerenciamento de servidores. Ele é criado com base Windows PowerShell e inclui um conjunto abrangente de cmdlets de gerenciamento e administração que são específicos para Skype e produtos de servidor herdados do Lync.
  
Windows PowerShell permite gerenciar aplicativos Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos do produto e um idioma de script completo. Windows PowerShell foi introduzida pela primeira vez como uma versão baixável para o sistema operacional Windows no final de 2006 e foi incorporada como a interface de linha de comando para gerenciar o Microsoft Exchange Server 2007. Ele foi incorporado à maioria dos produtos do Microsoft Server, incluindo o Lync e Skype a partir do Lync Server 2010. Há mais de 700 cmdlets Skype Lync específicos disponíveis no Shell de Gerenciamento Skype for Business Server.
  
> [!NOTE]
> Skype for Business referência de cmdlet foi movida para docs.microsoft.com. Clicar nos links abaixo o levará à nova página docs.microsoft.com. O conteúdo agora está aberto e disponível para contribuições da comunidade por meio GitHub. Interessado em contribuir? Confira o README no repo aqui: [https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype for Business Server com mais de 700 cmdlets que permitem que os administradores gerenciem o Skype for Business Server usando o Shell de Gerenciamento Skype for Business Server. Você pode recuperar ajuda para um cmdlet diretamente da linha de comando digitando um comando semelhante ao seguinte:
  
```PowerShell
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a ajuda completa disponível para o cmdlet **New-CsVoicePolicy**. Para exibir a ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** pelo nome do cmdlet para o qual você deseja recuperar a ajuda.
  
Para recuperar uma lista completa de cmdlets disponíveis para gerenciar Skype for Business Server, digite o seguinte no prompt de comando do shell: 
  
```PowerShell
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Coisas a saber sobre Windows PowerShell em Skype for Business Server:
  
- Para executar os cmdlets Skype for Business Server, abra o Shell Skype for Business Server Gerenciamento.
    
    > [!CAUTION]
    > Se você abrir uma Windows PowerShell em vez do Shell de Gerenciamento Skype for Business Server, por padrão, talvez não seja possível executar os cmdlets Skype de gerenciamento. Para executar Skype for Business Server cmdlets de dentro Windows PowerShell, digite o seguinte no prompt de comando Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype for Business Server O Shell de Gerenciamento é instalado automaticamente em todos os Skype for Business Server Edição Enterprise servidor front-end ou Edição Standard servidor.
    
- Você pode atualizar o Skype for Business Server conteúdo de ajuda do Shell de Gerenciamento executando o cmdlet [Update-Help.](/powershell/module/microsoft.powershell.core/update-help) O cmdlet Update-Help baixa e instala os arquivos de ajuda mais novos disponíveis para todos os módulos instalados em seu computador, incluindo atualizações para cmdlets Skype for Business.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados em seu Skype for Business Server. Se você quiser atualizar apenas determinados módulos, poderá usar o parâmetro _Module_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza apenas o Skype for Business módulo.
    
  ```PowerShell
  Update-Help -Module SkypeforBusiness
  ```

    Se você precisar atualizar a Ajuda em servidores que não estão conectados à Internet, use o cmdlet Save-Help para obter a versão mais recente da ajuda e [salvá-la](/powershell/module/microsoft.powershell.core/save-help) em um local especificado. Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _-SourcePath_ em servidores não conectados à Internet para obter a ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda em um compartilhamento de arquivos de rede e atualizar a ajuda para o módulo Skype for Business do compartilhamento de arquivos.
    
  ```PowerShell
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
  // Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [About Updatable Help](/powershell/module/microsoft.powershell.core/about/about_updatable_help).
    
    > [!NOTE]
    > Se você estiver usando o PowerShell remotamente, talvez seja necessário permitir a comunicação por meio de um firewall. Para saber mais sobre as portas que o PowerShell remoting usa, consulte [What Port Does PowerShell Remoting Use?](/archive/blogs/christwe/what-port-does-powershell-remoting-use).
