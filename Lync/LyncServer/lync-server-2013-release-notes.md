---
title: Notas de versão do Lync Server 2013
description: Lync Server 2013 Release Notes.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33fabb0912d7ea3defd91014df732368eced909e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555867"
---
# <a name="release-notes-for-lync-server-2013"></a>Notas de versão do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-08_

Bem-vindo às notas de versão do Lync Server 2013. Consulte este arquivo para obter informações sobre problemas conhecidos sobre o Lync Server 2013.

<div>

## <a name="about-this-document"></a>Sobre este documento

Este documento contém informações importantes que você deve saber antes de implantar e usar o Lync Server 2013. Para obter detalhes sobre o Lync Server 2013, consulte a documentação do [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

Este documento contém as seguintes seções:

  - Cliente do Lync 2013

  - Lync Server

  - Instalação

  - Mobilidade

  - Conferências

  - Enterprise Voice

  - Presença

  - Aplicativo de Grupo de Resposta e Aplicativo Ponto de Espera de Chamadas

  - Painel de controle do Lync Server, Construtor de topologias e Ferramenta de planejamento

  - Localização

  - Direitos autorais

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Cliente do Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>A transferência de um arquivo em uma mensagem instantânea falha se o arquivo estiver aberto em outro aplicativo

**Execute**

Se você tentar transferir um arquivo, como um documento do Word, incluindo-o em uma mensagem instantânea para outro usuário do Lync, a transferência parecerá bem-sucedida, mas pode falhar na transferência do arquivo. Um ícone para o tipo de arquivo será exibido no cliente do Lync, mas o arquivo não poderá ser aberto pelo destinatário pretendido. Nenhuma mensagem de erro é exibida para informá-lo que a transferência não foi bem-sucedida.

**Solução alternativa**

Para contornar esse problema, feche o arquivo aberto ou o aplicativo que o abriu antes de tentar transferir o arquivo em uma mensagem instantânea.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Lync Server

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Se a replicação de dados do serviço de armazenamento do Lync Server falhar, os administradores precisarão verificar os contadores de desempenho para itens de fila de serviço de armazenamento obsoleto

**Execute**

O serviço de armazenamento do Lync Server usa o Windows Fabric para replicação. Se os dados forem excluídos em um servidor front-end primário, mas a exclusão em um servidor front-end secundário falhar — por exemplo, se houver um desligamento ou erro inesperado no servidor de front-end, os dados podem ser deixados para trás e órfãos. Os dados órfãos podem causar desempenho a degradar e perder espaço na unidade.

**Solução alternativa**

Para contornar esse problema, se o espaço de LYSS de eventos de banco de 32058 \_ \_ \_ usado \_ (ID =) e o espaço de banco de \_ usado como \_ \_ \_ crítico (ID = 32059) forem gerados no log de eventos, os administradores devem verificar o contador de desempenho no servidor front **-** end em **ls: LYSS-Service** Se esse contador de desempenho tiver um valor alto — por exemplo, maior que 50000, o administrador deve executar a ferramenta CleanuUpStorageServiceData.exe no Lync Server 2013 Resource Kit, que excluirá todos os dados órfãos do pool. Para obter detalhes sobre a ferramenta, consulte a documentação do kit de recursos do Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Sempre que a configuração de endereço IP for alterada para um servidor ou pool, os serviços do Lync Server precisarão ser reiniciados

**Execute**

Quando a configuração de endereço IP for alterada para uma implantação do Lync Server 2013, como a alteração do IPv4 para a pilha dual ou de uma pilha dual para IPv6, nem todos os componentes do servidor selecionarão a alteração da configuração até que os serviços sejam reiniciados.

**Solução alternativa**

Para contornar esse problema, reinicie os serviços do Lync Server após alterar a configuração de endereço IP para a implantação. Para fazer isso, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>O cmdlet de transação sintética de conferência discada não está mais disponível no pacote de gerenciamento do Lync Server 2013

**Execute**

O cmdlet da transação sintética de conferência discada **Test-CsDialInConferencing** não está mais disponível no pacote de gerenciamento do Lync Server 2013.

**Solução alternativa**

O uso do cmdlet de transação sintética de conferência discada **Test-CsDialInConferencing** é suportado apenas internamente para uma empresa.

Os administradores podem continuar a usar o cmdlet no Shell de gerenciamento do Lync Server para fins de solução de problemas. Se necessário, uma empresa também pode desenvolver um pacote de gerenciamento privado para executar o cmdlet internamente.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>O serviço de registro em log centralizado interrompe se o tráfego de rede é interrompido quando os arquivos de log são copiados para o compartilhamento de rede

**Execute**

Quando o serviço de registro em log centralizado é configurado para usar um caminho de rede (o valor do parâmetro CacheFileNetworkFolder do cmdlet **Get-CsClsConfiguration** é um caminho UNC válido), os arquivos de log armazenados em cache são copiados para o compartilhamento de rede. Se houver uma interrupção no tráfego de rede enquanto os arquivos estão sendo copiados, ocorrerá uma exceção que causará a interrupção do serviço de registro em log centralizado.

O serviço é configurado para reiniciar automaticamente até três vezes, de modo que o serviço se recupere das três primeiras exceções.

**Solução alternativa**

Não há solução para esse problema. Para identificar o problema, monitore o log de eventos para o ID de evento 7031 no "Gerenciador de controle de serviço" que registra quando o serviço "agente de serviço de registro centralizado do Lync Server" foi finalizado inesperadamente. Se isso acontecer mais de três vezes, reinicie manualmente o serviço usando o cmdlet **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Os itens da fila de serviço de armazenamento precisam ser importados manualmente

**Execute**

O Lync Server 2013 armazena dados sobre conferência e mensagens instantâneas, como mensagens arquivadas e registro de detalhes de chamadas (CDR) em um banco de dados em cada servidor de front-end. Os dados são armazenados no banco de dados enquanto estão sendo processados antes de serem entregues ao destino desejado. Para melhorar o desempenho, o Lync Server 2013 exporta periodicamente os itens de fila do banco de dados local que não são processados por um período de tempo estendido e os salva no repositório de arquivos. Se o repositório de arquivos não estiver disponível, os itens serão armazenados em cada servidor de front-end. A mesma operação ocorre para evitar a perda de dados durante o failover do pool.

Durante a operação de exportação, o serviço de armazenamento do Lync Server registra cada estágio no log de eventos com IDs de evento de 32075 (operação de liberação completa iniciada), 32076 (a liberação completa é concluída), 32082 (liberação de nível de manutenção é iniciado), 32083 (a liberação do nível de manutenção é concluída), 32089 (liberação devido ao preenchimento do banco de dados). Esses dados não serão automaticamente importados de volta para o sistema para serem processados e entregues ao seu destino final (SQL Server ou Exchange Server).

**Solução alternativa**

Para importar os dados para o sistema, os administradores precisarão usar a ferramenta ImportStorageServiceData no kit de recursos do Lync Server, que adicionará os dados de volta ao sistema para serem processados e entregues ao seu destino final.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Pesquisas de consulta da Web do catálogo de endereços falharão se o valor padrão de UseNormalizationRules for alterado para false

**Execute**

Se o valor padrão de UseNormalizationRules for alterado para false, as pesquisas da consulta à Web do catálogo de endereços falharão. Após a alteração do valor padrão, os usuários do cliente do Lync não poderão usar a consulta da Web do catálogo de endereços do Lync para pesquisar usuários.

**Solução alternativa**

Se o valor padrão de UseNormalizationRules for definido como false para que os usuários possam usar números de telefone, conforme definido nos serviços de domínio do Active Directory sem o Lync Server 2013 aplicando regras de normalização, confira este problema fazendo o seguinte:

1.  Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**.

2.  Siga um destes procedimentos:
    
      - Se sua implantação incluir apenas servidores do Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de UseNormalizationRules e IgnoreGenericRules para true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se sua implantação incluir uma combinação do Lync Server 2013 e do Lync Server 2010 ou do Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Aguarde a replicação do CMS ocorrer em todos os pools.

4.  Modifique o arquivo de regras de normalização de telefone para a sua implantação para limpar o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013. Se o arquivo não estiver presente, crie um arquivo vazio chamado " \_ normalização de número de telefone da empresa \_ \_ \_Rules.txt".

5.  Aguarde alguns minutos para que todos os pools de front-ends leiam os novos arquivos.

6.  Execute o cmdlet a seguir em cada pool do Lync Server 2013 em sua implantação.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>O evento 21054 de erro do servidor do catálogo de endereços é gerado uma vez diariamente para cada pool do Lync 2013

**Execute**

Lync Server 2013 o servidor do catálogo de endereços gerará evento de erro 21054 a cada dia ao realizar manutenção diária. O erro também é gerado toda vez que um administrador executa o cmdlet **Update-csAddressBook** , mesmo quando a atualização é bem-sucedida. No entanto, esse evento de erro pode ser ignorado com segurança quando a atualização for bem-sucedida.

**Solução alternativa**

Quando você encontrar esse evento de erro, execute o seguinte cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Se o cmdlet relatar que não há objetos não indexados ou abandonados, o evento de erro 21054 pode ser ignorado com segurança.

Além disso, o Key Health Indicator (KHI) "usuários do catálogo de endereços indexados corretamente" deve ser desativado no System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>As solicitações podem falhar quando o IPv6 é configurado em um pool de borda

**Execute**

Quando o IPv6 é configurado em um pool de borda, algumas solicitações ao pool de borda podem falhar.

**Solução alternativa**

Para contornar esse problema, não configure um pool de borda com IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>O cmdlet Invoke-csPoolFailback pode falhar durante o failback do pool

**Execute**

Ao tentar fazer o failback de um pool, o cmdlet **Invoke-csPoolFailback** pode falhar com o erro "falha ao concluir o processo de hidratação após repetidas tentativas".

**Solução alternativa**

Para contornar esse problema, execute o cmdlet novamente e aguarde até que o cmdlet seja bem-sucedido. Observe que o processo de failback pode levar vários minutos para ser concluído. Pode levar até 60 minutos para um pool com 20.000 usuários.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>A perda de dados pode ocorrer quando você adiciona um servidor front-end a um pool já estabelecido – híbrido, Skype for Business Online

**Execute**

Você pode encontrar esse problema em um ambiente em que um pool tenha mais de um servidor front-end, e você reinicia um dos servidores front-end ou adiciona um novo servidor front-end que não faz parte do pool.

Os usuários cujos dados estão sendo arquivados podem sofrer perda de dados até que uma distribuição estável do arquivamento de dados seja estabelecida para o pool. Esse período de perda de dados em potencial é limitado a 15 minutos para conversas de pessoa a pessoa e 30 minutos para conferências.

**Solução alternativa**

Ao executar a manutenção, em vez de iniciar servidores front-end no pool um, você deve fazer failover do pool para outro pool e, em seguida, executar tarefas de manutenção nos servidores. Você também pode tornar o serviço indisponível antes de realizar tarefas de manutenção e, em seguida, restaurar a disponibilidade quando a manutenção estiver concluída.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Os administradores não podem obter uma contagem de licenciados usando o cmdlet Get-CsClientAccessLicense

**Execute**

Os administradores não podem obter o uso preciso da licença do cliente usando o cmdlet **Get-CsClientAccessLicense** .

**Solução alternativa**

Para verificar o tipo de licença do servidor, você pode executar o cmdlet **Get-CsService** para recuperar os nomes de domínio totalmente qualificados (FDQNs) de todos os bancos de dados. Se o FQDN do servidor front-end for igual ao FQDN do banco de dados back-end, a licença será uma licença Standard Edition. Caso contrário, a licença é uma licença Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>A contagem do licenciado do cliente não é reportada com precisão

**Execute**

Ao determinar as contagens de licença do cliente, você pode experimentar as seguintes condições:

1.  **Contagem de licenças imprecisas para usuários móveis**
    
    A contagem de licenças é baseada no número de endereços IP exclusivos para usuários baseados em dispositivos. A contagem de licenças será limitada das seguintes maneiras:
    
      - As licenças serão descontadas se o endereço IP do usuário mudar durante sessões do Lync. Isso pode ocorrer quando um usuário se conecta ao Lync Server de mais de um local com um cliente de desktop.
    
      - As licenças serão subcontadas se um usuário se conectar a um cliente móvel, porque o endereço IP do dispositivo não pode ser determinado.

2.  **As licenças são contadas duas vezes para chamadas PSTN (rede telefônica pública comutada) para o cliente Lync, chamadas do cliente Lync para linhas PSTN e chamadas do Lync encaminhadas para linhas PSTN**
    
    Nos cenários a seguir, duas licenças adicionais serão contadas em vez de uma porque o número de telefone e o usuário do Lync são contados para determinar o número de licenças usadas. Para obter dados de licenciamento precisos, remova manualmente as licenças geradas por um número de telefone.
    
      - Uma chamada telefônica PSTN para o Lync
    
      - Uma chamada do Lync para uma linha PSTN
    
      - Uma chamada PSTN para o Lync e o Lync encaminha a chamada para uma linha PSTN. Uma das linhas PSTN será contada.

3.  **Uma licença não será contada para um telefone do Lync conectado**
    
    Quando um usuário usa um telefone certificado pelo Lync, se o telefone efetuar login e permanecer conectado, o que mantém seu status de logon, o telefone não será contado como usando uma licença se a consulta de licenças ocorrer após o logon do telefone.

4.  **Licenças contadas para telefones PSTN que participam de conferências**
    
    Quando um usuário ingressa em uma conferência com um telefone PSTN, uma licença será contada incorretamente para ingressar na conferência. No entanto, nenhuma licença é necessária para ingressar em uma conferência com um telefone PSTN.

**Solução alternativa**

1.  **Contagem de licenças imprecisas para usuários móveis**
    
      - Você pode identificar manualmente os endereços IP que pertencem ao mesmo dispositivo e remover um deles na contagem de licenças.
    
      - Não há solução para esse problema com dispositivos móveis que se conectam ao cliente Lync.

2.  **As licenças são contadas duas vezes para chamadas PSTN para o cliente Lync, chamadas do cliente Lync para linhas PSTN e chamadas do Lync encaminhadas para linhas PSTN**
    
    Você precisará identificar manualmente o número de telefone PSTN e remover a contagem de licenças gerada para ele.

3.  **Uma licença não será contada para um telefone do Lync conectado**
    
    Você pode configurar o telefone do Lync para fazer logoff e, em seguida, fazer logon novamente, em um intervalo regular, como a cada três meses.

4.  **Licenças contadas para telefones PSTN que participam de conferências**
    
    Você pode identificar manualmente o número de telefone PSTN que é usado para ingressar na conferência e remover a licença gerada pelo número de telefone.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>O painel de controle do Lync Server pára de funcionar em um ambiente VMware após a atualização para o Silverlight 5

**Execute**

Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server pode parar de funcionar após a atualização do Microsoft Silverlight para a versão 5.

**Solução alternativa**

Para contornar esse problema, siga um destes procedimentos:

  - Desinstale o Silverlight 5 e instale o Silverlight 4 de [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156) .

  - Acessar o painel de controle do Lync Server em um computador que não é um computador virtual VMware.
    
    Para fazer isso, você pode iniciar o painel de controle do Lync Server a partir do menu **Iniciar** do Windows no servidor, se as ferramentas de administração do Lync Server estiverem instaladas no computador.
    
    Você também pode acessar o painel de controle do Lync Server usando um navegador da Web. A URL será semelhante a https:// \<frontend\_pool\_fqdn\> /CSCP.

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>As informações do usuário no serviço de catálogo de endereços não são atualizadas depois que o nome distinto do usuário é modificado no Active Directory

**Execute**

Se o nome diferenciado de um usuário (também conhecido como DN) for alterado nos serviços de domínio do Active Directory, as alterações adicionais não serão atualizadas no ABS (serviço de catálogo de endereços). Isso não afeta a entrada ou a presença do usuário, mas impedirá a comunicação do usuário se o endereço SIP também for alterado, pois as pesquisas retornarão um endereço SIP desatualizado.

**Solução alternativa**

Para contornar esse problema, não altere o DN de um usuário. Se você reverter o DN para o usuário para o valor anterior, as atualizações serão refletidas no serviço de catálogo de endereços.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Instalação

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>O uso de caracteres não ASCII pode resultar em falha na inicialização do Lync Server

**Execute**

A instalação falhará se o nome da pasta de destino incluir caracteres não-ASCII (incluindo UNICODE, conjunto de caracteres de byte duplo (DBCS), UTF-8 e UTF-16). Além disso, a instalação pode ser bem-sucedida, mas o servidor não iniciará se os caracteres não-ASCII estiverem contidos em qualquer um dos seguintes:

  - Nome do computador

  - Nome de domínio

  - Nome de usuário

  - URI do SIP do usuário

  - Nome da conta de serviço

**Solução alternativa**

Use apenas caracteres ASCII no nome da pasta de destino, nome do computador, nome do domínio, nome do usuário, URI do SIP do usuário e nomes da conta de serviço.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>O hotfix para "a corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5" deve ser instalado antes da instalação do Lync Server 2013

**Execute**

O hotfix para "a corrupção de pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5" ( [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) ), descrito no artigo da base de dados de conhecimento da Microsoft 264886 ( [https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603) ), deve ser instalado antes da instalação do Lync Server 2013.

**Solução alternativa**

Baixe e instale o hotfix do centro de download da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602) .

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>Lync Server 2013 falha ao instalar no ITA Windows Server 2012 so versão RTM

