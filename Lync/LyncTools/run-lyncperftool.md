---
title: Executar LyncPerfTool
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Run LyncPerfTool
ms:assetid: f2fd1940-d744-47b5-b299-04a914039182
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945612(v=OCS.15)
ms:contentKeyID: 51541437
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5325a3dab058132dfe6bbf8558ebe771450f36ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146284"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Executar LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

Antes de executar a ferramenta de estresse e desempenho do Lync Server 2013 (LyncPerfTool. exe), você deve criar usuários, contatos e cenários. Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [Create Users and contacts](create-users-and-contacts.md) e [Configure User Profile](configure-user-profile.md). A execução dessas ferramentas também gerará um arquivo que executará o LyncPerfTool. exe como parte de um arquivo em lote com os parâmetros necessários incluídos.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Executando a ferramenta de estresse e desempenho do Lync Server 2013

A ferramenta UserProfileGenerator. exe cria um arquivo em lotes que permite que você execute o LyncPerfTool. exe registrando os contadores de desempenho do LyncPerfTool e carregando o arquivo de configuração XML. O arquivo em lotes executa uma instância do LyncPerfTool. exe por arquivo de configuração. Para executar o arquivo em lotes, faça o seguinte:

1.  Copie a pasta que contém as pastas e os arquivos de configuração para o diretório que contém o LyncStressTool. exe em cada computador cliente. (Por exemplo, se você gerou os arquivos de configuração na pasta chamada 1,28\_13.16.16, copie essa pasta para a pasta que contém o LyncPerfTool. exe em cada cliente.)

2.  Navegue até a pasta de cliente numerada apropriadamente e execute o script de lote do RunClient. Você pode simplesmente clicar duas vezes no arquivo em lotes no Windows Explorer e ele executará todos os arquivos de configuração desse número de cliente. Você também pode executar o script a partir da pasta de cliente apropriada usando a seguinte sintaxe:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Para executar o LyncPerfTool. exe diretamente, abra um prompt de comando e digite o seguinte comando na linha de comando (ao fazer isso pela primeira vez, não se esqueça de registrar os contadores de desempenho regsvr32/i/n/s LyncPerfToolPerf. dll, conforme mostrado na observação mais adiante neste tópico): LyncPerfTool. exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Para que a ferramenta exiba os valores no arquivo de configuração, inclua o parâmetro/displayfile no comando anterior, da seguinte maneira:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Para finalizar o processo, pressione CTRL + C.

<div>


> [!NOTE]  
> Antes de executar o LyncPerfTool diretamente, você deve registrar os contadores de desempenho. Insira o seguinte comando para registrar contadores de desempenho:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Todas as instâncias de LyncPerfTool. exe iniciadas imediatamente começarão a se conectar aos usuários, normalmente a uma taxa de um usuário por segundo. A taxa de entrada de pico do pool de usuários é de cerca de 12 por segundo. Isso significa que você não deve iniciar mais de 12 instâncias do LyncPerfTool ao mesmo tempo, enquanto os usuários ainda estão entrando. 1000 os usuários levarão cerca de 20 minutos para entrar totalmente, de uma por segundo.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar usuários e contatos](create-users-and-contacts.md)  
[Configurar perfil de usuário](configure-user-profile.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

