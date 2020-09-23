---
title: Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
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
- ms.lync.tb.FeMediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 37166b87-8a43-42a6-a2aa-5a45bed8a6f3
description: 'Edite as propriedades das configurações do Gateway PSTN do Servidor de Mediação nesta caixa de diálogo. Defina as seguintes configurações:'
ms.openlocfilehash: 37baf89b6100528c1485f939f69e20c697803123
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217722"
---
# <a name="front-end-mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação de Front End para Lync Server 2010
 
Edite as propriedades das configurações do **Gateway PSTN do Servidor de Mediação** nesta caixa de diálogo. Defina as seguintes configurações:
  
- Selecione o **servidor de mediação posicionado habilitado** se você quiser colocar o servidor de mediação com este servidor front-end ou pools de front-ends.
    
- **Portas de escuta**: defina as portas nas quais o servidor de mediação escutará. É possível definir uma porta para **TLS**, ou transport layer security, ou para **TCP**, ou transport control protocol. Para a entrada da porta TCP ficar disponível, é necessário marcar a caixa de seleção **Habilitar porta TCP**. 
    
    > [!IMPORTANT]
    > Consulte a documentação e as configurações de seu gateway PSTN (rede telefônica pública comutada) para determinar se precisa habilitar e definir os valores de porta TLS, TCP ou ambos. O TLS é um protocolo mais seguro, usando certificados para criptografar o tráfego entre o servidor de mediação e o gateway PSTN. Nem todos os gateways PSTN suportam TLS. 
  
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

