---
title: 'Lync Server 2013: Notas de versão'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Release notes
ms:assetid: 9f9e864c-3365-4800-803c-5289bd8fd363
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205120(v=OCS.15)
ms:contentKeyID: 48184930
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf5eadb591b7e198ee75ff197b3836673ae0ecc3
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992378"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="release-notes-for-lync-server-2013"></a>Notas de versão para Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2016-12-08_

Bem-vindo às notas de versão do Lync Server 2013. Consulte este arquivo para obter informações sobre problemas conhecidos relacionados ao Lync Server 2013.

<div>

## <a name="about-this-document"></a>Sobre este documento

Este documento contém informações importantes que você deve saber antes de implantar e usar o Lync Server 2013. Para obter detalhes sobre o Lync Server 2013, confira a documentação do [Microsoft Lync server 2013](microsoft-lync-server-2013.md) .

Este documento contém as seguintes seções:

  - Cliente do Lync 2013

  - Servidor Lync

  - Instalação

  - Mobilidade

  - Conferência

  - Enterprise Voice

  - Presença

  - Aplicativo Grupo de Resposta e Aplicativo de Estacionamento de Chamada

  - Painel de Controle, Construtor de Topologia e Ferramenta de Planejamento do Lync Server

  - Localiza

  - Material

</div>

<span id="LyncClient"></span>

<div>

## <a name="lync-2013-client"></a>Cliente do Lync 2013

<div>

## <a name="transferring-a-file-in-an-instant-message-fails-if-the-file-is-open-in-another-application"></a>A transferência de um arquivo em uma mensagem instantânea falha se o arquivo estiver aberto em outro aplicativo

**Problema**

Se você tentar transferir um arquivo, como um documento do Word, incluindo-o em uma mensagem instantânea para outro usuário do Lync, a transferência parecerá bem-sucedida, mas, na verdade, não será possível transferir o arquivo. Um ícone para o tipo de arquivo será exibido no cliente do Lync, mas o arquivo não poderá ser aberto pelo destinatário pretendido. Nenhuma mensagem de erro é exibida para informá-lo que a transferência não foi bem-sucedida.

**Possíveis**

Para contornar esse problema, feche o arquivo aberto ou o aplicativo que o abriu antes de tentar transferir o arquivo em uma mensagem instantânea.

</div>

</div>

<span id="LyncServer"></span>

<div>

## <a name="lync-server"></a>Servidor Lync

<div>

## <a name="if-lync-server-storage-service-data-replication-fails-administrators-will-need-to-check-performance-counters-for-stale-storage-service-queue-items"></a>Se a replicação de dados do serviço de armazenamento do Lync Server falhar, os administradores precisarão verificar os contadores de desempenho para itens de fila do serviço de armazenamento obsoleto

**Problema**

O serviço de armazenamento do Lync Server usa a Windows Fabric para replicação. Se os dados forem excluídos em um servidor front-end primário, mas a exclusão em um servidor front-end secundário falhar — por exemplo, se houver um erro inesperado ou um erro no servidor front-end, os dados podem ser deixados para trás e "órfãos". Os dados órfãos podem fazer com que o desempenho diminua e desperdiçasse espaço na unidade.

**Possíveis**

Para contornar esse problema, se o LYSS\_de\_\_\_erros de BD (ID = 32058) e o espaço\_\_\_de BD do\_LYSS usados críticos (ID = 32059) forem gerados no log de eventos, os administradores devem verificar o contador de desempenho no servidor front-end em **ls: LYSS-Storage Service API** com um nome **LYSS-número atual de itens da fila obsoleto do serviço de armazenamento**. Se esse contador de desempenho tiver um valor alto — por exemplo, maior que 50000 – o administrador deve executar a ferramenta CleanuUpStorageServiceData. exe no kit de recursos do Lync Server 2013, que excluirá todos os dados órfãos do pool. Para obter detalhes sobre a ferramenta, consulte a documentação do kit de recursos do Lync Server 2013.

</div>

<div>

## <a name="whenever-the-ip-address-configuration-is-changed-for-a-server-or-pool-lync-server-services-need-to-be-restarted"></a>Sempre que a configuração do endereço IP for alterada para um servidor ou pool, os serviços do Lync Server precisarão ser reiniciados

**Problema**

Quando a configuração de endereço IP for alterada para uma implantação do Lync Server 2013, como mudar do IPv4 para a pilha dupla ou de uma pilha dupla para a IPv6, nem todos os componentes do servidor retomarão as alterações de configuração até que os serviços sejam reiniciados.

**Possíveis**

Para contornar esse problema, reinicie os serviços do Lync Server depois de alterar a configuração do endereço IP para a implantação. Para fazer isso, execute os seguintes cmdlets no Shell de gerenciamento do Lync Server:

   ```PowerShell
    Stop-CsWindowsService -graceful
   ```

   ```PowerShell
    Start-CsWindowsService
   ```

</div>

<div>

## <a name="the-dial-in-conferencing-synthetic-transaction-cmdlet-is-no-longer-available-in-the-lync-server-2013-management-pack"></a>O cmdlet de transação sintética de conferência discada não está mais disponível no pacote de gerenciamento do Lync Server 2013

**Problema**

O teste do cmdlet de transação sintética de conferência discada **-CsDialInConferencing** não está mais disponível no pacote de gerenciamento do Lync Server 2013.

**Possíveis**

Uso da conferência discada do cmdlet Test de transação sintética **-CsDialInConferencing** tem suporte apenas internamente para uma empresa.

Os administradores podem continuar a usar o cmdlet no Shell de gerenciamento do Lync Server para fins de solução de problemas. Se necessário, uma empresa também pode desenvolver um pacote de gerenciamento privado para executar o cmdlet internamente.

</div>

<div>

## <a name="the-centralized-logging-service-stops-if-network-traffic-is-disrupted-when-log-files-are-being-copied-to-network-share"></a>O serviço de registro centralizado é interrompido se o tráfego de rede for interrompido quando os arquivos de log estiverem sendo copiados para o compartilhamento de rede

**Problema**

Quando o serviço de log centralizado é configurado para usar um caminho de rede (o valor do parâmetro CacheFileNetworkFolder do cmdlet **Get-CsClsConfiguration** é um caminho UNC válido), os arquivos de log em cache são copiados para o compartilhamento de rede. Se houver uma interrupção no tráfego de rede durante a cópia dos arquivos, ocorrerá uma exceção que fará com que o serviço de log centralizado pare.

O serviço está configurado para reiniciar automaticamente até três vezes, para que o serviço se recupere das três primeiras exceções.

**Possíveis**

Não há solução alternativa para esse problema. Para identificar o problema, monitore o log de eventos para o ID de evento 7031 do "Gerenciador de controle de serviços" que registra quando o serviço do "agente de serviço de log centralizado do Lync Server" foi encerrado inesperadamente. Se isso acontecer mais de três vezes, reinicie manualmente o serviço usando o cmdlet **Start-CsWindowService** .

</div>

<div>

## <a name="storage-service-queue-items-need-to-be-imported-manually"></a>Itens da fila do serviço de armazenamento precisam ser importados manualmente

**Problema**

O Lync Server 2013 armazena dados sobre conferência e mensagens instantâneas, como mensagens arquivadas e CDR (registro de detalhes de chamadas) em um banco de dados em cada servidor front-end. Os dados são armazenados no banco de dados enquanto ele está sendo processado antes de ser entregue ao destino pretendido. Para melhorar o desempenho, o Lync Server 2013 exporta periodicamente os itens da fila do banco de dados local que não são processados por um período de tempo prolongado e os salva no repositório de arquivos. Se o armazenamento de arquivos estiver indisponível, os itens serão armazenados em cada servidor front-end. A mesma operação ocorre para evitar perda de dados durante o failover do pool.

