---
title: 'Lync Server 2013: visão geral do serviço de registro em log centralizado'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Centralized Logging Service
ms:assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688145(v=OCS.15)
ms:contentKeyID: 49733746
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e1c382151d34751e7e934f15fdd2855ce696e06
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520828"
---
# <a name="overview-of-the-centralized-logging-service-in-lync-server-2013"></a>Visão geral do serviço de registro em log centralizado no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

O serviço de registro em log centralizado foi projetado para fornecer um meio de um conjunto controlado de dados, com um escopo amplo ou estreito. Você pode coletar dados de todos os servidores na implantação simultaneamente, definir elementos específicos para rastrear, definir sinalizadores de rastreamento e retornar os resultados de pesquisa de um único computador ou uma agregação de todos os dados de todos os servidores. O serviço de registro em log centralizado é executado em todos os servidores em sua implantação. A arquitetura do serviço de registro em log centralizado consiste nos seguintes agentes e serviços:

  - Agente de serviço de *registro em log centralizado*    ClsAgent.exe é o executável do serviço que se comunica com o controlador e recebe os comandos que o controlador é emitido pelo administrador. O agente é executado como um serviço em cada computador do Lync Server. Quando o agente recebe um comando, ele executa o comando, envia mensagens para os componentes definidos para rastreamento e grava os logs de rastreamento no disco. Ele também lê os logs de rastreamento para seu computador e envia os dados de rastreamento de volta ao controlador, quando solicitado. O ClsAgent escuta comandos nas seguintes portas: **tcp 50001**, **TCP 50002**e **TCP 50003**.

  - Controlador de serviço de *log centralizado*    ClsControllerLib.dll é o mecanismo de execução do comando para o Shell de gerenciamento do Lync Server e para ClsController.exe. CLSControllerLib.dll envia comandos de início, parada, descarregamento e pesquisa para o ClsAgent. Quando os comandos de pesquisa são enviados, os logs resultantes são retornados para o ClsControllerLib.dll e agregados. O controlador é responsável por enviar comandos para o agente, recebendo o status desses comandos e gerenciando os dados do arquivo de log de pesquisa à medida que são retornados de todos os agentes em qualquer computador no escopo de pesquisa e agregando os dados de log em um conjunto de resultados significativos e ordenados. As informações nos tópicos a seguir se concentram em usar o Shell de gerenciamento do Lync Server. ClsController.exe é limitado a um subconjunto dos recursos e funções disponíveis no Shell de gerenciamento do Lync Server. A ajuda para ClsController.exe está disponível na linha de comando, digitando `ClsController` na pasta padrão C: Arquivos de \\ programa arquivos \\ comuns \\ do Microsoft Lync Server 2013 \\ ClsAgent.

**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e CLSAgent.](images/JJ688145.68c90811-5cf9-4a84-95b7-ea9ffc61eac4(OCS.15).jpg "Relação entre CLSController e CLSAgent.")

Você emite comandos usando a interface de linha de comando do Windows Server ou o Shell de gerenciamento do Lync Server. Os comandos são executados no computador em que você está conectado e enviados para o ClsAgent localmente ou para outros computadores e pools em sua implantação.

ClsAgent mantém um arquivo de índice de todos. Arquivos de CACHE que estão no computador local. O ClsAgent os aloca para que eles sejam distribuídos uniformemente entre volumes definidos pela opção CacheFileLocalFolders, que nunca consuma mais de 80% de cada volume (ou seja, o local do cache local e a porcentagem é configurável usando o cmdlet **set-CsClsConfiguration** ). O ClsAgent também é responsável por expirar arquivos de log de rastreamento de eventos (. ETL) em cache antigos no computador local. Após duas semanas (ou seja, o período de tempo é configurável usando o cmdlet **set-CsClsConfiguration** ), esses arquivos são copiados para um compartilhamento de arquivos e excluídos do computador local. Para obter detalhes, consulte [set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsClsConfiguration). Quando uma solicitação de pesquisa é recebida, o critério de pesquisa é usado para selecionar o conjunto de arquivos. etl armazenados em cache para executar a pesquisa com base nos valores no índice mantido pelo agente.

<div>


> [!NOTE]  
> Arquivos que são movidos para o compartilhamento de arquivos do computador local podem ser pesquisados pelo ClsAgent. Após o ClsAgent mover os arquivos para o compartilhamento de arquivos, a expiração e a remoção de arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquivá-los.



</div>

