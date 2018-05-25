---
title: Expansor de configurações de FQDN de servidor de borda do Lync Server 2010
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em configurações externas, configure o seguinte:'
ms.openlocfilehash: 2954c9add818e67f471cfb97893fef42e862bea3
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de configurações de FQDN de servidor de borda do Lync Server 2010
 
Para definir as propriedades em **configurações externas**, configure o seguinte:
  
Selecione o **FQDN de habilitar separado e endereço IP para Webconferência e A / V** lida com a caixa de seleção se você deseja definir distintos IP e FQDN do Pool para Webconferência e áudio/vídeo.
  
> [!NOTE]
> Se você optar por não marque a caixa de seleção para endereços IP e FQDN separados, você deve fornecer portas distintas para cada um dos três serviços fornecidos pelo servidor de borda. O único nome de domínio totalmente qualificado é configurar é o FQDN associado ao serviço de borda de acesso. 
  
Selecione o **uma / serviço de borda V é habilitado para NAT** caixa de seleção se quiser que A / endereço IP NAT (conversão) e a configuração de endereços de serviço de borda V para usar uma rede.
  
Para os serviços de borda habilitados, você digita um **FQDN do Pool** e uma porta em **portas**
  
- Defina o FQDN de Pool do **serviço de borda de acesso** e uma porta que identifique exclusivamente o serviço.
    
- Definir o FQDN de Pool do **serviço de borda de webconferência** (se habilitar separar o FQDN e endereço IP para Webconferência e A / V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.
    
- Definir o **uma / serviço de borda V** FQDN do Pool (se habilitar separar o FQDN e endereço IP para Webconferência e A / V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.
    
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  

