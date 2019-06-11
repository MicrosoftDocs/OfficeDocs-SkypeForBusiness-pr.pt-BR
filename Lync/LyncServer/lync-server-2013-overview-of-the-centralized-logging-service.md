---
title: 'Lync Server 2013: visão geral do serviço de log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 647e6b1e5797b3936dc1fef6023c85ce4baf68b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Visão geral do serviço de log centralizado no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

O serviço de log centralizado foi projetado para fornecer um meio para a coleta controlada de dados, com um escopo amplo ou estreito. Você pode coletar dados de todos os servidores na implantação simultaneamente, definir elementos específicos para rastrear, definir sinalizadores de rastreamento e retornar resultados de pesquisa de um único computador ou de uma agregação de todos os dados de todos os servidores. O serviço de log centralizado é executado em todos os servidores na sua implantação. A arquitetura do serviço de log centralizado é composta pelos seguintes agentes e serviços:

  - *O agente*   de serviço de log centralizado ClsAgent. exe é o executável do serviço que se comunica com o controlador e recebe os comandos que o controlador é emitido pelo administrador. O agente é executado como um serviço em cada computador do Lync Server. Quando o agente recebe um comando, ele executa o comando, envia mensagens para os componentes definidos para rastreamento e grava os logs de rastreamento em disco. Ele também lê os logs de rastreamento para seu computador e envia os dados de rastreamento de volta ao controlador quando solicitado. O ClsAgent escuta comandos nas seguintes portas: **tcp 50001**, **TCP 50002**e **TCP 50003**.

  - *O controlador*   de serviço de log centralizado ClsControllerLib. dll é o mecanismo de execução de comando para o Shell de gerenciamento do Lync Server e para ClsController. exe. CLSControllerLib. dll envia os comandos Iniciar, parar, liberar e Pesquisar para o ClsAgent. Quando comandos de pesquisa são enviados, os logs resultantes são retornados ao ClsControllerLib.dll e agregados. O controlador é responsável por enviar comandos para o agente, recebendo o status desses comandos e gerenciando os dados do arquivo de log de pesquisa à medida que ele é retornado de todos os agentes em qualquer computador do escopo da pesquisa e agregando os dados de log em um significativo e ordenado conjunto de saída. As informações nos tópicos a seguir se concentram em usar o Shell de gerenciamento do Lync Server. ClsController. exe é limitado a um subconjunto de recursos e funções que estão disponíveis no Shell de gerenciamento do Lync Server. A ajuda para ClsController. exe está disponível na linha de `ClsController` comando digitando o diretório padrão C:\\arquivos de\\programas comuns\\Microsoft Lync Server 2013\\ClsAgent.

