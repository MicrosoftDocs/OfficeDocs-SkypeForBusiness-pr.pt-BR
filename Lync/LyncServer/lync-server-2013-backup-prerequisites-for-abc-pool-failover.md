---
title: 'Lync Server 2013: pré-requisitos de backup para failover de pool ABC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup prerequisites for ABC pool failover
ms:assetid: 652046f5-6086-4592-902d-d5789581977d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945634(v=OCS.15)
ms:contentKeyID: 51541485
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0607a0ddc2a1b2a8249135fa1256f2cb706a250a
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527028"
---
# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Pré-requisitos de backup para failover de pool ABC no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-26_

Para obter o máximo benefício de usar o procedimento de failover do pool ABC, você deve executar determinados backups antes que ocorra o desastre e failover:

  - Você deve fazer o backup dos dados de configuração do LIS (serviço de informações de local) do pool A usando o cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Você deve fazer o backup regular dos dados de configuração do grupo de resposta no pool A usando o cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    No geral, recomendamos que você execute backups diários, mas caso possua um volume alto de alterações, você pode querer programar backups mais frequentes. A quantidade de informações que você pode perder no caso de um desastre depende da frequência de seus backups, bem como da frequência e do volume de alterações.
    
    O aplicativo grupo de resposta pode armazenar somente um conjunto de configurações no nível do aplicativo por pool. Essas configurações podem ser acessadas por meio dos cmdlets **Get-CsRgsConfiguration** . As configurações incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia de toque do agente e a configuração do contexto da chamada. Essas configurações podem ser transferidas de um pool para outro através do cmdlet **Import-CsRgsConfiguration** usando o parâmetro **ReplaceExistingSettings** , mas essa operação substituirá todas as configurações de aplicativo no pool de destino.
    
    <div>
    

    > [!TIP]  
    > Em um local separado, mantenha uma cópia de backup de todos os arquivos de áudio originais que foram usados para configurar o aplicativo de grupo de resposta (ou seja, gravações ou arquivos de música em espera).

    
    </div>
    
    Se você tiver arquivos de música em espera personalizados que foram carregados para estacionamento de chamada em um pool, deverá manter uma cópia deles em outro local. Não é feito backup desses arquivos como parte do processo de recuperação de desastres do Lync Server 2013 e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > O aplicativo de estacionamento de chamada pode armazenar somente um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool. Essas configurações podem ser acessadas por meio do cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Como o mecanismo de recuperação de desastre para estacionamento de chamadas se baseia no aplicativo de estacionamento de chamada do pool de backup, as configurações do pool primário não são submetidas a backup ou preservadas se ocorrer um desastre. Se o pool primário for perdido, essas configurações não poderão ser recuperadas e, quando um novo pool for implantado para substituir o pool principal, as configurações de estacionamento de chamada e qualquer arquivo de áudio de música em espera personalizado precisarão ser reconfigurados.

    
    </div>

  - Se você configurar qualquer comunicados como parte do recurso de voz de número não atribuído, recomendamos que você mantenha em outro local uma cópia de qualquer arquivo de áudio original usado durante a configuração inicial. Se você não fizer isso, poderá obter uma cópia dos arquivos de áudio configurados no repositório de arquivos do servidor ou pool para o qual os arquivos de áudio foram importados. Não é feito backup desses arquivos como parte do processo de recuperação de desastres do Lync Server 2013 e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Para copiar todos os arquivos de áudio usados para configurar o recurso de voz de número não atribuído no repositório de arquivos de um servidor ou pool, use:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Se você tiver bancos de dados de monitoramento e arquivamento em um pool, deverá usar as ferramentas de gerenciamento do SQL Server para fazer o backup. No procedimento de failover ABC, os bancos de dados de monitoramento e arquivamento não serão preservados se forem colocados no pool A, porque esses bancos de dados não são incluídos no backup do serviço de backup do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

