---
title: 'Lync Server 2013: serviço Web de atualização de dispositivo'
description: 'Lync Server 2013: serviço Web de atualização de dispositivo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45511d34ab99f295481472f2a3c14bf21da32ff6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565947"
---
# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="5a695-103">Serviço Web de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a695-103">Device Update Web service in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5a695-104">_**Última modificação do tópico:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="5a695-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="5a695-105">O Lync Server inclui o serviço Web de atualização de dispositivo, que é automaticamente instalado como parte da função de serviços Web.</span><span class="sxs-lookup"><span data-stu-id="5a695-105">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="5a695-106">Este serviço permite baixar atualizações da Microsoft, testá-las e implantar as atualizações em telefones IP em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5a695-106">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="5a695-107">Você também pode usar o Serviço Web de Atualização de Dispositivo para reverter os dispositivos às suas versões de software anteriores.</span><span class="sxs-lookup"><span data-stu-id="5a695-107">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="5a695-108">Esta seção fornece detalhes sobre como gerenciar o serviço Web de atualização de dispositivo e atualizações implantadas usando logs de atualização de dispositivo, regras (o Lync Phone Edition usa *regras* para associar atualizações de versão de firmware com dispositivos de hardware) e definições de configuração.</span><span class="sxs-lookup"><span data-stu-id="5a695-108">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="5a695-109">Para obter detalhes sobre o processo e os recursos do serviço Web de atualização de dispositivo, consulte [atualização de dispositivos](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) na Biblioteca TechNet do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="5a695-109">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="5a695-110">(Observe que o serviço Web de atualização de dispositivo, como todos os componentes do Lync Phone Edition, funciona da mesma maneira com o Lync Server 2013, como no Lync Server 2010.)</span><span class="sxs-lookup"><span data-stu-id="5a695-110">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5a695-111">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="5a695-111">In This Section</span></span>

  - [<span data-ttu-id="5a695-112">Logs e arquivos de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a695-112">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="5a695-113">Regras de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a695-113">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="5a695-114">Definições de configuração de atualização de dispositivo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a695-114">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="5a695-115">Exibir atualizações de software para dispositivos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5a695-115">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5a695-116">Confira também</span><span class="sxs-lookup"><span data-stu-id="5a695-116">See Also</span></span>


<span data-ttu-id="5a695-117">[Ferramentas e serviços para gerenciar e solucionar problemas de dispositivos](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="5a695-117">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

