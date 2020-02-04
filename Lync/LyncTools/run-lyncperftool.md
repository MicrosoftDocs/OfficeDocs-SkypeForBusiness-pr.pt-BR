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
ms.openlocfilehash: 29a36be8c6703dad52e6c36d363ae23013643bd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="run-lyncperftool"></a>Executar LyncPerfTool

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

Antes de executar a ferramenta de stress e desempenho do Lync Server 2013 (LyncPerfTool. exe), você deve criar usuários, contatos e cenários. Para obter detalhes sobre como usar as ferramentas para executar essas ações, consulte [criar usuários e contatos](create-users-and-contacts.md) e [Configurar o perfil do usuário](configure-user-profile.md). Executar essas ferramentas também irá gerar um arquivo que executará LyncPerfTool. exe como parte de um arquivo em lotes com os parâmetros necessários incluídos.

<div>

## <a name="running-the-lync-server-2013-stress-and-performance-tool"></a>Executando a ferramenta de stress e desempenho do Lync Server 2013

A ferramenta UserProfileGenerator. exe cria um arquivo em lotes que permite que você execute o LyncPerfTool. exe registrando os contadores de desempenho do LyncPerfTool e carregando o arquivo de configuração XML. O arquivo em lote executa uma instância do LyncPerfTool. exe por arquivo de configuração. Para executar o arquivo em lotes, faça o seguinte:

1.  Copie a pasta que contém os arquivos e pastas de configuração para o diretório que contém LyncStressTool. exe em cada computador cliente. (Por exemplo, se você gerou os arquivos de configuração na pasta chamado 1,28\_13.16.16, copie essa pasta para a pasta que contém LyncPerfTool. exe em cada cliente.)

2.  Navegue até a pasta de cliente numerada apropriadamente e execute o script em lotes RunClient. Basta clicar duas vezes no arquivo em lotes no Windows Explorer e ele executará todos os arquivos de configuração desse número de cliente. Você também pode executar o script da pasta de cliente apropriada usando a seguinte sintaxe:

    ```Batch
        RunClient0.bat "C:\Program Files\Microsoft Lync Server 2013\LyncStressAndPerfTool\LyncStress" 
    ```
Para executar o LyncPerfTool. exe diretamente, abra um prompt de comando e digite o seguinte comando na linha de comando (ao fazer isso pela primeira vez, certifique-se de registrar os contadores de desempenho regsvr32/i/n/s LyncPerfToolPerf. dll, como mostrar na observação mais adiante neste tópico): LyncPerfTool. exe/file:\<configXML\>
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml
```
Para que a ferramenta exiba os valores no arquivo de configuração, inclua o parâmetro/displayfile no comando anterior, como este:
```Powershell
    LyncPerfTool.exe /file:IM_client0.xml /displayfile
```
Para encerrar o processo, pressione CTRL + C.

<div>


> [!NOTE]  
> Antes de executar o LyncPerfTool diretamente, você deve registrar os contadores de desempenho. Digite o seguinte comando para registrar contadores de desempenho:



</div>

```Powershell
    regsvr32 /i /n /s LyncPerfToolPerf.dll
```
<div>


> [!NOTE]  
> Cada instância do LyncPerfTool. exe iniciada iniciará imediatamente a entrada de usuários, geralmente a uma taxa de um usuário por segundo. A taxa de conexão de usuários de pico para o pool é cerca de 12 a cada segundo. Isso significa que você não deve iniciar mais de 12 instâncias de LyncPerfTool ao mesmo tempo, enquanto os usuários ainda estão entrando. 1000 os usuários demorarão cerca de 20 minutos para se conectarem completamente, em um por segundo.



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

