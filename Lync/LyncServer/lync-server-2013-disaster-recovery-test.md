---
title: 'Lync Server 2013: teste de recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disaster recovery test
ms:assetid: 04f5e747-d837-4350-9fc0-8605dbf025a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn747887(v=OCS.15)
ms:contentKeyID: 63969571
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fc04381e315375fe0d5858c9a12ad577f6c8baf
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="disaster-recovery-test-in-lync-server-2013"></a>Teste de recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-01-26_

Execute uma recuperação do sistema para um servidor de pool do Lync Server 2013 para testar o processo de recuperação de desastres documentado. Este teste simulará uma falha completa de hardware para um servidor e ajudará a garantir que os recursos, planos e dados estejam disponíveis para recuperação. Tente girar o foco do teste a cada mês para que sua organização teste a falha de um servidor diferente ou outra parte do equipamento a cada vez.

Observe que a programação em que as organizações realizam testes de recuperação de desastres vai variar. É muito importante que o teste de recuperação de desastres não seja ignorado ou inativo.

<div>


Exporte sua topologia do Lync Server 2013, políticas e definições de configuração para um arquivo. Entre outras coisas, esse arquivo pode ser usado para restaurar essas informações para o repositório de gerenciamento central após uma atualização, uma falha de hardware ou algum outro problema resultou em perda de dados.

Importe a topologia do Lync Server 2013, políticas e definições de configuração para o repositório de gerenciamento central ou para o computador local, conforme mostrado nos seguintes comandos:

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

Para fazer backup dos dados de produção do Lync Server 2013:

  - Faça backup dos bancos de dados RTC e LCSLog usando o processo de backup do SQL Server padrão para despejar o banco de dados para um dispositivo de despejo de arquivo ou fita.

  - Use aplicativos de backup de terceiros para fazer o backup dos dados em um arquivo ou em uma fita.

  - Use o cmdlet Export-CsUserData para criar uma exportação XML de todo o banco de dados RTC.

  - Use o backup do sistema de arquivos ou terceiros para fazer o backup de conteúdo da reunião e logs de conformidade.

  - Use a ferramenta de linha de comando Export-CsConfiguration para fazer backup das configurações do Lync Server 2013.

A primeira etapa do procedimento de failover inclui uma movimentação forçada de usuários do pool de produção para o pool de recuperação de desastre.

Este será um movimento forçado porque o pool de produção não estará disponível para aceitar a realocação do usuário.

O processo de movimentação de usuário do Lync Server 2013 é efetivamente uma alteração para um atributo no objeto da conta de usuário, além de uma atualização de registro no banco de dados SQL RTC.

Esses dados podem ser restaurados por meio dos dois processos a seguir:

  - O banco de dados RTC pode ser restaurado a partir do dispositivo de despejo de backup original do SQL Server de produção usando o processo de restauração padrão do SQL Server, ou usando um utilitário de backup/restauração de terceiros.

  - Os dados de contato do usuário podem ser restaurados com o utilitário DBIMPEXP. exe usando o arquivo XML que foi criado a partir da exportação do SQL Server de produção.

Após a restauração desses dados, os usuários podem se conectar efetivamente ao pool de recuperação de desastres do Lync Server 2013 e operar como de costume.

Para permitir que os usuários se conectem ao pool de recuperação de desastres do Lync Server 2013, será necessária uma alteração de registro DNS.

O pool de produção do Lync Server 2013 será referenciado por clientes que usam a configuração automática e os registros SRV DNS de:

  - SRV: \_SIP. \_TLS. \<domínio\> /CNAME: SIP. \<domínio\>

  - CNAME: SIP. \<domínio\> /CVC-pool-1. \<domínio\>

Para facilitar o failover, esse registro CNAME deve ser atualizado para fazer referência ao FQDN DROCSPool:

  - CNAME: SIP. \<domínio\> /DROCSPool. \<domínio\>

  - SIP. \<domínio\>

  - AV.\<Domain\>

  - webconf. \<domínio\>

  - OCSServices. \<domínio\>

<div>


> [!IMPORTANT]  
> Para obter procedimentos detalhados de administração e gerenciamento, consulte <A href="lync-server-2013-backing-up-and-restoring-lync-server.md">fazendo backup e restaurando o Lync Server 2013</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento para alta disponibilidade e recuperação de desastre no Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
[Cmdlets de backup e alta disponibilidade no Lync Server 2013](https://docs.microsoft.com/powershell/module/skype/?view=skype-ps)  


[Import-CsConfiguration](https://docs.microsoft.com/powershell/module/skype/Import-CsConfiguration)  
[Fazendo backup e restaurando o Lync Server 2013](lync-server-2013-backing-up-and-restoring-lync-server.md)  
[Gerenciando recuperação de desastre, alta disponibilidade e serviço de backup do Lync Server 2013](lync-server-2013-managing-lync-server-disaster-recovery-high-availability-and-backup-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

