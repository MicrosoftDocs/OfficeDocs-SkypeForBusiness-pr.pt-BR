---
title: Shell de Gerenciamento do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 9/20/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 674b523b-c0b7-4ed6-9e67-afa6e8ac7e12
description: O Skype do Shell de gerenciamento do Business Server fornece a interface de linha de comando para gerenciamento e administração de servidor. Ele é baseado no Windows PowerShell e inclui um conjunto abrangente de gerenciamento e administração cmdlets específicos ao Skype e produtos de servidor herdados do Lync.
ms.openlocfilehash: e4eb5f183af29dd5f9932fb15cdb86a0f78e7840
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="skype-for-business-server-2015-management-shell"></a>Shell de Gerenciamento do Skype for Business Server 2015
 
O Skype do Shell de gerenciamento do Business Server fornece a interface de linha de comando para gerenciamento e administração de servidor. Ele é baseado no Windows PowerShell e inclui um conjunto abrangente de gerenciamento e administração cmdlets específicos ao Skype e produtos de servidor herdados do Lync.
  
Windows PowerShell permite gerenciar aplicativos da Microsoft a partir da linha de comando. Ele inclui um ambiente de linha de comando, comandos específicos de produtos e uma linguagem de script completa. Windows PowerShell foi introduzido primeiro como uma versão para download para o sistema operacional Windows no final de 2006 e foi incorporado como a interface de linha de comando para o gerenciamento do Microsoft Exchange Server 2007. Ele foi incorporado na maioria dos produtos Microsoft Server, incluindo servidores de Lync e Skype começando com o Lync Server 2010. Há mais de 700 cmdlets específicos do Lync e Skype disponíveis no Skype do Shell de gerenciamento do servidor de negócios.
  
> [!NOTE]
> Skype para referência de cmdlet Business foi movido para docs.microsoft.com. Clicando nos links a seguir o levará à nova página docs.microsoft.com. O conteúdo agora está aberto e disponível para contribuições da comunidade através do GitHub. Tem interesse em contribuir? Confira Leiame no repo aqui:[https://github.com/MicrosoftDocs/office-docs-powershell](https://github.com/MicrosoftDocs/office-docs-powershell)
  
Skype para Business Server 2015 é fornecido com mais de 700 cmdlets que permitem que administradores gerenciem Skype para Business Server usando o Skype do Shell de gerenciamento do servidor de negócios. Você pode obter ajuda para um cmdlet diretamente a partir da linha de comando digitando um comando similar ao seguinte:
  
```
Get-Help New-CsVoicePolicy -Full
```

O comando anterior recupera a Ajuda completa disponível para o cmdlet **New-CsVoicePolicy** . Para exibir a Ajuda para um cmdlet diferente, substitua **New-CsVoicePolicy** com o nome do cmdlet para o qual você deseja recuperar a Ajuda.
  
Para recuperar uma lista completa dos cmdlets disponíveis para gerenciamento do Skype for Business Server, digite o seguinte no prompt de comando do shell: 
  
```
Get-Command * -Module SkypeforBusiness -CommandType cmdlet
```



Informações importantes sobre o Windows PowerShell no Skype para Business Server:
  
- Para executar o Skype para cmdlets Business Server, abra o Skype do Shell de gerenciamento do servidor de negócios.
    
    > [!CAUTION]
    > Se você abrir uma janela do Windows PowerShell, em vez do Skype do Shell de gerenciamento do servidor de negócios, por padrão você pode não conseguir executar os cmdlets do Skype. Para executar o Skype para cmdlets do servidor de negócios de dentro do Windows PowerShell, primeiro digite o seguinte no prompt de comando do Windows PowerShell: >`Import-Module SkypeforBusiness`
  
- Skype do Shell de gerenciamento do servidor de negócios é instalado automaticamente em cada Skype para Business Server Enterprise Edition servidor Front-End ou servidor Standard Edition.
    
- Você pode atualizar o Skype para conteúdo de Ajuda do Shell de gerenciamento do Business Server executando o cmdlet [Update-Help](https://technet.microsoft.com/en-us/library/hh849720.aspx) . O cmdlet Update-Help baixa e instala os mais novos arquivos de ajuda disponíveis para todos os módulos instalados no computador, inclusive devido às Skype atualizações para cmdlets de negócios.
    
    Por padrão, o cmdlet **Update-Help** atualizará todos os módulos instalados no seu Skype para Business Server. Se você deseja atualizar apenas determinados módulos, você pode usar o parâmetro do _módulo_ para limitar o escopo do cmdlet. O exemplo a seguir atualiza apenas o Skype para módulo comercial.
    
  ```
  Update-Help -Module SkypeforBusiness
  ```

    Se você precisar atualizar a Ajuda em servidores que não estão conectados à internet, você pode usar o cmdlet [Salvar-Help](https://technet.microsoft.com/en-us/library/hh849724.aspx) para obter a versão mais recente da Ajuda e salvá-lo em um local especificado. Em seguida, você pode usar o cmdlet **Update-Help** com o parâmetro _- SourcePath_ nos servidores que não está conectado à internet para obter a Ajuda atualizada do local selecionado. O exemplo a seguir mostra como salvar os arquivos de ajuda para um compartilhamento de arquivo de rede e, em seguida, atualize a Ajuda para o Skype para módulo comercial do compartilhamento de arquivo.
    
  ```
  // Save the help files
   Save-Help -DestinationPath \\UpdateShare\HelpDownload
// Run Update-Help against the local help files
   Update-Help -Module SkypeforBusiness -SourcePath \\UpdateShare\HelpDownload
  ```

    Para obter informações mais detalhadas, consulte [Sobre ajuda atualizável](https://technet.microsoft.com/library/hh847735.aspx).
    