Durante a operação de exportação, o serviço de armazenamento do Lync Server registra todos os estágios do log de eventos com IDs de evento 32075 (operação de liberação completa iniciada), 32076 (liberação completa), 32082 (liberação do nível de manutenção é iniciada), 32083 (nível de manutenção liberado estiver concluído), 32089 (liberação ocorrida devido ao preenchimento do banco de dados). Esses dados não serão automaticamente importados de volta para o sistema para serem processados e entregues em seu destino final (SQL Server ou Exchange Server).

**Possíveis**

Para importar os dados para o sistema, os administradores precisarão usar a ferramenta ImportStorageServiceData no kit de recursos do Lync Server, que adicionará os dados de volta ao sistema para serem processados e entregues ao seu destino final.

</div>

<div>

## <a name="address-book-web-query-searches-will-fail-if-the-default-value-for-usenormalizationrules-is-changed-to-false"></a>Pesquisas da consulta à Web do catálogo de endereços falharão se o valor padrão de UseNormalizationRules for alterado para false

**Problema**

Se o valor padrão de UseNormalizationRules for alterado para false, a pesquisa da Web consulta de catálogo de endereços falhará. Após a alteração do valor padrão, os usuários do cliente do Lync não poderão usar a consulta à Web do catálogo de endereços do Lync para pesquisar usuários.

**Possíveis**

Se o valor padrão de UseNormalizationRules for definido como false para que os usuários possam usar números de telefone conforme definidos nos serviços de domínio Active Directory sem o Lync Server 2013 aplicando regras de normalização, confira este problema fazendo o seguinte:

1.  Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**.

2.  Siga um destes procedimentos:
    
      - Se a sua implantação inclui apenas servidores do Lync Server 2013, execute o seguinte cmdlet no nível global para alterar os valores de UseNormalizationRules e IgnoreGenericRules para true:
        
            Set-CsAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true
    
      - Se a sua implantação inclui uma combinação de Lync Server 2013 e Lync Server 2010 ou o Office Communications Server 2007 R2, execute o seguinte cmdlet e atribua-o a cada pool do Lync Server 2013 na topologia:
        
            new-csAddressBookConfiguration -identity <XdsIdentity> -UseNormalizationRules=$true -IgnoreGenericRules=$true

3.  Aguarde até que a replicação do CMS ocorra em todos os pools.

4.  Modifique o arquivo de regras de normalização de telefone para a sua implantação para limpar o conteúdo. O arquivo está no compartilhamento de arquivos de cada pool do Lync Server 2013. Se o arquivo não estiver presente, crie um arquivo\_vazio chamado "\_\_\_regras de normalidade de número de telefone da empresa. txt".

5.  Aguarde alguns minutos para que todos os pools de front-end leiam os novos arquivos.

6.  Execute o seguinte cmdlet em cada pool do Lync Server 2013 na sua implantação.
    
        Update-csAddressBook

</div>

<div>

## <a name="address-book-server-error-event-21054-is-generated-once-daily-for-each-lync-2013-pool"></a>O evento de erro do servidor do catálogo de endereços 21054 é gerado uma vez diariamente para cada pool do Lync 2013

**Problema**

O servidor do catálogo de endereços do Lync Server 2013 gerará evento de erro 21054 uma vez a cada dia ao realizar manutenção diária. O erro também é gerado toda vez que um administrador executa o cmdlet **Update-csAddressBook** , mesmo quando a atualização é bem-sucedida. No entanto, esse evento de erro pode ser ignorado com segurança quando a atualização for bem-sucedida.

**Possíveis**

Quando você encontrar esse evento de erro, execute o seguinte cmdlet:

    Debug-csAddressBookReplication -Poolfqdn <Pool FQDN for which the event was generated>

Se o cmdlet relata que não há objetos não indexados ou abandonados, o evento de erro 21054 pode ser ignorado com segurança.

Além disso, o Key Health Indicator (KHI) "usuários do catálogo de endereços indexados corretamente" deve ser desativado no System Center Operations Manager.

</div>

<div>

## <a name="requests-may-fail-when-ipv6-is-configured-on-an-edge-pool"></a>As solicitações podem falhar quando o IPv6 está configurado em um pool de bordas

**Problema**

Quando o IPv6 está configurado em um pool de bordas, algumas solicitações ao pool de bordas podem falhar.

**Possíveis**

Para contornar esse problema, não configure um pool de bordas com IPv6.

</div>

<div>

## <a name="the-invoke-cspoolfailback-cmdlet-may-fail-during-pool-failback"></a>O cmdlet Invoke-csPoolFailback pode falhar durante o failback do pool

**Problema**

Ao tentar fazer failback de um pool, o cmdlet **Invoke-csPoolFailback** pode falhar com o erro "falha ao concluir o processo do hidratação após tentativas repetidas."

**Possíveis**

Para contornar esse problema, execute o cmdlet novamente e aguarde até que o cmdlet seja bem-sucedido. Observe que o processo de failback pode demorar vários minutos para ser concluído. Pode levar até 60 minutos para um pool com usuários do 20.000.

</div>

<div>

## <a name="data-loss-may-occur-when-you-add-a-front-end-server-to-an-already-established-pool--hybrid-skype-for-business-online"></a>Pode haver perda de dados quando você adiciona um servidor front-end a um pool já estabelecido – híbrido, Skype for Business Online

**Problema**

Você pode encontrar esse problema em um ambiente em que um pool tem mais de um servidor front-end, e você reinicia um dos servidores front end ou adiciona um novo servidor front-end que não fazia parte do pool anteriormente.

Os usuários cujos dados estiverem sendo arquivados poderão sofrer perda de dados até que uma distribuição estável do arquivamento de dados seja estabelecida para o pool. Esse período de perda de dados potencial é limitado a 15 minutos para conversas de pessoa para pessoa e 30 minutos para conferências.

**Possíveis**

Ao executar a manutenção, em vez de iniciar servidores front-end no pool um por um, você deve fazer failover do pool para outro pool e, em seguida, executar tarefas de manutenção nos servidores. Você também pode deixar o serviço indisponível antes de executar tarefas de manutenção e, em seguida, restaurar a disponibilidade quando a manutenção estiver concluída.

</div>

<div>

## <a name="administrators-cannot-get-licensee-count-by-using-the-get-csclientaccesslicense-cmdlet"></a>Os administradores não podem obter a contagem do licenciado usando o cmdlet Get-CsClientAccessLicense

**Problema**

Os administradores não podem obter uso preciso da licença do cliente usando o cmdlet **Get-CsClientAccessLicense** .

**Possíveis**

Para verificar o tipo de licença do servidor, você pode executar o cmdlet **Get-CsService** para recuperar os nomes de domínio totalmente qualificados (FDQNs) de todos os bancos de dados. Se o FQDN do servidor front-end for igual ao FQDN do banco de dados back-end, a licença será uma licença padrão da edição. Caso contrário, a licença é uma licença Enterprise Edition.

</div>

<div>

## <a name="client-licensee-count-is-not-accurately-reported"></a>A contagem de licenças do cliente não é reportada com precisão

**Problema**

Ao determinar a contagem de licenças do cliente, você pode enfrentar as seguintes condições:

1.  **Contagem de licenças imprecisa para usuários móveis**
    
    A contagem de licenças é baseada no número de endereços IP exclusivos para usuários baseados em dispositivos. A contagem de licenças será limitada das seguintes maneiras:
    
      - As licenças serão sucontagem se o endereço IP do usuário mudar durante as sessões do Lync. Isso pode ocorrer quando um usuário se conecta ao Lync Server de mais de um local com um cliente de desktop.
    
      - As licenças serão subcontadas se um usuário se conectar a um cliente móvel, porque o endereço IP do dispositivo não pode ser determinado.

