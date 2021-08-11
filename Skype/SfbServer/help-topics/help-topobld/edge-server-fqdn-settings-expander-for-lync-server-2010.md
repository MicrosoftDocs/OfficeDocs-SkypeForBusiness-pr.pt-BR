---
title: Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em Configurações externas, configure o seguinte:'
ms.openlocfilehash: d8c800051dcbc6aa2c1a533940c3d3d558ef86ba8db115e557846dc04a08c795
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54307152"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
 
Para definir as propriedades em **Configurações externas**, configure o seguinte:
  
Marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V** se quiser definir FQDN de Pool e endereços IP distintos para webconferência e áudio/vídeo.
  
> [!NOTE]
> Se você optar por não selecionar a caixa de seleção para endereços IP e FQDN separados, deverá fornecer portas distintas para cada um dos três serviços fornecidos pelo Servidor de Borda. O único nome de domínio totalmente qualificado que deve ser configurar é o FQDN associado ao serviço de Borda de Acesso. 
  
Marque a caixa de seleção Serviço de Borda **A/V** habilitado para NAT se quiser que o serviço de Borda A/V use um endereço IP nat (conversão de endereço de rede) e configuração.
  
Para os serviços de Borda habilitados, digite um **FQDN de Pool** e uma porta em **Portas**
  
- Defina o FQDN do Pool dos **Serviços de Borda de Acesso** e uma porta que identifique exclusivamente o serviço.
    
- Defina o FQDN do Pool do **Serviço de Borda de Webconferência** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço
    
- Defina o FQDN do Pool do **Serviço de Borda de A/V** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

