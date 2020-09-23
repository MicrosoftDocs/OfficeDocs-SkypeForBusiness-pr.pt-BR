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
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215692"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de Confgurações de Servidor para Lync Server 2010
 
Para editar as propriedades deste computador, faça o seguinte:
  
- Edite o **nome de domínio totalmente qualificado (FQDN)** para este computador. Essa entrada deve corresponder ao nome do computador conforme definido no DNS (sistema de nomes de domínio) e em nomes alternativos de entidade (SAN) ou nome de entidade (SN) do certificado associado a este computador.
    
- Selecione uma das seguintes opções:
    
    **Usar todos os endereços IP configurados**: Selecione essa configuração para usar todos os endereços IP configurados no computador.
    
    > [!IMPORTANT]
    > Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a esse computador usarão todos os endereços IP de todos os serviços. Se um servidor ou serviço de escuta estiver esperando a comunicação de um endereço IP específico e uma porta, o serviço poderá não fazer a melhor seleção de qual endereço IP escuta. 
  
    **Limitar o uso do serviço para os endereços IP selecionados**: Selecione essa opção se quiser definir endereços IP específicos para o **endereço IP principal** que este computador escutará para comunicação de outros computadores e pools na implantação. Defina o **endereço IP PSTN** para o endereço IP específico que o computador e o serviço escutarão para comunicações e enviará comunicações para o gateway PSTN definido ou IP-PBX.
    

