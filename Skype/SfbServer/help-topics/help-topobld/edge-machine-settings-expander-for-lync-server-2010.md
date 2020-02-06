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
- NOCSH
ms.custom:
- ms.lync.tb.EdgeMachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de bordas, você deve definir o nome do servidor e as configurações de endereço IP:'
ms.openlocfilehash: b90a3a00dcb1198e696112fc3d3ded08ff00060d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820093"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de Configurações de Máquina de Borda para Lync Server 2010
 
Para editar as propriedades dos computadores do servidor de borda como um único servidor de borda ou como computadores membro em um pool de bordas, você deve definir o **nome do servidor e** as configurações de endereço IP:
  
- **Nome interno ou FQDN**: digite o nome do computador como ele é referenciado no sistema de nomes de domínio (DNS). 
    
- **Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede interna (NIC) do computador.
    
- Você configura o **serviço de borda do Access** **endereço IPv4 externo** associado a este computador
    
    > [!IMPORTANT]
    > Se você optou por usar um único endereço IP para a configuração do servidor de borda, só poderá editar o endereço IPv4 externo para o serviço de borda de acesso. Os outros serviços de borda compartilharão o mesmo endereço IPv4 que o serviço de borda de acesso. 
  
- Se estiver disponível para edição, configure o **serviço de Webconferência** do **endereço IPv4 externo** associado a este computador
    
- Se estiver disponível para edição, você deve configurar o **endereço IPv4 externo** do **serviço de borda a/V** associado a este computador
    
- Se estiver disponível para edição, configure o **endereço IPv4 público compatível com Nat** associado a este computador.
    
    > [!IMPORTANT]
    > A propriedade de configuração para o **endereço IPv4 público habilitado para NAT** só estará disponível para edição se você tiver optado por fornecer a NAT (conversão de endereços de rede) para o serviço de borda a/V
  
  **OK** Aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** Descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** Exibe essa tela de ajuda.
  