**Execute**

A instalação do Lync Server 2013 falha no ITA do Windows Server 2012 devido à falha na instalação do Windows Fabric.

A instalação do Windows Fabric falha porque os rastreamentos de malha são criados com o formato de hora de HH: MM: SS. No entanto, no Windows Server ITA, o formato de hora é HH. MM.SS.

**Solução alternativa**

Para contornar esse problema, atualize o registro do sistema antes de instalar o Lync Server 2013. A chave do registro que precisa ser atualizada é: HKEY \_ Users \\ . \\STimeFormat internacional do painel de controle padrão \\ \\ . Altere o valor de sTimeFormat para HH: mm: SS usando a interface de linha de comando do Windows PowerShell da seguinte maneira:

1.  Inicie o Windows PowerShell e execute os seguintes cmdlets:
    
       ```PowerShell
        New-PSDrive -Name HKU -PSProvider Registry -Root HKEY_USERS
       ```
    
       ```PowerShell
        $a="HKU:\.Default\Control Panel\International"
       ```

2.  Para exibir o valor atual, execute o seguinte cmdlet:
    
        Get-itemproperty $a -Name sTimeFormat
    
    Anote o valor atual de sTimeFormat para que ele possa ser restaurado após a conclusão da instalação.

3.  Para definir o novo valor, execute o seguinte cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Após a instalação bem-sucedida do Lync Server 2013, restaure o valor original do sTimeFormat executando o seguinte cmdlet:
    
        - Set-ItemProperty $a-Name sTimeFormat-Value "<valor observado na etapa 3. > acima "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilidade

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemas para clientes móveis durante o processo de failover do servidor

