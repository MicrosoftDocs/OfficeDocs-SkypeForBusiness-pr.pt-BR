---
title: 'Lync Server 2013: gerenciar comunicados durante recuperação de desastre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6058974b8473bc2c6db91abaaeb1550647ba592d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Gerenciar comunicados durante recuperação de desastre no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

O Lync Server 2013 oferece suporte a comunicados para chamadas de números não atribuídos durante interrupções. Restaurar a funcionalidade de anúncio durante uma interrupção é opcional. Se você escolher restaurar anúncios durante uma interrupção, é necessário recriar sua configuração de anúncio no pool de backup. Esta seção descreve o que você precisa fazer se escolher restaurar anúncios durante a recuperação de desastres.

Esta seção se aplica a intervalos de números não atribuídos que usam o aplicativo comunicado. Esta seção não se aplica ao intervalo de números não atribuídos que usam o Atendedor Automático do Exchange Unified Messaging (UM).

<div>

## <a name="before-an-outage"></a>Antes de uma interrupção

Independentemente de você optar por usar comunicados durante as interrupções, você deve fazer backups separados de qualquer arquivo de áudio personalizado que você configurou para o aplicativo de comunicado. Não é feito backup dos comunicados personalizados como parte do processo de recuperação de desastres do Lync Server. Se você não realizar backups separados dos arquivos e os arquivos que você carregou ao servidor ou pool estão danificados, corrompidos ou apagados, os arquivos serão perdidos.

Se você não tem cópias de backup de arquivos de áudio personalizados e os arquivos de áudio originais não estão mais disponíveis, você pode encontrar os arquivos de áudio que você configurou para um aplicativo de anúncio procurando no repositório de arquivos do servidor ou pool onde você originalmente importado os arquivos. Você pode copiar todos os arquivos de áudio que você configurou para o aplicativo de anúncio no repositório de arquivos.

**Para copiar arquivos de áudio do repositório de arquivos**

1.  Na linha de comando, execute:
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    Por exemplo:
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    Onde X-ApplicationServer-X refere-se à ID de serviço do Servidor de Aplicativos do pool (por exemplo, 1-ApplicationServer-1")


</div>

<div>

## <a name="during-an-outage"></a>Durante uma interrupção

Para usar o aplicativo de comunicado durante uma interrupção, você precisa recriar a configuração do comunicado no pool de backup executando as tarefas descritas nesta seção.

<div>


> [!NOTE]  
> Recomendamos realizar estas tarefas se você falhar no pool de backup, porque assim que você realizar a etapa 2, o pool de backup tem propriedade dos intervalos de número não atribuídos.



</div>

<div>


> [!NOTE]  
> Estas etapas não são obrigatórias para intervalos de número que usam um número de telefone do Atendedor Automático do Exchange UM.



</div>

**Para recriar a configuração do comunicado no pool de backup**

1.  Recrie os anúncios que você implantou no pool primário no pool de backup fazendo o seguinte:
    
    1.  Importe qualquer arquivo de áudio usado no pool primário para o pool de backup usando o cmdlet **Import-CsAnnouncementFile** e especificando o pool de backup para o parâmetro Parent.
    
    2.  Recriar cada anúncio usando o cmdlet **New-CsAnnouncement** e especificando o pool de backup para o parâmetro Parent.
    
    <div>
    

    > [!NOTE]  
    > Para obter detalhes sobre como usar esses parâmetros para criar comunicados no pool de backup, consulte <A href="lync-server-2013-create-an-announcement.md">criar um anúncio no Lync Server 2013</A>.

    
    </div>

2.  Após todos os anúncios serem recriados no pool de backup, redirecione todos os intervalos de número não atribuídos que usam anúncios no pool primário para os anúncios recriados no pool de backup.
    
    Para cada intervalo de número não atribuído que usa um anúncio no pool primário, execute o seguinte:
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>Após a interrupção

Quando o pool primário se torna disponível, você precisa redirecionar os intervalos de número não atribuídos que você alterou para a interrupção de volta para o pool primário.

<div>


> [!NOTE]  
> Estas etapas não são necessárias para intervalos de número que usam um número de telefone do Atendedor Automático do Exchange UM.



</div>

**Para restaurar comunicados no pool primário**

1.  Se você precisa reconstruir o pool primário durante a recuperação, é necessário recriar os anúncios no pool primário importando os arquivos de áudio e criando anúncios, assim como você faria no pool de backup, exceto que você especifica o pool primário para o parâmetro Parent. Para obter detalhes, consulte "Durante uma interrupção" anteriormente neste tópico.

2.  Para cada intervalo de número não atribuído que você alterou para a interrupção, execute o seguinte:
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  Opcionalmente, remova os anúncios recriados no pool de backup. Obtenha uma lista de comunicados para o aplicativo de anúncio do pool de backup. Na linha de comando, execute:
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    Por exemplo:
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    Na lista resultante, localize os anúncios que deseja remover e copie os GUIDs. Para cada anúncio que deseja remover, execute:
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    Por exemplo:
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

