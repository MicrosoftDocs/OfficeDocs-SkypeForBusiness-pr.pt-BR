---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
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
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de borda, você define o nome do servidor e as definições de configuração do endereço IP:'
ms.openlocfilehash: eb2135391791fdb915578fe9938329b56c85908c
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218922"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de Configurações de Máquina de Borda para Lync Server 2010
 
Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de borda, você define o **nome do servidor e** as definições de configuração do endereço IP:
  
- **Nome interno ou FQDN**: digite o nome do computador da forma como ele é chamado pelo DNS. 
    
- **Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede (NIC) interna desse computador.
    
- Você configura o **Access Edge service** **endereço IPv4 externo** do serviço de borda de acesso associado a este computador
    
    > [!IMPORTANT]
    > Se você optou por usar um único endereço IP para a configuração do servidor de borda, só poderá editar o endereço IPv4 externo do serviço de borda de acesso. Os outros serviços de borda compartilharão o mesmo endereço IPv4 que o serviço de borda de acesso. 
  
- Se estiver disponível para edição, configure o **serviço de Webconferência** do **endereço IPv4 externo** associado a este computador
    
- Se estiver disponível para edição, configure o **endereço IPv4 externo** do **serviço de borda a/V** associado a este computador
    
- Se estiver disponível para editar, configure o **Endereço IPv4 público habilitado por NAT** associado a esse computador.
    
    > [!IMPORTANT]
    > A propriedade de configuração para o **endereço IPv4 público habilitado para NAT** só estará disponível para edição se você optar por fornecer conversão de endereço de rede (NAT) para o serviço de borda a/V
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