**Execute**

Quando um Lync Server falha e o processo de failover é iniciado, os seguintes problemas podem afetar os usuários do cliente móvel:

  - Nenhuma chamada ou sinal de entrada do Lync para até 10 minutos após o início do failover.

  - Não é possível aceitar solicitações de chat de entrada

  - Não é possível ingressar em reuniões se o servidor com falha for o servidor local do usuário

**Solução alternativa**

Não há solução para esse problema. A funcionalidade normal será restaurada após a conclusão do processo de failover.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Se um usuário móvel recusar uma chamada de entrada de outro ponto de extremidade do Lync, a chamada será exibida como uma conversão perdida nos clientes móveis do Lync

**Execute**

Se um usuário móvel recusar uma chamada de entrada e a chamada tiver originado de outro ponto de extremidade do Lync, a chamada será exibida como uma conversa perdida no cliente móvel do Lync, em vez de uma chamada na lista de chamadas de dispositivo.

**Solução alternativa**

Não há solução para esse problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>O cliente móvel pode não exibir o nome de exibição de um contato federado ao pesquisar contatos

**Execute**

O nome para exibição de contatos federados pode não ser exibido em alguns cenários, como a pesquisa de um contato federado na lista de contatos. Isso pode ocorrer quando não há nenhuma assinatura de presença ativa para o contato do cliente móvel do Lync.

