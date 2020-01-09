---
title: Serviço centralizado de registro em log no Skype for Business 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Resumo: Saiba mais sobre os componentes de serviço e as configurações de configuração para o serviço de log centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: 1dfdc0de999e79182e5beb57c6d51ecc75359672
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992598"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Serviço centralizado de registro em log no Skype for Business 2015
 
**Resumo:** Saiba mais sobre os componentes do serviço e as configurações de configuração para o serviço de log centralizado no Skype for Business Server 2015.
  
O serviço de registro centralizado pode: 
  
- Iniciar ou parar o registro em um ou mais computadores e pools com um único comando de um local central.
    
- Pesquisar logs em um ou mais computadores e pools. Você pode personalizar a pesquisa para retornar todos os logs em todas as máquinas ou retornar resultados mais concisos.
    
- Configurar as sessões de registro em log conforme segue:
    
  - Definir um **Cenário** ou usar um cenário padrão. Um cenário no serviço de log centralizado é composto de escopo (global ou de site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Você pode executar o cenário padrão e um cenário definido a qualquer momento em um computador.
    
  - Usar um provedor local ou criar um novo provedor. Aprovider define o que a sessão de log coleta, o nível de detalhes, quais componentes rastrear e quais sinalizadores são aplicados.
    
    > [!TIP]
    >  Se você estiver familiarizado com o OCSLogger, o termproviders refere-se à coleção de **componentes** (por exemplo, S4, SIPStack), um **tipo de log** (por exemplo, WPP, EventLog ou logfile do IIS), um **nível de rastreamento** (por exemplo, All, Verbose, debug) e **flags** (por exemplo, TF_COMPONENT, TF_DIAG). Esses itens são definidos no provedor (uma variável do Windows PowerShell) e passados para o comando de serviço de log centralizado.
  
  - Configurar logs para computadores e pools específicos.
    
  - Definir o escopo da sessão de registro em log nas opções **Site** (executa capturas de registro em log em computadores somente naquele local) ou **Global** (executa capturas de registro log em todos os computadores da implantação).
    
O serviço de registro centralizado é uma poderosa ferramenta de solução de problemas para problemas grandes ou pequenos, da análise da causa raiz a problemas de desempenho. Todos os exemplos são exibidos usando o Shell de gerenciamento do Skype for Business Server. Ajuda é fornecida para a ferramenta de linha de comando através da própria ferramenta, mas há um conjunto limitado de funções que você pode executar a partir da linha de comando. Usando o Shell de gerenciamento do Skype for Business Server, você tem acesso a um conjunto muito maior e muito mais configurável de recursos, para que sempre seja sua primeira escolha. 
  
## <a name="logging-service-components"></a>Componente de serviço de registro em log

 O serviço de log centralizado é executado em todos os servidores na sua implantação e consiste nos seguintes agentes e serviços:
  
- O agente de serviço de log centralizado ClsAgent é executado em todas as máquinas com o Skype for Business Server implantado. Ele escuta (em portas **TCP 50001-50003**) para comandos do ClsController sobre o WCF e envia respostas de volta para o controlador. Ele gerencia sessões de registro (iniciar/parar/atualizar) e pesquisa logs. Ele também desempenha operações de governança como limpeza e arquivamento de log. 
    
- Cmdlets do controlador de serviço de log centralizado o Shell de gerenciamento do Skype for Business Server envia os comandos Iniciar, parar, liberar e Pesquisar para o ClsAgent. Quando comandos de pesquisa são enviados, os logs resultantes são retornados ao ClsControllerLib.dll e agregados. O controlador envia comandos para o agente, recebe o status desses comandos e gerencia os dados do arquivo de log de pesquisa à medida que eles são retornados de todos os agentes em qualquer computador no escopo da pesquisa, e agrega os dados do log em um conjunto ordenado de saída e significativa. As informações nos tópicos a seguir se concentram em usar o Shell de gerenciamento do Skype for Business Server.
    
**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Você emite comandos usando a interface de linha de comando do Windows Server ou usando o Shell de gerenciamento do Skype for Business Server. Os comandos são executados no computador que você fez logon e enviados ao ClsAgent localmente, ou para outros computadores e pools em sua implantação.
  
O ClsAgent mantém um arquivo de índice de todos os arquivos .CACHE que ele tem na máquina local. O ClsAgent os aloca de forma que fiquem distribuídos uniformemente nos volumes definidos na opção CacheFileLocalFolders, nunca consumindo mais de 80% de cada volume (isto é, o local do cache local e a porcentagem são configuráveis usando o cmdlet **Set-CsClsConfiguration**). O ClsAgent é responsável também por expirar arquivos de log de rastreamento de eventos antigos no cache (.etl) para fora da máquina local. Após duas semanas (isto é, o cronograma configurável usando o cmdlet **Set-CsClsConfiguration**, esses arquivos são copiados para um compartilhamento de arquivos e excluído do computador local. Para obter detalhes, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando uma solicitação de pesquisa é recebida, os critérios de pesquisa são usados para selecionar o conjunto de arquivos .etl em cache para fazer a pesquisa baseada nos valores no índice mantido pelo agente.
  
> [!NOTE]
> Arquivos que são movidos do computador local para o compartilhamento de arquivos podem ser pesquisados pelo ClsAgent. Assim que o ClsAgent move os arquivos para o compartilhamento de arquivos, a expiração e remoção de arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquivá-los. 
  
Os arquivos de log resultantes podem ser lidos e analisados usando várias ferramentas, incluindo **Snooper.exe** e qualquer ferramenta que possa ler um arquivo de texto, como **Notepad.exe**. O Snooper. exe faz parte das ferramentas de depuração do Skype for Business Server 2015 e está disponível como um [download da Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Assim como o OCSLogger, o serviço de log centralizado tem vários componentes para rastrear e fornece opções para selecionar sinalizadores, como TF_COMPONENT e TF_DIAG. O serviço de log centralizado também mantém as opções de nível de log do OCSLogger.
  
A vantagem mais importante de usar o Shell de gerenciamento do Skype for Business Server sobre o ClsController de linha de comando é que você pode configurar e definir novos cenários usando provedores selecionados que direcionam o espaço problemático, sinalizadores personalizados e níveis de registro em log. Os cenários disponíveis no ClsController são limitados àqueles definidos pelo executável.
  
Nas versões anteriores, o OCSLogger.exe era fornecido para permitir que os administradores e equipe de suporte coletassem arquivos de rastreamento de computadores na implantação. O OCSLogger, apesar de todos seus pontos fortes, tinha um problema. Você podia apenas coletar logs em um computador, em um dado momento. Você podia fazer logon em vários computadores usando cópias separadas do OCSLogger, mas terminava com vários logs e sem uma maneira fácil de agregar os resultados.
  
Quando um usuário solicita uma pesquisa de log, o ClsController determina quais máquinas devem receber as solicitações (isto é, baseado nos cenários selecionados). Ele também determina se a pesquisa precisa ser enviada ao compartilhamento de arquivos quando os arquivos .etl salvos forem localizados. Quando os resultados da pesquisa retornam ao ClsController, o controlador funde os resultados em um único conjunto de resultados ordenado pelo horário, que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa em sua máquina local para análises posteriores.
  
Ao iniciar uma sessão de log, você especifica cenários que são relativos ao problema que está tentando resolver. Você pode ter dois cenários sendo executados a qualquer momento. Um desses cenários deve ser o cenário AlwaysOn (sempre ativado). Como o nome implica, ele deve estar sempre sendo executado em sua implantação, coletando informações em todos os computadores, pools e componentes.
  
> [!IMPORTANT]
> Por padrão, o cenário AlwaysOn não está em execução em sua implantação. É necessário iniciar explicitamente o cenário. Assim que for iniciado, ele continuará sendo executado até que seja interrompido explicitamente, e o estado de execução persistirá nas reinicializações dos computadores. Para obter detalhes sobre como iniciar e parar cenários, consulte [Iniciar ou parar a captura de log do CLS no Skype for Business Server 2015](start-or-stop-log-capture.md). 
  
Quando ocorrer um problema, inicie um segundo cenário que está relacionado ao problema relatado. Reproduza o problema e interrompa o log para o segundo cenário. Inicie suas pesquisas de log relativas ao problema relatado. A coleção agregada de logs produz um arquivo de log que contém mensagens de rastreamento de todos os computadores em seu site ou escopo global de sua implantação. Se a pesquisa retornar mais dados que você possa analisar (geralmente conhecido como razão sinal-ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais restritos. Neste ponto, você pode começar a notar padrões que são exibidos e que podem ajudar a obter um foco mais claro do problema. Finalmente, após realizar algumas pesquisas refinadas, você poderá encontrar dados que sejam relevantes ao problema e descobrir a causa.
  
> [!TIP]
> Quando aparecer um cenário de problema no Skype for Business Server, comece perguntando-se "o que eu já sei sobre o problema?" Se você quantificar os limites do problema, pode eliminar uma grande parte das entidades operacionais no Skype for Business Server. 
  
Considere um exemplo de cenário no qual você sabe que os usuários não estão recebendo resultados atualizados ao procurar por um contato. Não há nenhum momento para procurar problemas nos componentes de mídia, no Enterprise Voice, na conferência e vários outros componentes. Você pode não saber onde está realmente o problema: no cliente, ou é um problema no lado dos servidor? Os contatos são coletados do Active Directory pelo duplicador de usuários e entregues ao cliente por meio do servidor de catálogo de endereços (ABServer). O ABServer obtém suas atualizações do banco de dados RTC (onde o Duplicador do usuário as gravou) e as coleta em arquivos do catálogo de endereços, por padrão-1:30 AM. Os clientes do Skype for Business Server recuperam o novo catálogo de endereços em um cronograma aleatório. Como você sabe como o processo funciona, pode reduzir sua pesquisa para que a causa potencial a um problema relacionado a dados coletados do Active Directory pelo Duplicador do usuário, o ABServer não recupere e crie os arquivos do catálogo de endereços ou os clientes não baixar o arquivo do catálogo de endereços.
  
## <a name="current-configuration"></a>Configuração atual

O serviço de log centralizado é configurado para definir o que o serviço de log destina-se a coletar, como ele coleta, de onde será coletado, e quais são as configurações de log. Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado na sua implantação). Qualquer log que você definir usará as configurações adequadas para a identidade usada para os comandos para iniciar, parar, liberar e pesquisar logs.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para exibir a configuração atual do serviço de log centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte em uma linha de comando do prompt:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Você pode restringir ou expandir o escopo das configurações que são retornadas definindo `-Identity` -se um escopo, como "site: Redmond", para retornar apenas o CsClsConfiguration para o site Redmond. Se quiser obter detalhes sobre uma determinada parte da configuração, você pode canalizar a saída para outro cmdlet do Windows PowerShell. Por exemplo, para obter detalhes sobre os cenários definidos na configuração do site "Redmond", digite:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemplo de saída do Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    O resultado do cmdlet exibe a configuração atual do serviço de log centralizado.
    
|**Definição da Configuração**|**Descrição**|
|:-----|:-----|
|**Identidade** <br/> |Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.  <br/> |
|**Cenários** <br/> |Lista de todos os cenários que são definidos para esta configuração.  <br/> |
|**Termos de busca** <br/> |Termos de busca definidos para a configuração. O Office 365, não implantações locais.  <br/> |
|**SecurityGroups** <br/> |Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão. O site, nesse contexto, é o site definido no construtor de topologias.  <br/> |
|**Regiões** <br/> |Regiões definidas são utilizadas para coletar SecurityGroups em uma região, por exemplo EMEA.  <br/> |
|**EtlFileRolloverSizeMB** <br/> |O parâmetro indica o tamanho máximo do arquivo de log antes que um log de rastreio de evento (.etl) novo seja criado. Um novo arquivo de log é criado quando o tamanho definido é atingido, mesmo se o tempo máximo definido no EtlFileRolloverMinutes não tiver sido atingido ainda.  <br/> |
|**EtlFileRolloverMinutes** <br/> |Quantidade de tempo máxima definida, em minutos, que um log pode decorrer antes de um novo arquivo .etl ser criado. Um novo arquivo de log é criado quando o cronômetro expira, mesmo que o tamanho máximo definido em EtlFileRolloverSizeMB não tenha sido atingido ainda.  <br/> |
|**TmfFileSearchPath** <br/> |Local para buscar por arquivos de formato de mensagens de rastreio.  <br/> |
|**CacheFileLocalFolders** <br/> |Caminho definido para o local onde os arquivos de cache são gravados nos computadores. O CLSAgent grava os arquivos de cache e executa sob o contexto do Serviço de Rede. Neste caso, %TEMP% expande-se para %WINDIR%\ServiceProfiles\NetworkService\AppData\Local. Por padrão, os arquivos de log e cache são gravados no mesmo diretório.  <br/> |
|**CacheFileNetworkFolder** <br/> |Você pode definir um caminho de convenção de nomenclatura universal (UNC) para receber os arquivos de cache durante operações de log.  <br/> |
|**CacheFileLocalRetentionPeriod** <br/> |Definido como o tempo máximo em dias que os arquivos de cache são retidos.  <br/> |
|**CacheFileMaxDiskUsage** <br/> |Definido como a porcentagem de espaço em disco que pode ser utilizado pelos arquivos de cache.  <br/> |
|**ComponentThrottleLimit** <br/> |Definido como o número máximo de rastreamentos por segundo que um componente pode produzir antes de o limitador de aceleração automática é acionado.  <br/> |
|**ComponentThrottleSample** <br/> |Número de vezes que o ComponentThrottleLimit pode ser excedido em 60 segundos.  <br/> |
|**MinimumClsAgentServiceVersion** <br/> |A versão mínima do CLSAgent que pode ser executada. Esse elemento destina-se ao Office 365.  <br/> |
   

