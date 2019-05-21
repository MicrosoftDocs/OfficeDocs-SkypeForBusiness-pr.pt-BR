---
title: Expansor de Confgurações de Servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297607"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="51fda-103">Expansor de Confgurações de Servidor para Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="51fda-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="51fda-104">Para editar as propriedades deste computador, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="51fda-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="51fda-105">Edite o **nome de domínio totalmente qualificado (FQDN)** deste computador.</span><span class="sxs-lookup"><span data-stu-id="51fda-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="51fda-106">Essa entrada deve coincidir com o nome do computador conforme definido no sistema de nomes de domínio (DNS) e em nomes alternativos da entidade (SAN) ou nome da entidade (SN) do certificado associado a este computador.</span><span class="sxs-lookup"><span data-stu-id="51fda-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="51fda-107">Selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="51fda-107">You select one of the following:</span></span>
    
    <span data-ttu-id="51fda-108">**Usar todos os endereços IP**configurados: Selecione esta configuração para usar todos os endereços IP configurados no computador.</span><span class="sxs-lookup"><span data-stu-id="51fda-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="51fda-109">Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a este computador usarão todos os endereços IP para todos os serviços.</span><span class="sxs-lookup"><span data-stu-id="51fda-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="51fda-110">Se um servidor ou serviço de escuta esperar a comunicação de um endereço IP e uma porta específicos, o serviço poderá não fazer a melhor seleção de qual endereço de IP escuta.</span><span class="sxs-lookup"><span data-stu-id="51fda-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="51fda-111">**Limitar o uso do serviço a endereços IP selecionados**: Selecione esta opção se quiser definir endereços IP específicos para o **endereço IP primário** que este computador escutará para comunicação de outros computadores e pools na implantação.</span><span class="sxs-lookup"><span data-stu-id="51fda-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="51fda-112">Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço escutarão para comunicações e enviar comunicações para o gateway PSTN definido ou PBX IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="51fda-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

