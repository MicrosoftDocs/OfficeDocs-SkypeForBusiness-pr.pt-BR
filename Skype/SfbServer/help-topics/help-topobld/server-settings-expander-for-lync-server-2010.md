---
title: Expansor de Confgurações de Servidor para Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: 'Para editar as propriedades deste computador, faça o seguinte:'
ms.openlocfilehash: 7eb3eb68114133c412653b9f02c493e2d85ba992
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60836473"
---
# <a name="server-settings-expander-for-lync-server-2010"></a>Expansor de Confgurações de Servidor para Lync Server 2010
 
Para editar as propriedades deste computador, faça o seguinte:
  
- Edite **o FQDN (nome** de domínio totalmente qualificado) para este computador. Essa entrada deve corresponder ao nome do computador como é definido no dns (sistema de nomes de domínio) e em nomes alternativos de assunto (SAN) ou SN (nome de assunto) do certificado associado a este computador.
    
- Selecione um dos seguintes:
    
    **Use todos os endereços IP configurados:** selecione isso para usar todos os endereços IP configurados no computador.
    
    > [!IMPORTANT]
    > Se o computador tiver vários endereços IP, você deve estar ciente de que os serviços associados a esse computador usarão todos os endereços IP para todos os serviços. Se um servidor ou serviço de escuta estiver esperando comunicação de um endereço IP específico e porta, o serviço pode não fazer a melhor seleção de qual endereço IP escutar. 
  
    **Limitar o** uso do serviço a endereços IP selecionados: selecione essa opção se quiser definir endereços IP específicos para o endereço **IP** principal que este computador escutará para comunicação de outros computadores e pools na implantação. Defina **o endereço IP PSTN** para o endereço IP específico que o computador e o serviço escutarão as comunicações e enviarão comunicações para o gateway PSTN ou IP-PBX definido.
    