**Solução alternativa**

Não há solução para esse problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>No cliente móvel, as informações de convidado e carimbo de data/hora estão ausentes de uma conversa perdida que é um convite para uma conferência

**Execute**

No cliente móvel, quando uma conversa perdida é um convite para uma conferência, as informações do convidado e do carimbo de data/hora estão ausentes da mensagem de conversa perdida.

**Solução alternativa**

Não há solução para esse problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Os usuários móveis de clientes que fazem chamadas usando VoIP não podem deixar a caixa postal para os usuários cujas mensagens de voz estão configuradas no Exchange 2010 ou versões anteriores

**Execute**

Se um usuário de cliente móvel estiver usando VoIP para fazer chamadas, o usuário não poderá deixar mensagens de caixa postal para usuários configurados para usar a caixa postal no Microsoft Exchange Server 2007 ou no Microsoft Exchange Server 2010.

**Solução alternativa**

Para contornar esse problema, use o Exchange 2010 com SP1 ou versão posterior do Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Ao usar bloquear com URL para configuração de versão de cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida

**Execute**

Ao usar **Bloquear com URL** para configuração de versão de cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida quando a versão do cliente não é suportada.

**Solução alternativa**

Para contornar esse problema, configure a configuração de versão do cliente para usar **Bloquear** em vez de **Bloquear com URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conferências

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>O software antivírus executado nos servidores front-end do Lync Server 2013 pode causar a reciclagem do domínio do aplicativo, que interrompe temporariamente o serviço para os clientes do Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013

**Execute**

O software antivírus pode acionar reinicializações de domínio de aplicativo, o que pode resultar em aplicativos de cliente de API da Web do Lync Mobility Service 2013 e UC (comunicações unificadas) (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013) para perder o estado.

**Solução alternativa**

Para contornar esse problema, exclua as pastas que contêm os componentes Web e o .NET Framework da verificação antivírus. Para obter detalhes, consulte o artigo 312592 da base de dados de conhecimento da Microsoft, "PRB: reinicializações aleatórias do aplicativo com o erro" o aplicativo está reiniciando "no ASP.NET" em [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592) .

As pastas a seguir devem ser excluídas:

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ ext

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ MCX \\ int

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ Ucwa \\ int

  - % ProgramFiles% \\ Microsoft Lync Server 2013 \\ Web Components \\ Ucwa \\ ext

  - % WINDIR% \\ Microsoft.NET \\ Framework64 \\ v 4.0.30319 \\ config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Os controles ActiveX ou o suporte a XMLHTTP nativo devem estar habilitados no Windows Internet Explorer para ingressar em conferências com êxito

**Execute**

Se um usuário desabilitou os controles ActiveX e o suporte a XMLHTTP nativo nas configurações de navegador da Internet do Windows Internet Explorer, o usuário não poderá participar de uma reunião se o Internet Explorer estiver selecionado como navegador padrão.

**Solução alternativa**

Habilite controles ActiveX ou "suporte ao XMLHTTP nativo" no Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>O serviço de conferência da Web do Lync Server não pode se recuperar do modo crítico

**Execute**

Se o modo crítico for habilitado para arquivamento, em caso de falhas no sistema, o modo crítico será iniciado e as conferências não funcionarão mais para os participantes. Depois que o administrador corrige as falhas do sistema (como correção de um problema de banco de dados), o serviço de audioconferência não recupera automaticamente e o administrador deve reiniciar manualmente o serviço de conferência para que a conferência continue.

**Solução alternativa**

Um administrador precisa reiniciar manualmente o serviço de conferência após a correção da falha do sistema.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>O serviço de Webconferência ignora o proxy HTTP para servidores do Office Web App externos

**Execute**

