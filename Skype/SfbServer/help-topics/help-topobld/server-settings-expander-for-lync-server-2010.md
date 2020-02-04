---
title: Expansor de Confgurações de Servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: da1029b6298d85aab8a80af1c52b152e040fbd80
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684404"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de Confgurações de Servidor para Lync Server 2010
 
Para editar as propriedades deste computador, faça o seguinte:
  
- Edite o **nome de domínio totalmente qualificado (FQDN)** deste computador. Essa entrada deve coincidir com o nome do computador conforme definido no sistema de nomes de domínio (DNS) e em nomes alternativos da entidade (SAN) ou nome da entidade (SN) do certificado associado a este computador.
    
- Selecione uma das seguintes opções:
    
    **Usar todos os endereços IP configurados**: Selecione esta configuração para usar todos os endereços IP configurados no computador.
    
    > [!IMPORTANT]
    > Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a este computador usarão todos os endereços IP para todos os serviços. Se um servidor ou serviço de escuta esperar a comunicação de um endereço IP e uma porta específicos, o serviço poderá não fazer a melhor seleção de qual endereço de IP escuta. 
  
    **Limitar o uso do serviço a endereços IP selecionados**: Selecione esta opção se quiser definir endereços IP específicos para o **endereço IP primário** que este computador escutará para comunicação de outros computadores e pools na implantação. Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço escutarão para comunicações e enviar comunicações para o gateway PSTN definido ou PBX IP-PBX.
    

