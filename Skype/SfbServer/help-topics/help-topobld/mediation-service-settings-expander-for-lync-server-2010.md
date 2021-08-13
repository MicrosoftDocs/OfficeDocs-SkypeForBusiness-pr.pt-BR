---
title: Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:'
ms.openlocfilehash: c1de5fa582df662dbb7e97c6e4402dd912524f6a4ddb8630e2341e06d9dec2a3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54299548"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
 
Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:
  
- **Portas de** escuta : Defina a **porta TLS** na qual o serviço de Mediação escutará. Por padrão, o valor da porta é TCP 5067 sobre segurança de camada de transporte (TLS)
    
    Opcionalmente, você define um **valor de porta TCP.** Por padrão, o valor é TCP 5068.
    
    > [!NOTE]
    > A configuração do valor da porta TCP é habilitada selecionando **Habilitar porta TCP**. Consulte a documentação do Gateway PSTN (Rede Telefônica Pública Comutado) ou do Protocolo de Internet Exchange (IP-PBX) para os requisitos para as configurações de porta necessárias para se comunicar com o serviço de Mediação. 
  
- **Habilita a porta TCP** para definir o valor da porta para comunicações TCP do gateway PSTN ou IP-PBX.
    
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

