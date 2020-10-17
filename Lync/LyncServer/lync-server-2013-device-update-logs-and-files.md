---
title: 'Lync Server 2013: logs e arquivos de atualização de dispositivos'
description: 'Lync Server 2013: logs e arquivos de atualização de dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50db4935f62a4c037ab81a0d11e1eb993466fa80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565987"
---
# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="a0aba-103">Logs e arquivos de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0aba-103">Device Update logs and files in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0aba-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="a0aba-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="a0aba-105">Os logs de atualização de dispositivo contêm informações importantes que você pode usar para gerenciar e solucionar problemas do serviço Web de atualização de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a0aba-105">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="a0aba-106">Você pode alterar o que está conectado e remover logs e atualizações de dispositivos que você não deseja mais.</span><span class="sxs-lookup"><span data-stu-id="a0aba-106">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="a0aba-107">Esta seção descreve como você pode usar o painel de controle do Lync Server ou o Shell de gerenciamento do Lync Server para modificar as configurações de registro em log, limpar o log de atualização de dispositivo ou remover arquivos de log do servidor.</span><span class="sxs-lookup"><span data-stu-id="a0aba-107">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="a0aba-108">Para obter detalhes sobre arquivos de log de atualização de dispositivo, consulte <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">logs e tipos de arquivos de log</A> na biblioteca do TechNet do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="a0aba-108">For details about device update log files, see <A href="https://technet.microsoft.com/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="a0aba-109">(Observe que o serviço Web de atualização de dispositivo, como todos os componentes do Lync Phone Edition, funciona da mesma maneira com o Lync Server 2013, como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="a0aba-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0aba-110">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="a0aba-110">In This Section</span></span>

  - [<span data-ttu-id="a0aba-111">Modificar configurações para arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0aba-111">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="a0aba-112">Excluir arquivos de log de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0aba-112">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="a0aba-113">Remover arquivos de atualização do dispositivo não associados a um dispositivo em remover arquivos de atualização do dispositivo não associados a um dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a0aba-113">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

