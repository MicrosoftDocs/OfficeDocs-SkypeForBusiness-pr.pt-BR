---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades de computadores servidores de borda como um único servidor de borda ou como computador membro em um pool de borda, você pode configurar definições de configuração de endereço IP e de nome do servidor:'
ms.openlocfilehash: ad8b763b2509d558a8de96e4fcda880934995e9e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915280"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de Configurações de Máquina de Borda para Lync Server 2010
 
Para editar as propriedades de computadores servidores de borda como um único servidor de borda ou como computador membro em um pool de borda, você deve configurar as configurações de **nome do servidor e a configuração de endereço IP** :
  
- **Nome interno ou FQDN**: digite o nome do computador, pois ele é referenciado no sistema de nome de domínio (DNS). 
    
- **Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede interna (NIC) para este computador.
    
- Configure o **serviço de borda de acesso** de **endereço IPv4 externo** associado a esse computador
    
    > [!IMPORTANT]
    > Se você optou por usar um único endereço IP para a configuração do servidor de borda, você só poderá editar o endereço IPv4 externo para o serviço de borda de acesso. Os outros serviços de borda irá compartilhar o mesmo endereço IPv4 como o serviço de borda de acesso. 
  
- Se estiver disponível para editar, configure o **serviço de webconferência** de **endereço IPv4 externo** associado a esse computador
    
- Se estiver disponível para editar, configure o **uma / serviço de borda V** **endereço IPv4 externo** associado a esse computador
    
- Se estiver disponível para editar, configure o **endereço IPv4 público habilitado por NAT** associado a esse computador.
    
    > [!IMPORTANT]
    > A propriedade de configuração para **endereço IPv4 público habilitado por NAT** só estará disponível para editar se você escolher fornecer conversão de endereço de rede (NAT) para A / serviço de borda V
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

