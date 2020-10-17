---
title: Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online
description: Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business online.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Windows PowerShell cmdlets, parameters, and parameter values
ms:assetid: 04615700-099f-4ac5-a801-ddeffccb9e4f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362765(v=OCS.15)
ms:contentKeyID: 56558799
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b1500713a02f85384be5a9cd9a7338b58d3c365f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555447"
---
# <a name="windows-powershell-cmdlets-parameters-and-parameter-values-in-skype-for-business-online"></a>Cmdlets, parâmetros e valores de parâmetro do Windows PowerShell no Skype for Business Online

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="https://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-05_

Se você estiver familiarizado com a janela de comando encontrada em todas as versões do Windows (ou se estiver familiarizado com o MS-DOS), terá uma partida de início quando se trata de aprender a usar o Windows PowerShell. Na janela de comando, digite um comando e pressione ENTER. Em resposta, o computador executa um comando ou um arquivo executável. Por exemplo, para retornar informações sobre todos os arquivos e pastas no diretório atual, digite este comando no prompt de comando e pressione ENTER:

```console
dir
```

Por sua vez, você obtém informações sobre todos os arquivos e pastas no diretório atual:

```console
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

Este é um exemplo de um resultado quando você digita apenas o nome de um comando ou um arquivo executável. No entanto, muitos dos comandos executados dentro da janela de comando também aceitam *argumentos*. Argumentos são partes adicionais de informações que são passadas para o comando, que modificam o comportamento do comando. Por exemplo, se você quisesse ver os nomes dos arquivos e pastas no diretório atual — não há outras informações, como o tamanho do arquivo ou pasta, ou a data e hora em que a pasta ou pasta foi criada. Nesse caso, você deve acrescentar o argumento **/b** ao executar o comando dir:

```console
dir /b
```

Quando você inclui o argumento **/b** , o comando **dir** retorna apenas os nomes das pastas e dos arquivos encontrados no diretório atual:

```console
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
```

No comando anterior, o argumento **/b** é a única informação necessária para limitar os dados retornados aos nomes de arquivos e pastas. Isso geralmente é o caso com comandos de linha de comando: a mera presença de um argumento é tudo o que é necessário para alterar o comportamento do comando. (Ou seja, você inclui o argumento **/b** para ocultar informações adicionais ou exclui o argumento **/b** para mostrar as informações extras.) Em outras ocasiões, no entanto, você deve especificar um *valor de argumento*. Um valor de argumento é uma informação adicional passada para o próprio argumento. Por exemplo, o argumento **/o** permite que você especifique como deseja que o comando dir Classifique os dados retornados. Entre outras opções, você pode usar o valor de argumento **e** para classificar por extensão de arquivo ou o valor de argumento **s** para classificar por tamanho de arquivo. Por exemplo, esse comando classifica os dados retornados por extensão de arquivo. Observe como o valor de argumento **e** é incluído imediatamente após o argumento **/o** :

```console
dir /oe
```

Usando nossa pasta de exemplo, os dados retornados terão a seguinte aparência, com os arquivos classificados alfabeticamente por extensão de arquivo:

```console
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

```console
setup.doc  
RHDSetup.exe  
pldok.log
```

Embora o Windows PowerShell use uma terminologia diferente, a abordagem básica para trabalhar com o Windows PowerShell é o mesmo que trabalhar com a janela de comando: você digita comandos, inclui argumentos e valores de argumentos conforme necessário e, em seguida, pressiona ENTER para executar esses comandos. Como observado, no entanto, o Windows PowerShell usa uma terminologia diferente da usada pelo shell de comando. No Windows PowerShell, os comandos executados são conhecidos como *cmdlets*. Por sua vez, os argumentos passados para um cmdlet são conhecidos como *parâmetros*, e os valores passados para um parâmetro são conhecidos como *valores de parâmetro*.

As definições anteriores são um pouco simplificadas. Os cmdlets são, basicamente, aplicativos que podem ser executados apenas de dentro do ambiente do Windows PowerShell. No entanto, você também pode executar outros comandos e aplicativos de dentro do Windows PowerShell, incluindo a maioria dos comandos e aplicativos que podem ser executados a partir de uma janela de comando. Por exemplo, se você deseja iniciar o bloco de notas no Windows PowerShell, tudo o que precisa fazer é digitar o seguinte e pressionar ENTER:

```console
notepad.exe
```

No entanto, quando se trata de gerenciar o Skype for Business Online, a maioria dos administradores confiará nos cmdlets do Windows PowerShell para executar tarefas administrativas. No momento, há poucos outros tipos de comandos ou aplicativos que podem ser usados para gerenciar o Skype for Business online. Às vezes, os cmdlets do Skype for Business Online podem ser usados sem nenhum argumento adicional (, conforme observado, os argumentos são conhecidos como parâmetros no Windows PowerShell). Por exemplo, o comando a seguir chama o cmdlet [Get-CsOnlineUser](https://technet.microsoft.com/library/JJ994026(v=OCS.15)) sem parâmetros adicionais. Em si, o comando retorna informações sobre todos os seus usuários do Skype for Business Online:

```powershell
Get-CsOnlineUser
```

No entanto, a maioria dos cmdlets do Skype for Business online também aceita parâmetros (e valores de parâmetro). Considere o seguinte comando:

```powershell
Get-CsOnlineUser -Identity "kenmyer@litwareinc.com"
```

Este comando consiste em três partes:

  - O cmdlet **Get-CsOnlineUser**.

  - O parâmetro Identity. Observe que, no Windows PowerShell, os parâmetros são sempre precedidas por um traço (-). Isso significa que, para esse mesmo cmdlet, o parâmetro UnassignedUser seria indicado usando esta sintaxe:
    
    ```powershell
    -UnassignedUser
    ```
    
    Isso é útil para saber, não apenas porque os parâmetros devem ser precedidas por um traço, mas também porque isso difere da janela de comando, onde os argumentos são precedidas usando uma barra (/):
    
    ```console
    /b
    ```

  - O valor do parâmetro **kenmyer@litwareinc.com**.

Esse comando, incidentalmente, retorna informações sobre um usuário específico: o usuário com a identidade kenmyer@litwareinc.com.

<div>

## <a name="see-also"></a>Confira também


[Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://technet.microsoft.com/library/Dn362785(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

