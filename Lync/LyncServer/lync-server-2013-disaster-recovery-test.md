---
title: 'Lync Server 2013: Teste de recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9b17f5841cad96cb83399082f61c00194ec4828
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829384"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Teste de recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-01-26_

Realize uma recuperação do sistema para um servidor de pool do Lync Server 2013 para testar o processo de recuperação de desastres documentado. Esse teste simulará uma falha completa de hardware de um servidor e ajudará a garantir que os recursos, os planos e os dados estejam disponíveis para recuperação. Tente alternar o foco do teste mensalmente para que sua organização teste sempre a falha de um servidor diferente ou de outro equipamento.

Observe que o cronograma de execução do teste de Recuperação de Desastre pelas organizações variará. É muito importante que o teste de recuperação de desastre não seja ignorado ou negligenciado.

<div>


Exportar a topologia, as políticas e as configurações de configuração do Lync Server 2013 para um arquivo. O arquivo poderá ser usado, entre outras coisas, para restaurar essas informações para o Repositório de Gerenciamento Central após uma atualização, uma falha de hardware ou outro problema que resulte em perda de dados.

Importe as configurações de topologia, políticas e configuração do Lync Server 2013 para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Para fazer backup de dados de produção do Lync Server 2013:

  - Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup padrão do SQL Server para despejar o banco de dados em um dispositivo de despejo de arquivo ou fita.

  - Use um aplicativo de backup terceirizado para fazer backup dos dados para um arquivo ou uma fita.

  - Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.

  - Use o backup do sistema de arquivos ou de terceiros para fazer backup do conteúdo de reuniões e de logs de conformidade.

  - Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Lync Server 2013.

A primeira etapa do procedimento de failover inclui um movimento forçado dos usuários do pool de produção para o pool de Recuperação de Desastre.

O movimento será forçado, pois o pool de produção não estará disponível para aceitar a realocação do usuário.

O processo de transferência de usuário do Lync Server 2013 é efetivamente uma alteração em um atributo no objeto de conta de usuário, além de uma atualização de registro no banco de dados SQL do RTC.

Esses dados podem ser restaurados por meio destes dois processos:

  - O banco de dados RTC pode ser restaurado do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server ou usando um utilitário de backup/restauração de terceiros.

  - Os dados de contato do usuário podem ser restaurados por meio do utilitário DBIMPEXP.exe, usando o arquivo XML criado a partir da exportação do SQL Server de produção.

Depois que esses dados são restaurados, os usuários podem se conectar efetivamente ao pool de recuperação de desastres do Lync Server 2013 e operar normalmente.

Para permitir que os usuários se conectem ao pool de recuperação de desastres do Lync Server 2013, será necessário alterar um registro de DNS.

O pool de produção do Lync Server 2013 será referenciado por clientes que usam os registros de configuração automática e SRV DNS de:

  - SRV: \_SIP. \_TLS. \</CNAME\> de domínio: SIP. \<domínio\>

  - CNAME: SIP. \</CVC-pool-1.\> de domínio \<domínio\>

Para facilitar o failover, esse registro CNAME deve ser atualizado para referenciar o FQDN DROCSPool:

  - CNAME: SIP. \</DROCSPool.\> de domínio \<domínio\>

  - SPI. \<domínio\>

  - AV.\<Domain\>

  - webconf. \<domínio\>

  - OCSServices. \<domínio\>

<div>


> [!IMPORTANT]  
> Para obter procedimentos detalhados de administração e gerenciamento, confira <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">backup e restauração do Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de backup e alta disponibilidade no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Fazer backup e restaurar o Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gerenciando recuperação de desastre, alta disponibilidade e Serviço de Backup do Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