**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e CLSAgent.] (images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relação entre CLSController e CLSAgent.")

Você emite comandos usando a interface de linha de comando do Windows Server ou usando o Shell de gerenciamento do Lync Server. Os comandos são executados no computador que você fez logon e enviados ao ClsAgent localmente, ou para outros computadores e pools em sua implantação.

O ClsAgent mantém um arquivo de índice de todos os arquivos .CACHE que ele tem na máquina local. O ClsAgent os aloca de forma que fiquem distribuídos uniformemente nos volumes definidos na opção CacheFileLocalFolders, nunca consumindo mais de 80% de cada volume (isto é, o local do cache local e a porcentagem são configuráveis usando o cmdlet **Set-CsClsConfiguration**). O ClsAgent é responsável também por expirar arquivos de log de rastreamento de eventos antigos no cache (.etl) para fora da máquina local. Após duas semanas (isto é, o cronograma configurável usando o cmdlet **Set-CsClsConfiguration**, esses arquivos são copiados para um compartilhamento de arquivos e excluído do computador local. Para obter detalhes, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Quando uma solicitação de pesquisa é recebida, os critérios de pesquisa são usados para selecionar o conjunto de arquivos .etl em cache para fazer a pesquisa baseada nos valores no índice mantido pelo agente.

<div>


> [!NOTE]  
> Arquivos que são movidos do computador local para o compartilhamento de arquivos podem ser pesquisados pelo ClsAgent. Assim que o ClsAgent move os arquivos para o compartilhamento de arquivos, a expiração e remoção de arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquivá-los.



</div>

Os arquivos de log resultantes podem ser lidos e analisados usando várias ferramentas, incluindo **Snooper.exe** e qualquer ferramenta que possa ler um arquivo de texto, como **Notepad.exe**. O Snooper. exe faz parte das ferramentas de depuração do Lync Server 2013 e está disponível como um download [http://go.microsoft.com/fwlink/?LinkId=285257](http://go.microsoft.com/fwlink/?linkid=285257)da Web.

Assim como o OCSLogger, o serviço de log centralizado tem vários componentes para rastrear e fornece opções para selecionar sinalizadores, como o\_componente TF e\_TF diag. O serviço de log centralizado também mantém as opções de nível de log do OCSLogger.

A vantagem mais importante de usar o Shell de gerenciamento do Lync Server sobre a linha de comando ClsController é que você pode configurar e definir novos cenários usando provedores selecionados que direcionam o espaço problemático, sinalizadores personalizados e níveis de registro em log. Os cenários disponíveis no ClsController são limitados àqueles definidos pelo executável.

Nas versões anteriores, o OCSLogger.exe era fornecido para permitir que os administradores e equipe de suporte coletassem arquivos de rastreamento de computadores na implantação. O OCSLogger, apesar de todos seus pontos fortes, tinha um problema. Você podia apenas coletar logs em um computador, em um dado momento. Você podia fazer logon em vários computadores usando cópias separadas do OCSLogger, mas terminava com vários logs e sem uma maneira fácil de agregar os resultados.

Quando um usuário solicita uma pesquisa de log, o ClsController determina quais máquinas devem receber as solicitações (isto é, baseado nos cenários selecionados). Ele também determina se a pesquisa precisa ser enviada ao compartilhamento de arquivos quando os arquivos .etl salvos forem localizados. Quando os resultados da pesquisa retornam ao ClsController, o controlador funde os resultados em um único conjunto de resultados ordenado pelo horário, que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa em sua máquina local para análises posteriores.

Ao iniciar uma sessão de log, você especifica cenários que são relativos ao problema que está tentando resolver. Você pode ter dois cenários sendo executados a qualquer momento. Um desses cenários deve ser o cenário AlwaysOn (sempre ativado). Como o nome implica, ele deve estar sempre sendo executado em sua implantação, coletando informações em todos os computadores, pools e componentes.

<div>


> [!IMPORTANT]  
> Por padrão, o cenário AlwaysOn não está em execução em sua implantação. É necessário iniciar explicitamente o cenário. Assim que for iniciado, ele continuará sendo executado até que seja interrompido explicitamente, e o estado de execução persistirá nas reinicializações dos computadores. Para obter detalhes sobre como iniciar e parar cenários, consulte <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">usando iniciar para o serviço de log centralizado para capturar logs no Lync server 2013</A> e <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">usando parar para o serviço de log centralizado no Lync Server 2013</A>.



</div>

Quando ocorrer um problema, inicie um segundo cenário que está relacionado ao problema relatado. Reproduza o problema e interrompa o log para o segundo cenário. Inicie suas pesquisas de log relativas ao problema relatado. A coleção agregada de logs produz um arquivo de log que contém mensagens de rastreamento de todos os computadores em seu site ou escopo global de sua implantação. Se a pesquisa retornar mais dados que você possa analisar (geralmente conhecido como razão sinal-ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais restritos. Neste ponto, você pode começar a notar padrões que são exibidos e que podem ajudar a obter um foco mais claro do problema. Finalmente, após realizar algumas pesquisas refinadas, você poderá encontrar dados que sejam relevantes ao problema e descobrir a causa.

<div>


> [!TIP]  
> Quando aparecer um cenário de problema no Lync Server, comece perguntando-se "o que eu já sei sobre o problema?" Se você quantificar os limites do problema, pode eliminar uma grande parte das entidades operacionais no Lync Server.<BR>Considere um exemplo de cenário no qual você sabe que os usuários não estão recebendo resultados atualizados ao procurar por um contato. Não há nenhum momento para procurar problemas nos componentes de mídia, no Enterprise Voice, na conferência e vários outros componentes. Você pode não saber onde está realmente o problema: no cliente, ou é um problema no lado dos servidor? Os contatos são coletados do Active Directory pelo duplicador de usuários e entregues ao cliente por meio do servidor de catálogo de endereços (ABServer). O ABServer obtém suas atualizações dos banco de dados RTC (onde o User Replicator os grava) e os coleta nos arquivos do catálogo de endereços, por padrão, às 1:30 AM. Os clientes do Lync Server recuperam o novo catálogo de endereços em um cronograma aleatório. Como você sabe como o processo funciona, pode reduzir sua pesquisa para que a causa potencial a um problema relacionado a dados coletados do Active Directory pelo Duplicador do usuário, o ABServer não recupere e crie os arquivos do catálogo de endereços ou os clientes não baixar o arquivo do catálogo de endereços.



</div>

</div>

<span> </span>

</div>

</div>

</div>

