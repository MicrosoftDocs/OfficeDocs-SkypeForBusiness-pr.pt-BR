---
title: 'Lync Server 2013: requisitos de backup e restauração: dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca6823c1f3e8265f7b06ea0d175b58d42ef4a08
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135738"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisitos de backup e restauração no Lync Server 2013: data

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-26_

O Lync Server usa configurações e informações de configuração que são armazenadas em bancos de dados e dados armazenados em bancos de dados e repositórios de arquivos. Este tópico descreve os dados dos quais você precisa fazer backup para poder restaurar o serviço se sua organização tiver uma falha ou uma interrupção, e também identificar os dados e os componentes usados pelo Lync Server para os quais você precisa fazer backup separadamente.

<div>

## <a name="settings-and-configuration-requirements"></a>Configurações e requisitos de configuração

Este tópico inclui procedimentos para fazer backup e restaurar as configurações e as informações de configuração necessárias para a recuperação do serviço do Lync Server. As informações de configuração estão localizadas no repositório de gerenciamento central ou em outro banco de dados de back-end ou no servidor Standard Edition.

A tabela a seguir identifica as configurações e as informações de configuração necessárias para fazer backup e restauração.

### <a name="settings-and-configuration-data"></a>Definições e dados de configuração

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipos de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informações de configuração de topologia</p></td>
<td><p>Repositório de gerenciamento central (banco de dados: XDS. MDF)</p></td>
<td><p>Configurações de topologia, política e configuração.</p>
<p>Faça o backup com seus backups regulares e depois de usar o painel de controle ou cmdlets do Lync Server para modificar sua configuração ou políticas.</p></td>
</tr>
<tr class="even">
<td><p>Informações de local</p></td>
<td><p>Repositório de gerenciamento central (banco de dados: Lis. MDF)</p></td>
<td><p>Informações de configuração do Enterprise Voice Enhanced 9-1-1 (E9-1-1). Geralmente, essas informações são estáticas.</p>
<p>Faça o backup com seus backups regulares.</p></td>
</tr>
<tr class="odd">
<td><p>Informações de configuração do grupo de resposta</p></td>
<td><p>Servidor back-end ou servidor Standard Edition (banco de dados: RgsConfig. MDF)</p></td>
<td><p>Grupos de agente de grupo de resposta, filas e fluxos de trabalho.</p>
<p>Faça o backup com seus backups regulares e depois de adicionar ou alterar grupos de agentes, filas ou fluxos de trabalho.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisitos de dados

Veja a seguir uma lista dos dados do Lync Server que você precisa fazer o backup para que possa restaurar o serviço do Lync Server em caso de falha.

Observe que alguns tipos de dados não são necessários para a recuperação. Este tópico não contém procedimentos para fazer backup desses tipos de dados, que incluem o seguinte:

  - Dados de usuários transitórios, como pontos de extremidade e assinaturas, servidores de conferência ativos e Estados de conferência transitórias (banco de dados: RtcDyn. MDF)

  - Dados do catálogo de endereços (bancos de dados: RTCAb. MDF e Rtcab1. MDF). O banco de dados do catálogo de endereços é regenerado automaticamente de serviços de domínio do Active Directory.

  - Informações dinâmicas para o aplicativo de estacionamento de chamada (banco de dados: CpsDyn. MDF)

  - Dados de grupo de resposta transitório, como o estado de entrada de agentes e informações de chamada em espera (banco de dados: RgsDyn. MDF)

  - O banco de dados de conformidade para chat persistente (banco de dados: MgcComp. MDF). Se você tiver a conformidade de chat persistente habilitada, as informações no banco de dados de conformidade de chat persistente serão temporárias, contanto que você tenha um adaptador configurado para ler informações do banco de dados e convertê-lo em um formato alternativo. Portanto, o banco de dados de conformidade para chat persistente é considerado temporário.
    
    Lync Server 2013 persistent chat Server é fornecido com um adaptador XML. Você também pode instalar adaptadores personalizados que usam esses dados e movê-los para outras fontes, como arquivos mortos hospedados do Exchange.

