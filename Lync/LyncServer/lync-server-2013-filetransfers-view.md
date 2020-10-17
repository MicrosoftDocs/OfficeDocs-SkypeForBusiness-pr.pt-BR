---
title: 'Lync Server 2013: modo de exibição de transferência'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FileTransfers view
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49733848
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e0fdfae0cefafc7ee6273af75e84e0ea6545188b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500868"
---
# <a name="filetransfers-view-in-lync-server-2013"></a><span data-ttu-id="75336-102">Modo de transferência de filetransfers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="75336-102">FileTransfers view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75336-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="75336-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="75336-104">O modo de exibição FileTransfer armazena informações sobre sessões de transferência de arquivos ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="75336-104">The FileTransfer view stores information about peer-to-peer file transfer sessions.</span></span> <span data-ttu-id="75336-105">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="75336-105">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="75336-106">O modo de exibição filetransfers contém todas as colunas no <A href="lync-server-2013-sessiondetails-view.md">modo de exibição SessionDetails no Lync Server 2013</A> , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="75336-106">The FileTransfers view contains all of the columns in the <A href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</A> in addition the columns listed below.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75336-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="75336-107">Column</span></span></th>
<th><span data-ttu-id="75336-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="75336-108">Data Type</span></span></th>
<th><span data-ttu-id="75336-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="75336-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75336-110"><strong>FileName</strong></span><span class="sxs-lookup"><span data-stu-id="75336-110"><strong>FileName</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-111">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="75336-111">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75336-112">Nome do arquivo transferido.</span><span class="sxs-lookup"><span data-stu-id="75336-112">Name of the file transferred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75336-113"><strong>Cookie</strong></span><span class="sxs-lookup"><span data-stu-id="75336-113"><strong>Cookie</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-114">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="75336-114">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="75336-115">Usado para identificar cada mensagem de acompanhamento como sendo associado a este.</span><span class="sxs-lookup"><span data-stu-id="75336-115">Used to identify every follow-up message as being associated with this one.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75336-116"><strong>Fileidentity</strong></span><span class="sxs-lookup"><span data-stu-id="75336-116"><strong>FileIdentity</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-117">identificador</span><span class="sxs-lookup"><span data-stu-id="75336-117">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="75336-118">Identificador exclusivo para distinguir entre as transferências de arquivo envolvendo o mesmo nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="75336-118">Unique identifier to distinguish between file transfers involving the same file name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75336-119"><strong>Accept</strong></span><span class="sxs-lookup"><span data-stu-id="75336-119"><strong>Accept</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-120">bits</span><span class="sxs-lookup"><span data-stu-id="75336-120">bit</span></span></p></td>
<td><p><span data-ttu-id="75336-p102">Pode ser TRUE ou NULL. Se for TRUE, Rejeitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="75336-p102">Can be TRUE or NULL. If TRUE, then Reject and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75336-123"><strong>Reject</strong></span><span class="sxs-lookup"><span data-stu-id="75336-123"><strong>Reject</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-124">bits</span><span class="sxs-lookup"><span data-stu-id="75336-124">bit</span></span></p></td>
<td><p><span data-ttu-id="75336-p103">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Cancelar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="75336-p103">Can be TRUE or NULL. If TRUE, then Accept and Cancel will be NULL.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75336-127"><strong>Cancel</strong></span><span class="sxs-lookup"><span data-stu-id="75336-127"><strong>Cancel</strong></span></span></p></td>
<td><p><span data-ttu-id="75336-128">bits</span><span class="sxs-lookup"><span data-stu-id="75336-128">bit</span></span></p></td>
<td><p><span data-ttu-id="75336-p104">Pode ser TRUE ou NULL. Se for TRUE, Aceitar e Rejeitar serão NULL.</span><span class="sxs-lookup"><span data-stu-id="75336-p104">Can be TRUE or NULL. If TRUE, then Accept and Reject will be NULL.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