2.  **As licenças são contadas duas vezes para chamadas PSTN (rede telefônica pública comutada) para o cliente do Lync, chamadas do cliente do Lync para linhas PSTN e chamadas encaminhadas para linhas PSTN**
    
    Nos cenários a seguir, duas licenças adicionais serão contadas em vez de uma porque o número de telefone e o usuário do Lync são contados para determinar o número de licenças usadas. Para obter dados de licenciamento precisos, remova manualmente as licenças geradas por um número de telefone.
    
      - Uma chamada telefônica PSTN para o Lync
    
      - Uma chamada do Lync para uma linha PSTN
    
      - Uma chamada PSTN para o Lync e, em seguida, o Lync encaminha a chamada para uma linha PSTN. Uma das linhas PSTN será contada.

3.  **Uma licença não será contada para um telefone do Lync conectado**
    
    Quando um usuário usa um telefone certificado pelo Lync, se o telefone se conecta e permanece conectado, o que mantém o status de logon, o telefone não será contado como sendo usado uma licença se a consulta de licenças ocorrer após o telefone que está conectado.

4.  **Licenças contadas para telefones PSTN participando de conferências**
    
    Quando um usuário ingressa em uma conferência com um telefone PSTN, uma licença é contada de forma inexata para ingressar na conferência. No entanto, nenhuma licença é necessária para ingressar em uma conferência com um telefone PSTN.

**Possíveis**

1.  **Contagem de licenças imprecisa para usuários móveis**
    
      - Você pode identificar manualmente os endereços IP que pertencem ao mesmo dispositivo e, em seguida, remover um deles na contagem de licenças.
    
      - Não há solução alternativa para esse problema com dispositivos móveis que se conectam ao cliente do Lync.

2.  **As licenças são contadas duas vezes para chamadas PSTN para o cliente do Lync, chamadas do cliente do Lync para linhas PSTN e chamadas encaminhadas para o PSTN**
    
    Você precisará identificar manualmente o número de telefone PSTN e remover a contagem de licenças gerada para ele.

3.  **Uma licença não será contada para um telefone do Lync conectado**
    
    Você pode configurar o telefone do Lync para fazer logoff e, em seguida, fazer logon novamente, em um intervalo regular, como a cada 3 meses.

4.  **Licenças contadas para telefones PSTN participando de conferências**
    
    Você pode identificar manualmente o número de telefone PSTN usado para ingressar na conferência e remover a licença gerada pelo número de telefone.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-upgrading-to-silverlight-5"></a>O painel de controle do Lync Server para de funcionar em um ambiente VMware após a atualização para o Silverlight 5

**Problema**

Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server pode parar de funcionar após a atualização do Microsoft Silverlight para a versão 5.

**Possíveis**

