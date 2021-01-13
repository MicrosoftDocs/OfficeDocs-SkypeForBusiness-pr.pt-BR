---
title: Expansor de Configurações de Máquina de Borda para Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
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
localization_priority: Normal
ms.assetid: fb72a5b5-70f4-44af-8dfd-c5d32e563882
description: 'Para editar as propriedades dos computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, você define as definições de configuração do nome do servidor e do endereço IP:'
ms.openlocfilehash: e25f68ec510cf15cd58872a8c584dc71aa939f48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807131"
---
# <a name="edge-machine-settings-expander-for-lync-server-2010"></a>Expansor de Configurações de Máquina de Borda para Lync Server 2010
 
Para editar as propriedades dos computadores do Servidor de Borda como um único Servidor de Borda ou como computadores membros em um pool de Borda, você define as definições de configuração do nome do servidor e **do endereço IP:**
  
- **Nome interno ou FQDN**: digite o nome do computador da forma como ele é chamado pelo DNS. 
    
- **Endereço IPv4 interno**: digite o endereço IPv4 da placa de interface de rede (NIC) interna desse computador.
    
- Configure o endereço **IPv4** **externo do** serviço de Borda de Acesso associado a este computador
    
    > [!IMPORTANT]
    > Se você selecionou usar um único endereço IP para a configuração do Servidor de Borda, só poderá editar o endereço IPv4 externo para o serviço de Borda de Acesso. Os outros serviços de Borda compartilharão o mesmo endereço IPv4 que o serviço de Borda de Acesso. 
  
- Se disponível para edição, configure o endereço **IPv4** externo do serviço de **Webconferência** associado a este computador
    
- Se estiver disponível para edição, configure o endereço **IPv4** externo do serviço de Borda **A/V** associado a este computador
    
- Se estiver disponível para editar, configure o **Endereço IPv4 público habilitado por NAT** associado a esse computador.
    
    > [!IMPORTANT]
    > A propriedade de configuração do endereço **IPv4** público habilitado para NAT só estará disponível para edição se você optar por fornecer NAT (conversão de endereço de rede) para o serviço de Borda A/V
  
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  

