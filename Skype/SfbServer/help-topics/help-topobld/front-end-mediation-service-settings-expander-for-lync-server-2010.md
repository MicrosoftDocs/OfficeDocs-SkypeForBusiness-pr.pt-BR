---
title: Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite as propriedades das configurações do gateway PSTN do servidor de mediação nesta caixa de diálogo. Você define as seguintes configurações:'
ms.openlocfilehash: b57ca675d3681886ea2a2853aa1357b394fda4c4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284386"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
 
Edite as propriedades das configurações do **Gateway PSTN do servidor** de mediação nesta caixa de diálogo. Você define as seguintes configurações:
  
- Selecione o **servidor de mediação posicionado habilitado** se você quiser posicionar o servidor de mediação com este servidor front-end ou grupos de front-end.
    
- **Portas de escuta**: defina as portas que o servidor de mediação escutará. Você pode definir uma porta para **TLS** ou Transport Layer Security ou **TCP**ou protocolo de controle de transporte. Para que a entrada de porta TCP esteja disponível, você deve marcar a caixa de seleção **habilitar porta TCP**. 
    
    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se você precisa habilitar e definir valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN dão suporte a TLS. 
  
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, selecione um novo o padrão e clique em **Tornar Padrão**.
    
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

