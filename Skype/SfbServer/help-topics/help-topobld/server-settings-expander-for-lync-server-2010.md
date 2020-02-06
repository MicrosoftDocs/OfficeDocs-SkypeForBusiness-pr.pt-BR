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
- NOCSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: 0f8a1a31c593c792ff4872d0e104c6aadabcd819
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819293"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de Confgurações de Servidor para Lync Server 2010
 
Para editar as propriedades deste computador, faça o seguinte:
  
- Edite o **nome de domínio totalmente qualificado (FQDN)** deste computador. Essa entrada deve coincidir com o nome do computador conforme definido no sistema de nomes de domínio (DNS) e em nomes alternativos da entidade (SAN) ou nome da entidade (SN) do certificado associado a este computador.
    
- Selecione uma das seguintes opções:
    
    **Usar todos os endereços IP configurados**: Selecione esta configuração para usar todos os endereços IP configurados no computador.
    
    > [!IMPORTANT]
    > Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a este computador usarão todos os endereços IP para todos os serviços. Se um servidor ou serviço de escuta esperar a comunicação de um endereço IP e uma porta específicos, o serviço poderá não fazer a melhor seleção de qual endereço de IP escuta. 
  
    **Limitar o uso do serviço a endereços IP selecionados**: Selecione esta opção se quiser definir endereços IP específicos para o **endereço IP primário** que este computador escutará para comunicação de outros computadores e pools na implantação. Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço escutarão para comunicações e enviar comunicações para o gateway PSTN definido ou PBX IP-PBX.
    

