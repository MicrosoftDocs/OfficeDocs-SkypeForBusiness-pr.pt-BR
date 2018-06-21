---
title: Expansor de configurações de serviço de mediação de Front-End do Lync Server 2010
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Você editar as propriedades das configurações de gateway PSTN do servidor de mediação nessa caixa de diálogo. Defina as seguintes configurações:'
ms.openlocfilehash: 7343fb4e2876ffa23fa7d37a8669f9b0c25f428b
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/20/2018
ms.locfileid: "19979768"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de configurações de serviço de mediação de Front-End do Lync Server 2010
 
Você editar as propriedades das configurações de **gateway PSTN do servidor de mediação** nessa caixa de diálogo. Defina as seguintes configurações:
  
- Selecione o **servidor de mediação posicionado habilitado** se quiser colocar o servidor de mediação com esse servidor Front-End ou Front-End pools.
    
- **Portas de escuta**: definir as portas que o servidor de mediação escutará. Você pode definir uma porta para segurança de camada de transporte ou **TLS** ou **TCP**, ou o protocolo de controle de transporte. Para a entrada de porta para TCP esteja disponível, você deve selecionar a caixa de seleção para **Habilitar TCP porta**. 
    
    > [!IMPORTANT]
    > Consulte as configurações de documentação e configuração de seu gateway PSTN (rede) telefônica pública comutada para determinar se você precisa habilitar e definir valores de portas TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS. 
  
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, selecione um novo o padrão e clique em **Tornar Padrão**.
    
 **OK** Aceita e confirma as alterações na caixa de diálogo.
  
 **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
 **Ajuda** Exibe essa tela de ajuda.
  

