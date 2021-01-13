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
ms.openlocfilehash: ddc6ab56f848179800b6398b7a638cdb7a061a9f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806681"
---
# <a name="mediation-service-settings-expander-for-lync-server-2010"></a>Expansor de Configurações do Serviço de Mediação para o Lync Server 2010
 
Edite as propriedades do serviço de Mediação definindo as seguintes propriedades:
  
- **Portas de** escuta: defina a **porta TLS** na qual o serviço de Mediação escutará. Por padrão, o valor da porta é TCP 5067 sobre a segurança da camada de transporte (TLS)
    
    Opcionalmente, você define um **valor de porta TCP.** Por padrão, o valor é TCP 5068.
    
    > [!NOTE]
    > A configuração do valor da porta TCP é habilitada **selecionando Habilitar porta TCP.** Consulte a documentação do Gateway PSTN (Rede Telefônica Pública Comucionada) ou ip-PBX (Internet Protocol Private Branch Exchange) para os requisitos para as configurações de porta necessárias para se comunicar com o serviço de Mediação. 
  
- Você **habilita a** porta TCP para definir o valor da porta para comunicações TCP do seu gateway PSTN ou IP-PBX.
    
- Uma listagem do **Tronco** associado atualmente e existente (ou seja, Troncos SIP [Session Initiation Protocol]), **Gateway** (Gateway PSTN ou IP-PBX) e **Site** (site configurado para o tronco e gateway).
    
- Selecione um Tronco, Gateway e Site e clique em **Tornar Padrão** para definir a seleção como padrão para esse serviço de Mediação. Selecione o padrão atual e clique em **Desfazer Padrão** para remover a seleção como o padrão atual. Em seguida, você seleciona um novo o padrão e clica em **Tornar Padrão**.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

