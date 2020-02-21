---
title: Os cmdlets de relatório do Skype for Business Online e o serviço Web REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbce4dda006bb45606a09eef29d8c47946ad2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="f61ed-102">Os cmdlets de relatório do Skype for Business Online e o serviço Web REST</span><span class="sxs-lookup"><span data-stu-id="f61ed-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f61ed-103">_**Última modificação do tópico:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="f61ed-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="f61ed-104">Em conjunto com os recursos de relatórios, o Skype for Business Online fornece acesso a cinco cmdlets do Windows PowerShell que ajudam a gerar esses relatórios e também podem ser usados por administradores para retornar dados de relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="f61ed-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="f61ed-105">O Skype for Business online também inclui o REST (transferência de estado representational), que pode ser usado por desenvolvedores para recuperar informações de relatórios personalizados.</span><span class="sxs-lookup"><span data-stu-id="f61ed-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="f61ed-106">Os cmdlets de relatórios disponíveis para os administradores incluem:</span><span class="sxs-lookup"><span data-stu-id="f61ed-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="f61ed-107">Get-CsActiveUserReport, que fornece informações sobre o número de usuários ativos (ou seja, usuários que fizeram logon no Skype for Business Online e que participaram de pelo menos uma conferência ou sessão de comunicação ponto a ponto).</span><span class="sxs-lookup"><span data-stu-id="f61ed-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="f61ed-108">Get-CsAVConferenceTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários gastaram em conferências de áudio/vídeo.</span><span class="sxs-lookup"><span data-stu-id="f61ed-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="f61ed-109">Get-CsConferenceReport, que fornece informações sobre o número e o tipo de conferências em que os usuários participaram.</span><span class="sxs-lookup"><span data-stu-id="f61ed-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="f61ed-110">Get-CsP2PAVTimeReport, que fornece informações sobre a quantidade de tempo (em minutos) que os usuários gastam em sessões ponto a ponto que incluíam áudio e/ou vídeo.</span><span class="sxs-lookup"><span data-stu-id="f61ed-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="f61ed-111">Get-CsP2PSessionReport, que fornece informações sobre o número e o tipo de sessões ponto a ponto nas quais os usuários participaram.</span><span class="sxs-lookup"><span data-stu-id="f61ed-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="f61ed-112">A maioria dos administradores usará os relatórios disponíveis no centro de administração do Microsoft 365: não apenas esses relatórios são gerados automaticamente, mas também fornecem uma representação gráfica dos dados que costumam ser mais fáceis de interpretar do que os valores de números brutos retornados pelo cmdlets de relatório.</span><span class="sxs-lookup"><span data-stu-id="f61ed-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="f61ed-113">No entanto, os administradores familiarizados com o Windows PowerShell podem usar os cmdlets de relatório para retornar dados que não estão prontamente disponíveis nos relatórios do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="f61ed-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="f61ed-114">Por exemplo, os cmdlets de relatório retornam informações sobre a duração da sessão (a quantidade de tempo, em minutos, que cada sessão lasted).</span><span class="sxs-lookup"><span data-stu-id="f61ed-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="f61ed-115">As durações de sessão individual não estão disponíveis usando os relatórios do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="f61ed-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="f61ed-116">Da mesma forma, em modo de exibição diário, os relatórios do Lync Online exibem informações somente nos 14 dias precedentes.</span><span class="sxs-lookup"><span data-stu-id="f61ed-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="f61ed-117">Se quiser rever os totais diários de um dia diferente (por exemplo, uma data de quatro meses atrás), você pode fazer isso usando os cmdlets de relatório.</span><span class="sxs-lookup"><span data-stu-id="f61ed-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="f61ed-118">Os administradores também podem estar interessados no artigo [usando o Excel para recuperar dados de relatórios do office 365](https://msdn.microsoft.com/library/dn781442.aspx), que explica como usar o recurso de consulta de dados OData no Microsoft Excel para criar um relatório personalizado do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f61ed-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="f61ed-119">Relatórios personalizados oferecem a capacidade de ditar quais dados (e quantos dados) são retornados do serviço de relatórios do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f61ed-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="f61ed-120">Relatórios personalizados também permitem que você faça coisas como especificar como os dados devem ser classificados e agrupados e fornecer acesso a informações que não são exibidas no centro de administração.</span><span class="sxs-lookup"><span data-stu-id="f61ed-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="f61ed-121">Os administradores com um plano de fundo de desenvolvimento podem usar o serviço Web REST para obter informações não exibidas no centro de administração do Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="f61ed-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="f61ed-122">O serviço REST é semelhante ao serviço SOAP, pois cada tecnologia oferece uma maneira de transferir dados XML entre um cliente e um servidor.</span><span class="sxs-lookup"><span data-stu-id="f61ed-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="f61ed-123">No entanto, o serviço REST tem pelo menos duas vantagens sobre o serviço SOAP.</span><span class="sxs-lookup"><span data-stu-id="f61ed-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="f61ed-124">Para um, REST realiza transferências de dados XML usando um formato padronizado conhecido como o formato de agregação ATOM.</span><span class="sxs-lookup"><span data-stu-id="f61ed-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="f61ed-125">Por outro lado, SOAP usando um formato não padrão ao transferir dados.</span><span class="sxs-lookup"><span data-stu-id="f61ed-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="f61ed-126">Além disso, o REST pode transferir dados entre redes que bloqueiam verbos HTTP diferentes de GET e POST.</span><span class="sxs-lookup"><span data-stu-id="f61ed-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="f61ed-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="f61ed-127">See Also</span></span>


<span data-ttu-id="f61ed-128">[Relatórios do Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="f61ed-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="f61ed-129">O serviço Web de relatórios do Office 365</span><span class="sxs-lookup"><span data-stu-id="f61ed-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="f61ed-130">Aprendendo sobre o serviço Web de relatórios do Office 365</span><span class="sxs-lookup"><span data-stu-id="f61ed-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="f61ed-131">[Os cmdlets de relatório do Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f61ed-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="f61ed-132">Usar o Excel para Recuperar Dados de Relatório do Office 365</span><span class="sxs-lookup"><span data-stu-id="f61ed-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

