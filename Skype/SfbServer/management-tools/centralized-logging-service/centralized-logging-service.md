---
title: Centralized Logging Service in Skype for Business 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: saiba mais sobre os componentes de serviço e as definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015.'
ms.openlocfilehash: f4cb47204aa4970e0a86d5f1d556099b52afd07c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835261"
---
# <a name="centralized-logging-service-in-skype-for-business-2015"></a>Centralized Logging Service in Skype for Business 2015
 
**Resumo:** Saiba mais sobre os componentes de serviço e as definições de configuração do Serviço de Log Centralizado no Skype for Business Server 2015.
  
O Serviço de Log Centralizado pode: 
  
- Inicie ou pare o registro em log em um ou mais computadores e pools com um único comando de um local central.
    
- Pesquisar logs em um ou mais computadores e pools. Você pode adaptar a pesquisa para retornar todos os logs em todos os máquinas ou retornar resultados mais concisos.
    
- Configurar as sessões de login conforme segue:
    
  - Defina um **Cenário** ou use um cenário default. Um cenário no Serviço de Log Centralizado é feito de escopo (global ou site), um nome de cenário para identificar a finalidade do cenário e um ou mais provedores. Você pode executar o cenário padrão e um cenário definido a qualquer momento em um computador.
    
  - Use um provedor existente ou crie um novo provedor. O Aprovider define o que a sessão de registro em log coleta, qual nível de detalhe, quais componentes rastrear e quais sinalizadores são aplicados.
    
    > [!TIP]
    >  Se você estiver familiarizado com o OCSLogger, os termproviders se referirão à coleção de componentes **(por** exemplo, S4, SIPStack), um tipo de log **(por** exemplo, WPP, EventLog ou arquivo de log do IIS), um nível de rastreamento **(por** exemplo, All, verbose, debug) e sinalizadores **(por** exemplo, TF_COMPONENT, TF_DIAG). Esses itens são definidos no provedor (uma variável do Windows PowerShell) e passados para o comando Serviço de Log Centralizado.
  
  - Configure logs para computadores e pools específicos.
    
  - Defina o escopo da sessão de registro em log a partir das opções **Site** (para executar capturas de log somente em computadores desse site) ou **Global** (para executar capturas de log em todos os computadores na implantação).
    
O Serviço de Log Centralizado é uma poderosa ferramenta de solução de problemas para problemas grandes ou pequenos, desde a análise de causa raiz até problemas de desempenho. Todos os exemplos são mostrados usando o Shell de Gerenciamento do Skype for Business Server. A ajuda é fornecida para a ferramenta de linha de comando por meio da própria ferramenta, mas há um conjunto limitado de funções que você pode executar a partir da linha de comando. Usando o Shell de Gerenciamento do Skype for Business Server, você tem acesso a um conjunto muito maior e muito mais configurável de recursos, portanto, essa sempre deve ser sua primeira opção. 
  
## <a name="logging-service-components"></a>Componentes do serviço de registro em log

 O Serviço de Log Centralizado é executado em todos os servidores em sua implantação e é feito pelos seguintes agentes e serviços:
  
- O ClsAgent do Agente de Serviço de Log Centralizado é executado em todas as máquinas com o Skype for Business Server implantado. Ele escuta ( nas portas **TCP 50001-50003**) comandos de ClsController sobre WCF e envia respostas de volta ao controlador. Ele gerencia sessões de log (iniciar/parar/atualizar) e pesquisa logs. Ele também executa operações de manutenção, como arquivamento de log e limpezas. 
    
- Cmdlets do Controlador de Serviço de Log Centralizado O Shell de Gerenciamento do Skype for Business Server envia comandos Iniciar, Parar, Liberar e Pesquisar para o ClsAgent. Quando os comandos de pesquisa são enviados, os logs resultantes são retornados ao ClsControllerLib.dll e agregados. O controlador envia comandos para o agente, recebe o status desses comandos e gerencia os dados do arquivo de log de pesquisa à medida que eles são retornados por todos os agentes em qualquer computador no escopo de pesquisa e agrega os dados de log em um conjunto de saída significativo e ordenado. As informações nos tópicos a seguir se concentram no uso do Shell de Gerenciamento do Skype for Business Server.
    
**Comunicações do ClsController com o ClsAgent**

![Relação entre CLSController e CLSAgent.](../../media/Ops_CLS_Architecture.jpg)
  
Empreça comandos usando a interface de linha de comando do Windows Server ou usando o Shell de Gerenciamento do Skype for Business Server. Os comandos são executados no computador em que você está conectado e enviados para o ClsAgent localmente ou para outros computadores e pools em sua implantação.
  
