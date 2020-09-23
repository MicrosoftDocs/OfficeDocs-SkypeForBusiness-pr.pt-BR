---
title: Expansor de Configurações Gerais de Bate-papo Persistente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PersistentChatGeneralSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 275ee1ae-ca58-4963-bc95-523319f90d96
description: 'Edite as configurações gerais do servidor de chat persistente ou pool do servidor de chat persistente Configurando ou definindo essas propriedades:'
ms.openlocfilehash: aae63b2d736f02b717b47aeff5fccb9b676daf99
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215992"
---
# <a name="persistent-chat-general-settings-expander"></a>Expansor de Configurações Gerais de Bate-papo Persistente
 
Edite as configurações **gerais** do servidor de chat persistente ou pool do servidor de chat persistente Configurando ou definindo essas propriedades:
  
 **Geral**
  
- **FQDN**: Edite essa configuração para definir o nome de domínio totalmente qualificado do seu servidor de chat persistente ou pool de servidor de chat persistente
    
- **Nome de exibição do pool de Chat Persistente**: defina essa configuração para fornecer uma configuração simples e legível do servidor ou pool. Essa configuração tornará mais fácil para os usuários a associação de um determinado servidor de chat persistente ou pool de servidor de chat persistente com base no nome de exibição em vez de mais difícil de entender o nome de domínio totalmente qualificado.
    
- **Porta de Chat Persistente**: especifique a porta a ser usada para o Chat Persistente.
    
Edite as configurações de **associações** para o servidor de chat persistente ou o pool do servidor de chat persistente Configurando ou definindo essas propriedades:
  
 **Associação**
  
- **Repositório do SQL Server**: selecione o repositório do SQL Server e a instância nomeada opcional na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser habilitar o espelhamento para o repositório principal do SQL Server.
    
    Se você optar por habilitar o espelhamento do repositório do SQL Server, selecione o repositório e a instância no **repositório do SQL Server de espelhamento**de lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** se quiser failover automático do repositório do SQL Server principal.
    
    Se você optar por habilitar a testemunha de espelhamento do repositório do SQL Server para habilitar o failover automático, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **usar repositórios de backup do SQL Server para habilitar a recuperação de desastres** se quiser habilitar o uso da recuperação de desastre do SQL Server
    
    Se você escolher habilitar a recuperação de desastre, selecione um repositório e uma instância na lista **Backup do SQL Server**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser habilitar o espelhamento para o armazenamento de espelhamento do SQL Server de backup.
    
    Se você escolher habilitar o espelhamento do repositório do SQL Server de backup, selecione o repositório e a instância na lista **espelho do SQL Server Store de backup**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** se quiser failover automático do repositório do SQL Server de backup.
    
    Se você optar por habilitar a testemunha de espelhamento do repositório do SQL Server para habilitar o failover automático, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Marque a caixa de seleção **Habilitar conformidade** se quiser habilitar o uso do banco de dados de conformidade
    
    Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **SQL Server store de conformidade**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser habilitar o espelhamento para o repositório do SQL Server de conformidade.
    
    Se você escolher habilitar o espelhamento do repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **espelho do SQL Server Store de conformidade**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** se quiser failover automático do repositório do SQL Server de conformidade.
    
    Se você optar por habilitar a testemunha de espelhamento do repositório do SQL Server para habilitar o failover automático, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- Se você escolher habilitar a conformidade, selecione um repositório e uma instância na lista **Backup do SQL Server store de conformidade**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **habilitar espelhamento do repositório do SQL Server** se quiser habilitar o espelhamento para o repositório do SQL Server de conformidade.
    
    Se você optar por habilitar o espelhamento do repositório do SQL Server de conformidade, selecione o repositório e a instância na lista **espelho de repositório do SQL Server de conformidade de backup**.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional.
    
- Marque a caixa de seleção **usar testemunha de espelhamento do SQL Server para habilitar failover automático** se quiser failover automático do repositório do SQL Server de conformidade de backup.
    
    Se você optar por habilitar a testemunha de espelhamento do repositório do SQL Server para habilitar o failover automático, selecione o repositório e a instância na lista.
    
    Clique em **Novo** para definir um novo SQL Server store e instância opcional para o repositório de testemunha.
    
- **Repositório de arquivos** Selecione um local de repositório de arquivos na lista ou clique em **novo** para criar um novo repositório de arquivos.
    
  **OK** aceita e confirma as alterações na caixa de diálogo.
  
  **Cancelar** descarta as alterações e fecha a caixa de diálogo.
  
  **Ajuda** exibe essa tela de ajuda.
  
## <a name="see-also"></a>Confira também

[Planejar o servidor de chat persistente no Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)
  
[Adicionar servidor de chat persistente à sua topologia do Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)
  
[Configurar alta disponibilidade e recuperação de desastre para servidor de chat persistente no Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)
