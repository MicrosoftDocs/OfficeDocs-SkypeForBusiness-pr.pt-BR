---
title: 'Lync Server 2013: Gerenciar comunicados durante recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 65627e68b31e23908e9fd5258a69862f7ea15b79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828913"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Gerenciar comunicados durante recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-23_

O Lync Server 2013 dá suporte a anúncios para chamadas para números não atribuídos durante paralisações. A restauração da funcionalidade do anúncio durante uma interrupção é opcional. Se você optar por restaurar os comunicados durante uma interrupção, será necessário recriar a configuração do comunicado no pool de backup. Esta seção descreve o que você precisa fazer se optar por restaurar os comunicados durante a recuperação de desastres.

Esta seção se aplica a intervalos de números não atribuídos que usam o aplicativo de anúncio. Esta seção não se aplica a intervalos de números não atribuídos que usam o atendedor automático de UM (Unificação de mensagens) do Exchange.

<div>

## <a name="before-an-outage"></a>Antes de uma interrupção

Independentemente de você optar por usar comunicados durante paralisações, você deve fazer backups separados de todos os arquivos de áudio personalizados que você configurou para o aplicativo de anúncio. Anúncios personalizados não são incluídos no backup como parte do processo de recuperação de desastres do Lync Server. Se você não fizer backups separados dos arquivos e os arquivos que você carregou no servidor ou pool estiverem danificados, corrompidos ou apagados, os arquivos serão perdidos.

Se você não tiver cópias de backup de arquivos de áudio personalizados e os arquivos de áudio originais não estiverem mais disponíveis, você poderá localizar os arquivos de áudio que você configurou para um aplicativo de anúncio, procurando no repositório de arquivos do servidor ou pool em que você originalmente importado os arquivos. Você pode copiar todos os arquivos de áudio que você configurou para o aplicativo de anúncio do repositório de arquivos.

**Para copiar arquivos de áudio do repositório de arquivos**

1.  Na linha de comando, execute:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Por exemplo:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Em que X-ApplicationServer-X se refere à ID de serviço do servidor de aplicativos do pool (por exemplo, 1-ApplicationServer-1 ")


</div>

<div>

## <a name="during-an-outage"></a>Durante uma interrupção

Para usar o aplicativo de anúncio durante uma interrupção, você precisa recriar a configuração do anúncio no pool de backup executando as tarefas descritas nesta seção.

<div>


> [!NOTE]  
> Recomendamos que você execute essas tarefas depois de fazer failover para o pool de backup, porque assim que executar a etapa 2, o pool de backup apropria-se dos intervalos de números não atribuídos.



</div>

<div>


> [!NOTE]  
> Essas etapas não são necessárias para intervalos de números que usam um número de telefone de atendedor automático do Exchange UM.



</div>

**Para recriar a configuração do anúncio no pool de backup**

1.  Recrie os comunicados que você implantou no pool primário do pool de backup fazendo o seguinte:
    
    1.  Importe todos os arquivos de áudio usados no pool primário para o pool de backup usando o cmdlet **Import-CsAnnouncementFile** e especificando o pool de backup para o parâmetro pai.
    
    2.  Recrie cada anúncio usando o cmdlet **New-CsAnnouncement** e especificando o pool de backup para o parâmetro pai.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre como usar esses parâmetros para criar anúncios no pool de backup, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.

    
    </div>

2.  Depois que todos os comunicados forem recriados no pool de backup, redirecione todos os intervalos de números não atribuídos que usam comunicados no pool primário para os anúncios recriados no pool de backup.
    
    Para cada intervalo de números não atribuído que usa um comunicado no pool primário, execute o seguinte:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Após a interrupção

Quando o pool primário se torna disponível, você precisa redirecionar os intervalos de números não atribuídos que você alterou para que a falha seja retomada para o pool primário.

<div>


> [!NOTE]  
> Essas etapas não são necessárias para intervalos de números que usam um número de telefone de atendedor automático do Exchange UM.



</div>

**Para restaurar anúncios no pool primário**

1.  Se você tiver que reconstruir o pool primário durante a recuperação, será necessário recriar os comunicados no pool primário importando os arquivos de áudio e criando anúncios, exatamente como o fez no pool de backup, exceto se você especificar o pool primário para o pai com. Para obter detalhes, consulte "durante uma falha" anteriormente neste tópico.

2.  Para cada intervalo de números não atribuído que você alterou para a interrupção, execute o seguinte:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Opcionalmente, remova os comunicados recriados no pool de backup. Obtenha uma lista de comunicados para o aplicativo de anúncio do pool de backup. Na linha de comando, execute:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Por exemplo:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Na lista resultante, localize os comunicados que você deseja remover e copie os GUIDs. Para cada anúncio que você deseja remover, execute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Por exemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