A tabela a seguir identifica os dados necessários para backup e restauração.

### <a name="data-stored-in-databases"></a>Dados armazenados em bancos de dados

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipos de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados de usuário persistente</p></td>
<td><p>Servidor back-end ou servidor Standard Edition (banco de dados: RTCXDS. MDF)</p></td>
<td><p>Direitos de usuário, listas de contatos do usuário, dados de servidor ou pool, conferências agendadas e assim por diante. Estes dados de usuário não incluem conteúdo carregado em uma conferência.</p>
<p>Faça o backup com seus backups regulares. Essas informações são dinâmicas, mas a perda de atualizações não é catastrófica no Lync Server se você precisar restaurar para o último backup regular. Se as listas de contatos forem fundamentais para sua organização, você pode fazer o backup desses dados com mais frequência.</p></td>
</tr>
<tr class="even">
<td><p>Arquivamento de dados</p></td>
<td><p>Banco de dados de arquivamento (banco de dados: LcsLog. MDF)</p>
<p>Esses dados podem ser armazenados no Exchange 2013, se você tiver habilitado a opção de integração do Microsoft Exchange. Caso contrário, esses dados são mantidos em um banco de dados de arquivamento do Lync Server, que pode ser colocado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</p></td>
<td><p>Mensagens instantâneas (IM) e conteúdo da reunião.</p>
<p>Esses dados não são críticos para o Lync Server, mas podem ser fundamentais para sua organização para fins normativos. Determine o backup agendado de acordo.</p></td>
</tr>
<tr class="odd">
<td><p>Dados de monitoramento</p></td>
<td><p>Bancos de dados de monitoramento (LcsCDR. MDF e QoeMetrics. MDF)</p>
<p>Esses bancos de dados podem ser colocados com outro banco de dados do Lync Server ou autônomos em um servidor de banco de dados separado.</p></td>
<td><p>Registros de detalhes da chamada (LcsCDR. MDF) e métricas de QoE (qualidade da experiência) (QoeMetrics. MDF).</p>
<p>Os registros de detalhes das chamadas são dinâmicos e podem ser fundamentais para a sua empresa. Determine sua agenda de backup, considerando se você precisa desses registros por razões regulamentares.</p>
<p>As informações de qualidade da experiência são dinâmicas. A perda de dados de QoE não é essencial para a operação do Lync Server, mas pode ser crucial para a sua empresa. Determine sua agenda de backup com base em quão crítica essas informações estão à sua organização.</p></td>
</tr>
<tr class="even">
<td><p>Dados de chat persistente</p></td>
<td><p>Banco de dados de chat persistente (gerenciadas. MDF).</p>
<p>Este banco de dados pode ser colocado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</p></td>
<td><p>Dados de chat persistente são o conteúdo de chat real que está sendo lançado em salas de chat. Esses dados costumam ser críticos para os negócios.</p>
<p>Você pode optar por usar o backup do SQL Server ou exportar o banco de dados usando o cmdlet <strong>Export-CsPersistentChatData</strong> fornecido no Lync Server. Para recuperação dos dados, você pode importar e restaurar o banco de dados para o ponto do último backup completo, o que significa que não é possível restaurar o banco de dados para o ponto de falha.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisitos de dados do repositório de arquivos

Em uma implantação Enterprise Edition, o repositório de arquivos do Lync Server normalmente está localizado em um servidor de arquivos. Em uma implantação do Standard Edition, o repositório de arquivos do Lync Server está localizado por padrão no servidor Standard Edition. Normalmente, há um repositório de arquivos do Lync Server que é compartilhado para um site. O repositório de arquivos de chat persistente usa o mesmo compartilhamento de arquivo que o repositório de arquivos do Lync Server.