ClsAgent mantém um arquivo de índice de todos. Arquivos CACHE que ele tem no computador local. O ClsAgent os aloca para que sejam distribuídos uniformemente entre volumes definidos pela opção CacheFileLocalFolders, nunca consumindo mais de 80% de cada volume (ou seja, o local do cache local e a porcentagem são configuráveis usando o cmdlet **Set-CsClsConfiguration).** O ClsAgent também é responsável por armazenar arquivos antigos de log de rastreamento de eventos em cache (.etl) do computador local. Após duas semanas (ou seja, o período de tempo é configurável usando o cmdlet **Set-CsClsConfiguration),** esses arquivos são copiados para um compartilhamento de arquivos e excluídos do computador local. Para obter detalhes, [consulte Set-CsClsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csclsconfiguration?view=skype-ps). Quando uma solicitação de pesquisa é recebida, os critérios de pesquisa são usados para selecionar o conjunto de arquivos .etl armazenados em cache para executar a pesquisa com base nos valores no índice mantido pelo agente.
  
> [!NOTE]
> Os arquivos movidos para o compartilhamento de arquivos do computador local podem ser pesquisados pelo ClsAgent. Depois que o ClsAgent move os arquivos para o compartilhamento de arquivos, a idade e a remoção dos arquivos não são mantidas pelo ClsAgent. Você deve definir uma tarefa administrativa para monitorar o tamanho dos arquivos no compartilhamento de arquivos e excluí-los ou arquiva-los. 
  
