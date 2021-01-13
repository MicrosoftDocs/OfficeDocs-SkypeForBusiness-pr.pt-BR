---
title: Expansor de Confgurações de Servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: 8b05fa82bcfeb10caa201ce303ddbbd8e8378b7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806651"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d0d0c-103">Expansor de Confgurações de Servidor para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d0d0c-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="d0d0c-104">Para editar as propriedades deste computador, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d0d0c-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="d0d0c-105">Edite **o FQDN (nome** de domínio totalmente qualificado) deste computador.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="d0d0c-106">Essa entrada deve corresponder ao nome do computador como está definido no DNS (sistema de nomes de domínio) e em nomes de assunto alternativos (SAN) ou nome de assunto (SN) do certificado associado a este computador.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="d0d0c-107">Selecione um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="d0d0c-107">You select one of the following:</span></span>
    
    <span data-ttu-id="d0d0c-108">**Use todos os endereços IP configurados:** selecione-o para usar todos os endereços IP configurados no computador.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d0d0c-109">Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a este computador usarão todos os endereços IP para todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="d0d0c-110">Se um servidor ou serviço de escuta estiver esperando a comunicação de um endereço IP e uma porta específicos, o serviço pode não fazer a melhor seleção de qual endereço IP escutar.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="d0d0c-111">**Limitar** o uso do serviço aos endereços IP selecionados: selecione essa opção se quiser definir endereços IP específicos para o endereço **IP** principal que este computador escutará para comunicação de outros computadores e pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="d0d0c-112">Defina o endereço **IP PSTN** para o endereço IP específico que o computador e o serviço escutarão para comunicações e enviarão comunicações para o gateway PSTN ou IP-PBX definido.</span><span class="sxs-lookup"><span data-stu-id="d0d0c-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