Se você tiver implantado um servidor do Office Web Apps externo para o serviço de Webconferência (ou seja, um servidor que não esteja na rede corporativa interna) na Internet, na rede de perímetro e o serviço de Webconferência exigir um proxy HTTP para se conectar a isso, a descoberta do servidor do Office Web Apps falhará. O serviço de Webconferência ignora a configuração de proxy HTTP, conforme definido no construtor de topologias para a instalação do servidor do Office Web Apps. Como resultado, o cliente do Lync não poderá fazer o compartilhamento do Microsoft PowerPoint 2010 com outros participantes na conferência. Se você estiver instalando o Lync Server local e também configurar o servidor do Office Web Apps no local na rede interna, não será necessária uma configuração de proxy.

**Solução alternativa**

A única solução alternativa é não ter uma configuração de implantação que exija o uso do proxy HTTP para se comunicar com um servidor externo do Office Web Apps.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>A adição de vídeo a uma conferência de provedor de audioconferência não é suportada

**Execute**

A adição de um vídeo não é suportada se o usuário fizer parte de uma conferência de provedor de audioconferência para áudio.

**Solução alternativa**

Não há solução para esse problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologias com IPv6 habilitado forçar a atualização automática do plug-in do Lync Web App Silverlight para garantir que a funcionalidade de compartilhamento de tela possa funcionar no Lync Web App

**Execute**

Quando uma topologia é configurada com IPv6 habilitado, os usuários não podem compartilhar sua tela do cliente do Lync Web App se uma versão anterior do plug-in de compartilhamento de tela já estiver instalada.

**Solução alternativa**

Para forçar uma atualização para a versão mais recente do plug-in de compartilhamento de tela ao ingressar na reunião via Lync Web App, modifique o valor de **MinSupportedBuildVersion** de "4.0.7457.0" para "4.0.7577.380" em ambos os arquivos a seguir:

  - % ProgramFiles% \\ Microsoft Lync Server 15 \\ Web Components \\ REACH plug-ins do \\ \\ cliente int \\ \\ReachAppShPluginProperties.xml

  - % ProgramFiles% \\ Microsoft Lync Server 15 \\ Web Components \\ atingem \\ plugins de cliente estendidos \\ \\ \\ReachAppShPluginProperties.xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>Em alguns casos, um cliente do Lync executando em um computador configurado para usar a pilha Dual IPv4 e IPv6 pode não oferecer suporte a recursos que dependem da sub-rede IP do computador, como E911, bypass de mídia, controle de admissão de chamadas e roteamento baseado em local

<div class="">


> [!NOTE]  
> As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

**Execute**

Quando um cliente Lync está sendo executado em um computador que está habilitado para a pilha Dual IPv4 e IPv6 e com base na resolução DNS do servidor proxy, o cliente pode usar o endereço IPv6 do computador para entrar. Depois disso, o cliente do Lync suportará apenas os recursos suportados para IPv6, que excluirá E911, bypass de mídia, controle de admissão de chamada e roteamento baseado em local.

**Solução alternativa**

Para contornar esse problema, desative o suporte a IPv6 no computador cliente.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Se o Enterprise Voice não estiver configurado para um usuário, o usuário deverá usar o formato e164 para discar de uma conferência

**Execute**

Se o Enterprise Voice não estiver configurado para um usuário, esse usuário precisará usar o formato e164 para discar com êxito de uma conferência. Se o formato e164 não for usado, o usuário não poderá discar da conferência.

**Solução alternativa**

Para contornar esse problema, os usuários que não estão habilitados para o Enterprise Voice devem discar de uma conferência usando números no formato e164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Presença

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Se um usuário selecionar "bloquear todos os convites e comunicações" enquanto o repositório de contato unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria

**Execute**

Se um usuário selecionar "bloquear todos os convites e comunicações" enquanto o repositório de contato unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria.

**Solução alternativa**

Para contornar esse problema, você pode desativar o repositório unificado de contatos para o usuário. Para fazer isso, execute os seguintes cmdlets:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Por exemplo:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Os usuários do Office Communications Server 2007 R2 hospedados no local não podem ver o status de presença de usuários do Skype for Business online em implantações híbridas-híbrido

**Execute**

O problema pode ocorrer em uma implantação híbrida quando você está usando um diretor do Lync Server 2013.

O status de presença para usuários hospedados no Skype for Business Online é exibido como presença desconhecida para usuários locais. Além disso, os usuários hospedados no Skype for Business online não podem ver o status de presença dos usuários locais do Office Communications Server R2.

**Solução alternativa**

Para resolver esse problema parcialmente, altere o servidor local (msRTCSIP-presencehomeserver) dos usuários do Skype for Business online para apontar para um pool local do Lync Server 2013 em vez do diretor do Lync Server 2013. Você pode modificar essa configuração no servidor front-end local.

Essa solução alternativa exibirá corretamente o status de presença de usuários hospedados no Office Communications Server 2007 R2 para os usuários do Skype for Business online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Aplicativo de grupo de resposta, aplicativo de estacionamento de chamada e recebimento de chamada em grupo

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Um chamador pode ouvir um segundo de música em espera durante o estabelecimento de uma chamada com a parte de recuperação

<div class="">


> [!NOTE]  
> As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

**Execute**

Quando uma chamada é recuperada por recebimento de chamada em grupo, o chamador pode ouvir um segundo de música em espera durante o estabelecimento da chamada com o participante do recuperador.

**Solução alternativa**

Não há solução para esse problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Um agente de grupo de resposta pode entrar e sair por meio de um console de agente do Lync Server 2010 para grupos de agente formal do Lync Server 2010 apenas

**Execute**

Um agente de grupo de resposta do Lync Server 2013 pode entrar e sair por meio de um console de agente do Lync Server 2010 para os grupos de agente formal do Lync Server 2010 apenas. No console de agente do Lync Server 2010, os usuários podem ver apenas o grupo de resposta do Lync Server 2010 ao qual eles pertencem. Eles não podem ver qualquer um dos grupos de resposta do Lync Server 2013 aos quais eles pertencem.

**Solução alternativa**