Os arquivos de log resultantes podem ser lidos e analisados usando uma variedade de ferramentas, incluindo o **Snooper.exe** e qualquer ferramenta que possa ler um arquivo de texto, comoNotepad.exe **.** Snooper.exe é parte das Ferramentas de Depuração do Skype for Business Server 2015 e está disponível como download [da Web.](https://go.microsoft.com/fwlink/p/?LinkId=285257)
  
Assim como o OCSLogger, o Serviço de Log Centralizado tem vários componentes a rastrear e fornece opções para selecionar sinalizadores, como TF_COMPONENT e TF_DIAG. O Serviço de Log Centralizado também mantém as opções de nível de log do OCSLogger.
  
A vantagem mais importante de usar o Shell de Gerenciamento do Skype for Business Server em relação à linha de comando ClsController é que você pode configurar e definir novos cenários usando provedores selecionados destinados ao espaço do problema, sinalizadores personalizados e níveis de log. Os cenários disponíveis para ClsController são limitados àqueles definidos para o executável.
  
Nas versões anteriores, OCSLogger.exe para permitir que os administradores e a equipe de suporte coletem arquivos de rastreamento de computadores na implantação. O OCSLogger, para todos os seus pontos fortes, tinha uma deficiência. Você só pode coletar logs em um computador em um dado momento. Você pode fazer logoff em vários computadores usando cópias separadas do OCSLogger, mas acabou com vários logs e nenhuma maneira fácil de agregar os resultados.
  
Quando um usuário solicita uma pesquisa de log, o ClsController determina para quais máquinas enviar a solicitação (ou seja, com base nos cenários selecionados). Ele também determina se a pesquisa precisa ser enviada para o compartilhamento de arquivos onde os arquivos .etl salvos estão localizados. Quando os resultados da pesquisa são retornados para o ClsController, o controlador mescla os resultados em um único conjunto de resultados ordenado por tempo que é apresentado ao usuário. Os usuários podem salvar os resultados da pesquisa no computador local para análise posterior.
  
Ao iniciar uma sessão de registro em log, você especifica cenários relativos ao problema que está tentando resolver. Você pode ter dois cenários em execução a qualquer momento. Um desses dois cenários deve ser o cenário AlwaysOn. Como o nome sugere, ele deve estar sempre em execução em sua implantação, coletando informações em todos os computadores, pools e componentes.
  
> [!IMPORTANT]
> Por padrão, o cenário AlwaysOn não está sendo executado em sua implantação. Você deve iniciar explicitamente o cenário. Uma vez iniciado, ele continuará a ser executado até que seja interrompido explicitamente, e o estado de execução persistirá por meio de reinicializações dos computadores. Para obter detalhes sobre como iniciar e parar cenários, consulte [Start or stop CLS log capture in Skype for Business Server 2015.](start-or-stop-log-capture.md) 
  
Quando ocorrer um problema, inicie um segundo cenário relacionado ao problema relatado. Reproduza o problema e pare o log para o segundo cenário. Inicie suas pesquisas de log em relação ao problema relatado. A coleção agregada de logs produz um arquivo de log que contém mensagens de rastreamento de todos os computadores em seu site ou escopo global da sua implantação. Se a pesquisa retornar mais dados do que você pode analisar (normalmente conhecido como uma taxa de sinal para ruído, onde o ruído é muito alto), execute outra pesquisa com parâmetros mais estreitos. Neste ponto, você pode começar a observar padrões que aparecem e podem ajudá-lo a obter um foco mais claro sobre o problema. Por fim, depois de realizar algumas pesquisas refinadas, você pode encontrar dados relevantes para o problema e descobrir a causa raiz.
  
> [!TIP]
> Quando for apresentado a um cenário de problema no Skype for Business Server, comece se perguntando "O que eu já sei sobre o problema?" Se você quantificar os limites do problema, poderá eliminar uma grande parte das entidades operacionais no Skype for Business Server. 
  
Considere um cenário de exemplo em que você sabe que os usuários não estão recebendo resultados atuais ao procurar um contato. Não faz sentido procurar problemas nos componentes de mídia, Enterprise Voice, conferência e vários outros componentes. O que você pode não saber é onde o problema está realmente: no cliente ou é um problema do lado do servidor? Os contatos são coletados do Active Directory pelo Replicador de usuários e entregues ao cliente por meio do Servidor de Agendamento de Endereços (ABServer). O ABServer obtém suas atualizações do banco de dados RTC (onde o Replicador de usuários as escreveu) e as coleta em arquivos do livro de endereços, por padrão - 1:30 AM. Os clientes do Skype for Business Server recuperam o novo livro de endereços em uma agenda aleatória. Como você sabe como o processo funciona, é possível reduzir sua pesquisa pela possível causa de um problema relacionado aos dados coletados do Active Directory pelo Replicador de Usuários, o ABServer não recupera e cria os arquivos do livro de endereços ou os clientes não baixam o arquivo do livro de endereços.
  
## <a name="current-configuration"></a>Configuração atual

O Serviço de Log Centralizado é configurado para definir o que o serviço de registro em log deve coletar, como ele coleta, de onde ele coletará e quais são as configurações de log. Você define essas configurações globalmente (ou seja, para toda a implantação) ou para um site (ou seja, um site nomeado em sua implantação). Qualquer log que você definir usará as configurações apropriadas para a identidade usada para os comandos iniciarem, interromperem, liberarem e pesquisarem logs.
  
### <a name="to-display-the-current-centralized-logging-service-configuration"></a>Para exibir a configuração atual do Serviço de Log Centralizado

1. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar,** em Todos os **Programas,** no **Skype for Business 2015** e, em seguida, clique no Shell de Gerenciamento do **Skype for Business Server.**
    
2. Digite o seguinte em uma linha de comando do promt:
    
   ```PowerShell
   Get-CsClsConfiguration
   ```

    > [!TIP]
    > Você pode restringir ou expandir o escopo das definições de configuração retornadas definindo e um escopo, como  `-Identity` "Site:Redmond", para retornar apenas o CsClsConfiguration para o site Redmond. Se quiser detalhes sobre uma determinada parte da configuração, você pode canalizou a saída para outro cmdlet do Windows PowerShell. Por exemplo, para obter detalhes sobre os cenários definidos na configuração do site "Redmond", digite: `Get-CsClsConfiguration -Identity "site:Redmond" | Select-Object -ExpandProperty Scenarios`
  
     ![Exemplo de saída de Get-CsClsConfiguration.](../../media/Ops_Get-CsClsConfiguration_Basic.jpg)
  
    O resultado do cmdlet exibe a configuração atual do Serviço de Log Centralizado.
    
|**Definição de Configuração**|**Descrição**|
|:-----|:-----|
|**Identidade** <br/> |Identifica o escopo e o nome para esta configuração. Há apenas uma configuração global e uma configuração por local.  <br/> |
|**Cenários** <br/> |Lista de todos os cenários que são definidos para esta configuração.  <br/> |
|**SearchTerms** <br/> |Termos de busca definidos para a configuração. Microsoft 365 ou Office 365, não implantações locais.  <br/> |
|**SecurityGroups** <br/> |Grupos de segurança definidos que controlam quem (isto é, membros dos grupos de segurança) podem ver computadores com base no local que estão. Nesse contexto, o site é definido no Construtor de Topologias.  <br/> |
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
|**MinimumClsAgentServiceVersion** <br/> |A versão mínima do CLSAgent que pode ser executada. Esse elemento destina-se ao Microsoft 365 ou Office 365.  <br/> |
   

