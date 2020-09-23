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
- CSH
ms.custom:
- ms.lync.tb.MediationServiceSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 230e0a08-9e16-4bbd-b550-1f04bad8ddbc
description: 'Edite as propriedades do serviço de mediação definindo as seguintes propriedades:'
ms.openlocfilehash: 51fbd889d7e9d673fb75b1062a70ae55a9f8585c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215102"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
 
Edite as propriedades do serviço de mediação definindo as seguintes propriedades:
  
- **Portas de escuta**: defina a porta **TLS** que o serviço de mediação escutará. Por padrão, o valor da porta é TCP 5067 sobre a segurança da camada de transporte (TLS)
    
    Opcionalmente, você define um valor de porta **TCP** . Por padrão, o valor é TCP 5068.
    
    > [!NOTE]
    > A configuração do valor da porta TCP é habilitada selecionando **habilitar porta TCP**. Você deve consultar a documentação do seu gateway PSTN (rede telefônica pública comutada) ou do protocolo IP para os requisitos das configurações de porta necessárias para se comunicar com o serviço de mediação. 
  
- Você **habilita a porta TCP** para definir o valor de porta para as comunicações TCP do seu gateway PSTN ou IP-PBX.
    
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

