---
title: 'Lync Server 2013: logs e arquivos de atualização do dispositivo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5a5b5e39f7720ac5c148a0d3d36a230d1cf4aa3e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="84610-102">Logs e arquivos de atualização de dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84610-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84610-103">_**Tópico da última modificação:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="84610-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="84610-104">Os logs de atualização de dispositivo contêm informações importantes que você pode usar para gerenciar e solucionar problemas do serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="84610-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="84610-105">Você pode alterar o que está registrado em log e remover logs e atualizações de dispositivos que você não quer ou que não sejam mais necessários.</span><span class="sxs-lookup"><span data-stu-id="84610-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="84610-106">Esta seção descreve como você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para modificar as configurações de registro em log, limpar o log de atualização do dispositivo ou remover arquivos de log do servidor.</span><span class="sxs-lookup"><span data-stu-id="84610-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="84610-107">Para obter detalhes sobre os arquivos de log de atualização de dispositivo, consulte <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">tipos de arquivos de log e locais</A> na biblioteca do TechNet do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="84610-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="84610-108">(Observe que o serviço Web de atualização de dispositivo, como todos os componentes do Lync Phone Edition, funciona da mesma maneira com o Lync Server 2013 como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="84610-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="84610-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="84610-109">In This Section</span></span>

  - [<span data-ttu-id="84610-110">Modificar as configurações dos arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84610-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="84610-111">Excluir arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84610-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="84610-112">Remover arquivos de atualização de dispositivo não associados a um dispositivo em remover arquivos de atualização de dispositivo não associados a um dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84610-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

