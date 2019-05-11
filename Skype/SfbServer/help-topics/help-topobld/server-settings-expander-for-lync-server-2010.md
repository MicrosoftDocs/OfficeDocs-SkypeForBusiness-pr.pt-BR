---
title: Expansor de Confgurações de Servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 0db8f318f7c4381707869fe06ee7c492c78d63ac
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929536"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de Confgurações de Servidor para Lync Server 2010
 
Para editar as propriedades desse computador, faça o seguinte:
  
- Edite o **nome domínio totalmente qualificado (FQDN)** para este computador. Essa entrada deve corresponder ao nome de computador, como definido no sistema de nome de domínio (DNS) e em nomes de entidade alternativos (SAN) ou o nome da entidade (SN) do certificado associado a esse computador.
    
- Você selecionar um dos seguintes procedimentos:
    
    **Usar todos os endereços IP configurados**: Selecione essa opção para usar endereços IP configurados tudo no computador.
    
    > [!IMPORTANT]
    > Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a esse computador usará todos os endereços IP para todos os serviços. Se um servidor de escuta ou serviço está esperando a comunicação de um determinado endereço IP e porta, o serviço talvez não seja a melhor seleção de qual endereço IP para escutar em. 
  
    **Limitar o uso do serviço aos endereços IP selecionados**: Selecione essa opção se você deseja definir endereços IP específicos para o **endereço IP primário** deste computador escutará para comunicação dos outros computadores e pools na implantação. Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço irá ouvir comunicações e enviar comunicações ao gateway PSTN ou IP-PBX definido.
    

