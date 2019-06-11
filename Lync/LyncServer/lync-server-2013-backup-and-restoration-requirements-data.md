---
title: 'Lync Server 2013: requisitos de backup e restauração: dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Backup and restoration requirements: data'
ms:assetid: ecfb8e4d-cb4f-476d-9772-4486bd683c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202194(v=OCS.15)
ms:contentKeyID: 51541526
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 54814295343b99cb51e5827791df160dbeff2638
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-requirements-in-lync-server-2013-data"></a>Requisitos de backup e restauração no Lync Server 2013: dados

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-26_

O Lync Server usa configurações e informações de configuração que são armazenadas em bancos de dados e dados armazenados em bancos de dados e repositórios de arquivos. Este tópico descreve os dados dos quais você precisa fazer backup para restaurar o serviço se a sua organização tiver uma falha ou uma interrupção, além de identificar os dados e os componentes usados pelo Lync Server dos quais você precisa fazer backup separadamente.

<div>

## <a name="settings-and-configuration-requirements"></a>Configurações e requisitos de configuração

Este tópico inclui procedimentos para fazer o backup e a restauração das configurações e informações de configuração necessárias para a recuperação do serviço do Lync Server. As informações de configuração estão localizadas no repositório de gerenciamento central ou em outro banco de dados back-end ou no servidor Standard Edition.

A tabela a seguir identifica as configurações e informações de configuração das quais você precisa fazer backup e restaurar.

### <a name="settings-and-configuration-data"></a>Configurações e dados de configuração

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Informações de configuração de topologia</p></td>
<td><p>Repositório de gerenciamento central (banco de dados: XDS. MDF)</p></td>
<td><p>Configurações de topologia, política e configuração.</p>
<p>Faça backup com seus backups regulares e depois de usar os cmdlets ou o painel de controle do Lync Server para modificar sua configuração ou políticas.</p></td>
</tr>
<tr class="even">
<td><p>Informações de localização</p></td>
<td><p>Repositório de gerenciamento central (banco de dados: Lis. MDF)</p></td>
<td><p>Informações de configuração do 9-1-1 (E9-1-1) avançada do Enterprise Voice. Geralmente, essas informações são estáticas.</p>
<p>Faça backup com seus backups regulares.</p></td>
</tr>
<tr class="odd">
<td><p>Informações de configuração do grupo de resposta</p></td>
<td><p>Servidor back-end ou servidor Standard Edition (banco de dados: RgsConfig. MDF)</p></td>
<td><p>Grupo de resposta grupos, filas e fluxos de trabalho.</p>
<p>Faça backup com seus backups regulares e depois de adicionar ou alterar grupos de agente, filas ou fluxos de trabalho.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="data-requirements"></a>Requisitos de dados

Aqui está uma lista dos dados do Lync Server dos quais você precisa fazer backup para que você possa restaurar o serviço do Lync Server em caso de falha.

Observe que alguns tipos de dados não são necessários para a recuperação. Este tópico não contém procedimentos para fazer backup desses tipos de dados, que incluem o seguinte:

  - Dados de usuários transitórios, como pontos de extremidade e assinaturas, servidores de conferência ativos e Estados de conferência transitória (banco de dados: RtcDyn. MDF)

  - Dados de catálogo de endereços (bancos de dados: RTCAb. MDF e Rtcab1. MDF). O banco de dados do catálogo de endereços é regenerado automaticamente dos serviços de domínio Active Directory.

  - Informações dinâmicas para o aplicativo parque de chamadas (banco de dados: CpsDyn. MDF)

  - Dados de grupo de resposta transitório, como estado de entrada do agente e informações de chamada em espera (banco de dados: RgsDyn. MDF)

  - O banco de dados de conformidade para chats persistentes (banco de dados: MgcComp. MDF). Se a conformidade de chat persistente estiver habilitada, as informações no banco de dados de conformidade de chat persistente serão transitórias desde que você tenha um adaptador configurado para ler as informações do banco de dados e convertê-las em um formato alternativo. Portanto, o banco de dados de conformidade para chats persistentes é considerado transitório.
    
    O servidor de chat persistente do Lync Server 2013 vem com um adaptador XML. Você também pode instalar adaptadores personalizados que tomam esses dados e movê-los para outras fontes, como arquivos Exchange hospedados.

