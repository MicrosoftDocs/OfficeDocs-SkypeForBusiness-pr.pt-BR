---
title: 'Lync Server 2013: regras de atualização de dispositivos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update rules
ms:assetid: a2f7e293-3342-4566-9605-410cb95f3b3b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994062(v=OCS.15)
ms:contentKeyID: 51803973
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b52fa2f2aefae05f713972df5c3b15e6db7c0b57
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42031245"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-rules-in-lync-server-2013"></a><span data-ttu-id="07283-102">Regras de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-102">Device Update rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07283-103">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="07283-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="07283-104">Periodicamente, a Microsoft lança um novo conjunto de atualizações de firmware de dispositivo para o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="07283-104">Periodically, Microsoft releases a new set of device firmware updates for Lync Phone Edition.</span></span> <span data-ttu-id="07283-105">*As regras de atualização de dispositivo* associam atualizações de firmware com dispositivos de hardware — telefones e outros dispositivos que executam o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="07283-105">*Device update rules* associate firmware updates with hardware devices—phones and other devices running Lync Phone Edition.</span></span>

<span data-ttu-id="07283-106">Para obter o conjunto mais recente de regras de atualização de dispositivo, vá para a página ajuda e suporte no site da Microsoft e procure por "Phone Edition".</span><span class="sxs-lookup"><span data-stu-id="07283-106">To get the latest set of device update rules, go to the Help and Support page on the Microsoft website, and search for "Phone Edition."</span></span> <span data-ttu-id="07283-107">Baixe o pacote de atualização e extraia os arquivos para uma pasta no computador onde as atualizações devem ser carregadas.</span><span class="sxs-lookup"><span data-stu-id="07283-107">Download the update package, and extract the files to a folder on the computer where the updates are to be uploaded.</span></span> <span data-ttu-id="07283-108">Após a extração dos arquivos, importe as regras de atualização de dispositivo encontradas no arquivo extraído. Arquivo CAB (que tem o nome UCUpdates. cab).</span><span class="sxs-lookup"><span data-stu-id="07283-108">After the files have been extracted, import the device update rules found in the extracted .CAB file (which have the name UCUpdates.cab).</span></span> <span data-ttu-id="07283-109">Em seguida, use o painel de controle do Lync Server ou cmdlets do Windows PowerShell para exibir e gerenciar essas regras para os dispositivos de sua organização.</span><span class="sxs-lookup"><span data-stu-id="07283-109">Then, use the Lync Server Control Panel or Windows PowerShell cmdlets to view and manage these rules for your organization’s devices.</span></span>

<span data-ttu-id="07283-110">Os tópicos a seguir explicam como importar, exibir e gerenciar regras de atualização de dispositivos.</span><span class="sxs-lookup"><span data-stu-id="07283-110">The following topics tell you how to import, view, and manage device update rules.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="07283-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="07283-111">In This Section</span></span>

  - [<span data-ttu-id="07283-112">Exibir informações sobre as regras de atualização de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-112">View information about Device Update rules in Lync Server 2013</span></span>](lync-server-2013-view-information-about-device-update-rules.md)

  - [<span data-ttu-id="07283-113">Importar regras de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-113">Import Device Update rules in Lync Server 2013</span></span>](lync-server-2013-import-device-update-rules.md)

  - [<span data-ttu-id="07283-114">Aprovar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-114">Approve a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-approve-a-device-update-rule.md)

  - [<span data-ttu-id="07283-115">Remover uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-115">Remove a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-remove-a-device-update-rule.md)

  - [<span data-ttu-id="07283-116">Redefinir uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-116">Reset a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-reset-a-device-update-rule.md)

  - [<span data-ttu-id="07283-117">Restaurar uma regra de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="07283-117">Restore a Device Update rule in Lync Server 2013</span></span>](lync-server-2013-restore-a-device-update-rule.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

