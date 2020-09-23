---
title: Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em Configurações externas, configure o seguinte:'
ms.openlocfilehash: 2de4b562d5b6a8b8ef9707d603fe5f4667893ba4
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218242"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
 
Para definir as propriedades em **Configurações externas**, configure o seguinte:
  
Marque a caixa de seleção **Habilitar FQDN e endereço IP separados para webconferência e A/V** se quiser definir FQDN de Pool e endereços IP distintos para webconferência e áudio/vídeo.
  
> [!NOTE]
> Se você optar por não marcar a caixa de seleção para endereços IP e FQDN separados, deverá fornecer portas distintas para cada um dos três serviços fornecidos pelo servidor de borda. O único nome de domínio totalmente qualificado que é configurado é o FQDN associado ao serviço de borda de acesso. 
  
Marque a caixa de seleção **serviço de borda a/v habilitado para NAT** se quiser que o serviço de borda a/v Use um endereço IP de conversão de endereços de rede (NAT) e configuração.
  
Para os serviços de Borda habilitados, digite um **FQDN de Pool** e uma porta em **Portas**
  
- Defina o FQDN do Pool dos **Serviços de Borda de Acesso** e uma porta que identifique exclusivamente o serviço.
    
- Defina o FQDN do Pool do **Serviço de Borda de Webconferência** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço
    
- Defina o FQDN do Pool do **Serviço de Borda de A/V** (se Habilitar FQDN e endereço IP separados para webconferência e A/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