A tabela a seguir identifica os dados dos quais você precisa fazer backup e restaurar.

### <a name="data-stored-in-databases"></a>Dados armazenados em bancos de dados

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dados persistentes do usuário</p></td>
<td><p>Servidor back-end ou servidor Standard Edition (banco de dados: RTCXDS. MDF)</p></td>
<td><p>Direitos de usuário, listas de contatos do usuário, dados de servidor ou pool, conferências programadas e assim por diante. Estes dados do usuário não incluem o conteúdo carregado em uma conferência.</p>
<p>Faça backup com seus backups regulares. Essas informações são dinâmicas, mas a perda de atualizações não é catastrófica no Lync Server, caso seja necessário restaurar o último backup regular. Se as listas de contatos forem essenciais para a sua organização, você poderá fazer backup desses dados com mais frequência.</p></td>
</tr>
<tr class="even">
<td><p>Arquivar dados</p></td>
<td><p>Banco de dados de arquivamento (banco de dados: LcsLog. MDF)</p>
<p>Esses dados podem ser armazenados no Exchange 2013, se você tiver habilitado a opção de integração do Microsoft Exchange. Caso contrário, esses dados são mantidos em um banco de dados de arquivamento do Lync Server, que pode ser posicionado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</p></td>
<td><p>Mensagens instantâneas (IM) e conteúdo da reunião.</p>
<p>Esses dados não são críticos para o Lync Server, mas podem ser críticos para a sua organização para fins reguladores. Determine o seu cronograma de backup de acordo.</p></td>
</tr>
<tr class="odd">
<td><p>Monitorando dados</p></td>
<td><p>Bancos de dados de monitoramento (LcsCDR. MDF e QoeMetrics. MDF)</p>
<p>Esses bancos de dados podem estar posicionados com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</p></td>
<td><p>Registros de detalhes da chamada (LcsCDR. MDF) e métricas de qualidade da experiência (QoE) (QoeMetrics. MDF).</p>
<p>Os registros de detalhes da chamada são dinâmicos e podem ser críticos para a sua empresa. Determine o seu cronograma de backup, considerando se você precisa desses registros por motivos reguladores.</p>
<p>As informações de qualidade da experiência são dinâmicas. A perda de dados de QoE não é essencial para a operação do Lync Server, mas pode ser fundamental para a sua empresa. Determine sua agenda de backup com base em quão críticas essas informações são para sua organização.</p></td>
</tr>
<tr class="even">
<td><p>Dados de chat persistente</p></td>
<td><p>Banco de dados de chat persistente (MGD. MDF).</p>
<p>Esse banco de dados pode estar posicionado com outro banco de dados do Lync Server ou autônomo em um servidor de banco de dados separado.</p></td>
<td><p>Dados de chat persistentes são postados pelo conteúdo real do chat em salas de chat. Geralmente, esses dados são críticos para os negócios.</p>
<p>Você pode optar por usar o backup do SQL Server ou exportar o banco de dados usando o cmdlet <strong>Export-CsPersistentChatData</strong> fornecido no Lync Server. Para a recuperação dos dados, você pode importar e restaurar o banco de dados para o ponto do último backup completo, o que significa que você não pode restaurar o banco de dados ao ponto de falha.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="file-store-data-requirements"></a>Requisitos de dados do repositório de arquivos

Em uma implantação do Enterprise Edition, o armazenamento de arquivos do Lync Server geralmente está localizado em um servidor de arquivos. Em uma implantação de edição padrão, o repositório de arquivos do Lync Server está localizado por padrão no servidor Standard Edition. Geralmente, há um repositório de arquivos do Lync Server que é compartilhado para um site. O repositório de arquivos de chat persistente usa o mesmo compartilhamento de arquivo que o repositório de arquivos do Lync Server.