Para contornar esse problema, siga um destes procedimentos:

  - Desinstale o Silverlight 5 e instale o Silverlight [https://go.microsoft.com/fwlink/p/?LinkID=149156](https://go.microsoft.com/fwlink/p/?linkid=149156)4 de.

  - Acesse o painel de controle do Lync Server em um computador que não seja um computador virtual do VMware.
    
    Para fazer isso, você pode iniciar o painel de controle do Lync Server no menu **Iniciar** do Windows no servidor, se as ferramentas de administração do Lync Server estiverem instaladas no computador.
    
    Você também pode acessar o painel de controle do Lync Server usando um navegador da Web. A URL será semelhante à\<https://de front\_-\_/CSCP.\>FQDN do pool de front-

</div>

<div>

## <a name="user-information-in-the-address-book-service-is-not-updated-after-the-distinguished-name-for-the-user-is-modified-in-active-directory"></a>As informações do usuário no serviço de catálogo de endereços não são atualizadas depois que o nome diferenciado do usuário é modificado no Active Directory

**Problema**

Se o nome diferenciado de um usuário (também conhecido como DN) for alterado nos serviços de domínio Active Directory, todas as alterações adicionais não serão atualizadas no ABS (serviço de catálogo de endereços). Isso não afeta a entrada ou a presença do usuário, mas ele impedirá a comunicação para o usuário se o endereço SIP também for alterado, pois as pesquisas retornarão um endereço SIP desatualizado.

**Possíveis**

Para contornar esse problema, não altere o DN de um usuário. Se você reverter o DN do usuário para o valor anterior, as atualizações serão refletidas no serviço de catálogo de endereços.

</div>

</div>

<span id="Installation"></span>

<div>

## <a name="installation"></a>Instalação

<div>

## <a name="using-non-ascii-characters-may-result-in-lync-server-failing-to-start"></a>O uso de caracteres não ASCII pode resultar em falha na inicialização do Lync Server

**Problema**

A instalação falhará se o nome da pasta de destino incluir caracteres não ASCII (incluindo UNICODE, conjunto de caracteres de dois bytes (DBCS), UTF-8 e UTF-16). Além disso, a instalação pode ser bem-sucedida, mas o servidor não será iniciado se os caracteres não ASCII estiverem contidos em qualquer um dos seguintes itens:

  - Nome do computador

  - Nome do domínio

  - Nome de usuário

  - URI de SIP do usuário

  - Nome da conta de serviço

**Possíveis**

Use somente caracteres ASCII no nome da pasta de destino, nome do computador, nome do domínio, nome de usuário, URI de SIP do usuário e nomes de conta de serviço.

</div>

<div>

## <a name="the-hotfix-for-heap-corruption-occurs-when-a-module-calls-the-insertentitybody-method-in-iis-75-must-be-installed-prior-to-installing-lync-server-2013"></a>O hotfix para "a corrupção da pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5" deve ser instalado antes da instalação do Lync Server 2013

**Problema**

O hotfix para "a corrupção da pilha ocorre quando um módulo chama o método InsertEntityBody no IIS 7,5[https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)" (), descrito no artigo 264886 ([https://go.microsoft.com/fwlink/p/?LinkId=268603](https://go.microsoft.com/fwlink/p/?linkid=268603)) da base de dados de conhecimento Microsoft, deve ser instalado antes da instalação do Lync Server 2013.

**Possíveis**

Baixe e instale o hotfix a partir do centro de download [https://go.microsoft.com/fwlink/p/?LinkId=268602](https://go.microsoft.com/fwlink/p/?linkid=268602)da Microsoft em.

</div>

<div>

## <a name="lync-server-2013-fails-to-install-on-ita-windows-server-2012-os-rtm-version"></a>O Lync Server 2013 falha ao instalar na versão do ITA do Windows Server 2012 OS RTM

**Problema**

A instalação do Lync Server 2013 falha no Windows Server 2012 ITA devido à falha na instalação do Windows Fabric.

A instalação do Windows Fabric falha porque os rastreamentos de malha são criados com o formato de hora de HH: MM: SS. No entanto, no servidor ITA do Windows, o formato de hora é HH. MM.SS.

**Possíveis**

Para contornar esse problema, atualize o registro do sistema antes de instalar o Lync Server 2013. A chave do registro que precisa ser atualizada é: HKEY\_usuários\\. STimeFormat\\internacional\\do\\painel de controle padrão. Altere o valor de sTimeFormat para HH: mm: SS usando a interface de linha de comando do Windows PowerShell da seguinte maneira:

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

3.  Para definir para novo valor, execute o seguinte cmdlet:
    
        Set-ItemProperty $a -Name sTimeFormat -Value "HH:mm:ss"

4.  Após a instalação bem-sucedida do Lync Server 2013, restaure o valor original do sTimeFormat executando o seguinte cmdlet:
    
        - Set-sTimeFormat valor de $a-Name "<valor observado na etapa 3. acima> "

</div>

</div>

<span id="Mobility"></span>

<div>

## <a name="mobility"></a>Mobilidade

<div>

## <a name="issues-for-mobile-clients-during-the-server-failover-process"></a>Problemas para clientes móveis durante o processo de failover do servidor

**Problema**

Quando um servidor do Lync falha e o processo de failover começa, os seguintes problemas podem afetar os usuários do cliente móvel:

  - Nenhuma chamada recebida pelo Lync ou sinal para até 10 minutos após o início do failover.

  - Não é possível aceitar solicitações de chat de entrada

  - Não é possível ingressar em reuniões se o servidor com falha for o servidor primário do usuário

**Possíveis**

Não há solução alternativa para esse problema. A funcionalidade normal será restaurada quando o processo de failover estiver concluído.

</div>

<div>

## <a name="if-a-mobile-user-declines-an-incoming-call-from-another-lync-endpoint-the-call-is-displayed-as-a-missed-conversion-on-lync-mobile-clients"></a>Se um usuário móvel recusar uma chamada de entrada de outro ponto de extremidade do Lync, a chamada será exibida como uma conversão perdida em clientes móveis do Lync

**Problema**

Se um usuário móvel recusar uma chamada de entrada e a chamada tiver sido originada de outro ponto de extremidade do Lync, a chamada será exibida como uma conversa perdida no cliente móvel do Lync, em vez de uma chamada na lista de chamadas do dispositivo.

**Possíveis**

Não há solução alternativa para esse problema.

</div>

<div>

## <a name="the-mobile-client-may-not-display-a-federated-contacts-display-name-when-searching-for-contacts"></a>O cliente móvel pode não exibir o nome de exibição de um contato federado durante a pesquisa de contatos

**Problema**

O nome de exibição de contatos federados pode não ser exibido em alguns cenários, como ao pesquisar por um contato federado na lista de contatos. Isso pode ocorrer quando não há nenhuma assinatura de presença ativa para o contato do cliente móvel do Lync.

**Possíveis**

Não há solução alternativa para esse problema.

</div>

<div>

## <a name="in-the-mobile-client-invitee-and-timestamp-information-are-missing-from-a-missed-conversation-that-is-an-invitation-to-a-conference"></a>No cliente móvel, as informações de convidado e carimbo de data/hora estão ausentes de uma conversa perdida que é um convite para uma conferência

**Problema**

No cliente móvel, quando uma conversa perdida é um convite para uma conferência, as informações de convidado e carimbo de data/hora estão ausentes da mensagem de conversa perdida.

**Possíveis**

Não há solução alternativa para esse problema.

</div>

<div>

## <a name="mobile-client-users-making-calls-using-voip-are-not-be-able-to-leave-voice-mail-for-users-whose-voice-mail-is-configured-in-exchange-2010-or-earlier-versions"></a>Os usuários de cliente móvel que fizerem chamadas usando VoIP não poderão sair da caixa postal para os usuários cujas caixas de correio de voz estiverem configuradas no Exchange 2010 ou versões anteriores

**Problema**

Se um usuário de cliente móvel estiver usando VoIP para fazer chamadas, o usuário não poderá deixar mensagens de correio de voz para usuários configurados para usar a caixa postal no Microsoft Exchange Server 2007 ou Microsoft Exchange Server 2010.

**Possíveis**

Para contornar esse problema, use o Exchange 2010 com SP1 ou versão mais recente do Microsoft Exchange Server.

</div>

<div>

## <a name="when-using-block-with-url-for-client-version-configuration-on-mobile-clients-an-incorrect-error-message-may-be-displayed"></a>Ao usar o bloco com URL para a configuração de versão do cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida

**Problema**

Ao usar o **bloco com URL** para a configuração de versão do cliente em clientes móveis, uma mensagem de erro incorreta pode ser exibida quando a versão do cliente não é suportada.

**Possíveis**

Para contornar esse problema, configure a configuração de versão do cliente para usar o **bloqueio** em vez do **bloco com a URL**.

</div>

</div>

<span id="Conferencing"></span>

<div>

## <a name="conferencing"></a>Conferência

<div>

## <a name="antivirus-software-running-on-lync-server-2013front-end-servers-can-cause-application-domain-recycling-which-temporarily-interrupts-service-for-lync-web-app-2013-lync-mobile-2010-and-lync-mobile-2013-clients"></a>O software antivírus em execução nos servidores front-end do Lync Server 2013 pode causar a reciclagem do domínio do aplicativo, que interrompe temporariamente o serviço para os clientes do Lync Web App 2013, Lync Mobile 2010 e Lync 2013 móvel do Lync

**Problema**

O software antivírus pode disparar reinicializações de domínio de aplicativo, o que pode resultar em aplicativos de cliente de API Web do Lync Mobility Service 2013 e na comunicação unificada (Lync Web App 2013, Lync Mobile 2010 e Lync Mobile 2013) para perder o estado.

**Possíveis**

Para contornar esse problema, exclua as pastas que contêm componentes Web e .NET Framework da verificação de antivírus. Para obter detalhes, consulte o artigo 312592 da base de dados de conhecimento Microsoft, erro "PRB: reinícios do aplicativo aleatório com o" aplicativo está reiniciando "em ASP.NET," at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=312592](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=312592).

As seguintes pastas devem ser excluídas:

  - % ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components MCX\\ext

  - % ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components MCX\\int

  - % ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components Ucwa\\int

  - % ProgramFiles\\% Microsoft Lync Server\\2013 Web\\Components Ucwa\\ext

  - % WINDIR%\\Microsoft.NET\\Framework64\\v 4.0.30319\\config

</div>

<div>

## <a name="activex-controls-or-native-xmlhttp-support-must-be-enabled-in-windows-internet-explorer-to-successfully-join-conferences"></a>Os controles ActiveX ou o suporte a XMLHTTP nativo devem estar habilitados no Windows Internet Explorer para ingressar com êxito em conferências

**Problema**

Se um usuário tiver desabilitado os controles ActiveX e o suporte a XMLHTTP nativo nas configurações do navegador da Internet do Windows Internet Explorer, o usuário não poderá ingressar em uma reunião se o Internet Explorer estiver selecionado como o navegador padrão.

**Possíveis**

Habilite controles ActiveX ou "suporte XMLHTTP nativo" no Internet Explorer.

</div>

<div>

## <a name="lync-server-web-conferencing-service-cannot-recover-from-critical-mode"></a>O serviço do Lync Server Web referencing não pode recuperar do modo crítico

**Problema**

Se o modo crítico for ativado para arquivamento, em caso de falhas do sistema, o modo crítico será iniciado e as conferências deixarão de funcionar para os participantes. Depois que o administrador corrigir as falhas do sistema (como corrigir um problema de banco de dados), o serviço data de conferência não recupera automaticamente e o administrador deve reiniciar manualmente o serviço de conferência para que a conferência seja retomada.

**Possíveis**

Um administrador precisa reiniciar o serviço de conferência manualmente após a correção da falha do sistema.

</div>

<div>

## <a name="web-conferencing-service-ignores-the-http-proxy-for-external-office-web-app-servers"></a>Serviço Web de Webconferência ignora o proxy HTTP para servidores do Office Web App externos

**Problema**

Se você implantou um servidor Office Web Apps externo para o serviço de Webconferência (ou seja, um servidor que não está na rede corporativa interna) na Internet, na rede de perímetro e o serviço de Webconferência exigem um proxy HTTP para se conectar a isso, a O aplicativo Office Web Apps Server Discovery falhará. O serviço Web de Webconferência ignora a configuração do proxy HTTP, conforme definido no construtor de topologias para a configuração do servidor do Office Web Apps. Como resultado, o cliente do Lync não poderá fazer o compartilhamento do Microsoft PowerPoint 2010 com outros participantes da conferência. Se você estiver instalando o Lync Server local e também configurar o servidor do Office Web Apps no local na rede interna, não será necessária uma configuração de proxy.

**Possíveis**

A única solução alternativa é não ter uma configuração de implantação que exija o uso do proxy HTTP para se comunicar com um servidor externo de Office Web Apps.

</div>

<div>

## <a name="adding-video-to-an-audio-conferencing-provider-conference-is-not-supported"></a>Não há suporte para a adição de vídeo a uma conferência de provedor de audioconferência

**Problema**

Não há suporte para a adição de um vídeo se o usuário estiver associado a uma conferência de provedor de audioconferência para áudio.

**Possíveis**

Não há solução alternativa para esse problema.

</div>

<div>

## <a name="topologies-with-ipv6-enabled-force-the-lync-web-app-silverlight-plug-in-auto-update-to-ensure-screen-sharing-functionality-can-work-from-lync-web-app"></a>Topologias com IPv6 habilitado forçam a atualização automática do plug-in do Silverlight Web App Silverlight para garantir que a funcionalidade de compartilhamento de tela possa funcionar no Lync Web App

**Problema**

Quando uma topologia é configurada com o IPv6 habilitado, os usuários não podem compartilhar a tela a partir do cliente do Lync Web App se uma versão anterior do plug-in de compartilhamento de tela já estiver instalada.

**Possíveis**

Para forçar uma atualização para a versão mais recente do plug-in de compartilhamento de tela ao ingressar na reunião pelo Lync Web App, modifique o valor de **MinSupportedBuildVersion** de "4.0.7457.0" para "4.0.7577.380" nos dois arquivos a seguir:

  - % ProgramFiles\\% Microsoft Lync Server\\15 os\\Web\\Components\\acessam plug-ins\\de cliente int\\ReachAppShPluginProperties. xml

  - % ProgramFiles\\% o Microsoft Lync\\Server 15\\Web\\Components\\atinge\\os plugins do\\cliente ReachAppShPluginProperties. xml

</div>

</div>

<span id="EnterpriseVoice"></span>

<div>

## <a name="enterprise-voice"></a>Enterprise Voice

<div>

## <a name="in-some-cases-a-lync-client-running-on-a-computer-configured-to-use-ipv4-and-ipv6-dual-stack-might-not-support-capabilities-that-rely-in-the-ip-subnet-of-the-computer-such-as-e911-media-bypass-call-admission-control-and-location-based-routing"></a>Em alguns casos, um cliente do Lync executando em um computador configurado para usar o IPv4 e o IPv6 dual stack pode não dar suporte a recursos que dependem da sub-rede IP do computador, como E911, bypass de mídia, controle de admissão de chamadas e roteamento baseado em localização

<div class="">


> [!NOTE]  
> A informação nesta seção está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.



</div>

**Problema**

Quando um cliente do Lync está em execução em um computador habilitado para IPv4 e IPv6 dual stack e com base na resolução DNS do servidor proxy, o cliente pode usar o endereço IPv6 do computador para entrar. Depois disso, o cliente do Lync dará suporte somente aos recursos com suporte para IPv6, que exclui E911, ignorar mídia, controle de admissão de chamadas e roteamento baseado em localização.

**Possíveis**

Para contornar esse problema, desabilite o suporte do IPv6 no computador cliente.

</div>

<div>

## <a name="if-enterprise-voice-is-not-configured-for-a-user-the-user-will-need-to-use-e164-format-to-dial-out-from-a-conference"></a>Se o Enterprise Voice não estiver configurado para um usuário, o usuário precisará usar o formato e164 para discar de uma conferência

**Problema**

Se o Enterprise Voice não estiver configurado para um usuário, esse usuário precisará usar o formato e164 para discar com êxito de uma conferência. Se o formato e164 não for usado, o usuário não será capaz de discar da conferência.

**Possíveis**

Para contornar esse problema, os usuários que não estão habilitados para o Enterprise Voice devem discar de uma conferência usando números no formato e164.

</div>

</div>

<span id="Presence"></span>

<div>

## <a name="presence"></a>Presença

<div>

## <a name="if-a-user-has-selected-block-all-invites-and-communications-while-the-unified-contact-store-is-turned-on-for-the-user-presence-status-is-not-rejected-when-it-should-be"></a>Se um usuário tiver selecionado "bloquear todos os convites e comunicações" enquanto o repositório de contatos unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria ser

**Problema**

Se um usuário tiver selecionado "bloquear todos os convites e comunicações" enquanto o repositório de contatos unificado estiver ativado para o usuário, o status de presença não será rejeitado quando deveria.

**Possíveis**

Para contornar esse problema, você pode desativar o repositório de contatos unificado para o usuário. Para fazer isso, execute os seguintes cmdlets:

    Set-CsUserServicesPolicy -Identity "<user display name>" -UcsAllowed $False

Por exemplo:

    Set-CsUserServicesPolicy -Identity "Ken Myer" -UcsAllowed $False

</div>

<div>

## <a name="office-communications-server-2007-r2-users-homed-on-premises-are-not-able-to-see-the-presence-status-of-skype-for-business-online-users-in-hybrid-deployments---hybrid"></a>Os usuários do Office Communications Server 2007 R2 hospedados no local não podem ver o status de presença de usuários do Skype for Business online em implantações híbridas-híbrido

**Problema**

O problema pode ocorrer em uma implantação híbrida quando você estiver usando um diretor do Lync Server 2013.

O status de presença para os usuários hospedados no Skype for Business Online é exibido como presença desconhecida para usuários locais. Além disso, os usuários hospedados no Skype for Business online não poderão ver o status de presença dos usuários locais do Office Communications Server R2.

**Possíveis**

Para solucionar parcialmente esse problema, altere o servidor primário (msRTCSIP-presencehomeserver) dos usuários do Skype for Business online para apontar para um pool local do Lync Server 2013 em vez do diretor do Lync Server 2013. Você pode modificar essa configuração no servidor front-end local.

Esta solução alternativa exibirá corretamente o status de presença de usuários hospedados no Office Communications Server 2007 R2 para usuários do Skype for Business online.

</div>

</div>

<span id="ResponseGroup"></span>

<div>

## <a name="response-group-application-call-park-application-and-group-call-pickup"></a>Aplicativo de grupo de resposta, aplicativo de estacionamento de chamadas e retirada de chamadas em grupo

<div>

## <a name="a-caller-might-hear-one-second-of-music-on-hold-during-the-establishment-of-a-call-with-the-retrieving-party"></a>Um chamador pode ouvir um segundo de música em espera durante a determinação de uma chamada com a festa de recuperação

<div class="">


> [!NOTE]  
> A informação nesta seção está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.



</div>

**Problema**

Quando uma chamada é recuperada pela retirada de chamadas em grupo, o chamador pode ouvir um segundo de música em espera durante o estabelecimento da chamada com o participante do recuperador.

**Possíveis**

Não há solução alternativa para esse problema.

</div>

<div>

## <a name="a-response-group-agent-can-sign-in-and-sign-out-through-a-lync-server-2010-agent-console-to-lync-server-2010-formal-agent-groups-only"></a>Um agente do grupo de resposta pode entrar e sair por meio de um console do agente do Lync Server 2010 para o Lync Server 2010 somente grupos de agente formal

**Problema**

Um agente do grupo de resposta do Lync Server 2013 pode entrar e sair por meio de um console do agente do Lync Server 2010 para o Lync Server 2010 somente grupos de agente formal. No console do agente do Lync Server 2010, os usuários podem ver apenas o grupo de respostas do Lync Server 2010 ao qual eles pertencem. Eles não podem ver qualquer um dos grupos de resposta do Lync Server 2013 aos quais eles pertencem.

**Possíveis**

Se o agente do grupo de resposta for um usuário do Lync Server 2013 e parte de um grupo de agente formal do Lync Server 2013, o usuário deverá acessar o console do agente do Lync Server 2013 diretamente por meio de um link da Web em um navegador para entrar e sair dos grupos do agente do Lync Server 2013.

</div>

<div>

## <a name="a-lync-server-2010response-group-agent-cannot-place-calls-on-behalf-of-a-lync-server-2013response-group"></a>Um agente do grupo de resposta do Lync Server 2010 não pode fazer chamadas em nome de um grupo de respostas do Lync Server 2013

**Problema**

Um usuário do Lync Server 2010 que é um agente de um grupo de resposta do Lync Server 2013 não consegue fazer uma chamada em nome do grupo de resposta. O grupo de resposta do Lync Server 2013 não estará disponível no cliente do Lync para fazer uma chamada.

**Possíveis**

Para contornar esse problema, você deve mover o usuário do Lync Server 2010 para o Lync Server 2013.

</div>

<div>

## <a name="removing-a-response-group-from-lync-server-2010-after-it-has-been-migrated-to-lync-server-2013-will-prevent-the-response-group-from-accepting-any-incoming-calls"></a>A remoção de um grupo de respostas do Lync Server 2010 após a migração para o Lync Server 2013 impedirá que o grupo de resposta aceite nenhuma chamada recebida

**Problema**

Se um grupo de resposta que foi migrado do Lync Server 2010 para o Lync Server 2013 for removido do Lync Server 2010 por meio do painel de controle do Lync Server ou do Shell de gerenciamento do Lync Server, o grupo resposta do Lync Server 2013 deixará de receber qualquer chamada recebida.

**Possíveis**

Para contornar esse problema, não remova os grupos de resposta do Lync Server 2010 que foram migrados do Lync Server 2010 para o Lync Server 2013.

Se o grupo de resposta já tiver sido removido, você deve reimplantá-lo no Lync Server 2013.

</div>

<div>

## <a name="when-a-new-managed-workflow-is-set-to-inactive-when-created-deployment-of-the-workflow-will-fail"></a>Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falhará

**Problema**

Quando um novo fluxo de trabalho gerenciado é definido como inativo quando criado, a implantação do fluxo de trabalho falha. Esse problema é encontrado quando o fluxo de trabalho é definido como inativo quando criado, mas não afeta um fluxo de trabalho que é editado para configurá-lo como inativo após a implantação.

**Possíveis**

Ao criar e implantar um fluxo de trabalho, defina o fluxo de trabalho como ativo e implante-o. Após a implantação bem-sucedida do fluxo de trabalho, o fluxo de trabalho pode ser editado e definido como inativo.

</div>

<div>

## <a name="removing-a-response-group-from-the-owner-pool-will-prevent-the-response-group-of-the-backup-pool-from-accepting-any-incoming-calls-during-failover-if-the-response-group-has-been-imported-to-the-backup-pool"></a>A remoção de um grupo de resposta do pool de proprietários impedirá que o grupo de resposta do pool de backup aceite chamadas de entrada durante o failover se o grupo de resposta tiver sido importado para o pool de backup

**Problema**

Se um grupo de resposta pertencente ao pool primário tiver sido importado para o pool de backup sem substituir o proprietário, e o grupo de resposta for removido do pool de proprietários, o grupo de resposta no pool de backup não aceitará chamadas de entrada durante o failover.

**Possíveis**

Será necessário reimplantar o grupo de resposta no pool primário. Em seguida, você precisará exportar a configuração do grupo de resposta do pool primário e importá-la para o pool de backup novamente.

Você também pode recriar o grupo de resposta no pool de backup. Nesse caso, o pool de backup será o pool de proprietários do grupo de resposta.

</div>

<div>

## <a name="a-parked-call-cant-be-retrieved-from-the-call-park-application-if-the-retrieve-request-is-done-on-behalf-of-a-response-group"></a>Uma chamada estacionada não pode ser recuperada do aplicativo de estacionamento de chamada se a solicitação de recuperação for feita em nome de um grupo de resposta

**Problema**

Quando as seguintes condições forem verdadeiras, ocorrerá uma solicitação de recuperação para uma chamada estacionada:

  - Um agente faz parte de um grupo de respostas anônimas

  - O agente tenta recuperar uma chamada estacionada do aplicativo de estacionamento de chamada por meio do grupo de resposta anônima

  - O agente tenta recuperar a chamada discando o número órbita por meio da opção ligar em nome de uma chamada em nome ou por meio da mesma opção no cliente do atendedor do Lync

**Possíveis**

Não há soluções alternativas para esse problema. A chamada estacionada deve ser recuperada sem fazer isso em nome de um grupo de resposta.

</div>

</div>

<span id="TopoBuilder"></span>

<div>

## <a name="lync-server-control-panel-topology-builder-and-planning-tool"></a>Painel de Controle, Construtor de Topologia e Ferramenta de Planejamento do Lync Server

<div>

## <a name="planning-tool-limitations"></a>Limitações da ferramenta de planejamento

<div class="">


> [!NOTE]  
> A informação nesta seção está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.



</div>

**Problema**

A ferramenta de planejamento tem as seguintes limitações ao planejar sua implantação:

  - Há suporte para um máximo de 10 sites centrais

  - Cada site central pode ter no máximo 14 sites de filiais

  - Cada site central pode ter no máximo 240.000 usuários

Além disso, a ferramenta de planejamento não inclui valores para os seguintes itens ao calcular a topologia recomendada:

  - O número de usuários que estão hospedados online

  - A porcentagem de usuários habilitados para Federação do XMPP

  - Porcentagem de usuários que estão usando o Lync Web App

**Possíveis**

Não há solução alternativa para esses problemas. Para obter mais informações sobre a ferramenta de planejamento, consulte [projetando a topologia do Lync Server 2013 usando a ferramenta de planejamento](lync-server-2013-designing-the-topology-by-using-the-planning-tool.md).

</div>

<div>

## <a name="planning-tool-may-not-use-previously-defined-ip-addresses-for-the-edge-network-when-updating-options"></a>A ferramenta de planejamento pode não usar os endereços IP definidos anteriormente para a rede de borda ao atualizar as opções

**Problema**

Depois de concluir o design usando a ferramenta de planejamento, se você fizer alterações nas opções de rede de borda, endereços IP adicionais poderão ser adicionados ao design em vez de atualizar os endereços IP existentes. Isso pode ocorrer quando você estiver exibindo os detalhes do diagrama de rede de borda, selecione **clique aqui para atualizar suas opções**e, em seguida, na caixa de diálogo opções de configuração, selecione usar o Edge Network selecionar **eu quero usar os mesmos FQDNS e endereços IP, mas diferentes portas para os serviços de borda no meu servidor de borda**. Aplicar alterações pode resultar em novos endereços IP e servidores de borda sendo adicionados ao design.

**Possíveis**

No momento, não há solução alternativa para esse problema.

</div>

<div>

## <a name="in-lync-server-control-panel-move-all-users-to-pool-may-not-work-as-expected"></a>No painel de controle do Lync Server, "mover todos os usuários para o pool" pode não funcionar como esperado

**Problema**

Ao usar o painel de controle do Lync Server para mover todos os usuários de um pool para outro em um ambiente do Active Directory complexo, como um com vários controladores de domínio e domínios pai/filho, uma mensagem de erro pode ser retornada que diz: "o usuário especificado não é um usuário herdado, use o cmdlet Move-CsUser em vez disso." Isso resulta de tempos de replicação mais longos em ambientes complexos do Active Directory.

**Possíveis**

Para contornar esse problema, siga um destes procedimentos:

  - Use filtros no painel de controle do Lync Server para pesquisar usuários herdados, selecionar esses usuários e usar o **comando mover usuários selecionados para pool** em vez de **mover todos os usuários para o pool**.

  - Use o Shell de gerenciamento do Lync Server para mover usuários herdados em lotes usando cmdlets do Lync Server.

</div>

<div>

## <a name="the-lync-server-control-panel-stops-working-in-a-vmware-environment-after-the-microsoft-silverlight-browser-plug-in-is-updated-to-version-5"></a>O painel de controle do Lync Server para de funcionar em um ambiente VMware após o plug-in do navegador Microsoft Silverlight ser atualizado para a versão 5

**Problema**

Se você usar o painel de controle do Lync Server em um ambiente VMware, o painel de controle do Lync Server poderá parar de funcionar após a atualização do Silverlight para a versão 5.

**Possíveis**

Para contornar esse problema, siga um destes procedimentos:

  - Desinstale o Silverlight 5 e instale o Silverlight 4 [https://go.microsoft.com/fwlink/p/?LinkID=149156\&v=4.0](https://go.microsoft.com/fwlink/p/?linkid=149156%26v=4.0)a partir de.

  - Abra o painel de controle do Lync Server em um computador que não seja um computador virtual do VMware.
    
    Para abrir o painel de controle do Lync Server em um computador remoto, instale as ferramentas de administração do Lync Server no computador e, em seguida, inicie o painel de controle do Lync Server no menu **Iniciar** do Windows.
    
    Você também pode abrir o painel de controle do Lync Server inserindo a URL em um navegador da Web. A URL será semelhante à\<https://de front\_-\_/CSCP.\>FQDN do pool de front-

</div>

<div>

## <a name="an-administrator-cannot-run-the-uninstall-csmirrordb-cmdlet-after-removing-the-mirroring-database-in-topology-builder"></a>Um administrador não pode executar o cmdlet Uninstall-csMirrorDB após remover o banco de dados de espelhamento no construtor de topologias

**Problema**

Quando um administrador desabilita um banco de dados de espelhamento no construtor de topologias e, em seguida, exclui o banco de dados de espelhamento no construtor de topologias, uma mensagem é exibida na lista de tarefas pendentes para que o administrador execute o cmdlet **Uninstall-csMirrorDatabase** para remover o espelhamento do SQL Server. Quando o administrador tenta executar o cmdlet, ele falha.

**Possíveis**

Para remover o espelhamento do SQL de um pool no construtor de topologias, você deve primeiro usar um cmdlet para remover o espelho no SQL Server. Em seguida, você poderá usar o Construtor de Topologias para remover o espelho da topologia. Para remover o espelho no SQL Server, use o cmdlet a seguir:

    Uninstall-CsMirrorDatabase -SqlServerFqdn <SQLServer FQDN> [-SqlInstanceName <SQLServer instance name>] -DatabaseType <Application | Archiving | CentralMgmt | Monitoring | User | BIStaging | PersistentChat | PersistentChatCompliance> [-DropExistingDatabasesOnMirror] [-Verbose]

Por exemplo, para remover o espelhamento e solte os bancos de dados dos bancos de dados do usuário, digite o seguinte:

    Uninstall-CsMirrorDatabase -SqlServerFqdn primaryBE.contoso.com -SqlInstanceName rtc -Verbose -DatabaseType User -DropExistingDatabasesOnMirror

O parâmetro *DropExistingDatabasesOnMirror* faz com que os bancos de dados afetados sejam excluídos do espelho. Depois, para remover o espelho da topologia, faça o seguinte:

1.  No Construtor de Topologias, clique com o botão direito do mouse no pool e clique em **Editar Propriedades**.

2.  Desmarque **habilitar o espelhamento do SQL Store** e clique em **OK**.

3.  Publique a topologia.

<div class="">


> [!IMPORTANT]  
> Sempre que você fizer uma alteração em uma relação de espelhamento de banco de dados back-end, será preciso reiniciar todos os servidores de front-end do pool.



</div>

</div>

<div>

## <a name="validation-errors-are-returned-in-topology-builder-when-an-administrator-attempts-to-remove-a-deployment-with-a-front-end-pool-that-has-an-associated-witness-store"></a>Erros de validação são retornados no construtor de topologias quando um administrador tenta remover uma implantação com um pool de front-end que tenha um repositório de testemunha associado

**Problema**

Se um administrador tentar usar o comando **remover implantação** no construtor de topologias para remover uma implantação que inclui um pool de front-ends com um repositório testemunha associado, um erro de validação será exibido no construtor de topologias e a ação não continuará.

**Possíveis**

Para contornar esse problema, siga um destes procedimentos:

  - Remova o repositório testemunha antes de tentar remover a implantação.

  - Adicione um repositório testemunha para o pool de front-ends e remova-o.

</div>

<div>

## <a name="persistent-chat-server-deployment-information-is-inconsistent-between-the-planning-tool-and-topology-builder"></a>As informações de implantação do servidor de chat persistente são inconsistentes entre a ferramenta de planejamento e o construtor de topologias

**Problema**

Quando o Lync Server 2013, a ferramenta de planejamento emite o diagrama de topologia de site para uma implantação persistente do servidor de chat com a recuperação de desastre habilitada, o diagrama de topologia de site inclui vários sites (físicos), com servidores de chat persistentes atribuídos uniformemente em cada instalação. No construtor de topologias, todos os servidores de chat persistentes são representados como pertencentes a um único site (lógico) e estão listados no mesmo nó de pool persistente do servidor de chat.

**Possíveis**

No momento, não temos uma solução alternativa para esse problema. O usuário deve analisar a saída da ferramenta de planejamento para a implantação persistente do servidor de chat e modificar o plano para atender às suas necessidades específicas.

</div>

</div>

<span id="Localization"></span>

<div>

## <a name="localization"></a>Localiza

<div>

## <a name="monitoring"></a>Monitoramento

<div>

## <a name="the-deploy-monitoring-reports-wizard-displays-incorrect-characters-under-certain-circumstances-when-using-the-east-asian-version-of-lync-server"></a>O assistente implantar relatórios de monitoramento exibe caracteres incorretos em determinadas circunstâncias ao usar a versão do leste asiático do Lync Server

**Problema**

Ao usar uma versão do leste asiático do Lync Server 2013 — por exemplo, chinês (simplificado), chinês (tradicional), japonês ou coreano – em um sistema operacional que tenha a localidade do sistema não definida para um idioma do leste asiático, o assistente implantar relatórios de monitoramento será Exibir pontos de interrogação ou outros caracteres em vez de mensagens localizadas.

**Possíveis**

Para corrigir esse problema, defina a localidade do sistema operacional e do Lync Server 2013 para o mesmo idioma, o que mostrará todas as mensagens corretamente.

</div>

</div>

<div>

## <a name="lync-server-control-panel"></a>Painel de Controle do Lync Server

<div>

## <a name="in-certain-cases-the-first-item-in-the-top-navigation-bar-on-a-page-of-lync-server-control-panel-disappears-when-the-last-item-in-the-top-navigation-bar-is-clicked"></a>Em certos casos, o primeiro item na barra de navegação superior em uma página do painel de controle do Lync Server desaparece quando o último item na barra de navegação superior é clicado

**Problema**

Há três casos conhecidos em que clicar no último item na barra de navegação superior de uma página do painel de controle do Lync Server fará com que o primeiro item na barra de navegação superior desapareça:

  - Na versão francesa, na página "Féderation et accès externe", o item "Stratégie d'accès externo" desaparecerá quando "Partenaires fédérés XMPP" for clicado.

  - Na versão em alemão, na página "clientes", o item "Clientversionskonfiguration" desaparece quando "Pushbenachrichtigungskonfiguration" é clicado.

  - Na versão em Russo, na página "Конфигурация сети", o item "Глобально" desaparece quando "Маршрут региона" é clicado.

**Possíveis**

Para contornar esse problema, atualize a página do painel de controle do Lync Server no navegador. A página será carregada no navegador com todos os itens na barra de navegação superior exibida.

</div>

</div>

<div>

## <a name="address-book"></a>Catálogo de endereços

<div>

## <a name="indexing-in-the-address-book-does-not-work-as-expected-in-some-languages"></a>A indexação no catálogo de endereços não funciona como esperado em alguns idiomas

<div class="">


> [!NOTE]  
> A informação nesta seção está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.



</div>

Se as propriedades de um usuário contiverem um campo indexado e esse campo contiver apenas caracteres que não podem ser indexados, o usuário não será exibido nas pesquisas realizadas no catálogo de endereços.

Os seguintes caracteres e locais não podem ser indexados:

  - Caracteres cirílico, grego e armênio maiúsculo

  - Caracteres acentuados em maiúsculas

  - Tailandês

  - Laosiana

  - Sinal

  - Devanagari

  - Etíope

  - Sinal

  - Bengalês

  - Guzerate

  - Telugu

  - Todos os outros scripts indianos

</div>

</div>

<div>

## <a name="lync-web-app-web-scheduler-and-web-components"></a>Lync Web App, Web Scheduler e Web Components

<div>

## <a name="language-fallback-for-certain-languages-in-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-might-not-work-as-expected"></a>O fallback de idioma para determinados idiomas no Lync Web Scheduler, no redirecionamento, no inicializador de junção, no gerenciamento de salas de chat persistente e OCTab pode não funcionar como esperado

**Problema**

Ao selecionar uma localidade neutra em um navegador da Web (no Internet Explorer, por exemplo, o nome do idioma sem especificação adicional, como \["\]norueguês não") em vez de uma localidade especificando o idioma, o script e a localidade (como "norueguês \[, BOKMÅL (\]Noruega) NB-não") pode levar a comportamento de exibição inesperado para certos idiomas no Lync Web Scheduler, discar, inicializador de junção, gerenciamento de salas de chat persistente e OCTab. Por exemplo, os usuários podem ver a página em inglês quando um dos seguintes idiomas estiver selecionado:

  - Norueguês

  - Português

  - Sérvio

**Possíveis**

Se você quiser selecionar um idioma com uma localidade neutra, sempre certifique-se de adicionar o idioma com uma localidade específica (com código de script e/ou país) como um idioma adicional na lista de preferências de idioma do seu navegador.

</div>

<div>

## <a name="there-is-limited-support-for-azeri-and-uzbek-locales-when-using-lync-web-scheduler-dial-in-join-launcher-persistent-chat-room-management-and-octab-in-some-web-browsers"></a>Há suporte limitado para localidades azeri e uzbeque ao usar o Web Scheduler do Lync, o recurso de discagem, o inicializador de junção persistente, o gerenciamento de salas de chat persistente e o OCTab em alguns navegadores da Web

<div class="">


> [!NOTE]  
> A informação nesta seção está relacionada às Atualizações Cumulativas para Lync Server 2013: Fevereiro de 2013.



</div>

**Problema**

Quando você usa o Internet Explorer 8 ou o Internet Explorer 9 e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), as páginas de discagem e do inicializador de junção serão exibidas em inglês ou no conjunto de idiomas preferencial no navegador.

Quando você usa o Firefox ou navegadores Chrome e define o idioma do navegador como Azeri (latino) ou uzbeque (latino), o Lync Web App, o Lync Web Scheduler e RGS OCTab serão exibidos em inglês ou no conjunto de idiomas preferencial para o navegador.

A localidade uzbeque (latino) não é compatível com o navegador Safari.

**Possíveis**

Não há solução alternativa para esses problemas.

</div>

</div>

<div>

## <a name="the-drop-down-arrow-is-missing-for-join-meeting-from-list-in-the-romanian-version-of-lync-web-app"></a>A seta suspensa está ausente para a lista "ingressar na reunião de" na versão em romeno do Lync Web App

**Problema**

Quando um usuário que estiver usando a versão em romeno do Lync Web App executar as etapas a seguir, a seta suspensa não será exibida para **participar da reunião** na lista suspensa:

1.  Selecione **lembrar-me neste computador** na guia **geral** .

2.  Selecione a guia **telefone** .

3.  Clique na lista suspensa de **ingressar na reunião**.
    
    Os usuários não verão uma seta que indica que há mais opções do que o **Lync**padrão do Lync, que inclui: **não ingressar no áudio** (em Romeno, "nu se asociaža o componenteum áudio") e **novo número**"(em Romeno," Număr Nou ").

**Possíveis**

Embora a seta desta lista suspensa não seja exibida, os usuários ainda podem selecionar as configurações adicionais na lista clicando no valor padrão.

</div>

<div>

## <a name="when-using-the-turkish-version-of-lync-web-scheduler-a-meeting-cannot-be-saved-when-using-the-people-i-choose-option-under-who-is-a-presenter"></a>Ao usar a versão em Turco do Web Scheduler do Lync, não é possível salvar uma reunião usando a opção "quem eu escolher" em "quem é um apresentador"

**Problema**

Ao criar ou editar uma reunião na versão em Turco do Web Scheduler do Lync, a opção "pessoas que eu escolher" em "quem é um apresentador" não é suportada. Quando esta opção for selecionada, a reunião não poderá ser salva. Em vez disso, uma mensagem de erro é exibida, indicando que uma ou mais pessoas não podem se tornar apresentadores.

**Possíveis**

Para contornar esse problema, os usuários podem usar a opção padrão "pessoas da minha empresa" ou qualquer outra opção, como "somente organizador" ou "todos, incluindo pessoas de fora da minha empresa". O organizador pode rebaixar ou promover pessoas para as funções corretas mais tarde, depois de ingressar na reunião.

Como alternativa, os usuários que entendem outro idioma podem alterar a seleção de idioma no navegador para um dos outros idiomas com suporte do 43 e tentar usar a opção "quem eu escolher".

</div>

</div>

<span id="Copyright"></span>

<div>

## <a name="copyright"></a>Material

Este documento dá suporte a uma versão preliminar de um produto de software que pode ser alterado substancialmente antes do lançamento comercial final, além de informações confidenciais e proprietárias da Microsoft Corporation. Ela é divulgada de acordo com um contrato de não divulgação entre o destinatário e a Microsoft. Este documento é fornecido apenas para fins informativos, e a Microsoft não oferece garantias, sejam expressas ou implícitas, neste documento. As informações contidas neste documento, incluindo URL e outras referências de site da Internet, estão sujeitas a mudanças sem aviso prévio. Todo o risco do uso ou dos resultados do uso deste documento permanecerá com o usuário. Salvo indicação em contrário, as empresas, organizações, produtos, nomes de domínio, endereços de email, logotipos, pessoas, lugares e eventos descritos nos exemplos aqui são fictícios. Nenhuma associação com qualquer empresa, organização, produto, nome de domínio, endereço de email, logotipo, pessoa, lugar ou evento real é intencional ou deve ser inferida. Obedecer a todas as leis de direitos autorais aplicáveis é responsável pelo usuário. Sem limitar os direitos sob direitos autorais, nenhuma parte deste documento pode ser reproduzida, armazenada ou introduzida em um sistema de recuperação, ou transmitida de qualquer forma ou por qualquer meio (eletrônico, mecânico, fotocópia, gravação ou de outra forma) ou para qualquer propósito, sem a permissão expressa por escrito da Microsoft Corporation.

A Microsoft pode ter patentes, aplicativos de patente, marcas comerciais, direitos autorais ou outros direitos de propriedade intelectual que abranjam o assunto deste documento. Exceto conforme expressamente fornecido em qualquer contrato de licença escrito da Microsoft, o fornecimento deste documento não lhe concede nenhuma licença para essas patentes, marcas comerciais, direitos autorais ou outra propriedade intelectual.

© 2012 Microsoft Corporation. Todos os direitos reservados.

Microsoft, Windows, Windows Live, Active Directory, Internet Explorer, MSN, Outlook e SQL Server são marcas registradas ou marcas comerciais da Microsoft Corporation nos Estados Unidos e/ou em outros países/regiões.

Todas as outras marcas comerciais são propriedade de seus respectivos proprietários.

</div>

</div>

<span> </span>

</div>

</div>

</div>