Se o agente de grupo de resposta for um usuário do Lync Server 2013 e parte de um grupo de agente formal do Lync Server 2013, o usuário deverá acessar o console de agente do Lync Server 2013 diretamente por meio de um link da Web em um navegador para entrar e sair de grupos de agentes do Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Um agente de grupo de resposta do Lync Server 2010 não pode fazer chamadas em nome de um grupo de resposta do Lync Server 2013

**Execute**

Um usuário do Lync Server 2010 que é um agente de um grupo de resposta do Lync Server 2013 não é capaz de fazer uma chamada em nome do grupo de resposta. O grupo de resposta do Lync Server 2013 não estará disponível no cliente do Lync para fazer uma chamada.

**Solução alternativa**

Para contornar esse problema, você deve mover o usuário do Lync Server 2010 para o Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>Remover um grupo de resposta do Lync Server 2010 após a migração para o Lync Server 2013 impedirá que o grupo de resposta aceite qualquer chamada de entrada

**Execute**

Se um grupo de resposta que foi migrado do Lync Server 2010 para o Lync Server 2013 for removido do Lync Server 2010 através do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server, o grupo de resposta no Lync Server 2013 deixará de receber todas as chamadas de entrada.

**Solução alternativa**

Para contornar esse problema, não remova nenhum grupo de resposta do Lync Server 2010 que tenha sido migrado do Lync Server 2010 para o Lync Server 2013.

Se o grupo de resposta já tiver sido removido, você deverá reimplantá-lo no Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falhará

**Execute**

Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falhará. Esse problema é encontrado quando o fluxo de trabalho é definido como inativo quando criado, mas não afeta um fluxo de trabalho que é editado para configurá-lo como inativo após ter sido implantado.

**Solução alternativa**

Ao criar e implantar um fluxo de trabalho, defina o fluxo de trabalho como ativo e implante-o. Depois que o fluxo de trabalho é implantado com êxito, o fluxo de trabalho pode ser editado e definido como inativo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>Remover um grupo de resposta do pool proprietário impedirá que o grupo de resposta do pool de backup aceite quaisquer chamadas de entrada durante o failover se o grupo de resposta tiver sido importado para o pool de backup

**Execute**

Se um grupo de resposta pertencente ao pool primário tiver sido importado para o pool de backup sem substituir o proprietário e o grupo de resposta for removido do pool de proprietário, o grupo de resposta no pool de backup não aceitará chamadas de entrada durante o failover.

**Solução alternativa**

Será necessário reimplantar o grupo de resposta no pool primário. Você precisará exportar a configuração do grupo de resposta do pool primário e importá-la para o pool de backup novamente.

Você também pode recriar o grupo de resposta no pool de backup. Nesse caso, o pool de backup será o pool de proprietários do grupo de resposta.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Uma chamada estacionada não pode ser recuperada do aplicativo de estacionamento de chamada se a solicitação de recuperação for feita em nome de um grupo de resposta

**Execute**

Quando as seguintes condições forem verdadeiras, uma solicitação de recuperação de uma chamada estacionada falhará:

  - Um agente é parte de um grupo de resposta anônimo

  - O agente tenta recuperar uma chamada estacionada do aplicativo de estacionamento de chamada através do grupo de resposta anônima

  - O agente tenta recuperar a chamada discando o número de órbita através da opção chamar em nome de ou através da mesma opção no cliente do atendedor do Lync

**Solução alternativa**

Não há soluções alternativas para esse problema. A chamada estacionada deve ser recuperada sem fazer isso em nome de um grupo de resposta.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Painel de controle do Lync Server, Construtor de topologias e Ferramenta de planejamento

<div>

## <a name="planning-tool-limitations"></a>Limitações da ferramenta de planejamento

<div class="">


> [!NOTE]  
> As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

**Execute**

A ferramenta de planejamento tem as seguintes limitações ao planejar sua implantação:

  - Há suporte para o máximo de 10 sites centrais

  - Cada site central pode ter no máximo 14 sites de filial

  - Cada site central pode ter no máximo 240.000 usuários

Além disso, a ferramenta de planejamento não inclui valores para o seguinte ao calcular a topologia recomendada:

  - O número de usuários hospedados online

  - A porcentagem de usuários habilitados para Federação do XMPP

  - Porcentagem de usuários que estão usando o Lync Web App

**Solução alternativa**