Os arquivos de log resultantes podem ser lidos e analisados usando várias ferramentas, incluindo **Snooper.exe** e qualquer ferramenta que possa ler um arquivo de texto, como **Notepad.exe**. Snooper.exe é parte das ferramentas de depuração do Lync Server 2013 e está disponível como um download da Web no [https://go.microsoft.com/fwlink/?LinkId=285257](https://go.microsoft.com/fwlink/?linkid=285257) .

Como o OCSLogger, o serviço de registro em log centralizado tem vários componentes para rastrear e fornece opções para selecionar sinalizadores, como o \_ componente TF e TF \_ diag. O serviço de registro em log centralizado também mantém as opções de nível de log do OCSLogger.

A vantagem mais importante de usar o Shell de gerenciamento do Lync Server sobre a linha de comando ClsController é que você pode configurar e definir novos cenários usando provedores selecionados que direcionam o espaço problemático, sinalizadores personalizados e níveis de log. Os cenários disponíveis para o ClsController estão limitados àqueles definidos para o executável.

Nas versões anteriores, OCSLogger.exe foi fornecido para permitir que os administradores e o pessoal de suporte coletem arquivos de rastreamento de computadores na implantação. OCSLogger, para todos os seus pontos fortes, teve uma deficiência. Você só podia coletar logs em um computador em um determinado momento. Você pode fazer logon em vários computadores usando cópias separadas do OCSLogger, mas você terminou com vários logs e não tem uma maneira fácil de agregar os resultados.

Quando um usuário solicita uma pesquisa de log, o ClsController determina quais máquinas serão enviadas para a solicitação (ou seja, com base nos cenários selecionados). Também determina se a pesquisa precisa ser enviada ao compartilhamento de arquivos onde os arquivos. etl salvos estão localizados. Quando os resultados da pesquisa são retornados para o ClsController, o controlador mescla os resultados em um conjunto de resultados de tempo único que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa em sua máquina local para análise adicional.

Ao iniciar uma sessão de registro em log, você especifica cenários que são relativos ao problema que você está tentando resolver. Você pode ter dois cenários em execução a qualquer momento. Um desses dois cenários deve ser o cenário AlwaysOn. Como o nome sugere, ele deve estar sempre em execução na sua implantação, coletando informações em todos os computadores, pools e componentes.

<div>


> [!IMPORTANT]  
> Por padrão, o cenário AlwaysOn não está sendo executado em sua implantação. Você deve iniciar o cenário explicitamente. Depois de iniciado, ele continuará a ser executado até ser explicitamente interrompido, e o estado de execução persiste pelas reinicializações dos computadores. Para obter detalhes sobre iniciar e interromper cenários, consulte <A href="lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md">using Start for the central Logging Service to Capture logs in Lync server 2013</A> e <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">using Stop for the central Logging Service in Lync Server 2013</A>.



</div>

Quando ocorrer um problema, inicie um segundo cenário que se relacione com o problema relatado. Reproduza o problema e pare o registro em log para o segundo cenário. Inicie suas pesquisas de log em relação ao problema relatado. A coleção de logs agregada produz um arquivo de log que contém mensagens de rastreamento de todos os computadores no seu site ou escopo global da sua implantação. Se a pesquisa retornar mais dados do que você pode possa analisar (normalmente conhecido como uma taxa de sinal para ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais estreitos. Neste ponto, você pode começar a observar padrões que são exibidos e podem ajudá-lo a se concentrar no problema. Em última análise, depois de realizar algumas pesquisas refinadas, você pode encontrar dados relevantes para o problema e descobrir a causa raiz.

<div>


> [!TIP]  
> Quando apresentado com um cenário de problema no Lync Server, comece se perguntando "o que eu já sei sobre o problema?" Se você quantificar os limites do problema, poderá eliminar uma grande parte das entidades operacionais no Lync Server.<BR>Considere um exemplo de cenário no qual você sabe que os usuários não estão obtendo resultados atuais ao procurar um contato. Não há nenhum ponto em procurar por problemas nos componentes de mídia, no Enterprise Voice, na conferência e em vários outros componentes. O que você pode não saber é onde o problema realmente está: no cliente ou é um problema do servidor? Os contatos são coletados do Active Directory pelo replicador de usuários e entregues ao cliente por meio do servidor de catálogo de endereços (ABServer). O ABServer obtém suas atualizações do banco de dados RTC (onde o replicador de usuários as gravou) e as coleta nos arquivos do catálogo de endereços, por padrão – 1:30 AM. Os clientes do Lync Server recuperam o novo catálogo de endereços em uma agenda aleatória. Como você sabe como funciona o processo, é possível reduzir sua pesquisa para a possível causa de um problema relacionado aos dados coletados do Active Directory pelo replicador de usuários, o ABServer não recuperando e criando os arquivos do catálogo de endereços ou os clientes que não estão baixando o arquivo do catálogo de endereços.



</div>

</div>

<span> </span>

</div>

</div>

</div>

