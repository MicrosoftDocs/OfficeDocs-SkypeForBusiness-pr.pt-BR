---
title: Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce954eff790bae6974f144360637d6061318d3d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837060"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-05_

Se você estiver familiarizado com a janela de comando encontrada em todas as versões do Windows (ou se estiver familiarizado com o MS-DOS), terá um início para aprender como usar o Windows PowerShell. Na janela de comando, digite um comando e pressione ENTER. Em resposta, o computador executa um comando ou um arquivo executável. Por exemplo, para retornar informações sobre todos os arquivos e pastas do diretório atual, digite este comando no prompt de comando e pressione ENTER:

    dir

Em seguida, você recebe informações sobre todos os arquivos e pastas no diretório atual:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/13/2013  02:53 PM                 117   pldok.log
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/21/2013  03:37 PM            207   setup.doc
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Esse é um exemplo de um resultado quando você digita somente o nome de um comando ou um arquivo executável. No entanto, muitos dos comandos executados na janela de comando também aceitam *argumentos*. Os argumentos são partes adicionais de informações que são transmitidas ao comando, que modificam o comportamento do comando. Por exemplo, se você quisesse ver somente os nomes dos arquivos e da pasta no diretório atual, não há outras informações, como o tamanho do arquivo ou da pasta, ou a data e a hora em que a pasta ou pasta foi criada. Nesse caso, você deve acrescentar o argumento **/b** ao executar o comando dir:

    dir /b

Quando você inclui o argumento **/b** , o comando **dir** relata somente os nomes das pastas e dos arquivos encontrados no diretório atual:

    Deploy
    Intel
    PerfLogs
    Program Files
    Program Files (x86)
    Users
    Windows
    pldok.log
    RHDSetup.exe
    setup.doc

No comando anterior, o argumento **/b** é a única informação necessária para limitar os dados retornados a nomes de arquivos e pastas. Geralmente, esse é o caso com comandos de linha de comando: a mera presença de um argumento é tudo o que é necessário para alterar o comportamento do comando. (Ou seja, você inclui o argumento **/b** para ocultar informações adicionais ou exclui o argumento **/b** para mostrar as informações extras.) Em outras ocasiões, no entanto, você deve especificar um *valor de argumento*. Um valor de argumento são informações adicionais passadas para o argumento em si. Por exemplo, o argumento **/o** permite que você especifique como deseja que o comando dir Classifique os dados retornados. Entre outras opções, você pode usar o valor de argumento **e** para classificar por extensão de arquivo ou o valor de argumento **s** para classificar por tamanho do arquivo. Por exemplo, esse comando classifica os dados retornados por extensão de arquivo. Observe como o valor de argumento **e** é incluído imediatamente após o argumento **/o** :

    dir /oe

Usando nossa pasta de exemplo, os dados retornados terão a seguinte aparência, com os arquivos classificados em ordem alfabética pela extensão de arquivo:

``` 
    Directory: C:\

03/21/2013  03:39 PM    <DIR>          Deploy
03/21/2013  02:55 PM    <DIR>          Intel
07/26/2012  12:33 AM    <DIR>          PerfLogs
04/10/2013  10:29 AM    <DIR>          Program Files
04/08/2013  10:28 AM    <DIR>          Program Files (x86)
03/22/2013  08:44 AM    <DIR>          Users
04/11/2013  03:00 PM    <DIR>              Windows
03/21/2013  03:37 PM            207   setup.doc
03/21/2013  03:35 PM                 769   RHDSetup.exe
03/13/2013  02:53 PM                 117   pldok.log
              3 File(s)        1,093 bytes
              7 Dir(s)21,386,002,432 bytes free
```

Ou, para ajudá-lo a identificar exatamente o que estamos falando:

configuração. **documentação**  
RHDSetup. **exe**  
pldok. **efetua**

Embora o Windows PowerShell use uma terminologia diferente, a abordagem básica para trabalhar com o Windows PowerShell é a mesma que trabalhar com a janela de comando: você digita comandos, inclui argumentos e valores de argumento conforme necessário e, em seguida, pressiona ENTER para executar esses comandos. Como observado, no entanto, o Windows PowerShell usa uma terminologia diferente do que o Shell de comando usa. No Windows PowerShell, os comandos que você executa são conhecidos ** como cmdlets. Por sua vez, os argumentos passados para um cmdlet são conhecidos como *parâmetros*, e os valores passados para um parâmetro são conhecidos como *valores de parâmetro*.

As definições anteriores são um pouco simplificadas. Cmdlets são essencialmente mini-aplicativos que podem ser executados somente de dentro do ambiente do Windows PowerShell. No entanto, você também pode executar outros comandos e aplicativos no Windows PowerShell, incluindo a maioria dos comandos e aplicativos que podem ser executados a partir de uma janela de comando. Por exemplo, se você quiser iniciar o bloco de notas no Windows PowerShell, tudo o que precisa fazer é digitar o seguinte e pressionar ENTER:

    notepad.exe

No entanto, ao gerenciar o Skype for Business Online, a maioria dos administradores confiará nos cmdlets do Windows PowerShell para executar tarefas administrativas. No momento, há poucos outros tipos de comandos ou aplicativos que podem ser usados para gerenciar o Skype for Business online. Às vezes, os cmdlets do Skype for Business Online podem ser usados sem nenhum argumento adicional (, como observado, os argumentos são conhecidos como parâmetros no Windows PowerShell). Por exemplo, o comando a seguir chama o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/en-us/library/JJ994026(v=OCS.15)) sem parâmetros adicionais. Por si só, o comando retorna informações sobre todos os seus usuários do Skype for Business Online:

    Get-CsOnlineUser

No entanto, a maioria dos cmdlets do Skype for Business online também aceita parâmetros (e valores de parâmetro). Considere o seguinte comando:

    Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"

Este comando consiste em três partes:

  - O cmdlet **Get-CsOnlineUser**.

  - O parâmetro Identity. Observe que, no Windows PowerShell, os parâmetros são sempre precedidas por um traço (-). Isso significa que, para esse mesmo cmdlet, o parâmetro UnassignedUser seria indicado usando esta sintaxe:
    
        -UnassignedUser
    
    Isso é útil, não apenas porque os parâmetros devem ser precedidas com um traço, mas também porque isso é diferente da janela de comando, em que os argumentos são precedidas usando uma barra (/):
    
    ``` 
    /b
    ```

  - O valor do parâmetro **kenmyer@litwareinc.com**.

Esse comando, incidentalmente, retorna informações sobre um usuário específico: o usuário com a identidade, kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Confira também


[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/en-us/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