Não há solução para esses problemas. Para obter mais informações sobre a ferramenta de planejamento, consulte [projetando a topologia do Lync Server 2013 usando a ferramenta de planejamento](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>A ferramenta de planejamento pode não usar endereços IP previamente definidos para a rede de borda ao atualizar opções

**Execute**

Depois de concluir o design usando a ferramenta de planejamento, se você fizer alterações nas opções de rede de borda, poderão ser adicionados endereços IP adicionais ao design em vez de atualizar os endereços IP existentes. Isso pode ocorrer quando você estiver exibindo os detalhes do diagrama de rede de borda, selecione **clique aqui para atualizar suas opções**e, em seguida, na caixa de diálogo opções de configuração, selecione rede de borda selecionar **desejo usar os mesmos endereços IP e FQDNs, mas diferentes portas para os serviços de borda no meu servidor de borda**. A aplicação de qualquer alteração pode resultar na adição de novos endereços IP e servidores de borda ao design.

**Solução alternativa**

No momento, não há solução para esse problema.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>No painel de controle do Lync Server, "mover todos os usuários para o pool" pode não funcionar como esperado

**Execute**

Ao usar o painel de controle do Lync Server para mover todos os usuários de um pool para outro em um ambiente do Active Directory complexo, como um com vários controladores de domínio e domínios pai/filho, uma mensagem de erro pode ser retornada que diz, "o usuário especificado não é um usuário herdado, usar Move-CsUser cmdlet". Isso é um resultado de tempos de replicação mais longos em ambientes complexos do Active Directory.

**Solução alternativa**

Para contornar esse problema, siga um destes procedimentos:

  - Use filtros no painel de controle do Lync Server para pesquisar usuários herdados, selecione-os e use o **comando mover usuários selecionados para o pool** em vez de **mover todos os usuários para o pool**.

  - Use o Shell de gerenciamento do Lync Server para mover usuários herdados em lotes usando cmdlets do Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>O painel de controle do Lync Server pára de funcionar em um ambiente VMware depois que o plug-in do navegador Microsoft Silverlight é atualizado para a versão 5

**Execute**

Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server pode parar de funcionar após a atualização do Silverlight para a versão 5.

**Solução alternativa**

Para contornar esse problema, siga um destes procedimentos:

  - Desinstale o Silverlight 5 e, em seguida, instale o Silverlight 4 a partir do [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0) .

  - Abra o painel de controle do Lync Server em um computador que não é um computador virtual VMware.
    
    Para abrir o painel de controle do Lync Server em um computador remoto, instale as ferramentas de administração do Lync Server no computador e, em seguida, inicie o painel de controle do Lync Server no menu **Iniciar** do Windows.
    
    Você também pode abrir o painel de controle do Lync Server inserindo a URL em um navegador da Web. A URL será semelhante a https:// \<frontend\_pool\_fqdn\> /CSCP.

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Um administrador não pode executar o cmdlet Uninstall-csMirrorDB após remover o banco de dados de espelhamento no construtor de topologias

**Execute**

Quando um administrador desativa um banco de dados de espelhamento no construtor de topologias e, em seguida, exclui o banco de dados de espelhamento no construtor de topologia, uma mensagem é exibida na lista de tarefas pendentes para que o administrador execute o cmdlet **Uninstall-csMirrorDatabase** para remover o espelhamento do SQL Server. Quando o administrador tenta executar o cmdlet, ele falha.

**Solução alternativa**

Para remover o espelhamento de SQL de um pool no construtor de topologia, você deve primeiro usar um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por exemplo, para remover o espelhamento e descartar os bancos de dados dos bancos de dados do usuário, digite o seguinte:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

O parâmetro *DropExistingDatabasesOnMirror* faz com que os bancos de dados afetados sejam excluídos do espelho. Em seguida, para remover o espelho da topologia, faça o seguinte:

1.  No Construtor de Topologias, clique com o botão direito do mouse no pool e em **Editar Propriedades**

2.  Desmarque **habilitar espelhamento do repositório SQL** e clique em **OK**.

3.  Publique a topologia.

<div class="">


> [!IMPORTANT]  
> Sempre que fizer uma alteração em uma relação de espelhamento de banco de dados de back-end, você deverá reiniciar todos os servidores front-end no pool.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Erros de validação são retornados no construtor de topologia quando um administrador tenta remover uma implantação com um pool de front-ends que tem um repositório testemunha associado

**Execute**

Se um administrador tentar usar o comando **remover implantação** no construtor de topologias para remover uma implantação que inclui um pool de front-ends com um repositório testemunha associado, um erro de validação será exibido no construtor de topologias e a ação não prosseguirá.

**Solução alternativa**

Para contornar esse problema, siga um destes procedimentos:

  - Remova o repositório testemunha antes de tentar remover a implantação.

  - Adicione um repositório testemunha para o pool de front-ends e remova-o.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>As informações de implantação do servidor de chat persistente são inconsistentes entre a ferramenta de planejamento e o construtor de topologia

**Execute**

Quando o Lync Server 2013, a ferramenta de planejamento gera o diagrama de topologia de site para uma implantação de servidor de chat persistente com a recuperação de desastre habilitada, o diagrama de topologia de site inclui vários sites (físicos), com servidores de chat persistentes atribuídos igualmente em cada site. No construtor de topologias, todos os servidores de chat persistentes são representados como pertencentes a um único site (lógico) e estão listados no mesmo nó do pool de servidores de chat persistente.

**Solução alternativa**

No momento, não temos uma solução alternativa para esse problema. O usuário deve analisar a saída da ferramenta de planejamento para a implantação do servidor de chat persistente e modificar o plano para atender às suas necessidades específicas.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localização

<div>

## <a name="monitoring"></a>Monitoramento

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>O assistente implantar relatórios de monitoramento exibe caracteres incorretos sob determinadas circunstâncias ao usar a versão do leste asiático do Lync Server

**Execute**

Ao usar uma versão do leste asiático do Lync Server 2013 — por exemplo, chinês (simplificado), chinês (tradicional), japonês ou coreano — em um sistema operacional que tenha a localidade do sistema não definida para um idioma do leste asiático, o assistente implantar relatórios de monitoramento exibirá pontos de interrogação ou outros caracteres em vez de mensagens localizadas.

**Solução alternativa**

Para corrigir esse problema, defina a localidade do sistema operacional e do Lync Server 2013 para o mesmo idioma, que exibirá todas as mensagens corretamente.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Painel de controle do Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>Em determinados casos, o primeiro item da barra de navegação superior em uma página do painel de controle do Lync Server desaparece quando o último item na barra de navegação superior é clicado

**Execute**

Há três casos conhecidos em que clicar no último item na barra de navegação superior em uma página do painel de controle do Lync Server fará com que o primeiro item na barra de navegação superior desapareça:

  - Na versão francesa, na página "Féderation et accès externe", o item "Stratégie d'accès externo" desaparecerá quando "Partenaires fédérés XMPP" for clicado.

  - Na versão em alemão, na página "clientes", o item "Clientversionskonfiguration" desaparecerá quando "Pushbenachrichtigungskonfiguration" for clicado.

  - Na versão em Russo, na página "Конфигурация сети", o item "Глобально" desaparecerá quando "Маршрут региона" for clicado.

**Solução alternativa**

Para contornar esse problema, atualize a página do painel de controle do Lync Server no navegador. A página será carregada no navegador com todos os itens na barra de navegação superior exibida.

</div>

</div>

<div>

## <a name="address-book"></a>Catálogo de endereços

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>A indexação no catálogo de endereços não funciona como esperado em alguns idiomas

<div class="">


> [!NOTE]  
> As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

Se as propriedades de um usuário contiverem um campo indexado e esse campo contiver apenas caracteres que não podem ser indexados, o usuário não será exibido nas pesquisas realizadas no catálogo de endereços.

Os seguintes caracteres e localidades não podem ser indexados:

  - Caracteres cirílico, grego e armênio em maiúsculas e minúsculas

  - Caracteres acentuados em maiúsculas

  - Tailandês

  - Lao

  - Myanmar

  - Devanágari

  - Etiópico

  - Tibetano

  - Bengali

  - Gujarati

  - Telugu

  - Todos os outros scripts índicos

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Agendador da Web e componentes da Web

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>O fallback de idioma para determinados idiomas do Lync Web Scheduler, discar, inicializador de ingresso, gerenciamento de salas de chat persistente e OCTab pode não funcionar conforme o esperado

**Execute**

Ao selecionar uma localidade neutra em um navegador da Web (no Internet Explorer, por exemplo, o nome do idioma sem mais especificação, como "norueguês \[ no \] ") em vez de uma localidade especificando o idioma, o script e a localidade (como "norueguês, Bokmål (Noruega) \[ NB-não \] ") pode levar a um comportamento de exibição inesperado para determinados idiomas no navegador do Lync Web, no iniciador de ingresso, no gerenciamento da sala de chat persistente Por exemplo, os usuários podem ver a página em inglês quando um dos seguintes idiomas é selecionado:

  - Norueguês

  - Português

  - Sérvio

**Solução alternativa**

Se você quiser selecionar um idioma com uma localidade neutra, sempre certifique-se de que você também adicionou o idioma com uma localidade específica (com código de script e/ou país) como um idioma adicional na lista de preferência de idioma do seu navegador.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Há suporte limitado para localidades azeri e uzbeque ao usar o Agendador do Lync, discagem, inicializador de ingresso, gerenciamento de salas de chat persistente e OCTab em alguns navegadores da Web

<div class="">


> [!NOTE]  
> As informações contidas nesta seção pertencem às atualizações cumulativas do Lync Server 2013:2013 de fevereiro.



</div>

**Execute**

Quando você usa o Internet Explorer 8 ou o Internet Explorer 9 e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), as páginas de discagem e inicializador de ingresso serão exibidas em inglês ou no conjunto de idiomas preferencial no navegador.

