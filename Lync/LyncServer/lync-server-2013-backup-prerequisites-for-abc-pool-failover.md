---
title: 'Lync Server 2013: pré-requisitos de backup para failover do pool ABC'
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
ms.openlocfilehash: 37a6b5694d8eaa9467fafa8923bb97423fd6e33f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-prerequisites-for-abc-pool-failover-in-lync-server-2013"></a>Pré-requisitos de backup para failover de pool ABC no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-26_

Para obter o máximo de benefícios de usar o procedimento de failover do pool ABC, você deve executar determinados backups antes que ocorra o desastre e o failover:

  - Você deve fazer regularmente o backup dos dados de configuração do LIS (serviço de informações de localização) do pool A usando o cmdlet **Export-CsLISConfiguration** .
    
        Export-csLisConfiguration -FileName <C:\LISExportPrimary.zip>

  - Você deve fazer regularmente o backup dos dados de configuração do grupo de resposta no pool A usando o cmdlet **Export-CsRgsConfiguration** .
    
        Export-CsRgsConfiguration -Source "service:ApplicationServer:<Pool A FQDN>" -FileName "C:\RgsExportPrimary.zip"
    
    Em geral, recomendamos que você realize backups diários, mas se você tiver um grande volume de alterações, talvez queira agendar backups mais frequentes. A quantidade de informações que você pode perder no caso de um desastre depende da frequência dos seus backups, bem como da frequência e do volume das alterações.
    
    O aplicativo grupo de resposta pode armazenar apenas um conjunto de configurações no nível do aplicativo por pool. Essas configurações podem ser acessadas por meio dos cmdlets **Get-CsRgsConfiguration** . As configurações incluem a configuração de música em espera padrão, o arquivo de áudio de música em espera padrão, o período de cortesia de toque do agente e a configuração do contexto de chamada. Essas configurações podem ser transferidas de um pool para outro por meio do cmdlet **Import-CsRgsConfiguration** usando o parâmetro **ReplaceExistingSettings** , mas essa operação substituirá qualquer configuração de nível de aplicativo no pool de destino.
    
    <div>
    

    > [!TIP]  
    > Em um local separado, mantenha uma cópia de backup de todos os arquivos de áudio originais que foram usados para configurar o aplicativo do grupo de resposta (ou seja, quaisquer gravações ou arquivos de música em espera).

    
    </div>
    
    Se você tiver qualquer arquivo de música em espera personalizado que tenha sido carregado para o parque de chamadas em um pool, mantenha uma cópia deles em outro local. Esses arquivos não são submetidos a backup como parte do processo de recuperação de desastres do Lync Server 2013, e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados.
    
        Xcopy  <Source: Pool A CPS File Store Path>  <Destination>
        Example: Xcopy  "<Pool A File Store Path>\LyncFileStore\coX-ApplicationServer-X\AppServerFiles\CPS\"  "<Destination:  Backup location 1>"
    
    <div>
    

    > [!NOTE]  
    > O aplicativo de estacionamento de chamadas pode armazenar apenas um conjunto de configurações e um arquivo de áudio de música em espera personalizado por pool. Essas configurações podem ser acessadas por meio do cmdlet <STRONG>Get-CsCpsConfiguration</STRONG> . Como o mecanismo de recuperação de desastres do parque de chamadas depende do aplicativo parque de chamadas do pool de backup, as configurações do pool primário não são coligadas nem preservadas se ocorrer um desastre. Se o pool primário for perdido, essas configurações não poderão ser recuperadas e, quando um novo pool for implantado para substituir o pool primário, as configurações de estacionamento de chamada e qualquer arquivo de áudio personalizado de música em espera precisariam ser reconfigurados.

    
    </div>

  - Se você configurar anúncios como parte do recurso de voz número não atribuído, recomendamos que você mantenha em outro local uma cópia de qualquer arquivo de áudio original usado durante a configuração inicial. Se você não fez isso, pode obter uma cópia dos arquivos de áudio configurados no repositório de arquivos do servidor ou pool para o qual os arquivos de áudio foram importados. Esses arquivos não são submetidos a backup como parte do processo de recuperação de desastres do Lync Server 2013, e eles serão perdidos se os arquivos carregados no pool estiverem danificados, corrompidos ou apagados. Para copiar todos os arquivos de áudio usados para configurar o recurso de voz número não atribuído do repositório de arquivos de um servidor ou de um pool, use:
    
        Use: Xcopy  <Source: Pool A Announcement Service File Store Path>  <Destination>
        Example Usage:  Xcopy  "<Pool A File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS"  "<Destination: Backup location>"

  - Se você tiver bancos de dados de monitoramento e arquivamento em um pool, use as ferramentas de gerenciamento do SQL Server para fazer o backup. No procedimento de failover do ABC, os bancos de dados de monitoramento e arquivamento não são preservados se eles são posicionados no pool A, porque esses bancos de dados não têm backup do serviço de backup do Lync Server.

</div>

<span> </span>

</div>

</div>

</div>