Locais do repositório de arquivos são \\ \\identificados\\como nome do compartilhamento do servidor. Para localizar os locais específicos de seus armazenamentos de arquivos, abra o construtor de topologias e procure no nó armazenamentos de **arquivos** .

A tabela a seguir identifica os armazenamentos de arquivos que você precisa fazer backup e restaurar.

### <a name="file-stores"></a>Repositórios de arquivos

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de dados</th>
<th>Onde armazenado</th>
<th>Descrição/quando fazer backup</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Repositório de arquivos do Lync Server</p></td>
<td><p>Geralmente em um servidor de arquivos, um cluster de arquivos ou um servidor Standard Edition</p></td>
<td><p>Conteúdo da reunião, metadados de conteúdo da reunião, logs de conformidade da reunião, arquivos de dados do aplicativo, arquivos de atualização para atualizações de dispositivo, arquivos de áudio para o grupo de resposta, estacionamento de chamadas e aplicativos de anúncio e arquivos postados em salas de chat persistente.</p>
<p>Faça backup com seus backups regulares.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="additional-backup-requirements"></a>Requisitos adicionais de backup

Para ajudar a garantir a capacidade de restaurar os serviços do Lync Server em caso de falha, você deve fazer backup de alguns componentes necessários que não fazem parte do Lync Server propriamente dito. Não é possível fazer backup ou restauração dos seguintes componentes, como parte do processo de backup e restauração do Lync Server descrito neste documento:

  - **Serviços de domínio do Active Directory**   você precisa fazer backup do AD DS usando as ferramentas do Active Directory ao mesmo tempo em que fizer backup do Lync Server. É importante manter o AD DS sincronizado com o Lync Server para evitar problemas que podem ocorrer quando o Lync Server espera objetos de contato que não correspondem àqueles no AD DS. O AD DS armazena as seguintes configurações que são usadas pelo Lync Server:
    
      - URI de SIP do usuário e outras configurações do usuário.
    
      - Objetos de contato para aplicativos como o assistente de grupo de resposta e conferência.
    
      - Um ponteiro para o repositório de gerenciamento central.
    
      - Conta de autenticação Kerberos (um objeto de computador opcional) e grupos de segurança do Lync Server.
    
    Para obter detalhes sobre como fazer backup e restaurar o AD DS no Windows Server 2008, consulte "guia passo a passo de backup e recuperação do AD DS [http://go.microsoft.com/fwlink/p/?linkId=209105](http://go.microsoft.com/fwlink/p/?linkid=209105)" em.

  - **A autoridade de certificação e os certificados**   usam a política da sua organização para fazer backup da autoridade de certificação e dos certificados. Se você usar chaves privadas exportáveis, poderá fazer backup do certificado e da chave privada e exportá-los se usar os procedimentos deste documento para restaurar o Lync Server. Se você usar uma autoridade de certificação interna, poderá recadastrar se precisar restaurar o Lync Server. É importante manter a chave privada em um local seguro, onde estará disponível se um computador falhar.

  - **System Center Operations Manager**   se você usar o Microsoft System Center Operations Manager (antigo Microsoft Operations Manager) para monitorar a implantação do Lync Server, você pode, opcionalmente, fazer o backup dos dados que ele cria enquanto estiver monitorando o Lync Servidor. Use o processo de backup padrão do SQL Server para fazer backup dos arquivos do System Center Operations Manager. Esses arquivos não são restaurados durante a recuperação.

  - **Configuração de gateway da rede de telefonia pública comutada (PSTN)**   se você usar aparelhos de filial e filiais sobreviventes, será necessário fazer backup da configuração do gateway PSTN. Consulte o fornecedor para obter detalhes sobre como fazer backup e restaurar configurações de gateway PSTN.

  - **Versões coexistentes do Lync Server ou do Office Communications Server**   se sua implantação do Lync Server 2013 existir no Lync Server 2010 ou em uma versão anterior do Office Communications Server, você não poderá usar os procedimentos deste documento para fazer o backup ou restaurar a versão anterior. Em vez disso, você deve usar os procedimentos de backup e restauração documentados especificamente para a versão anterior. Para obter detalhes sobre como fazer backup e restaurar o Lync Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=265417](http://go.microsoft.com/fwlink/p/?linkid=265417) , consulte. Para obter detalhes sobre como fazer backup e restaurar o Microsoft Office Communications Server 2007 [http://go.microsoft.com/fwlink/p/?linkId=168162](http://go.microsoft.com/fwlink/p/?linkid=168162)R2, consulte.

  - **Informações de infraestrutura**   você precisa fazer backup de informações sobre sua infraestrutura, como a configuração do seu firewall, a configuração de balanceamento de carga, a configuração dos serviços de informações da Internet (IIS), os registros do sistema de nomes de domínio (DNS) e Endereços IP e configuração de protocolo DHCP (Dynamic Host Configuration Protocol). Para obter detalhes sobre como fazer backup desses componentes, consulte seus respectivos fornecedores.

  - **Microsoft Exchange e Exchange Unified Messaging (um)**   backup e restauração do Microsoft Exchange e do Exchange um, conforme descrito na documentação do Microsoft Exchange. Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2013 [http://go.microsoft.com/fwlink/?LinkId=285384](http://go.microsoft.com/fwlink/?linkid=285384), consulte. Para obter detalhes sobre como fazer backup e restaurar o Exchange Server 2010 [http://go.microsoft.com/fwlink/p/?linkId=209179](http://go.microsoft.com/fwlink/p/?linkid=209179), consulte.
    
    Observe que o Lync Server 2013 introduz a capacidade de ter listas de contatos do usuário, fotos de usuários de alta definição e arquivar dados armazenados no Exchange 2013. Veja a lista a seguir para ver como fazer backup desses tipos de dados:
    
      - **Fotos de alta definição** são cofeitas como parte do backup do Exchange Server.
    
      - O **repositório de contatos** unificado é apresentado no Lync Server 2013. O repositório de contatos unificado permite que os usuários mantenham todas as informações de contato no Exchange 2013.
        
        Você deve garantir que os backups sejam atualizados para os usuários em termos de se seus contatos do usuário estão armazenados no repositório de contatos unificado ou no servidor do Lync back-end. Os cenários a seguir ilustram onde a migração de contatos do usuário para o repositório de contatos unificado pode causar problemas para o processo de backup e restauração.
        
        **Cenário 1:** Os contatos do usuário são migrados para o repositório de contatos unificado, e uma restauração é realizada de um backup do Lync Server feito antes da migração dos contatos do usuário. Nesse cenário, o usuário terá um estado de contatos desatualizados para até um dia até que a tarefa de migração do Lync Server comece a migrar contatos do usuário para o Exchange. (Observe que, como os contatos do usuário foram anteriormente migrados para o repositório de contatos unificado, as informações de contato do Exchange serão usadas). Nesse cenário, nenhuma intervenção do administrador é necessária.
        
        **Cenário 2:** Os contatos do usuário foram armazenados anteriormente no repositório de contatos unificado, mas depois revertidos. Uma restauração é realizada de um backup do Lync Server realizada quando os contatos do usuário eram armazenados no repositório de contatos unificado. Nesse cenário, uma mensagem de erro nos `Error: Incorrect Exchange Version` logs do servidor cliente ou Lyss pode indicar isso como um problema. O usuário poderá acessar a lista de contatos no Lync 2013 diretamente do Exchange, mas o estado do cliente não será compatível com o estado do Lync Server. Para corrigir isso, um administrador precisará executar os cmdlets **Invoke-CsUCSRollback** para os usuários afetados.
    
      - O arquivamento de **dados** pode ser armazenado no Exchange 2013. Esses dados não são críticos para o Lync Server, mas podem ser críticos para a sua organização para fins reguladores. Se o arquivamento de dados estiver armazenado no Exchange e for essencial para sua organização, siga os procedimentos de backup e restauração do Exchange. Observe que o arquivamento de dados armazenados no Exchange não pode ser retornado ao Lync Server. Além disso, não há nenhuma maneira de mover os dados já armazenados no banco de dados de arquivamento do Lync para o Exchange.

</div>

</div>

<span> </span>

</div>

</div>

</div>

