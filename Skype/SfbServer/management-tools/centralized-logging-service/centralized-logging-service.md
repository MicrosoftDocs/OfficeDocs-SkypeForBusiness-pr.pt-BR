---
title: Serviço centralizado de registro em log no Skype for Business 2015
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 975718a0-f3e3-404d-9453-6224e73bfdd0
description: 'Resumo: Saiba sobre os componentes de serviço e as definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.'
ms.openlocfilehash: 6f1766e97c318a11095aa2f064cd09a0785c1562
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32217584"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Serviço centralizado de registro em log no Skype for Business 2015
 
**Resumo:** Saiba mais sobre os componentes de serviço e definições de configuração para o serviço de registro em log centralizado no Skype para Business Server 2015.
  
The Centralized Logging Service pode: 
  
- Iniciar ou parar o login em um ou mais computadores e pools com um único comando de um local central.
    
- Pesquisar logs em um ou mais computadores e pools. Você pode ajustar a pesquisa para retornar todos os logs em todas as máquinas ou retornar resultados mais concisos.
    
- Configurar as sessões de registro em log conforme segue:
    
  - Definir um **Cenário** ou usar um cenário padrão. Um cenário Centralized Logging Service é formado pelo escopo (global ou site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Em um computador, você pode executar o cenário padrão e um cenário definido em um determinado momento.
    
  - Usar um provedor local ou criar um novo provedor. Aprovider define o que a sessão de log coleta, qual nível de detalhamento, quais componentes de rastreamento e os sinalizadores são aplicados.
    
    > [!TIP]
    >  Se você está familiarizado com OCSLogger, o termproviders refere-se à coleção de **componentes** (por exemplo, S4, SIPStack), um **tipo de log** (por exemplo, /logfile WPP, o log de eventos ou o IIS), um **nível de rastreamento** (por exemplo, All, verbose, debug) e os **sinalizadores** (por exemplo, TF_COMPONENT, TF_DIAG). Estes itens são definidos no provedor (uma variável com o Windows PowerShell) e passados para o comando Centralized Logging Service.
  
  - Configure logs para computadores específicos e pools.
    
  - Definir o escopo da sessão de registro em log nas opções **Site** (executa capturas de registro em log em computadores somente naquele local) ou **Global** (executa capturas de registro log em todos os computadores da implantação).
    
The Centralized Logging Service é uma poderosa ferramenta de solução de problemas para problemas grandes ou pequenos, da análise de causa raiz para problemas de desempenho. Todos os exemplos são mostrados usando o Skype para Business Server Management Shell. Ajuda é fornecida para a ferramenta de linha de comando através da própria ferramenta, mas há um conjunto limitado de funções que você pode executar a partir da linha de comando. Usando o Skype do Shell de gerenciamento do servidor de negócios, você tem acesso a um conjunto muito maior e muito mais configurável de recursos, que deve ser sempre sua primeira opção. 
  
## <a name="logging-service-components"></a>Componente de serviço de registro em log

 The Centralized Logging Service é executado em todos os servidores em sua implantação e é formada pelos agentes e serviços a seguir:
  
- Centralizado log serviço agente com o ClsAgent é executado em cada máquina com Skype para Business Server implantado. Ele escuta (portas **TCP 50001-50003**) para os comandos do ClsController por meio do WCF e envia respostas de volta para o controlador. Ele gerencia as sessões de log (Iniciar/Parar/atualizar) e logs de pesquisa. Ele também desempenha operações de governança como limpeza e arquivamento de log. 
    
- Centralizado log serviço controlador Cmdlets o Skype do Shell de gerenciamento do servidor de negócios envia comandos Iniciar, parar, Flush e pesquisa o com o clsagent. Quando comandos de pesquisa são enviados, os logs resultantes são retornados ao ClsControllerLib.dll e agregados. O controlador envia comandos para o agente, recebe o status desses comandos e gerencia os dados do arquivo de log de pesquisa à medida que eles são retornados de todos os agentes em qualquer computador no escopo da pesquisa, e agrega os dados do log em um conjunto ordenado de saída e significativa. As informações nos tópicos a seguir se concentra em usando o Skype para Business Server Management Shell.
    
**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e com o CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Executar comandos usando a interface de linha de comando do Windows Server ou usando o Skype do Shell de gerenciamento do servidor de negócios. Os comandos são executados no computador que você fez logon e enviados ao ClsAgent localmente, ou para outros computadores e pools em sua implantação.
  
O ClsAgent mantém um arquivo de índice de todos os arquivos .CACHE que ele tem na máquina local. O ClsAgent os aloca de forma que fiquem distribuídos uniformemente nos volumes definidos na opção CacheFileLocalFolders, nunca consumindo mais de 80% de cada volume (isto é, o local do cache local e a porcentagem são configuráveis usando o cmdlet **Set-CsClsConfiguration**). O ClsAgent é responsável também por expirar arquivos de log de rastreamento de eventos antigos no cache (.etl) para fora da máquina local. Após duas semanas (isto é, o cronograma configurável usando o cmdlet **Set-CsClsConfiguration**, esses arquivos são copiados para um compartilhamento de arquivos e excluído do computador local. Para obter detalhes, consulte [Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando uma solicitação de pesquisa é recebida, os critérios de pesquisa são usados para selecionar o conjunto de arquivos .etl em cache para fazer a pesquisa baseada nos valores no índice mantido pelo agente.
  
> [!NOTE]
> Arquivos que são movidos do computador local para o compartilhamento de arquivos podem ser pesquisados pelo ClsAgent. Assim que o ClsAgent move os arquivos para o compartilhamento de arquivos, a expiração e remoção de arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquivá-los. 
  
Os arquivos de log resultantes podem ser lidos e analisados usando várias ferramentas, incluindo **Snooper.exe** e qualquer ferramenta que possa ler um arquivo de texto, como **Notepad.exe**. Snooper.exe faz parte do Skype para as ferramentas de depuração do Business Server 2015 e está disponível como um [download da Web](https://go.microsoft.com/fwlink/p/?LinkId=285257).
  
Como OCSLogger, the Centralized Logging Service tem vários componentes de rastreamento contra e fornece opções para selecionar os sinalizadores, como TF_COMPONENT e TF_DIAG. Serviço de registro em log centralizado também mantém as opções de nível de log de OCSLogger.
  
Usando o Skype do Shell de gerenciamento do servidor de negócios sobre a linha de comando ClsController a vantagem mais importante é que você pode configurar e definir novos cenários usando provedores selecionados que visam o espaço do problema, sinalizadores personalizados e os níveis de log. Os cenários disponíveis no ClsController são limitados àqueles definidos pelo executável.
  
Nas versões anteriores, o OCSLogger.exe era fornecido para permitir que os administradores e equipe de suporte coletassem arquivos de rastreamento de computadores na implantação. O OCSLogger, apesar de todos seus pontos fortes, tinha um problema. Você podia apenas coletar logs em um computador, em um dado momento. Você podia fazer logon em vários computadores usando cópias separadas do OCSLogger, mas terminava com vários logs e sem uma maneira fácil de agregar os resultados.
  
Quando um usuário solicita uma pesquisa de log, o ClsController determina quais máquinas devem receber as solicitações (isto é, baseado nos cenários selecionados). Ele também determina se a pesquisa precisa ser enviada ao compartilhamento de arquivos quando os arquivos .etl salvos forem localizados. Quando os resultados da pesquisa retornam ao ClsController, o controlador funde os resultados em um único conjunto de resultados ordenado pelo horário, que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa em sua máquina local para análises posteriores.
  
Ao iniciar uma sessão de log, você especifica cenários que são relativos ao problema que está tentando resolver. Você pode ter dois cenários sendo executados a qualquer momento. Um desses cenários deve ser o cenário AlwaysOn (sempre ativado). Como o nome implica, ele deve estar sempre sendo executado em sua implantação, coletando informações em todos os computadores, pools e componentes.
  
> [!IMPORTANT]
> Por padrão, o cenário AlwaysOn não está em execução em sua implantação. É necessário iniciar explicitamente o cenário. Assim que for iniciado, ele continuará sendo executado até que seja interrompido explicitamente, e o estado de execução persistirá nas reinicializações dos computadores. Para obter detalhes sobre Iniciando e interrompendo cenários, consulte [Iniciar ou Parar captura de log CLS no Skype para Business Server 2015](start-or-stop-log-capture.md). 
  
Quando ocorrer um problema, inicie um segundo cenário que está relacionado ao problema relatado. Reproduza o problema e interrompa o log para o segundo cenário. Inicie suas pesquisas de log relativas ao problema relatado. A coleção agregada de logs produz um arquivo de log que contém mensagens de rastreamento de todos os computadores em seu site ou escopo global de sua implantação. Se a pesquisa retornar mais dados que você possa analisar (geralmente conhecido como razão sinal-ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais restritos. Neste ponto, você pode começar a notar padrões que são exibidos e que podem ajudar a obter um foco mais claro do problema. Finalmente, após realizar algumas pesquisas refinadas, você poderá encontrar dados que sejam relevantes ao problema e descobrir a causa.
  
> [!TIP]
> Quando for apresentado um cenário de problema em Skype para Business Server, comece perguntando-se a "O que eu já sabe sobre o problema?" Se você quantificam os limites de problema, você poderá eliminar uma grande parte das entidades operacionais em Skype para Business Server. 
  
Considere um exemplo de cenário no qual você sabe que os usuários não estão recebendo resultados atualizados ao procurar por um contato. Não há nenhum ponto em busca de problemas em um número de outros componentes, Enterprise Voice, conferência e os componentes de mídia. Você pode não saber onde está realmente o problema: no cliente, ou é um problema no lado dos servidor? Contatos são coletados do Active Directory pelo replicador de usuários e entregue ao cliente por meio do servidor de catálogo de endereços (ABServer). O ABServer obtém suas atualizações do banco de dados RTC (onde User Replicator escreveu-los) e reúne-los em arquivos do catálogo de endereços, por padrão - 1:30 AM. O Skype para clientes Business Server recuperar o novo catálogo de endereços em um agendamento aleatório. Porque você sabe como funciona o processo, você pode reduzir sua pesquisa para a causa potencial para uma questão relacionada à dados coletados pelo replicador de usuários, o ABServer não recuperar e criando os arquivos do catálogo de endereços ou os clientes não do Active Directory Baixando o arquivo do catálogo de endereços.
  
## <a name="current-configuration"></a>Configuração atual

The Centralized Logging Service está configurado para definir o que é o serviço de log foi projetado para coletar, como ele coleta, onde ele coletará da e quais são as configurações de log. Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado em sua implantação). Qualquer log que você define usará as configurações que são apropriadas para a identidade que você usa para comandos para iniciar, interromper, liberar e logs de pesquisa.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para exibir a configuração atual do Centralized Logging Service

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
2. Digite o seguinte em uma linha de comando do prompt:
    
   ```
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Você pode reduzir ou expandir o escopo das definições de configuração que são retornados definindo `-Identity` e um escopo, como "Site: Redmond", para retornar apenas o CsClsConfiguration para o site Redmond. Se você deseja obter informações detalhadas sobre uma determinada parte da configuração, você pode canalizar a saída em outro cmdlet do Windows PowerShell. Por exemplo, para obter detalhes sobre os cenários definidos na configuração para o site "Redmond", digite:`Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemplo de saída do Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    O resultado do cmdlet exibe a configuração atual do the Centralized Logging Service.
    
|**Definição da Configuração**|**Descrição**|
|:-----|:-----|
|**Identidade** <br/> |Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.  <br/> |
|**Cenários** <br/> |Lista de todos os cenários que são definidos para esta configuração.  <br/> |
|**Termos de busca** <br/> |Termos de busca definidos para a configuração. Office 365, não a implantações em instalações.  <br/> |
|**SecurityGroups** <br/> |Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão. Site, nesse contexto, é o site, conforme definido no construtor de topologia.  <br/> |
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
   