Quando você usa o Firefox ou navegadores Chrome e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), o Lync Web App, Lync Web Scheduler e RGS OCTab serão mostrados em inglês ou no conjunto de idiomas preferencial para o navegador.

A localidade uzbeque (latino) não é suportada no navegador Safari.

**Solução alternativa**

Não há solução alternativa para esses problemas.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>A seta suspensa está ausente para a lista "participar da reunião de" na versão romeno do Lync Web App

**Execute**

Quando um usuário que está usando a versão romeno do Lync Web App executa as etapas a seguir, a seta suspensa não é exibida para **participar da reunião** na lista suspensa:

1.  Selecione **lembrar-me neste computador** na guia **geral** .

2.  Selecione a guia **telefone** .

3.  Clique na lista suspensa para **participar da reunião**.
    
    Os usuários não verão uma seta que indica que há mais opções do que o **Lync Web App**padrão, que inclui: **não ingressar em áudio** (no romeno, "nu se asociaža la") e **novo número**"(no romeno," Număr Nou ").

**Solução alternativa**

Embora a seta dessa lista suspensa não seja exibida, os usuários ainda podem selecionar as configurações adicionais na lista clicando no valor padrão.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Ao usar a versão em Turco do Agendador do Lync Web, não é possível salvar uma reunião ao usar a opção "pessoas que eu escolher" em "quem é um apresentador"

**Execute**

Ao criar ou editar uma reunião na versão em Turco do programa de programação do Lync Web, a opção "pessoas que eu escolher" em "quem é um apresentador" não é suportada. Quando essa opção é selecionada, a reunião não pode ser salva. Em vez disso, uma mensagem de erro é exibida, indicando que uma ou mais pessoas não podem ser feitas apresentadores.

**Solução alternativa**

Para contornar esse problema, os usuários podem usar a opção padrão "pessoas da minha empresa" ou qualquer outra opção, como "somente organizador" ou "todos incluindo pessoas fora da minha empresa". O organizador pode rebaixar ou promover pessoas para suas funções corretas posteriormente, depois de ingressar na reunião.

Como alternativa, os usuários que entendem outro idioma podem alterar a seleção de idioma no navegador para um dos outros idiomas com suporte do 43 e tentar usar a opção "pessoas que eu escolher".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Direitos autorais

Este documento oferece suporte a uma versão preliminar de um produto de software que pode ser alterado substancialmente antes do lançamento comercial final, e é a informação confidencial e proprietária da Microsoft Corporation. Ela é divulgada de acordo com um contrato de não divulgação entre o destinatário e a Microsoft. Este documento é fornecido apenas para fins informativos, e a Microsoft não oferece garantias, expressas ou implícitas, neste documento. As informações neste documento, incluindo URLs e outras referências de sites da Internet, estão sujeitas a alterações sem aviso prévio. Todo o risco do uso ou dos resultados do uso deste documento permanece com o usuário. Salvo indicação em contrário, as empresas, organizações, produtos, nomes de domínio, endereços de email, logotipos, pessoas, lugares e eventos descritos nos exemplos aqui mencionados são fictícios. Nenhuma associação com qualquer empresa, organização, produto, nome de domínio, endereço de email, logotipo, pessoa, lugar ou evento real é intencional ou deve ser inferida. A conformidade com as leis de copyright aplicáveis é de responsabilidade do usuário. Sem limitar os direitos de copyright, nenhuma parte deste documento pode ser reproduzida, armazenada ou inserida em um sistema de recuperação, nem transmitida em qualquer forma ou por qualquer meio (eletrônico, mecânico, fotocópia, gravação ou outros) ou por qualquer propósito, sem permissão expressa por escrito da Corporation.

A Microsoft pode ter patentes, aplicações de patentes, marcas registradas, copyrights ou direitos de propriedade intelectual que são objetos de discussão neste documento. Exceto conforme expressamente fornecido em qualquer contrato de licença por escrito, o fornecimento deste documento não lhe concede nenhuma licença a essas patentes, marcas registradas, copyrights ou outra propriedade intelectual.

© 2012 Microsoft Corporation. Todos os direitos reservados.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server são marcas registradas ou comerciais da Microsoft Corporation nos Estados Unidos e/ou em outros países/regiões.

Todas as outras marcas comerciais são propriedade dos respectivos donos.

</div>

</div>

<span> </span>

</div>

</div>

</div>

