---
title: 'Lync Server 2013: exportação de dados arquivados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bb0bcb30c49a44fe92920d4db77d6bf9697cd9e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008693"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Exportar dados arquivados do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-23_

Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet Export-CsArchivingData para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML). Para obter detalhes sobre como exportar dados arquivados, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) na documentação Operações.

Se você habilitar a integração com o Microsoft Exchange, os dados serão arquivados nos repositórios do Exchange 2013. Os dados arquivados no Exchange 2013 são pesquisáveis e detectáveis. Para obter detalhes sobre o suporte para comunicações integradas do Exchange 2013 e do Lync Server 2013, consulte [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) na documentação de suporte. Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Exportar dados de arquivamento usando cmdlets do Windows PowerShell

Os dados de arquivamento podem ser exportados usando o cmdlet Export-CSArchivingData. Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.

**Para exportar dados de arquivamento**

  - Este comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.litwareinc.com desde 1 de junho de 2012. O arquivo de saída resultante será armazenado na pasta C:\\ArchivingExports.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Para exportar dados de arquivamento para um único usuário**

  - O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@litwareinc.com. Isso é feito incluindo o parâmetro UserUri seguido pelo endereço SIP do usuário. Por exemplo:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>Confira também


[Suporte à integração do Exchange Server e do SharePoint no Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Gerenciando o arquivamento do Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