Os locais do repositório de arquivos \\ \\são\\identificados como o nome do compartilhamento do servidor. Para localizar os locais específicos dos repositórios de arquivos, abra o construtor de topologias e examine o nó **repositórios de arquivos** .

A tabela a seguir identifica os repositórios de arquivos necessários para backup e restauração.

### <a name="file-stores"></a>Repositórios de Arquivo

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipos de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Repositório de arquivos do Lync Server</p></td>
<td><p>Normalmente em um servidor de arquivos, um cluster de arquivos ou um servidor Standard Edition</p></td>
<td><p>Conteúdo de reunião, metadados de conteúdo de reunião, logs de conformidade, arquivos de dados de aplicativo, arquivos de atualização para atualizações de dispositivo, arquivos de áudio para grupo de resposta, estacionamento de chamada e aplicativos de anúncio e arquivos publicados em salas de chat persistente.</p>
<p>Faça o backup com seus backups regulares.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Requisitos adicionais de backup

Para ajudar a garantir a capacidade de restaurar os serviços do Lync Server em caso de falha, você deve fazer o backup de alguns componentes necessários que não fazem parte do Lync Server propriamente dito. Os seguintes componentes não são armazenados ou restaurados como parte do processo de backup e restauração do Lync Server descrito neste documento:

  - **Serviços de domínio do Active Directory**   você precisa fazer backup do AD DS usando as ferramentas do Active Directory ao mesmo tempo em que faz backup do Lync Server. É importante manter o AD DS sincronizado com o Lync Server para evitar problemas que podem ocorrer quando o Lync Server espera objetos de contato que não correspondem àqueles no AD DS. O AD DS armazena as seguintes configurações que são usadas pelo Lync Server:
    
      - URI do SIP do usuário e outras configurações do usuário.
    
      - Objetos de contato para aplicativos como o grupo de resposta e o atendedor de conferência.
    
      - Um ponteiro para o repositório de gerenciamento central.
    
      - Conta de autenticação Kerberos (um objeto de computador opcional) e grupos de segurança do Lync Server.
    
    Para obter detalhes sobre como fazer backup e restaurar o AD DS no Windows Server 2008, consulte "guia passo a passo de backup e recuperação do AD DS [https://go.microsoft.com/fwlink/p/?linkId=209105](https://go.microsoft.com/fwlink/p/?linkid=209105)" em.

  - **A autoridade de certificação e os certificados**   usam a política da sua organização para fazer o backup da autoridade de certificação (CA) e dos certificados. Se você usar chaves privadas exportáveis, será possível fazer backup do certificado e da chave privada e exportá-los se usar os procedimentos neste documento para restaurar o Lync Server. Se você usar uma autoridade de certificação interna, poderá reinscrever se precisar restaurar o Lync Server. É importante que você mantenha a chave privada em um local seguro, onde estará disponível se um computador falhar.

  - **System Center Operations Manager**   se você usar o Microsoft System Center Operations Manager (anteriormente Microsoft Operations Manager) para monitorar sua implantação do Lync Server, é possível fazer o backup dos dados que ele cria enquanto está monitorando o Lync Server. Use o processo de backup padrão do SQL Server para fazer backup dos arquivos do System Center Operations Manager. Esses arquivos não são restaurados durante a recuperação.

  - **Configuração de gateway de rede telefônica pública comutada (PSTN)**   se você usar aparelhos de filial persistente ou Enterprise Voice, precisará fazer o backup da configuração de gateway PSTN. Consulte seu fornecedor para obter detalhes sobre o backup e a restauração de configurações de gateway PSTN.

  - **Versões coexistentes do Lync Server ou do Office Communications Server**   se sua implantação do Lync Server 2013 coexistir com o Lync Server 2010 ou uma versão anterior do Office Communications Server, você não pode usar os procedimentos neste documento para fazer o backup ou a restauração da versão anterior. Em vez disso, você deve usar os procedimentos de backup e restauração documentados especificamente para sua versão anterior. Para obter detalhes sobre como fazer backup e restaurar o Lync Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=265417](https://go.microsoft.com/fwlink/p/?linkid=265417) , consulte. Para obter detalhes sobre como fazer backup e restaurar o Microsoft Office Communications Server 2007 [https://go.microsoft.com/fwlink/p/?linkId=168162](https://go.microsoft.com/fwlink/p/?linkid=168162)R2, consulte.

  - **Informações de infraestrutura**   você precisa fazer o backup de informações sobre sua infraestrutura, como a configuração de seu firewall, configuração de balanceamento de carga, configuração de serviços de informações da Internet (IIS), registros DNS (sistema de nomes de domínio) e endereços IP e configuração de protocolo de configuração dinâmica de hosts (DHCP). Para obter detalhes sobre como fazer backup desses componentes, verifique com seus respectivos fornecedores.

  - **Microsoft Exchange e Exchange Unified Messaging (um)**   fazer backup e restaurar o Microsoft Exchange e o um do Exchange conforme descrito na documentação do Microsoft Exchange. Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2013 [https://go.microsoft.com/fwlink/?LinkId=285384](https://go.microsoft.com/fwlink/?linkid=285384), consulte. Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2010 [https://go.microsoft.com/fwlink/p/?linkId=209179](https://go.microsoft.com/fwlink/p/?linkid=209179), consulte.
    
    Observe que o Lync Server 2013 introduz a capacidade de ter listas de contatos de usuário, fotos de usuário de alta definição e dados de arquivamento armazenados no Exchange 2013. Consulte a lista a seguir para ver como fazer backup desses tipos de dados:
    
      - Há backup de **fotos de alta definição** como parte do backup do Exchange Server.
    
      - O **repositório unificado de contatos** é apresentado no Lync Server 2013. O repositório unificado de contatos permite que os usuários mantenham todas as informações de contato no Exchange 2013.
        
        Você deve verificar se os backups estão atualizados para os usuários em termos de que seus contatos de usuário estejam armazenados no repositório unificado de contatos ou no servidor back-end do Lync. Os cenários a seguir ilustram onde a migração de contatos do usuário para o repositório unificado de contatos pode causar problemas para o processo de backup e restauração.
        
        **Cenário 1:** Os contatos do usuário são migrados para o repositório unificado de contatos e uma restauração é realizada de um backup do Lync Server realizado antes da migração dos contatos do usuário. Neste cenário, o usuário terá um estado de contatos desatualizados para até um dia até a tarefa de migração do Lync Server começar a migrar contatos de usuário para o Exchange. (Observe que, como os contatos do usuário foram anteriormente migrados para o repositório unificado de contatos, as informações de contato do Exchange serão usadas). Nenhuma intervenção do administrador é necessária neste cenário.
        
        **Cenário 2:** Os contatos do usuário foram armazenados anteriormente no repositório unificado de contatos, mas revertidos. Uma restauração é realizada de um backup do Lync Server feito quando os contatos do usuário foram armazenados no repositório unificado de contatos. Neste cenário, uma mensagem de `Error: Incorrect Exchange Version` erro nos logs do servidor cliente ou do Lyss pode indicar isso como um problema. O usuário poderá acessar a lista de contatos no Lync 2013 diretamente do Exchange, mas o estado do cliente não corresponderá ao estado do Lync Server. Para corrigir isso, um administrador precisará executar os cmdlets **Invoke-CsUCSRollback** para os usuários afetados.
    
      - **Os dados de arquivamento** podem ser armazenados no Exchange 2013. Esses dados não são críticos para o Lync Server, mas podem ser fundamentais para sua organização para fins normativos. Se os dados de arquivamento estiverem armazenados no Exchange e forem fundamentais para sua organização, siga os procedimentos de backup e restauração do Exchange. Observe que os dados de arquivamento armazenados no Exchange não podem ser movidos de volta para o Lync Server. Além disso, não há como mover dados já armazenados no banco de dados de arquivamento do Lync para o Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

