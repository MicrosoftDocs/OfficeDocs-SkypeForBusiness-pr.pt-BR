---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades para computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, configure as configurações de nome do servidor e endereço IP:'
ms.openlocfilehash: 215e103cd7fd41ec6d6788f5884ce741170d19cd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739277"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de Configurações de Máquina de Borda para Lync Server 2010
 
Para editar as propriedades para computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, configure as configurações de nome do servidor e **endereço IP:**
  
- **Nome interno ou FQDN**: digite o nome do computador da forma como ele é chamado pelo DNS. 
    
- **Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede (NIC) interna desse computador.
    
- Você configura o endereço **IPv4** externo do serviço **de Borda** de Acesso associado a este computador
    
    > [!IMPORTANT]
    > Se você selecionou para usar um único endereço IP para a configuração do Servidor de Borda, só poderá editar o endereço IPv4 externo para o serviço de Borda de Acesso. Os outros serviços de Borda compartilharão o mesmo endereço IPv4 que o serviço de Borda de Acesso. 
  
- Se estiver disponível para edição, configure o endereço **IPv4** externo do serviço de **WebConferência** associado a este computador
    
- Se estiver disponível para edição, configure o endereço **IPv4** externo do serviço **de Borda A/V** associado a este computador
    
- Se estiver disponível para editar, configure o **Endereço IPv4 público habilitado por NAT** associado a esse computador.
    
    > [!IMPORTANT]
    > A propriedade de configuração do endereço **IPv4** público habilitado para NAT só estará disponível para edição se você optar por fornecer NAT (conversão de endereço de rede) para o serviço de Borda A/V
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

