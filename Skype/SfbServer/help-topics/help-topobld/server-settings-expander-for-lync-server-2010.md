---
title: Expansor de configurações de servidor do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades desse computador, faça o seguinte:'
ms.openlocfilehash: 242f2b25a77de7f81ce8c11828f2fc0fbe1c2d41
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992446"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="27692-103">Expansor de configurações de servidor do Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="27692-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="27692-104">Para editar as propriedades desse computador, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="27692-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="27692-105">Edite o **nome domínio totalmente qualificado (FQDN)** para este computador.</span><span class="sxs-lookup"><span data-stu-id="27692-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="27692-106">Essa entrada deve corresponder ao nome de computador, como definido no sistema de nome de domínio (DNS) e em nomes de entidade alternativos (SAN) ou o nome da entidade (SN) do certificado associado a esse computador.</span><span class="sxs-lookup"><span data-stu-id="27692-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="27692-107">Você selecionar um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="27692-107">You select one of the following:</span></span>
    
    <span data-ttu-id="27692-108">**Usar todos os endereços IP configurados**: Selecione essa opção para usar endereços IP configurados tudo no computador.</span><span class="sxs-lookup"><span data-stu-id="27692-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="27692-109">Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a esse computador usará todos os endereços IP para todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="27692-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="27692-110">Se um servidor de escuta ou serviço está esperando a comunicação de um determinado endereço IP e porta, o serviço talvez não seja a melhor seleção de qual endereço IP para escutar em.</span><span class="sxs-lookup"><span data-stu-id="27692-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="27692-111">**Limitar o uso do serviço aos endereços IP selecionados**: Selecione essa opção se você deseja definir endereços IP específicos para o **endereço IP primário** deste computador escutará para comunicação dos outros computadores e pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="27692-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="27692-112">Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço irá ouvir comunicações e enviar comunicações ao gateway PSTN ou IP-PBX definido.</span><span class="sxs-lookup"><span data-stu-id="27692-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

