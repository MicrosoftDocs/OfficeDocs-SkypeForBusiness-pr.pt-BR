---
title: 'Lync Server 2013: exportação de dados arquivados'
description: 'Lync Server 2013: exportação de dados arquivados.'
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
ms.openlocfilehash: 656751f1a2d03b50f0c938a8501ba3e95e304cff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564747"
---
# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="d2055-103">Exportar dados arquivados do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2055-103">Exporting archived data from Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2055-104">_**Última modificação do tópico:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d2055-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d2055-105">Os dados arquivados em bancos de dados de Arquivamento não estão em um formato legível ou com possibilidade de pesquisa, mas é possível usar o cmdlet Export-CsArchivingData para extrair registros do banco de dados e salvá-los como um arquivo do Outlook Electronic Mail (EML).</span><span class="sxs-lookup"><span data-stu-id="d2055-105">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="d2055-106">Para obter detalhes sobre como exportar dados arquivados, consulte [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) na documentação Operações.</span><span class="sxs-lookup"><span data-stu-id="d2055-106">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="d2055-107">Se você habilitar a integração com o Microsoft Exchange, os dados serão arquivados nos repositórios do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d2055-107">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="d2055-108">Os dados arquivados no Exchange 2013 são pesquisáveis e detectáveis.</span><span class="sxs-lookup"><span data-stu-id="d2055-108">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="d2055-109">Para obter detalhes sobre o suporte para comunicações integradas do Exchange 2013 e do Lync Server 2013, consulte [Exchange Server and SharePoint Integration Support in Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) na documentação de suporte.</span><span class="sxs-lookup"><span data-stu-id="d2055-109">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="d2055-110">Para obter detalhes sobre como acessar dados arquivados no Exchange, consulte a documentação do Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="d2055-110">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d2055-111">Exportar dados de arquivamento usando cmdlets do Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d2055-111">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d2055-112">Os dados de arquivamento podem ser exportados usando o cmdlet Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="d2055-112">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="d2055-113">Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d2055-113">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d2055-114">Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server 2010 using Remote PowerShell" em [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d2055-114">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="d2055-115">**Para exportar dados de arquivamento**</span><span class="sxs-lookup"><span data-stu-id="d2055-115">**To export archiving data**</span></span>

  - <span data-ttu-id="d2055-116">Este comando exporta todos os dados de arquivamento gravados no banco de dados de arquivamento atl-sql-001.litwareinc.com desde 1 de junho de 2012.</span><span class="sxs-lookup"><span data-stu-id="d2055-116">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="d2055-117">O arquivo de saída resultante será armazenado na pasta C: \\ ArchivingExports.</span><span class="sxs-lookup"><span data-stu-id="d2055-117">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="d2055-118">**Para exportar dados de arquivamento para um único usuário**</span><span class="sxs-lookup"><span data-stu-id="d2055-118">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="d2055-p105">O comando a seguir exporta dados de arquivamento para um único usuário: kenmyer@litwareinc.com. Isso é feito incluindo o parâmetro UserUri seguido pelo endereço SIP do usuário. Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d2055-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="d2055-122">Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="d2055-122">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d2055-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2055-123">See Also</span></span>


[<span data-ttu-id="d2055-124">Suporte à integração do Exchange Server e do SharePoint no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2055-124">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="d2055-125">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="d2055-125">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="d2055-126">Gerenciando o arquivamento do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2055-126">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

