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
- ms.lync.tb.EdgeFqdnsSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb57268c-2419-4655-ace1-91cf871f25c7
description: 'Para definir as propriedades em configurações externas, configure o seguinte:'
ms.openlocfilehash: 2936c910f2cfc1d7e9106e2dca7477f5e1d2860e
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684754"
---
# <a name="edge-server-fqdn-settings-expander-for-lync-server-2010"></a>Expansor de Configurações FQDN de Servidor de Borda para Lync Server 2010
 
Para definir as propriedades em **configurações externas**, configure o seguinte:
  
Marque a caixa de seleção **habilitar FQDN e endereço IP separados para Webconferência e A/V,** se você quiser definir endereços IP e FQDN de pool distintos para Webconferência e áudio/vídeo.
  
> [!NOTE]
> Se você optar por não marcar a caixa de seleção para endereços IP e FQDN separados, será necessário fornecer portas distintas para cada um dos três serviços fornecidos pelo servidor de borda. O único nome de domínio totalmente qualificado que é configurado é o FQDN associado ao serviço de borda de acesso. 
  
Marque a caixa de seleção o **serviço de borda a/v está habilitado para NAT** se você quiser que o serviço de borda a/v Use um endereço IP e uma configuração de NAT (conversão de endereços de rede).
  
Para os serviços de borda habilitados, digite um **FQDN do pool** e uma porta em **portas**
  
- Defina o FQDN do pool de **serviços de borda de acesso** e uma porta que identifique exclusivamente o serviço.
    
- Defina o FQDN do pool de **serviços de borda de Webconferência** (se habilitar o FQDN e o endereço IP separados para Webconferência e a/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.
    
- Defina o FQDN do pool de **serviços de borda a/V** (se habilitar FQDN e o endereço IP separados para Webconferência e a/V não estiver selecionado) e uma porta que identifique exclusivamente o serviço.
    
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

