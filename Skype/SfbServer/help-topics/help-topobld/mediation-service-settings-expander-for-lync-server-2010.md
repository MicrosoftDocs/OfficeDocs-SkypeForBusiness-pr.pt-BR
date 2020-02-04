---
title: Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:'
ms.openlocfilehash: 29c5172157d993c73ca35a5217c67ee6d6df87ef
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41696966"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
 
Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:
  
- **Portas de escuta**: defina a porta **TLS** na qual o serviço de Mediação escutará. Por padrão, o valor da porta é TCP 5067 sobre o protocolo TLS
    
    Como opção, você define um valor de porta **TCP**. Por padrão, o valor é TCP 5068.
    
    > [!NOTE]
    > A configuração do valor de porta TCP é habilitada selecionando **Habilitar porta TCP**. Consulte a documentação de seu Gateway PSTN (Rede Telefônica Pública Comutada) ou IP-PBX (Internet Protocol Private Branch Exchange) para os requisitos de configurações de porta necessários para se comunicar com o serviço de Mediação. 
  
- Você deve **Habilitar porta TCP** para definir o valor de porta para as comunicações TCP a partir de seu gateway PSTN ou IP-PBX.
    
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, selecione um novo o padrão e clique em **Tornar Padrão**.
    
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

