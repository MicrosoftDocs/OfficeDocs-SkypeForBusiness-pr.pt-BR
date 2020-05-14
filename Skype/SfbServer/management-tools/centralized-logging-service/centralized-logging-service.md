---
title: Serviço de registro em log centralizado no Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Resumo: Saiba mais sobre os componentes de serviço e definições de configuração para o serviço de registro em log centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: e65ea3a0a5ed4d86591b630df6d84e436a7efd66
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221885"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Serviço de registro em log centralizado no Skype for Business 2015
 
**Resumo:** Saiba mais sobre os componentes de serviço e definições de configuração para o serviço de registro em log centralizado no Skype for Business Server 2015.
  
O serviço de registro em log centralizado pode: 
  
- Inicie ou interrompa o registro em um ou mais computadores e pools com um único comando de um local central.
    
- Pesquisar logs em um ou mais computadores e pools. Você pode ajustar a pesquisa para retornar todos os logs em todas as máquinas ou retornar resultados mais concisos.
    
- Configurar as sessões de login conforme segue:
    
  - Defina um **Cenário** ou use um cenário default. Um cenário no serviço de registro em log centralizado é feito de escopo (global ou site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Você pode executar o cenário padrão e um cenário definido em um determinado momento em um computador.
    
  - Usar um provedor existente ou criar um novo provedor. Aprovider define o que a sessão de registro em log coleta, qual nível de detalhe, quais componentes rastrear e quais sinalizadores são aplicados.
    
    > [!TIP]
    >  Se você estiver familiarizado com o OCSLogger, o termproviders se refere à coleção de **componentes** (por exemplo, S4, SIPStack), um **tipo de log** (por exemplo, WPP, EventLog ou logfile do IIS), um nível de **rastreamento** (por exemplo, All, Verbose, debug) e **flags** (por exemplo, TF_COMPONENT TF_DIAG). Esses itens são definidos no provedor (uma variável do Windows PowerShell) e passados para o comando de serviço de registro em log centralizado.
  
  - Configure logs para computadores e pools específicos.
    
  - Defina o escopo da sessão de registro em log no **site** de opções (para executar capturas de log somente nos computadores desse site) ou **global** (para executar capturas de log em todos os computadores na implantação).
    
O serviço de registro em log centralizado é uma poderosa ferramenta de solução de problemas para problemas grandes ou pequenos, da análise de causa principal para problemas de desempenho. Todos os exemplos são mostrados usando o Shell de gerenciamento do Skype for Business Server. A ajuda é fornecida para a ferramenta de linha de comando por meio da ferramenta em si, mas há um conjunto limitado de funções que você pode executar a partir da linha de comando. Usando o Shell de gerenciamento do Skype for Business Server, você tem acesso a um conjunto muito maior e mais configurável de recursos, para que sempre seja a primeira opção. 
  
## <a name="logging-service-components"></a>Componentes de serviço de log

 O serviço de registro em log centralizado é executado em todos os servidores na sua implantação e é composto pelos seguintes agentes e serviços:
  
- O agente de serviço de log centralizado ClsAgent é executado em todas as máquinas com o Skype for Business Server implantado. Ele escuta (on ports **TCP 50001-50003**) para comandos de ClsController sobre o WCF e envia respostas de volta para o controlador. Ele gerencia sessões de log (iniciar/parar/atualizar) e pesquisa os logs. Ele também realiza operações de manutenção, como arquivamento de logs e limpezas. 
    
- Cmdlets do controlador de serviço de registro centralizado o Shell de gerenciamento do Skype for Business Server envia comandos de início, parada, liberação e pesquisa para o ClsAgent. Quando os comandos de pesquisa são enviados, os logs resultantes são retornados para ClsControllerLib. dll e agregados. O controlador envia comandos para o agente, recebe o status desses comandos e gerencia os dados do arquivo de log de pesquisa à medida que são retornados de todos os agentes em qualquer computador no escopo de pesquisa e agrega os dados de log em um conjunto de resultados significativos e ordenados. As informações nos tópicos a seguir se concentram em usar o Shell de gerenciamento do Skype for Business Server.
    
**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Você emite comandos usando a interface de linha de comando do Windows Server ou o Shell de gerenciamento do Skype for Business Server. Os comandos são executados no computador em que você está conectado e enviados para o ClsAgent localmente ou para outros computadores e pools em sua implantação.
  
ClsAgent mantém um arquivo de índice de todos. Arquivos de CACHE que estão no computador local. O ClsAgent os aloca para que eles sejam distribuídos uniformemente entre volumes definidos pela opção CacheFileLocalFolders, que nunca consuma mais de 80% de cada volume (ou seja, o local do cache local e a porcentagem é configurável usando o cmdlet **set-CsClsConfiguration** ). O ClsAgent também é responsável por expirar arquivos de log de rastreamento de eventos (. ETL) em cache antigos no computador local. Após duas semanas (ou seja, o período de tempo é configurável usando o cmdlet **set-CsClsConfiguration** ), esses arquivos são copiados para um compartilhamento de arquivos e excluídos do computador local. Para obter detalhes, consulte [set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando uma solicitação de pesquisa é recebida, o critério de pesquisa é usado para selecionar o conjunto de arquivos. etl armazenados em cache para executar a pesquisa com base nos valores no índice mantido pelo agente.
  
> [!NOTE]
> Arquivos que são movidos para o compartilhamento de arquivos do computador local podem ser pesquisados pelo ClsAgent. Após o ClsAgent mover os arquivos para o compartilhamento de arquivos, a expiração e a remoção de arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquivá-los. 
  
Os arquivos de log resultantes podem ser lidos e analisados usando várias ferramentas, incluindo **Snooper. exe** e qualquer ferramenta que possa ler um arquivo de texto, como o **Notepad. exe**. O Snooper. exe faz parte das ferramentas de depuração do Skype for Business Server 2015 e está disponível como um [download da Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Como o OCSLogger, o serviço de registro em log centralizado tem vários componentes para rastrear e fornece opções para selecionar sinalizadores, como TF_COMPONENT e TF_DIAG. O serviço de registro em log centralizado também mantém as opções de nível de log do OCSLogger.
  
A vantagem mais importante de usar o Shell de gerenciamento do Skype for Business Server sobre a linha de comando ClsController é que você pode configurar e definir novos cenários usando os provedores selecionados que direcionam o espaço problemático, sinalizadores personalizados e níveis de log. Os cenários disponíveis para o ClsController estão limitados àqueles definidos para o executável.
  
Nas versões anteriores, o OCSLogger. exe foi fornecido para permitir que os administradores e o pessoal de suporte coletem arquivos de rastreamento de computadores na implantação. OCSLogger, para todos os seus pontos fortes, teve uma deficiência. Você só podia coletar logs em um computador em um determinado momento. Você pode fazer logon em vários computadores usando cópias separadas do OCSLogger, mas você terminou com vários logs e não tem uma maneira fácil de agregar os resultados.
  
Quando um usuário solicita uma pesquisa de log, o ClsController determina quais máquinas serão enviadas para a solicitação (ou seja, com base nos cenários selecionados). Também determina se a pesquisa precisa ser enviada ao compartilhamento de arquivos onde os arquivos. etl salvos estão localizados. Quando os resultados da pesquisa são retornados para o ClsController, o controlador mescla os resultados em um conjunto de resultados de tempo único que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa em sua máquina local para análise adicional.
  
Ao iniciar uma sessão de registro em log, você especifica cenários que são relativos ao problema que você está tentando resolver. Você pode ter dois cenários em execução a qualquer momento. Um desses dois cenários deve ser o cenário AlwaysOn. Como o nome sugere, ele deve estar sempre em execução na sua implantação, coletando informações em todos os computadores, pools e componentes.
  
> [!IMPORTANT]
> Por padrão, o cenário AlwaysOn não está sendo executado em sua implantação. Você deve iniciar o cenário explicitamente. Depois de iniciado, ele continuará a ser executado até ser explicitamente interrompido, e o estado de execução persiste pelas reinicializações dos computadores. Para obter detalhes sobre como iniciar e interromper cenários, consulte [Iniciar ou parar a captura de log do CLS no Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Quando ocorrer um problema, inicie um segundo cenário que se relacione com o problema relatado. Reproduza o problema e pare o registro em log para o segundo cenário. Inicie suas pesquisas de log em relação ao problema relatado. A coleção de logs agregada produz um arquivo de log que contém mensagens de rastreamento de todos os computadores no seu site ou escopo global da sua implantação. Se a pesquisa retornar mais dados do que você pode possa analisar (normalmente conhecido como uma taxa de sinal para ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais estreitos. Neste ponto, você pode começar a observar padrões que são exibidos e podem ajudá-lo a se concentrar no problema. Em última análise, depois de realizar algumas pesquisas refinadas, você pode encontrar dados relevantes para o problema e descobrir a causa raiz.
  
> [!TIP]
> Quando apresentado com um cenário de problema no Skype for Business Server, comece se perguntando "o que eu já sei sobre o problema?" Se você quantificar os limites do problema, poderá eliminar uma grande parte das entidades operacionais no Skype for Business Server. 
  
Considere um exemplo de cenário no qual você sabe que os usuários não estão obtendo resultados atuais ao procurar um contato. Não há nenhum ponto em procurar por problemas nos componentes de mídia, no Enterprise Voice, na conferência e em vários outros componentes. O que você pode não saber é onde o problema realmente está: no cliente ou é um problema do servidor? Os contatos são coletados do Active Directory pelo replicador de usuários e entregues ao cliente por meio do servidor de catálogo de endereços (ABServer). O ABServer obtém suas atualizações do banco de dados RTC (onde o replicador do usuário as gravou) e as coleta nos arquivos do catálogo de endereços, por padrão-1:30 AM. Os clientes do Skype for Business Server recuperam o novo catálogo de endereços em uma agenda aleatória. Como você sabe como funciona o processo, é possível reduzir sua pesquisa para a possível causa de um problema relacionado aos dados coletados do Active Directory pelo replicador de usuários, o ABServer não recuperando e criando os arquivos do catálogo de endereços ou os clientes que não estão baixando o arquivo do catálogo de endereços.
  
## <a name="current-configuration"></a>Configuração atual

O serviço de registro em log centralizado é configurado para definir o que o serviço de registro em log deve coletar, como ele coleta, onde coletará e quais serão as configurações de log. Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado em sua implantação). Qualquer log que você definir usará as configurações apropriadas para a identidade que você usa para os comandos Iniciar, parar, liberar e pesquisar logs.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para exibir a configuração atual do serviço de registro em log centralizado

1. Inicie o Shell de gerenciamento do Skype for Business Server: clique em **Iniciar**, em **todos os programas**, em **Skype for Business 2015**e em **Shell de gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte em uma linha de comando do promt:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Você pode restringir ou expandir o escopo das definições de configuração que são retornadas definindo `-Identity` um escopo, como "site: Redmond", para retornar apenas o CsClsConfiguration para o site Redmond. Se quiser obter detalhes sobre uma determinada parte da configuração, você pode canalizar a saída para outro cmdlet do Windows PowerShell. Por exemplo, para obter detalhes sobre os cenários definidos na configuração para o site "Redmond", digite:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemplo de saída de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    O resultado do cmdlet exibe a configuração atual do serviço de registro em log centralizado.
    
|**Definição de configuração**|**Descrição**|
|:-----|:-----|
|**Identidade** <br/> |Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.  <br/> |
|**Cenários** <br/> |Lista de todos os cenários que são definidos para esta configuração.  <br/> |
|**SearchTerms** <br/> |Termos de busca definidos para a configuração. Microsoft 365 ou Office 365, não implantações locais.  <br/> |
|**SecurityGroups** <br/> |Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão. O site, neste contexto, é o site, conforme definido no construtor de topologias.  <br/> |
|**Regiões** <br/> |Regiões definidas são utilizadas para coletar SecurityGroups em uma região, por exemplo EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |O parâmetro indica o tamanho máximo do arquivo de log antes que um log de rastreio de evento (.etl) novo seja criado. Um novo arquivo de log é criado quando o tamanho definido é atingido, mesmo se o tempo máximo definido no EtlFileRolloverMinutes não tiver sido atingido ainda.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Quantidade de tempo máxima definida, em minutos, que um log pode decorrer antes de um novo arquivo .etl ser criado. Um novo arquivo de log é criado quando o cronômetro expira, mesmo que o tamanho máximo definido em EtlFileRolloverSizeMB não tenha sido atingido ainda.  <br/> |
|**TmfFileSearchPath** <br/> |Local para buscar por arquivos de formato de mensagens de rastreio.  <br/> |
|**CacheFileLocalFolders** <br/> |Caminho definido para o local onde os arquivos de cache são gravados nos computadores. O CLSAgent grava os arquivos de cache e executa sob o contexto do Serviço de Rede. Neste caso, %TEMP% expande-se para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Por padrão, os arquivos de log e cache são gravados no mesmo diretório.  <br/> |
|**CacheFileNetworkFolder** <br/> |Você pode definir um caminho de convenção de nomenclatura universal (UNC) para receber os arquivos de cache durante operações de log.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definido como o tempo máximo em dias que os arquivos de cache são retidos.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definido como a porcentagem de espaço em disco que pode ser utilizado pelos arquivos de cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Definido como o número máximo de rastreios por segundo que um componente pode produzir antes de o limitador de aceleração automática é acionado.  <br/> |
|**ComponentThrottleSample** <br/> |Número de vezes em 60 segundos em que o ComponentThrottleLimit pode ser excedido.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |A versão mínima do CLSAgent que pode ser executada. Este elemento é destinado ao Microsoft 365 ou ao Office 365.  <br/> |
   

